---
title: 프로젝트에 NuGet 패키지 포함하기
description: 이 문서에서는 Mac용 Visual Studio를 사용하여 프로젝트에 NuGet 패키지를 포함하는 방법을 설명합니다. 여기에서는 IDE 통합 기능을 소개할 뿐 아니라 패키지를 찾아 다운로드하는 방법도 살펴봅니다.
author: jmatthiesen
ms.author: jomatthi
ms.date: 09/17/2019
ms.assetid: 5C800815-0B13-4B27-B017-95FCEF1A0EA2
ms.custom: conceptual
ms.openlocfilehash: 22b2e07509403d8e19e3a3e920d45b064c2e51c0
ms.sourcegitcommit: 541a0556958201ad6626bc8638406ad02640f764
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71079476"
---
# <a name="install-and-manage-nuget-packages-in-visual-studio-for-mac"></a>Mac용 Visual Studio에서 NuGet 패키지 설치 및 관리

Mac용 Visual Studio의 NuGet 패키지 관리자 UI를 사용하여 프로젝트 및 솔루션에서 NuGet 패키지를 쉽게 설치, 제거 및 업데이트할 수 있습니다. .NET Core, ASP.NET Core 및 Xamarin 프로젝트를 검색하고 패키지를 추가할 수 있습니다.

이 문서에서는 프로젝트에 NuGet 패키지를 포함하는 방법을 설명하고 이 프로세스를 원활하게 하는 도구 체인을 보여줍니다.

Mac용 Visual Studio에서 NuGet을 사용하는 방법에 대해서는 [빠른 시작: Mac용 Visual Studio에서 패키지 설치 및 사용](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)을 참조하세요.

## <a name="find-and-install-a-package"></a>패키지 찾기 및 설치

1. Mac용 Visual Studio에서 프로젝트를 연 상태로 **Solution Pad**의 **종속성** 폴더(Xamarin 프로젝트를 사용하는 경우에는 **패키지** 폴더)를 마우스 오른쪽 단추로 클릭하고 **패키지 추가**를 선택합니다.

    ![새 NuGet 패키지 컨텍스트 작업 추가하기](media/nuget-walkthrough-PackagesMenu.png)

2. 이렇게 하면 **패키지 추가** 창이 시작됩니다. 대화 상자의 왼쪽 상단에 있는 소스 드롭다운이 `nuget.org`로 설정되어 있는지 확인합니다.

    ![NuGet 패키지 목록](media/nuget-walkthrough-AddPackages1.png)

3. 오른쪽 위의 검색 상자를 사용하여 특정 패키지(예: `EntityFramework`)를 검색합니다. 사용하려는 패키지를 찾았다면 해당 패키지를 선택하고 **패키지 추가** 단추를 클릭하여 설치를 시작합니다.

    ![Azure NuGet 패키지 추가](media/nuget-walkthrough-AddPackages2.png)

4. 패키지가 다운로드된 후 프로젝트에 추가됩니다. 솔루션은 편집 중인 프로젝트의 형식에 따라 변경됩니다.

    **Xamarin 프로젝트**
    * **참조** 노드는 NuGet 패키지의 일부인 모든 어셈블리의 목록을 포함합니다.
    * **패키지** 노드는 다운로드한 각 NuGet 패키지를 표시합니다. 이 목록에서 패키지를 업데이트하거나 제거할 수 있습니다.
    
    **.NET Core 프로젝트**

    **종속성 > NuGet** 노드에 다운로드한 각 NuGet 패키지가 표시됩니다. 이 목록에서 패키지를 업데이트하거나 제거할 수 있습니다.

## <a name="using-nuget-packages"></a>NuGet 패키지 사용하기

NuGet 패키지를 추가하고 프로젝트 참조를 업데이트하면 모든 프로젝트 참조와 같은 방식으로 API에 대해 프로그래밍할 수 있습니다.

파일 상단에 필요한 `using` 지시문을 추가했는지 확인하세요.

```csharp
using Newtonsoft.Json;
```

<a name="Package_Updates" class="injected"></a>

## <a name="updating-packages"></a>패키지 업데이트

패키지 업데이트는 **종속성** 노드(Xamarin 프로젝트의 경우 **패키지** 노드)를 마우스 오른쪽 단추로 클릭하여 한꺼번에 수행하거나 각 구성 요소에서 개별적으로 수행할 수 있습니다.

**종속성**을 마우스 오른쪽 단추로 클릭하여 상황에 맞는 메뉴에 액세스합니다.

![패키지 메뉴](media/nuget-walkthrough-PackagesMenu.png)

* **NuGet 패키지 관리** - 프로젝트에 패키지를 더 추가하기 위한 창을 엽니다.
* **업데이트** - 각 패키지에 대해 소스 서버를 확인하고 모든 최신 버전을 다운로드합니다.
* **복원** - 기존 패키지를 최신 버전으로 업데이트하지 않고 모든 누락된 패키지를 다운로드합니다.

업데이트 및 복원 옵션은 솔루션 수준에서도 사용 가능하며, 솔루션 내의 모든 프로젝트에 영향을 줍니다.

solution pad에서 현재 설치된 패키지 버전을 확인하 고 업데이트할 패키지를 마우스 오른쪽 단추로 클릭할 수 있습니다.

![업데이트, 제거, 새로 고침 옵션이 있는 패키지 메뉴](media/nuget-walkthrough-PackageMenu.png)

패키지의 새 버전을 사용할 수 있는 경우 패키지 이름 옆에 알림이 표시되므로 업데이트할지 여부를 결정할 수 있습니다.

![새 패키지 버전을 사용할 수 있을 때 표시되는 알림](media/nuget-walkthrough-package-update-available.png)

표시된 메뉴에는 두 가지 옵션이 있습니다.

* **업데이트** - 소스 서버를 확인하고 새 버전(있는 경우)을 다운로드합니다.
* **제거** - 이 프로젝트에서 패키지를 제거하고 프로젝트의 참조에서 관련 어셈블리를 제거합니다.

## <a name="adding-package-sources"></a>패키지 소스 추가하기

설치에 사용할 수 있는 패키지를 처음에는 nuget.org에서 검색합니다. 하지만 Mac용 Visual Studio에 다른 패키지 위치를 추가할 수 있습니다. 이는 개발 중인 자체 NuGet 패키지를 테스트하거나, 회사나 조직 내에서 개인 NuGet 서버를 사용할 때 유용할 수 있습니다.

Mac용 Visual Studio에서 **Visual Studio > 기본 설정 > NuGet > 소스**로 이동하여 패키지 소스의 목록을 보고 편집합니다. 소스는 (URL로 지정된) 원격 서버 또는 로컬 디렉터리일 수 있습니다.

![패키지 소스](media/nuget-walkthrough-PackageSource.png)

새로운 소스를 설정하려면 **추가**를 클릭합니다. 패키지 소스에 식별 이름과 URL(또는 파일 경로)을 입력하세요. 소스가 보안 웹 서버인 경우에는 사용자 이름과 암호도 입력하고, 그렇지 않은 경우에는 비워둡니다.

![패키지 소스 추가](media/nuget-walkthrough-PackageSource2.png)

그런 다음 패키지를 검색할 때 서로 다른 소스를 선택할 수 있습니다.

![패키지 소스 추가](media/nuget-walkthrough-PackageSource3.png)

## <a name="version-control"></a>버전 제어

NuGet 설명서에서는 [소스 제어에 패키지를 커밋하지 않고 NuGet을 사용하는 방법](/nuget/consume-packages/packages-and-source-control)에 대해 논의합니다. 소스 제어에 이진 파일 및 사용되지 않은 정보를 저장하지 않으려는 경우 Mac용 Visual Studio를 구성하여 서버에서 패키지를 자동으로 복원할 수 있습니다. 즉, 개발자가 소스 제어에서 프로젝트를 처음 검색하는 경우에는 Mac용 Visual Studio에서 필요한 패키지를 자동으로 다운로드하고 설치합니다.

![패키지를 자동으로 복원](media/nuget-walkthrough-AutoRestore.png)

추적 대상에서 `packages` 디렉터리를 제외하는 방법에 대한 자세한 내용은 해당 소스 제어 설명서를 참조하세요.

## <a name="related-video"></a>관련 동영상

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Using-NuGet/player]

## <a name="see-also"></a>참고 항목

* [Visual Studio에서 패키지 설치 및 사용(Windows에서)](/nuget/quickstart/install-and-use-a-package-in-visual-studio)
