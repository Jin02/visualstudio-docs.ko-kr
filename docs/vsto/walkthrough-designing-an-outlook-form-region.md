---
title: '연습: Outlook 양식 영역 디자인'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3e306f07f3c528c27c60e9b55675ff945413bf45
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440860"
---
# <a name="walkthrough-design-an-outlook-form-region"></a>연습: Outlook 양식 영역 디자인
  사용자 지정 양식 영역은 표준 또는 사용자 지정 Microsoft Office Outlook 양식을 확장합니다. 이 연습에서는 연락처 항목의 검사기 창에 새 페이지로 표시되는 사용자 지정 양식 영역을 디자인합니다. 이 양식 영역은 Windows Live 로컬 검색 웹 사이트에 주소 정보를 전송하여 연락처에 대해 나열된 각 주소의 지도를 표시합니다. 양식 영역에 대 한 자세한 내용은 [만들 Outlook 양식 영역](../vsto/creating-outlook-form-regions.md)합니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

 이 연습에서는 다음 작업을 수행합니다.

- 새 Outlook VSTO 추가 기능 프로젝트 만들기

- VSTO 추가 기능 프로젝트에 양식 영역 추가

- 양식 영역의 레이아웃 디자인

- 양식 영역의 동작 사용자 지정

- Outlook 양식 영역 테스트

> [!NOTE]
> 일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## <a name="prerequisites"></a>전제 조건
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)] 이상 버전

  ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 이 항목의 비디오 버전을 참조 하세요. [비디오 방법: Outlook 양식 영역 디자인](http://go.microsoft.com/fwlink/?LinkID=140824)합니다.

## <a name="create-a-new-outlook-vsto-add-in-project"></a>새 Outlook VSTO 추가 기능에서 프로젝트 만들기
 먼저 기본 VSTO 추가 기능 프로젝트를 만듭니다.

### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>새 Outlook VSTO 추가 기능 프로젝트를 만들려면

1. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 이름에서 Outlook VSTO 추가 기능 프로젝트를 만듭니다 **MapItAddIn**합니다.

2. **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기**를 선택합니다.

3. 임의 디렉터리에 프로젝트를 저장합니다.

     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.

## <a name="add-a-form-region-to-the-outlook-vsto-add-in-project"></a>Outlook VSTO 추가 기능 프로젝트에 양식 영역 추가
 Outlook VSTO 추가 기능 솔루션에는 하나 이상의 Outlook 양식 영역 항목이 포함될 수 있습니다. 사용 하 여 프로젝트에 양식 영역 항목을 추가 합니다 **새 Outlook 양식 영역** 마법사.

### <a name="to-add-a-form-region-to-the-outlook-vsto-add-in-project"></a>Outlook VSTO 추가 기능 프로젝트에 양식 영역을 추가하려면

1. **솔루션 탐색기**를 선택 합니다 **MapItAddIn** 프로젝트입니다.

2. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

3. 에 **새 항목 추가** 대화 상자에서 **Outlook 양식 영역**, 파일 이름을 **mapit 지정한**를 클릭 하 고 **추가**합니다.

     합니다 **NewOutlook 양식 영역** 마법사가 시작 됩니다.

4. 에 **양식 영역을 만드는 방법 선택** 페이지에서 **새 양식 영역을 디자인**를 클릭 하 고 **다음**합니다.

5. 에 **만들려는 양식 영역의 유형을 선택** 페이지에서 클릭 **별도**를 클릭 하 고 **다음**합니다.

     A *별도* 양식 영역이 Outlook 양식에 새 페이지를 추가 합니다. 양식 영역 형식에 대 한 자세한 내용은 참조 하세요. [만들 Outlook 양식 영역](../vsto/creating-outlook-form-regions.md)합니다.

6. 에 **설명 텍스트를 입력 하 고 디스플레이 기본 설정을 선택** 페이지에서 입력 **Map It** 에 **이름** 상자입니다.

     이 이름은 연락처 항목이 열려 있을 때 검사기 창의 리본 메뉴에 나타납니다.

7. 선택 **작성 모드의 검사기** 하 고 **읽기 모드의 검사기**를 클릭 하 고 **다음**합니다.

8. 에 **이 양식 영역을 표시할 메시지 클래스를 식별** 페이지 지우기 **메일 메시지**를 선택 **연락처**를 클릭 하 고 **마침**.

     A *MapIt.cs* 하거나 *MapIt.vb* 파일이 프로젝트에 추가 됩니다.

## <a name="design-the-layout-of-the-form-region"></a>양식 영역의 레이아웃 디자인
 양식 영역을 사용 하 여 시각적으로 개발 된 *양식 영역 디자이너*합니다. 관리되는 컨트롤을 양식 영역 디자이너 화면으로 끌 수 있습니다. 디자이너를 사용 하며 **속성** 창 컨트롤 레이아웃 및 모양을 조정 합니다.

### <a name="to-design-the-layout-of-the-form-region"></a>양식 영역의 레이아웃을 디자인하려면

1. **솔루션 탐색기**를 확장 합니다 **MapItAddIn** 프로젝트를 차례로 클릭 한 다음 *MapIt.cs* 또는 *MapIt.vb* 양식 영역을 엽니다 디자이너입니다.

2. 디자이너를 마우스 오른쪽 단추로 누른 **속성**합니다.

3. 에 **속성** 창에서 **크기** 하 **664, 469**합니다.

     이렇게 하면 양식 영역이 지도를 표시할 수 있을 만큼 커집니다.

4. **보기** 메뉴에서 **도구 상자**를 클릭합니다.

5. **공용 컨트롤** 탭의 **도구 상자**, 추가 **WebBrowser** 을 양식 영역.

     합니다 **WebBrowser** 연락처에 나열 된 각 주소의 지도가 표시 됩니다.

## <a name="customize-the-behavior-of-the-form-region"></a>양식 영역의 동작을 사용자 지정
 양식 영역 이벤트 처리기에 코드를 추가하여 런타임에 양식 영역이 동작하는 방식을 사용자 지정합니다. 이 양식 영역에 대해 코드에서 Outlook 항목의 속성을 검사하고 Map It 양식 영역을 표시할지 여부를 확인합니다. 양식 영역을 표시하는 경우 코드에서 Windows Live 로컬 검색으로 이동하고 Outlook 연락처 항목에 나열된 각 주소의 지도를 로드합니다.

### <a name="to-customize-the-behavior-of-the-form-region"></a>양식 영역의 동작을 사용자 지정하려면

1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 *MapIt.cs* 또는 *MapIt.vb*를 클릭 하 고 **코드 보기**합니다.

    *MapIt.cs* 나 *MapIt.vb* 코드 편집기에서 열립니다.

2. 확장 된 **양식 영역 팩터리** 코드 영역.

    `MapItFactory`라는 양식 영역 팩터리 클래스가 노출됩니다.

3. 다음 코드를 `MapItFactory_FormRegionInitializing` 이벤트 처리기에 추가합니다. 이 이벤트 처리기는 사용자가 연락처 항목을 열 때 호출됩니다. 다음 코드는 연락처 항목에 주소가 포함되어 있는지 여부를 확인합니다. 이 코드를 설정 하는 연락처 항목에 주소를 찾을 수 없는 경우는 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 의 속성을 <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> 클래스를 **true** 양식 영역이 표시 되지 않습니다. 그렇지 않은 경우 VSTO 추가 기능에서 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 이벤트가 발생하고 양식 영역이 표시됩니다.

    [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
    [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]

4. 다음 코드를 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 이벤트 처리기에 추가합니다. 이 코드는 다음 작업을 수행합니다.

   - 연락처 항목의 각 주소를 연결하고 URL 문자열을 만듭니다.

   - <xref:System.Windows.Forms.WebBrowser> 개체의 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드를 호출하고 URL 문자열을 매개 변수로 전달합니다.

     로컬 검색 웹 사이트가 Map It 양식 영역에 나타나고 각 주소를 스크래치 패드에 표시합니다.

     [!code-csharp[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#2)]
     [!code-vb[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#2)]

## <a name="test-the-outlook-form-region"></a>Outlook 양식 영역 테스트
 프로젝트를 실행하면 Visual Studio에서 Outlook을 엽니다. 연락처 항목을 열어 Map It 양식 영역을 표시합니다. Map It 양식 영역은 주소가 포함된 연락처 항목의 양식에 페이지로 표시됩니다.

### <a name="to-test-the-map-it-form-region"></a>Map It 양식 영역을 테스트하려면

1. **F5** 키를 눌러 프로젝트를 실행합니다.

     Outlook이 열립니다.

2. Outlook에서에 **홈** 탭을 클릭 **새 항목**를 클릭 하 고 **연락처**합니다.

3. 연락처 양식 입력 **Ann Beebe** 연락처로 이름을 지정 하 고 다음 세 개의 주소를 지정 합니다.

    |주소 형식|주소|
    |------------------|-------------|
    |**비즈니스**|**4567 Main St. Buffalo, NY**|
    |**Home**|**1234 North St. Buffalo, NY**|
    |**기타**|**3456 Main St. 시애틀, 워싱턴**|

4. 연락처 항목을 저장하고 닫습니다.

5. 다시 합니다 **Ann Beebe** 연락처 항목입니다.

    Outlook에서 수행할 수 있습니다 합니다 **찾을** 주소록 연락처에 대 한 열 또는 Ann Beebe에를 입력 하 여 그룹 **사람 검색**합니다.

6. 에 **표시** 항목의 리본 메뉴의 그룹 클릭 **Map It** Map It 양식 영역을 엽니다.

     Map It 양식 영역이 나타나고 로컬 검색 웹 사이트를 표시합니다. 합니다 **비즈니스**를 **홈**, 및 **다른** 주소가 스크래치 패드에 나타납니다. 스크래치 패드에서 매핑할 주소를 선택합니다.

## <a name="next-steps"></a>다음 단계
 다음 항목에서 Outlook 애플리케이션의 UI를 사용자 지정하는 방법에 대해 자세히 알아볼 수 있습니다.

- Outlook 항목의 리본을 사용자 지정 하는 방법에 알아보려면 [Outlook에 대 한 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)합니다.

## <a name="see-also"></a>참고자료
- [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)
- [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)
- [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)
- [연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)
- [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)
- [Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.](../vsto/associating-a-form-region-with-an-outlook-message-class.md)
- [Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)
- [방법: Outlook에서 양식 영역 표시 하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)
