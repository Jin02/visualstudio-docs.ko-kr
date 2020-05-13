---
title: 원격 IIS 컴퓨터의 원격 디버그 ASP.NET Core | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.topic: conceptual
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 3e11480949545781630dec0c533949dd200ecbc7
ms.sourcegitcommit: 7a9d5c10690c594dcdb414d88b20e070d43e7a4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82218888"
---
# <a name="remote-debug-aspnet-core-on-a-remote-iis-computer-in-visual-studio"></a>Visual Studio에서 원격 IIS 컴퓨터의 원격 디버그 ASP.NET Core

IIS에 배포 된 ASP.NET Core 응용 프로그램을 디버깅 하려면 앱을 배포한 컴퓨터에 원격 도구를 설치 하 고 실행 한 후 Visual Studio에서 실행 중인 앱에 연결 합니다.

![원격 디버거 구성 요소](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

이 가이드에서는 Visual Studio ASP.NET Core를 설정 및 구성 하 고, IIS에 배포 하 고, Visual Studio에서 원격 디버거를 연결 하는 방법을 설명 합니다. ASP.NET 4.5.2를 원격으로 디버그 하려면 [IIS 컴퓨터의 원격 디버그 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)를 참조 하세요. 또한 Azure를 사용 하 여 IIS에서 배포 하 고 디버그할 수 있습니다. Azure App Service의 경우 [스냅숏 디버거](../debugger/debug-live-azure-applications.md) 를 사용 하거나 [서버 탐색기에서 디버거를 연결](../debugger/remote-debugging-azure.md)하 여 미리 구성 된 IIS 및 원격 디버거의 인스턴스를 쉽게 배포 하 고 디버그할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

::: moniker range=">=vs-2019"
이 문서에 표시 된 단계를 수행 하려면 Visual Studio 2019가 필요 합니다.
::: moniker-end
::: moniker range="vs-2017"
이 문서에 표시 된 단계를 수행 하려면 Visual Studio 2017가 필요 합니다.
::: moniker-end

이러한 절차는 다음 서버 구성에서 테스트 되었습니다.
* Windows Server 2012 R2 및 IIS 8
* Windows Server 2016 및 IIS 10

## <a name="network-requirements"></a>네트워크 요구 사항

프록시를 통해 연결 된 두 컴퓨터 간의 디버깅은 지원 되지 않습니다. 대기 시간이 긴 경우 (예: 전화 접속 인터넷) 또는 인트라넷을 통해 인터넷을 통해 디버깅 하는 것은 권장 되지 않으며 오류가 발생 하거나 지나치게 느릴 수 있습니다. 요구 사항의 전체 목록은 [요구 사항](../debugger/remote-debugging.md#requirements_msvsmon)을 참조 하세요.

## <a name="app-already-running-in-iis"></a>앱이 이미 IIS에서 실행 되 고 있나요?

이 문서에는 Windows server에서 IIS의 기본 구성을 설정 하 고 Visual Studio에서 앱을 배포 하는 단계가 포함 되어 있습니다. 이러한 단계는 서버에 필수 구성 요소가 설치 되어 있고, 앱이 올바르게 실행 될 수 있고, 원격으로 디버깅할 준비가 되었는지 확인 하기 위해 포함 되었습니다.

* 앱이 IIS에서 실행 중이 고 원격 디버거를 다운로드 하 여 디버깅을 시작 하려는 경우 [Windows Server에서 원격 도구 다운로드 및 설치](#BKMK_msvsmon)로 이동 합니다.

* 디버그할 수 있도록 응용 프로그램이 IIS에서 올바르게 설정, 배포 및 실행 되는지 확인 하려면이 항목의 모든 단계를 수행 합니다.

## <a name="create-the-aspnet-core-application-on-the-visual-studio-computer"></a>Visual Studio 컴퓨터에 ASP.NET Core 응용 프로그램 만들기

1. 새 ASP.NET Core 웹 애플리케이션을 만듭니다. 

    ::: moniker range=">=vs-2019"
    Visual Studio 2019에 **Ctrl + Q** 를 입력 하 여 검색 상자를 열고 **asp.net**를 입력 한 다음 **템플릿**을 선택 하 고 **새 ASP.NET Core 웹 응용 프로그램 만들기**를 선택 합니다. 표시 되는 대화 상자에서 프로젝트 이름을 **MyASPApp**로 지정한 다음 **만들기**를 선택 합니다. 그런 다음 **웹 응용 프로그램 (모델-뷰-컨트롤러)** 을 선택 하 고 **만들기**를 선택 합니다.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Visual Studio 2017에서 **파일 > 새 > 프로젝트**를 선택한 다음 **Visual c # > 웹 > ASP.NET Core 웹 응용 프로그램**을 선택 합니다. ASP.NET Core 템플릿 섹션에서 **웹 응용 프로그램 (모델-뷰-컨트롤러)** 을 선택 합니다. ASP.NET Core 2.1가 선택 되어 있는지 확인 하 고 **Docker 지원 사용** 이 선택 되지 않은 상태 **이며 인증** **안 함**으로 설정 되어 있는지 확인 합니다. 프로젝트 이름을 **MyASPApp**로 합니다.
    ::: moniker-end

4. About.cshtml.cs 파일을 열고 `OnGet` 메서드에 중단점을 설정 합니다. 이전 템플릿에서 HomeController.cs를 대신 열고 `About()` 메서드에 중단점을 설정 합니다.

## <a name="install-and-configure-iis-on-windows-server"></a><a name="bkmk_configureIIS"></a>Windows Server에서 IIS 설치 및 구성

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정 업데이트

Internet Explorer에서 보안 강화 구성이 사용 하도록 설정 되어 있는 경우 (기본적으로 사용 됨) 일부 웹 서버 구성 요소를 다운로드할 수 있도록 일부 도메인을 신뢰할 수 있는 사이트로 추가 해야 할 수 있습니다. **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트**로 이동 하 여 신뢰할 수 있는 사이트를 추가 합니다. 다음 도메인을 추가 합니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

소프트웨어를 다운로드 하는 경우 다양 한 웹 사이트 스크립트 및 리소스를 로드 하는 권한을 부여 하는 요청을 받을 수 있습니다. 이러한 리소스 중 일부는 필요 하지 않지만 프로세스를 간소화 하려면 메시지가 표시 되 면 **추가** 를 클릭 합니다.

## <a name="install-aspnet-core-on-windows-server"></a>Windows Server에 ASP.NET Core 설치

1. 호스팅 시스템에 [.NET Core Windows Server 호스팅 번들](https://aka.ms/dotnetcore-2-windowshosting)을 설치합니다. 번들은 .NET Core 런타임, .NET Core 라이브러리 및 ASP.NET Core 모듈을 설치합니다. 자세한 지침은 [IIS에 게시를](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)참조 하세요.

    > [!NOTE]
    > 시스템이 인터넷에 연결되지 않은 경우 *[Microsoft Visual C++ 2015 재배포 가능 패키지](https://www.microsoft.com/download/details.aspx?id=53840)* 를 설치한 후에 .NET Core Windows Server 호스팅 번들을 설치합니다.

3. 시스템을 다시 시작하거나 명령 프롬프트에서 **net stop was /y**에 이어 **net start w3svc**를 실행하여 시스템 PATH에 대한 변경 내용을 선택합니다.

## <a name="choose-a-deployment-option"></a>배포 옵션 선택

IIS에 앱을 배포 하는 데 도움이 필요한 경우 다음 옵션을 고려 합니다.

* IIS에서 게시 설정 파일을 만들고 Visual Studio에서 설정을 가져와서 배포 합니다. 일부 시나리오에서는 앱을 신속 하 게 배포 하는 방법입니다. 게시 설정 파일을 만들 때 IIS에서 사용 권한이 자동으로 설정 됩니다.

* 로컬 폴더에 게시 하 고 기본 방법으로 출력을 IIS의 준비 된 앱 폴더에 복사 하 여 배포 합니다.

## <a name="optional-deploy-using-a-publish-settings-file"></a>필드 게시 설정 파일을 사용 하 여 배포

이 옵션을 사용 하 여 게시 설정 파일을 만들고 Visual Studio로 가져올 수 있습니다.

> [!NOTE]
> 이 배포 방법은 웹 배포을 사용 합니다. 설정을 가져오는 대신 Visual Studio에서 웹 배포를 수동으로 구성 하려는 경우 호스팅 서버에 웹 배포 3.6 대신 웹 배포 3.6를 설치할 수 있습니다. 그러나 웹 배포를 수동으로 구성 하는 경우 서버의 앱 폴더가 올바른 값 및 사용 권한으로 구성 되어 있는지 확인 해야 합니다 ( [ASP.NET 웹 사이트 구성](#BKMK_deploy_asp_net)참조).

### <a name="install-and-configure-web-deploy-for-hosting-servers-on-windows-server"></a>Windows Server에서 호스트 서버에 대 한 웹 배포 설치 및 구성

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

### <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server의 IIS에서 게시 설정 파일 만들기

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/create-publish-settings-iis.md)]

### <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

앱을 성공적으로 배포한 후 자동으로 시작해야 합니다. 앱이 Visual Studio에서 시작 되지 않으면 IIS에서 앱을 시작 합니다. ASP.NET Core의 경우 **DefaultAppPool**에 대한 애플리케이션 풀 필드가 **관리 코드 없음**으로 설정되었는지 확인해야 합니다.

1. **설정** 대화 상자에서 **다음**을 클릭 하 여 디버깅을 사용 하도록 설정 하 고, **디버그** 구성을 선택 하 고, **파일 게시** 옵션에서 **대상의 추가 파일 제거** 를 선택 합니다.

    > [!NOTE]
    > 릴리스 구성을 선택 하는 경우 게시할 때 *web.config 파일에서* 디버깅을 사용 하지 않도록 설정 합니다.

1. **저장** 을 클릭 한 다음 앱을 다시 게시 합니다.

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>필드 로컬 폴더에 게시 하 여 배포

PowerShell, RoboCopy를 사용 하 여 앱을 IIS에 복사 하거나 수동으로 파일을 복사 하려는 경우이 옵션을 사용 하 여 앱을 배포할 수 있습니다.

### <a name="configure-the-aspnet-core-web-site-on-the-windows-server-computer"></a><a name="BKMK_deploy_asp_net"></a>Windows Server 컴퓨터에서 ASP.NET Core 웹 사이트 구성

1. Windows 탐색기를 열고 나중에 ASP.NET Core 프로젝트를 배포할 새 폴더 **C:\publish**를 만듭니다.

2. 아직 열려 있지 않은 경우 **인터넷 정보 서비스 (IIS) 관리자**를 엽니다. 서버 관리자의 왼쪽 창에서 **IIS**를 선택 합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 **인터넷 정보 서비스 (IIS) 관리자**를 선택 합니다.

3. 왼쪽 창의 **연결** 아래에서 **사이트**로 이동 합니다.

4. **기본 웹 사이트**를 선택 하 고 **기본 설정**을 선택 하 고 **실제 경로** 를 **c:\publish**로 설정 합니다.

4. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **애플리케이션 추가**를 선택합니다.

5. **별칭** 필드를 **MyASPApp**로 설정 하 고, 기본 응용 프로그램 풀 (**DefaultAppPool**)을 적용 하 고, **실제 경로** 를 **c:\publish**로 설정 합니다.

6. **연결**아래에서 **응용 프로그램 풀**을 선택 합니다. **DefaultAppPool** 을 열고 응용 프로그램 풀 필드를 **관리 코드 없음**으로 설정 합니다.

7. IIS 관리자에서 새 사이트를 마우스 오른쪽 단추로 클릭 하 고 **사용 권한 편집**을 선택한 다음 IUSR, IIS_IUSRS 또는 웹 앱에 대 한 액세스를 위해 구성 된 사용자가 읽기 & 실행 권한을 가진 권한 있는 사용자 인지 확인 합니다.

    액세스 권한이 있는 사용자 중 하나가 표시 되지 않으면 읽기 & 실행 권한이 있는 사용자로 IUSR를 추가 하는 단계를 진행 합니다.

### <a name="publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>Visual Studio에서 로컬 폴더에 게시 하 여 앱을 게시 하 고 배포 합니다.

또한 파일 시스템 또는 기타 도구를 사용 하 여 앱을 게시 하 고 배포할 수 있습니다.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="download-and-install-the-remote-tools-on-windows-server"></a><a name="BKMK_msvsmon"></a>Windows Server에서 원격 도구 다운로드 및 설치

Visual Studio 버전과 일치 하는 버전의 원격 도구를 다운로드 합니다.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="set-up-the-remote-debugger-on-windows-server"></a><a name="BKMK_setup"></a>Windows Server에서 원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 추가 사용자에 대 한 사용 권한을 추가 하거나 원격 디버거의 인증 모드 또는 포트 번호를 변경 해야 하는 경우 [원격 디버거 구성](../debugger/remote-debugging.md#configure_msvsmon)을 참조 하세요.

원격 디버거를 서비스로 실행 하는 방법에 대 한 자세한 내용은 [원격 디버거를 서비스로 실행](../debugger/remote-debugging.md#bkmk_configureService)을 참조 하세요.

## <a name="attach-to-the-aspnet-application-from-the-visual-studio-computer"></a><a name="BKMK_attach"></a>Visual Studio 컴퓨터에서 ASP.NET 응용 프로그램에 연결

1. Visual Studio 컴퓨터에서 디버그 하려는 솔루션을 엽니다 (이 문서의 모든 단계를 수행 하는 경우**MyASPApp** ).
2. Visual Studio에서 **디버그 > 프로세스에 연결을** 클릭 합니다 (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017 이상 버전에서는 **디버그 > 프로세스에** 다시 연결 ... (Shift + Alt + P)을 사용 하 여 이전에 연결한 프로세스와 동일한 프로세스에 다시 연결할 수 있습니다.

3. 한정자 필드를 ** \<원격 컴퓨터 이름>** 설정 하 고 **enter**키를 누릅니다.

    Visual Studio에서 ** \<원격 컴퓨터 이름>:p ort 형식으로 표시 되는 컴퓨터 이름에 필요한 포트를 추가 하는지 확인 합니다.**

    ::: moniker range=">=vs-2019"
    Visual Studio 2019에서 ** \<원격 컴퓨터 이름>:4024이 표시 되어야 합니다.**
    ::: moniker-end
    ::: moniker range="vs-2017"
    Visual Studio 2017에서 ** \<원격 컴퓨터 이름>:4022이 표시 되어야 합니다.**
    ::: moniker-end
    포트가 필요 합니다. 포트 번호가 표시 되지 않으면 수동으로 추가 합니다.

4. **새로 고침**을 클릭 합니다.
    일부 프로세스가 **사용 가능한 프로세스** 창에 표시됩니다.

    프로세스가 표시 되지 않는 경우 원격 컴퓨터 이름 대신 IP 주소를 사용해 보세요 (포트가 필요 함). 명령줄에서를 `ipconfig` 사용 하 여 IPv4 주소를 가져올 수 있습니다.

    **찾기** 단추를 사용 하려는 경우 서버에서 [UDP 포트 3702을 열어야](#bkmk_openports) 할 수 있습니다.

5. **모든 사용자의 프로세스 표시**를 선택합니다.

6. 앱을 신속 하 게 찾으려면 프로세스 이름의 첫 글자를 입력 합니다.

    * 에서 IIS의 [in-process 호스팅 모델](/aspnet/core/host-and-deploy/aspnet-core-module?view=aspnetcore-3.1#hosting-models) 을 사용 하는 경우 적절 한 w3wp.exe **.exe** 프로세스를 선택 합니다. .NET Core 3부터이는 기본값입니다.

    * 그렇지 않으면 **dotnet** 프로세스를 선택 합니다. 이는 out-of-process 호스팅 모델입니다.

    W3wp.exe 또는 *dotnet* *을 보여 주는* 여러 프로세스가 있는 경우 **사용자 이름** 열을 확인 합니다. 일부 시나리오에서 **사용자 이름** 열에는 **IIS APPPOOL\DefaultAppPool**와 같은 앱 풀 이름이 표시 됩니다. 응용 프로그램 풀이 표시 되지 않지만 고유 하지 않은 경우 디버깅 하려는 앱 인스턴스에 대해 새 명명 된 앱 풀을 만든 다음 **사용자 이름** 열에서 쉽게 찾을 수 있습니다.

    ::: moniker range=">=vs-2019"
    ![RemoteDBG_AttachToProcess](../debugger/media/vs-2019/remotedbg-attachtoprocess-aspnetcore.png "RemoteDBG_AttachToProcess")
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg-attachtoprocess-aspnetcore.png "RemoteDBG_AttachToProcess")
    ::: moniker-end

7. **연결**을 클릭합니다.

8. 원격 컴퓨터의 웹 사이트를 엽니다. 브라우저에서 **http://\<원격 컴퓨터 이름>** 으로 이동합니다.

    ASP.NET 웹 페이지가 표시됩니다.

9. 실행 중인 ASP.NET 응용 프로그램에서 정보 페이지에 **대 한** 링크를 클릭 합니다.

    Visual Studio에서 중단점이 적중됩니다.

## <a name="troubleshooting-open-required-ports-on-windows-server"></a><a name="bkmk_openports"></a> 문제 해결 Windows Server에서 필요한 포트를 열려면

대부분의 설치에서는 ASP.NET 및 원격 디버거를 설치 하 여 필요한 포트를 엽니다. 그러나 포트가 열려 있는지 확인 해야 할 수도 있습니다.

> [!NOTE]
> Azure VM에서 [네트워크 보안 그룹](/azure/virtual-machines/windows/nsg-quickstart-portal)을 통해 포트를 열어야 합니다.

필요한 포트:

* 80-IIS에 필요 합니다.
::: moniker range=">=vs-2019"
* 4024-Visual Studio 2019에서 원격 디버깅에 필요 합니다 (자세한 내용은 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md) 참조).
::: moniker-end
::: moniker range="vs-2017"
* 4022-Visual Studio 2017에서 원격 디버깅에 필요 합니다 (자세한 내용은 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md) 참조).
::: moniker-end
* UDP 3702-(선택 사항) 검색 포트를 사용 하면 Visual Studio에서 원격 디버거에 연결할 때 **찾기** 단추를 사용할 수 있습니다.

1. Windows Server에서 포트를 열려면 **시작** 메뉴를 열고 **고급 보안이 포함 된 Windows 방화벽**을 검색 합니다.

2. 그런 다음 **인바운드 규칙 > 새 규칙 > 포트**를 선택 하 고 **다음**을 클릭 합니다. (UDP 3702의 경우 대신 **아웃 바운드 규칙** 을 선택 합니다.)

3. **특정 로컬 포트**에서 포트 번호를 입력 하 고 **다음**을 클릭 합니다.

4. **연결 허용**을 클릭 하 고 **다음**을 클릭 합니다.

5. 포트에 대해 사용 하도록 설정할 네트워크 종류를 하나 이상 선택 하 고 **다음**을 클릭 합니다.

    선택한 유형은 원격 컴퓨터가 연결된 네트워크를 포함해야 합니다.
6. 인바운드 규칙의 이름 (예: **IIS**, **웹 배포**또는 **msvsmon**)을 추가 하 고 **마침**을 클릭 합니다.

    인바운드 규칙 또는 아웃바운드 규칙 목록에 새 규칙이 표시되어야 합니다.

    Windows 방화벽 구성에 대 한 자세한 내용은 [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)을 참조 하세요.

3. 다른 필요한 포트에 대 한 추가 규칙을 만듭니다.
