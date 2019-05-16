---
title: Office 프로젝트 디버깅
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel projects [Office development in Visual Studio], debugging
- Word projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], debugging
- debugging [Office development in Visual Studio], Outlook projects
- Office projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], projects
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8b48335ccaa8bd21cf9f6e108d043ecf706903bb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441877"
---
# <a name="debug-office-projects"></a>Office 프로젝트 디버깅
  다른 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트에 사용한 것과 동일한 Microsoft [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 도구를 사용하여 Office 프로젝트를 디버그할 수 있습니다. 중단점 삽입 및[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 지역 **창에 변수 표시와 같은** 디버거 기능은 Office 프로젝트를 디버그할 때도 사용할 수 있습니다. 에 대 한 자세한 내용은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버깅 도구를 참조 하세요 [Visual Studio에서 디버그](../debugger/debugging-in-visual-studio.md)합니다.

> [!TIP]
> 디버깅을 간소화하려면 빌드하고 디버그하기 전에 Office 애플리케이션의 열린 인스턴스를 모두 닫습니다.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

> [!NOTE]
> Office 환경을 확장 하는 솔루션을 개발 하는 데 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 새 확인해 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능의 VSTO 추가 기능 및 솔루션에 비해 작은 사용 공간이 있고 거의 모든 웹 프로그래밍 기술을, HTML5, JavaScript, CSS3, XML 등을 사용 하 여 빌드할 수 있습니다.

## <a name="start-and-stop-the-debugger"></a>시작 하 고 디버거를 중지 합니다.
 다른 디버깅을 시작 하는 것 처럼 Office 프로젝트 디버깅을 시작할 수 있습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 누르면 예를 들어 합니다 **F5** 키입니다. VSTO 추가 기능 프로젝트 디버깅을 시작 하면 대상된 Office 응용 프로그램에 대 한 새 프로세스가 시작 되 고 VSTO 추가 기능에 로드 됩니다.

 문서 수준 프로젝트의 디버깅을 시작하면 문서 또는 통합 문서가 새로운 Word 또는 Excel 프로세스로 열립니다.

 디버거를 중지하면 디버거에서 애플리케이션 프로세스를 갑자기 종료하거나 디버거를 분리로 설정한 경우에는 분리합니다. 종료된 Office 애플리케이션 프로세스에서 연 다른 모든 문서도 경고를 표시하지 않고 닫혀 저장되지 않은 모든 변경 내용이 손실됩니다. 여기에는 디버거가 실행되는 동안 열린 모든 문서 또는 통합 문서가 포함될 수 있습니다.

 일반적으로 디버거를 중지하기 전에 프로세스에서 분리하여 정상적인 방식으로 Office 애플리케이션을 종료할 수 있도록 하는 것이 좋습니다. 또한 디버거를 중지한 후에도 열려 있는 문서 또는 워크시트로 계속 작업하려는 경우 프로세스에서 분리할 수 있습니다.

 Word에 대해 문서 수준 사용자 지정을 디버깅하는 경우 반복적으로 디버거를 중지하여 Word가 갑자기 닫히도록 하면 기본 서식 파일이 손상될 수 있습니다. 이런 경우 손상된 기본 서식 파일을 삭제할 수 있습니다. 그러면 다음에 Word를 열 때 자동으로 다시 만들어집니다. 그러나 기본 서식 파일에 저장된 모든 매크로는 다시 만들어지지 않습니다.

### <a name="debug-office-2013-vsto-add-ins-by-using-either-office-2013-or-office-2016"></a>Office 2013 또는 Office 2016을 사용하여 Office 2013 VSTO 추가 기능 디버깅
 Visual Studio 2015를 사용 하는 두 버전의 Office 설치 하 여 나란히 있는 경우 Visual Studio는 Office 2016을 시작 합니다. Visual Studio 2013을 사용 하는 경우 Visual Studio Office 2013을 시작 합니다.

 다른 버전의 Office(2013 또는 2016)를 사용하여 VSTO 추가 기능을 디버그하려면 **프로젝트 디자이너**를 열고 **디버그** 탭에서 **시작 외부 프로그램** 옵션 단추를 선택합니다. 그런 다음 적절한 Office 애플리케이션 실행의 위치로 이동합니다.

## <a name="f10-and-f11-behavior"></a>F10 및 F11 동작
 Office 프로젝트 디버깅을 시작할 때 **F10** 하 고 **F11** 다른 Visual Basic 또는 C# 프로젝트 디버깅을 시작할 때와 동일한 동작에 있지 않습니다. Visual Basic 또는 C# 프로젝트에서는 디버거가 main 함수에서 중지하고 Office 프로젝트에서는 Visual Studio가 Office 애플리케이션의 main 함수를 제어하지 않습니다. 그러나 디버깅 중 **F10** 하 고 **F11** Visual Basic 및 C# 프로젝트 에서처럼 동일한 역할 권한이 있습니다.

## <a name="display-exceptions"></a>예외를 표시 합니다.
 관리 코드가 비관리 코드와 상호 작용하는 방식으로 인해 Visual Studio는 Microsoft Office 애플리케이션에서 throw되는 오류를 표시하지 않습니다. 예를 들어, 한 VSTO 추가 기능으로 만든 Visual Studio에서 Office 개발 도구를 사용 하 여 예외를 throw 하는 경우 Microsoft Office 응용 프로그램 오류를 표시 하지 않고 계속 됩니다. 이러한 오류를 표시하려면 공용 언어 런타임 예외에서 중단하도록 디버거를 설정합니다. 자세한 내용은 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)합니다.

 공용 언어 런타임 예외에서 중단하도록 디버거를 설정하면 이미 처리한 예외 및 런타임 자체의 몇 가지 첫째 예외를 포함한 모든 예외가 프로젝트와 관련 없는 디버거로 중단됩니다. 찾을 수 없는 msosec를 참조하는 오류가 모든 프로젝트에 나타나지만 무시해도 됩니다. 이러한 msosec 예외는 솔루션에 영향을 주지 않습니다.

 메서드에서 **Try...Catch** 문을 사용하여 예외를 catch할 수도 있습니다.

 기본적으로 Visual Studio는 Office 프로젝트에 대한 Just-In-Time 디버깅 오류를 표시하지 않습니다. 그러나 이 기능을 사용하도록 설정하여 발생되는 오류를 표시할 수 있습니다. 자세한 내용은 [Just In Time Visual Studio에서 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)합니다.

## <a name="command-line-arguments"></a>명령줄 인수
 경우는 **시작 작업** 에 **디버그** 속성 페이지 설정 되어 **프로젝트 시작**, Visual Studio 사용 하지 않습니다 명령줄 인수 프로젝트를 디버깅할 때 해야 하는 경우에 시작 옵션으로 명령줄 인수를 지정 합니다. 디버깅을 시작할 때 명령줄 인수를 사용 하려는 경우 선택 해야 합니다는 **시작 작업** 이외의 **프로젝트 시작**합니다.

## <a name="source-control"></a>소스 제어
 디버그 속성은 소스 제어에서 여러 사용자 간에 공유되지 않습니다. Visual Basic 및 C# 프로젝트는 디버깅 속성을 사용자별 파일(*ProjectName*.vbproj.user 또는 *ProjectName*.csproj.user)에 저장하며 이 파일은 소스 제어에서 사용되지 않습니다. 둘 이상의 사용자를 디버깅하는 경우 각 사용자가 디버그 속성을 수동으로 입력해야 합니다.

## <a name="debug-cached-datasets-in-a-document-level-project"></a>문서 수준 프로젝트에서 캐시 된 데이터 집합 디버깅
 프로젝트를 빌드할 때마다 데이터 세트가 비워지고 다시 만들어집니다. 캐시된 데이터 세트를 디버그하려면 Visual Studio 외부에서 문서를 열고 디버거를 연결해야 합니다.

## <a name="debug-word-document-projects-based-on-the-word-97-2003-document-doc-format"></a>Word 97-2003 문서를 기반으로 디버그 Word 문서 프로젝트 (*.doc) 형식
 Word 97-2003 문서를 기반으로 Word 문서 프로젝트를 디버그 하려면 (*/*.doc*) 형식으로 신뢰할 수 있는 폴더 목록에 프로젝트 폴더를 추가 해야 합니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)합니다.

## <a name="debug-disabled-add-ins"></a>디버그 추가 기능을 사용 하지 않도록 설정
 Microsoft Office 애플리케이션에서는 예기치 않게 동작하는 VSTO 추가 기능을 사용하지 않도록 설정할 수 있습니다. Microsoft Office 애플리케이션에서는 애플리케이션이 시작될 때마다 문제가 있는 코드가 로드되지 않도록 하는 VSTO 추가 기능을 사용하지 않도록 설정합니다. 그러나 일반적인 디버깅 중에는 예기치 않은 동작이 쉽게 발생할 수 있습니다. VSTO 추가 기능을 다시 활성화 하는 방법에 대 한 정보를 참조 하세요. [방법: VSTO 추가 기능을 비활성화 된 다시 사용 하도록 설정](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)합니다.

 Microsoft Office 애플리케이션에서 VSTO 추가 기능에 사용할 수 있는 비활성화는 하드 비활성화와 소프트 비활성화의 두 가지 유형이 있습니다.

### <a name="hard-disabling"></a>하드 비활성화
 하드 비활성화는 VSTO 추가 기능으로 인해 응용 프로그램이 예기치 않게 종료 하는 경우 발생할 수 있습니다. 또한 개발 컴퓨터에서 VSTO 추가 기능의 <xref:Microsoft.Office.Tools.AddIn.Startup> 이벤트 처리기가 실행되고 있는 동안 디버거를 중지하는 경우 발생합니다. VSTO 추가 기능에 하드 비활성화 되 면 합니다 **사용할 수 없는 항목** 응용 프로그램의 목록입니다.

 Office 응용 프로그램에서 하드 비활성화는 VSTO 추가 기능으로 만든 Visual Studio에서 Office 개발 도구를 사용 하 여 하면만 vsto 추가 하는 오류를 발생 시킨 응용 프로그램을 비활성화 합니다. 해당 Office 애플리케이션에 대해 Visual Studio에서 Office 개발 도구를 사용하여 만든 다른 VSTO 추가 기능은 계속 로드됩니다.

### <a name="soft-disabling"></a>소프트 비활성화
 소프트 비활성화는 VSTO 추가 기능에서 애플리케이션이 예기치 않게 닫히지 않는 오류를 생성하는 경우 수행됩니다. 예를 들어 <xref:Microsoft.Office.Tools.AddIn.Startup> 이벤트 처리기가 실행되는 동안 처리되지 않은 예외가 발생하는 경우 애플리케이션에서 VSTO 추가 기능을 소프트 비활성화할 수 있습니다. VSTO 추가 기능을 소프트 비활성화 되 면 합니다 **비활성 응용 프로그램 추가 기능** 응용 프로그램 및 응용 프로그램 목록의 값을 변경 합니다 **LoadBehavior** VSTO 추가 기능에 대 한 레지스트리 항목 로드 하지 임을 나타냅니다. 에 대 한 자세한 내용은 합니다 **LoadBehavior** 레지스트리 항목을 참조 하세요 [VSTO 추가 기능에 대 한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)합니다.

## <a name="troubleshoot-installation-errors-by-using-the-event-viewer"></a>이벤트 뷰어를 사용 하 여 설치 오류 해결
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 은 Office 솔루션을 설치하거나 제거할 때 throw되는 모든 예외에 대한 메시지를 Windows의 이벤트 뷰어에 기록합니다. 이러한 메시지를 사용하여 설치 및 배포 문제를 해결할 수 있습니다.

## <a name="troubleshoot-startup-errors-by-using-a-log-file-and-error-messages"></a>로그 파일 및 오류 메시지를 사용 하 여 시작 오류 문제 해결
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 은 시작하는 동안 발생하는 모든 오류를 로그 파일에 기록하거나 각 오류를 메시지 상자에 표시할 수 있습니다. 기본적으로 이러한 옵션은 해제되어 있습니다. 환경 변수를 만들어 옵션을 켤 수 있습니다.

 메시지 상자에 각 오류를 표시하려면 `VSTO_SUPPRESSDISPLAYALERTS` 라는 환경 변수를 만들어 0으로 설정합니다. 환경 변수를 삭제하거나 1로 설정하여 메시지를 표시하지 않을 수 있습니다.

 오류를 로그 파일에 기록하려면 `VSTO_LOGALERTS` 라는 환경 변수를 만들고 1로 설정합니다. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 은 VSTO 추가 기능에 대한 배포 매니페스트를 포함하는 폴더 또는 사용자 지정과 관련된 문서 또는 통합 문서를 포함하는 폴더에 로그 파일을 만듭니다. 실패할 경우 합니다 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 로컬에서 로그 파일을 만듭니다 *% TEMP %* 폴더입니다. 애플리케이션 수준 VSTO 추가 기능의 경우 기본 이름은 *추가 기능 이름*.vsto.log입니다. 문서 수준 프로젝트의 경우 로그 파일의 이름은 *문서 이름*.*확장명*.log(예: ExcelWorkbook1.xlsx.log)입니다. 오류 로깅을 중지하려면 환경 변수를 삭제하거나 0으로 설정합니다.

## <a name="see-also"></a>참고 항목

- [Office 솔루션 빌드](../vsto/building-office-solutions.md)
- [방법: VSTO 추가 기능을 비활성화 된 다시 사용 하도록 설정](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)
- [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)