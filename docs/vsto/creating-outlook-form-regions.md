---
title: Outlook 양식 영역 만들기
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- MICROSOFT.OFFICE.TOOLS.OUTLOOK.FORMREGION
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio]
- form regions [Office development in Visual Studio], creating
- Outlook [Office development in Visual Studio], form regions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: dc0f56331c11c6c33561774d38ef79e286a4133a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445577"
---
# <a name="create-outlook-form-regions"></a>Outlook 양식 영역 만들기
  양식 영역을 사용하여 Microsoft Office Outlook 양식을 사용자 지정할 수 있습니다. Visual Studio는 양식 영역을 쉽게 디자인, 개발 및 디버그할 수 있도록 하는 고급 도구를 제공합니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

 이 항목에서는 다음 내용에 대해 설명합니다.

- [양식 영역을 사용할 때의 장점](#Enhance)

- [프로젝트에 Outlook 양식 영역 추가](#Adding)

- [양식 영역 디자이너를 사용 하 여](#UsingFormRegionDesigner)

- [Outlook에서 디자인 한 양식 영역 사용](#UsingFormRegionDesignedOutlook)

- [양식 영역에 사용자 지정 코드 추가](#AddingCustomCode)

- [프로젝트 빌드](#Building)

- [양식 영역 디버그](#Debugging)

- [양식 영역을 배포](#Deploying)

## <a name="Enhance"></a> 양식 영역을 사용할 때의 장점
 양식 영역은 기존의 Outlook 양식 개발보다 많은 향상된 기능을 제공합니다.

- 모든 표준 양식의 기본 페이지를 사용자 지정합니다.

- 모든 표준 양식에 최대 12개의 추가 페이지를 추가합니다.

- 모든 표준 양식을 바꾸거나 향상시킵니다.

- 읽기 창과 검사기에 사용자 지정 UI를 표시합니다.

  자세한 내용은 [양식 페이지 및 양식 영역을 사용자 지정](/office/vba/outlook/Concepts/Forms/customizing-form-pages-and-form-regions)합니다.

## <a name="Adding"></a> 프로젝트에 Outlook 양식 영역 추가
 사용할 수는 **새 Outlook 양식 영역** 새 양식 영역을 디자인 하거나 Outlook에서 디자인 된 양식 영역 가져오기 마법사. 또한 다른 Outlook VSTO 추가 기능 프로젝트에서 사용한 양식 영역이 있는 경우 기존 양식 영역을 다시 사용할 수 있습니다.

### <a name="CreatingFormRegion"></a> 마법사를 사용 하 여 새 양식 영역 만들기
 양식 영역을 만들려면 추가 **Outlook 양식 영역** 에서 Outlook VSTO 추가 기능 프로젝트에 대 한 항목입니다. 이 시작 합니다 **새 Outlook 양식 영역** 마법사.

 이 마법사를 사용하여 새 양식 영역을 디자인할지 또는 Outlook에서 디자인한 양식 영역을 가져올지 지정합니다. 새 양식 영역을 디자인 하는 방법에 대 한 자세한 내용은 참조 하세요. [양식 영역 디자이너를 사용 하 여](#UsingFormRegionDesigner)입니다. Outlook에서 디자인 한 양식 영역을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Outlook에서 디자인 한 양식 영역 가져오기](#UsingFormRegionDesignedOutlook)합니다.

 마법사를 사용하여 만들려는 양식 영역의 형식을 지정합니다. 다음 표에서는 각 양식 영역 형식에 대해 설명합니다.

|영역 형식|설명|
|-----------------|-----------------|
|별도|Outlook 양식에 새 페이지로 양식 영역을 추가합니다.|
|인접|Outlook 양식의 기본 페이지 맨 아래에 양식 영역을 추가합니다.|
|Replacement|Outlook 양식의 기본 페이지를 대체하는 새 페이지로 양식 영역을 추가합니다.|
|모두 바꾸기|전체 Outlook 양식을 양식 영역으로 바꿉니다.|

 마법사를 사용하여 표시 조건을 지정하고 확장할 양식의 형식을 선택할 수도 있습니다. 자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.

 마법사에서 선택한 항목은 다른 마법사 페이지에서 사용할 수 있는 옵션에 영향을 줍니다. 예를 들어, 선택 하는 경우 **인접** 또는 **별도** 에 **새 Outlook 양식 영역을 만들** 페이지에서 해당 **제목** 및 **설명을** 필드에서 사용할 수 없는 합니다 **설명 텍스트를 입력 하 고 디스플레이 기본 설정을 선택** 페이지입니다. 이는 Outlook에서 인접 또는 별도 양식 영역을 표시할 때 이러한 필드를 사용하지 않기 때문입니다.

#### <a name="form-region-files"></a>양식 영역 파일
 완료 되 면 합니다 **새 Outlook 양식 영역** 마법사, Visual Studio 프로젝트에 다음 파일을 자동으로 추가 합니다.

- 양식 영역 코드 파일. 이 파일에 지정 하는 이름에는 **Outlook 양식 영역** 항목에 **새 항목 추가** 대화 상자. 이 파일에 양식 영역 이벤트를 처리하는 코드를 추가합니다.

- 양식 영역 디자이너 코드 파일. 이 파일은 양식 영역 디자이너에서 생성된 코드를 포함하며 직접 편집할 수 없습니다.

- Outlook 양식 저장 ( *.ofs*) 파일입니다.

    > [!NOTE]
    > Outlook에서 디자인한 양식 영역을 가져오는 경우 이 파일만 프로젝트에 추가됩니다.

#### <a name="form-region-factory-class"></a>양식 영역 팩터리 클래스
 양식 영역 코드 파일에는 <xref:Microsoft.Office.Tools.Outlook.IFormRegionFactory> 인터페이스를 구현하는 partial 클래스가 포함되어 있습니다. 이는 양식 영역 팩터리 클래스입니다. 양식 영역 팩터리 클래스는 양식 영역의 새 인스턴스를 만듭니다.

 이 클래스를 확장 하 여 찾을 수 있습니다 합니다 **양식 영역 팩터리** 지역입니다.

 합니다 **새 Outlook 양식 영역** 양식 영역의 내부 이름을 지정 하는이 클래스 및 양식 영역을 표시 하는 메시지 클래스에 특성을 추가 합니다. 파일이 프로젝트에 추가된 후 이러한 특성을 수동으로 수정할 수 있습니다.

 대부분의 양식 영역 팩터리 클래스는 양식 영역 디자이너 파일에서 구현됩니다. 그러나 `FormRegionInitializing` 이벤트 처리기는 양식 영역 코드 파일에 노출됩니다. 이 이벤트 처리기를 사용하여 Outlook에서 양식 영역을 표시할지 여부를 지정할 수 있습니다. 자세한 내용은 [양식 영역 이벤트 처리](#HandlingFormRegionEvents)합니다.

### <a name="AddingExistingFormRegion"></a> 프로젝트에 기존 양식 영역 추가
 다른 Outlook 프로젝트에서 사용한 Outlook 양식 영역이 있는 경우 **기존 항목 추가** 대화 상자를 사용하여 현재 Outlook VSTO 추가 기능 프로젝트에서 다시 사용할 수 있습니다.

 기존 양식 영역 코드 파일이 있어야 합니다 ( *.vb* 하거나 *.cs*); Outlook 양식 저장을 추가할 수 없습니다 ( *.ofs*)를 사용 하 여 파일을 **기존 항목 추가** 대화 상자. 그러나 Outlook 양식 스토리지 파일을 가져와 새 양식 영역을 만들 수 있습니다. 자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.

## <a name="UsingFormRegionDesigner"></a> 양식 영역 디자이너를 사용 하 여
 양식 영역 디자이너는 양식 영역의 모양과 레이아웃을 디자인하는 데 도움이 됩니다. 관리 되는 컨트롤 디자이너의 화면으로 끌어, 이벤트 처리기를 열고 컨트롤을 두 번 클릭 및에서 속성을 설정 합니다 **속성** 창입니다.

> [!NOTE]
> 아래에 Outlook에서 양식 영역이 표시 되는 방식에 영향을 주는 속성을 찾을 수 있습니다 합니다 **매니페스트** 에서 노드를 **속성** 창입니다.

 양식 영역 디자이너를 선택 하는 경우에 사용할 수 **새 양식 영역 디자인** 에 **양식 영역을 만드는 방법을 선택할** 페이지를 **새 Outlook 양식 영역** 마법사입니다.

 양식 영역 디자이너를 여는 방법에는 다음 세 가지가 있습니다.

- **솔루션 탐색기**, 양식 영역 코드 파일을 두 번 클릭 합니다.

- **솔루션 탐색기**양식 영역 코드 파일을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **뷰 디자이너**합니다.

- **솔루션 탐색기**, 양식 영역 코드 파일을 선택를 선택한 후 합니다 **뷰** 메뉴에서 클릭 **디자이너**합니다.

  양식 영역 디자이너는 관리되는 컨트롤만 지원합니다. 네이티브 Outlook 컨트롤을 추가할 수 없습니다.

## <a name="UsingFormRegionDesignedOutlook"></a> Outlook에서 디자인 한 양식 영역 가져오기
 Outlook에서 디자인할 때 양식 영역에 네이티브 Outlook 컨트롤을 추가할 수 있습니다. 네이티브 Outlook 컨트롤을 사용하여 디자인 타임에 Outlook 데이터에 바인딩할 수 있습니다. 그러나 양식 영역 디자이너를 사용하여 관리되는 컨트롤을 추가하거나 양식 영역의 디자인을 변경할 수 없습니다.

 사용 하 여에서 Outlook VSTO 추가 기능 프로젝트로 양식 영역을 가져올 수 있습니다 합니다 **새 Outlook 양식 영역** 마법사. 에 **양식 영역을 만드는 방법 선택** 페이지에서 선택 **Outlook 양식 저장 (.ofs) 파일로 가져올**합니다. Outlook 양식 저장 파일의 위치로 이동할 수 있습니다 ( *.ofs*) 파일입니다. (Outlook 양식 영역으로 저장 *.ofs* 파일입니다.)

 합니다 **새 Outlook 양식 영역** 마법사 복사 합니다 *.ofs* 프로젝트 디렉터리에 파일 및 양식 영역 디자이너 파일에 컨트롤 참조를 추가 합니다. 그런 다음 양식 영역 코드 파일에서 컨트롤 이벤트를 처리할 수 있습니다.

 Visual Basic 프로젝트에서 이벤트를 처리하려면 코드 편집기 맨 위의 메서드 이름 목록에서 이벤트를 선택합니다.

 C# 프로젝트의 이벤트를 처리하려면 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 메서드에서 컨트롤 이벤트를 구독합니다. 자세한 내용은 [방법: 구독 및 이벤트 구독 취소 &#40;C&#35; 프로그래밍 가이드&#41;](/dotnet/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events)합니다.

 양식 영역 팩터리 클래스의 `InitializeManifest` 메서드에서 양식 영역 속성을 변경할 수 있습니다.

> [!NOTE]
> 양식 영역을 가져오려면 개발 컴퓨터에 설치한 것과 동일한 버전의 Outlook을 대상으로 하는 프로젝트에서 작업해야 합니다. 예를 들어 Outlook 2010이 설치 된 경우 가져오기는 양식 영역 에서만 작동 프로젝트를 사용 하 여 만든 합니다 **Outlook 2010 추가 기능에** 프로젝트 템플릿.

### <a name="update-an-imported-form-regions-design"></a>가져온된 양식 영역을 디자인 업데이트
 양식 영역에서 컨트롤을 추가, 제거 또는 변경할 수 있습니다. 이 작업을 수행하기 전에 양식 영역 코드 파일에 추가한 코드를 모두 백업합니다. 그런 다음 엽니다는 *.ofs* Outlook 파일 양식 영역을 수정한 다음 변경 내용을 저장 합니다. 사용 된 **새 Outlook 양식 영역** 수정 된 가져오기 마법사 *.ofs* 파일입니다. 그런 다음 새 양식 영역 코드 파일에 코드를 붙여넣을 수 있습니다.

## <a name="AddingCustomCode"></a> 양식 영역에 사용자 지정 코드 추가
 <xref:Microsoft.Office.Tools.Outlook> 네임스페이스는 양식 영역을 나타내는 클래스, 양식 영역을 표시하는 Outlook 항목 및 기타 유용한 항목에 대한 액세스를 제공합니다. 합니다 **Outlook 양식 영역** 항목이 자동으로 프로젝트에서이 어셈블리에 대 한 참조를 추가 하 고 적절 한 삽입 **사용 하 여** 또는 **Imports** 맨 위에 있는 문을 양식 영역 코드 파일입니다.

 `Microsoft.Office.Interop.Outlook` 네임스페이스의 클래스, 메서드 및 속성을 사용하여 Outlook 프로그래밍 작업을 대부분 수행할 수 있습니다. Outlook 개체 모델에 대 한 자세한 내용은 참조 하세요. [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)합니다. Outlook 개체 모델을 사용 하는 일반적인 작업에 대 한 예제 [Outlook 솔루션](../vsto/outlook-solutions.md)합니다.

### <a name="HandlingFormRegionEvents"></a> 양식 영역 이벤트 처리
 합니다 **Outlook 양식 영역** 항목 양식 영역 코드 파일에 다음 세 개의 이벤트 처리기를 자동으로 추가 합니다.

|이벤트(event)|설명|
|-----------|-----------------|
|FormRegionInitializing|양식 영역을 초기화하기 전에 발생합니다. 이 이벤트 처리기의 조건을 검사하여 Outlook에서 양식 영역을 표시할지 여부를 확인할 수 있습니다. 자세한 내용은 [방법: Outlook에서 양식 영역 표시 하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)합니다.|
|FormRegionShowing|양식 영역의 인스턴스가 만들어진 후 양식 영역이 표시되기 전에 발생합니다.|
|FormRegionClosed|양식 영역이 닫히기 전에 발생합니다.|

## <a name="Building"></a> 프로젝트 빌드
 양식 영역을 포함하는 Outlook VSTO 추가 기능 프로젝트를 빌드하면 Visual Studio에서 다음 정보를 레지스트리에 추가합니다.

- 하나 이상의 양식 영역과 연결된 각 메시지 클래스에 대한 키

- 각 양식 영역에 대한 항목 및 Outlook VSTO 추가 기능의 이름을 나타내는 관련된 값

  Outlook은 이 정보를 사용하여 양식 영역을 로드합니다.

## <a name="Debugging"></a> 양식 영역 디버그
 다른 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트의 디버그와 마찬가지로 양식 영역을 포함하는 Outlook VSTO 추가 기능을 디버그할 수 있습니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버거를 시작하면 Visual Studio에서 자동으로 Outlook을 시작합니다.

 양식 영역을 보려면 해당 Outlook 항목을 열어야 합니다. 예를 들어 메일 항목의 맨 아래에 인접 양식 영역이 추가되는 경우 메일 항목을 엽니다.

## <a name="Deploying"></a> 양식 영역을 배포
 양식 영역은 연결된 Outlook VSTO 추가 기능과 함께 자동으로 배포됩니다. 따라서 양식 영역을 배포하기 위해 특별한 작업을 수행할 필요가 없습니다. VSTO 추가 기능을 배포 하는 방법에 대 한 자세한 내용은 참조 하세요. [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)합니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[지침에 대 한 Outlook 양식 영역 만들기](../vsto/guidelines-for-creating-outlook-form-regions.md)|양식 영역을 최적화하고 잠재적인 문제를 방지하는 데 도움이 되는 정보를 제공합니다.|
|[방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)|사용 하 여 표준 또는 사용자 지정 Microsoft Office Outlook 양식을 확장 하는 양식 영역을 만드는 방법을 보여 줍니다 합니다 **새 Outlook 양식 영역** 마법사.|
|[Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.](../vsto/associating-a-form-region-with-an-outlook-message-class.md)|각 항목의 메시지 클래스에 양식 영역을 연결하여 양식 영역을 표시하는 Microsoft Office Outlook 항목을 지정하는 방법을 설명합니다.|
|[연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)|연락처 항목의 검사기 창에 새 페이지로 표시되는 사용자 지정 양식 영역을 디자인하는 방법을 보여 줍니다.|
|[연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)|Microsoft Office Outlook에서 양식 영역을 디자인 하 고 사용 하 여에서 Outlook VSTO 추가 기능 프로젝트로 양식 영역을 가져온 다음 하는 방법을 보여 줍니다 합니다 **새 Outlook 양식 영역** 마법사.|
|[런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)|양식 영역에서 컨트롤을 표시, 숨기기 또는 수정하는 코드를 작성하고 사용자가 `Globals` 클래스를 사용하여 프로젝트의 다른 영역에서 코드를 실행할 수 있도록 하는 방법을 설명합니다.|
|[방법: Outlook에서 양식 영역 표시 하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)|Microsoft Office Outlook에서 특정 항목에 대한 양식 영역을 표시하지 않도록 하는 방법을 보여 줍니다.|
|양식 영역이 표시되는 Outlook 항목에 액세스하는 방법을 보여 줍니다.|
|[Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)|사용자가 Outlook 항목에 응답할 수 있도록 하는 방법을 설명합니다.|
