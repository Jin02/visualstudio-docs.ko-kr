---
title: 리본 개체 모델 개요
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], object model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6ca22704345fefb4944bda7dd9f71942fe8dfb50
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256022"
---
# <a name="ribbon-object-model-overview"></a>리본 개체 모델 개요
  는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 런타임에 리본 컨트롤의 속성을 가져오고 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다. 예를 들어, 메뉴 컨트롤을 동적으로 채우거 나 컨텍스트 컨트롤을 표시 하 고 숨길 수 있습니다. 리본 메뉴에 탭, 그룹 및 컨트롤을 추가할 수도 있습니다. 단, Office 응용 프로그램에서 리본 메뉴를 로드 하기 전에만 가능 합니다. 자세한 내용은 읽기 전용으로 [설정 된 속성 설정](#SettingReadOnlyProperties)을 참조 하세요.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

 이 리본 개체 모델은 주로 [리본 클래스](#RibbonClass), [리본 이벤트](#RibbonEvents)및 [리본 컨트롤 클래스로](#RibbonControlClasses)구성 됩니다.

## <a name="RibbonClass"></a>리본 클래스
 프로젝트에 새 **리본 (비주얼 디자이너)** 항목을 추가 하면 visual Studio에서 **리본** 클래스를 프로젝트에 추가 합니다. **리본** 클래스는 <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> 클래스에서 상속 됩니다.

 이 클래스는 리본 코드 파일과 리본 디자이너 코드 파일 사이에서 분할 되는 partial 클래스로 나타납니다.

## <a name="RibbonEvents"></a>리본 이벤트
 **리본** 클래스는 다음과 같은 세 가지 이벤트를 포함 합니다.

|이벤트|설명|
|-----------|-----------------|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office 응용 프로그램에서 리본 사용자 지정을 로드할 때 발생 합니다. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> 이벤트 처리기는 리본 코드 파일에 자동으로 추가 됩니다. 리본이 로드 될 때이 이벤트 처리기를 사용 하 여 사용자 지정 코드를 실행 합니다.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|리본이 로드 될 때 리본 사용자 지정에서 이미지를 캐시할 수 있습니다. 이 이벤트 처리기에서 리본 이미지를 캐시 하는 코드를 작성 하는 경우 약간의 성능 향상을 얻을 수 있습니다. 자세한 내용은 <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>을 참조하세요.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|리본 인스턴스가 닫힐 때 발생 합니다.|

## <a name="RibbonControlClasses"></a>리본 컨트롤
 네임 스페이스에는 **도구 상자**의 **Office 리본 컨트롤** 그룹에 표시 되는 각 컨트롤에 대 한 형식이 포함 되어 있습니다. <xref:Microsoft.Office.Tools.Ribbon>

 다음 표에서는 각 `Ribbon` 컨트롤의 형식을 보여 줍니다. 각 컨트롤에 대 한 설명은 [리본 개요](../vsto/ribbon-overview.md)를 참조 하세요.

|컨트롤 이름|클래스 이름|
|------------------|----------------|
|**Object^**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**Button**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|
|**DropDown**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|
|**EditBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**갤러리**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**레이블**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|
|**메뉴**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**구분 기호**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|
|**SplitButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**Tab**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|

 네임 <xref:Microsoft.Office.Tools.Ribbon> 스페이스는 이러한 형식에 대해 "리본" 접두사를 사용 하 여 <xref:System.Windows.Forms> 네임 스페이스에 있는 컨트롤 클래스의 이름과 이름 충돌을 방지 합니다.

 리본 디자이너에 컨트롤을 추가 하면 리본 디자이너에서 해당 컨트롤에 대 한 클래스를 리본 디자이너 코드 파일의 필드로 선언 합니다.

### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>리본 컨트롤의 속성을 사용 하는 일반적인 작업
 각 `Ribbon` 컨트롤에는 컨트롤에 레이블을 할당 하거나 컨트롤을 숨기 거 나 표시 하는 등의 다양 한 작업을 수행 하는 데 사용할 수 있는 속성이 포함 되어 있습니다.

 경우에 따라 리본이 로드 된 후 또는 동적 메뉴에 컨트롤이 추가 된 후 속성이 읽기 전용이 됩니다. 자세한 내용은 읽기 전용으로 [설정 된 속성 설정](#SettingReadOnlyProperties)을 참조 하세요.

 다음 표에서는 컨트롤 속성을 사용 `Ribbon` 하 여 수행할 수 있는 몇 가지 작업에 대해 설명 합니다.

|작업|방법|
|--------------------|--------------|
|컨트롤을 숨기 거 나 표시 합니다.|Visible 속성을 사용 합니다.|
|컨트롤을 사용 하거나 사용 하지 않도록 설정 합니다.|Enabled 속성을 사용 합니다.|
|컨트롤의 크기를 설정 합니다.|ControlSize 속성을 사용 합니다.|
|컨트롤에 표시 되는 이미지를 가져옵니다.|Image 속성을 사용 합니다.|
|컨트롤의 레이블을 변경 합니다.|레이블 속성을 사용 합니다.|
|사용자 정의 데이터를 컨트롤에 추가 합니다.|Tag 속성을 사용 합니다.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox> ,<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>, 또는의 항목을 가져옵니다. <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>조절.|Items 속성을 사용 합니다.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox> ,<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>또는 컨트롤<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 에 항목을 추가 합니다.|Items 속성을 사용 합니다.|
|에 컨트롤을 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>추가 합니다.|Items 속성을 사용 합니다.<br /><br /> 리본이 office 응용 프로그램 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 에 로드 된 후에 컨트롤을에 추가 하려면 리본이 office 응용 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 프로그램에 로드 되기 전에 속성을 **true** 로 설정 해야 합니다. 자세한 내용은 읽기 전용으로 [설정 된 속성 설정](#SettingReadOnlyProperties)을 참조 하세요.|
|의 선택 된 항목 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>을 가져옵니다.<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>입니다.|SelectedItem 속성을 사용 합니다. 의 경우 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> 속성을 사용 합니다. <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|
|에서 그룹을 가져옵니다 <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>.|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> 속성을 사용합니다.|
|에 표시 되는 행과 열의 수를 지정 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>합니다.|사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 고 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 속성입니다.|

## <a name="SettingReadOnlyProperties"></a>읽기 전용으로 설정 되는 속성 설정
 일부 속성은 리본이 로드 되기 전에만 설정할 수 있습니다. 이러한 속성을 설정 하는 데는 세 가지 위치가 있습니다.

- Visual Studio **속성** 창에서

- **리본** 클래스의 생성자에서.

- 프로젝트의 `ThisAddin`, 또는`ThisWorkbook` `CreateRibbonExtensibilityObject` 클래스`ThisDocument` 에 대 한 메서드입니다.

  동적 메뉴는 몇 가지 예외를 제공 합니다. 메뉴를 포함 하는 리본이 로드 된 후에도 새 컨트롤을 만들고, 해당 속성을 설정 하 고, 런타임에 동적 메뉴에 추가할 수 있습니다.

  동적 메뉴에 추가 하는 컨트롤의 속성은 언제 든 지 설정할 수 있습니다.

  자세한 내용은 [읽기 전용으로 되는 속성](#ReadOnlyProperties)을 참조 하세요.

### <a name="set-properties-in-the-constructor-of-the-ribbon"></a>리본의 생성자에서 속성 설정
 `Ribbon` **리본** 클래스의 생성자에서 컨트롤의 속성을 설정할 수 있습니다. 이 코드는 `InitializeComponent` 메서드를 호출한 후에 나타나야 합니다. 다음 예에서는 현재 시간이 17:00 태평양 표준시 (UTC-8) 이상인 경우 그룹에 새 단추를 추가 합니다.

 다음 코드를 추가 합니다.

 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]

 Visual Studio C# 2008에서 업그레이드 한 visual 프로젝트에서 생성자는 리본 코드 파일에 나타납니다.

 C# 에서[!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]만든 Visual 프로젝트 또는 Visual Basic 프로젝트에서 생성자는 리본 디자이너 코드 파일에 나타납니다. 이 파일의 이름은 해당 하는 *리본 항목*입니다. Designer.cs 또는 해당 하는 *리본 항목*입니다. 디자이너 .vb. Visual Basic 프로젝트에서이 파일을 보려면 먼저 솔루션 탐색기의 **모든 파일 표시** 단추를 클릭 해야 합니다.

### <a name="set-properties-in-the-createribbonextensibilityobject-method"></a>CreateRibbonExtensibilityObject 메서드의 속성 설정
 `Ribbon` 프로젝트의 `ThisAddin` `CreateRibbonExtensibilityObject` , 또는`ThisWorkbook`클래스에서 메서드를 재정의할 때 컨트롤의 속성을 설정할 수 있습니다. `ThisDocument` `CreateRibbonExtensibilityObject` 메서드에 대 한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)를 참조 하세요.

 다음 예제에서는 Excel 통합 문서 프로젝트 `CreateRibbonExtensibilityObject` `ThisWorkbook` 클래스의 메서드에서 리본 속성을 설정 합니다.

 다음 코드를 추가 합니다.

 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]

### <a name="ReadOnlyProperties"></a>읽기 전용으로 되는 속성
 다음 표에서는 리본을 로드 하기 전에만 설정할 수 있는 속성을 보여 줍니다.

> [!NOTE]
> 언제 든 지 동적 메뉴에서 컨트롤의 속성을 설정할 수 있습니다. 이 경우에는이 테이블이 적용 되지 않습니다.

|속성|Ribbon 컨트롤 클래스|
|--------------|--------------------------|
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**ColumnCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ControlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**Dynamic**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**Global**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**그룹과**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**ImageName**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**MaxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**이름**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|
|**위치**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**RowCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**탭**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**제목**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|

### <a name="set-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Outlook 검사기에 표시 되는 리본에 대 한 속성 설정
 리본 메뉴가 표시 되는 검사기를 사용자가 열 때마다 리본의 새 인스턴스가 만들어집니다. 그러나 리본 메뉴의 첫 번째 인스턴스가 만들어지기 전에만 위의 표에 나열 된 속성을 설정할 수 있습니다. 첫 번째 인스턴스가 만들어진 후에는 첫 번째 인스턴스가 Outlook에서 리본을 로드 하는 데 사용 하는 XML 파일을 정의 하기 때문에 이러한 속성은 읽기 전용이 됩니다.

 다른 리본 인스턴스가 만들어질 때 이러한 속성을 다른 값으로 설정 하는 조건부 논리가 있는 경우이 코드는 아무런 영향을 주지 않습니다.

> [!NOTE]
> Outlook 리본에 추가 하는 각 컨트롤에 대해 **Name** 속성이 설정 되어 있는지 확인 합니다. 런타임에 Outlook 리본에 컨트롤을 추가 하는 경우 코드에서이 속성을 설정 해야 합니다. 디자인 타임에 Outlook 리본에 컨트롤을 추가 하는 경우 이름 속성이 자동으로 설정 됩니다.

## <a name="ribbon-control-events"></a>리본 컨트롤 이벤트
 각 컨트롤 클래스에는 하나 이상의 이벤트가 포함 되어 있습니다. 다음 표에서는 이러한 이벤트에 대해 설명 합니다.

|이벤트|설명|
|-----------|-----------------|
|클릭 대상|컨트롤을 클릭 하면 발생 합니다.|
|TextChanged|편집 상자 또는 콤보 상자의 텍스트가 변경 될 때 발생 합니다.|
|ItemsLoading|Office에서 컨트롤의 항목 컬렉션을 요청할 때 발생 합니다. Office는 코드에서 컨트롤의 속성을 변경 하거나 메서드를 <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> 호출할 때까지 Items 컬렉션을 캐시 합니다.|
|System.windows.forms.toolbar.buttonclick>|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 또는<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 의 단추를 클릭할 때 발생 합니다.|
|SelectionChanged|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 의<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 선택 영역이 변경 되 면 발생 합니다.|
|DialogLauncherClick|그룹의 오른쪽 아래 모퉁이에 있는 대화 상자 시작 관리자 아이콘을 클릭 하면 발생 합니다.|

 이러한 이벤트에 대 한 이벤트 처리기에는 다음과 같은 두 개의 매개 변수가 있습니다.

|매개 변수|설명|
|---------------|-----------------|
|*sender*|<xref:System.Object> 이벤트를 발생 시킨 컨트롤을 나타내는입니다.|
|*e*|<xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs>이 들어 있는 <xref:Microsoft.Office.Core.IRibbonControl>입니다. 이 컨트롤을 사용 하 여에서 제공 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]하는 리본 개체 모델에서 사용할 수 없는 속성에 액세스할 수 있습니다.|

## <a name="see-also"></a>참고 항목
- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
- [리본 개요](../vsto/ribbon-overview.md)
- [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [연습: 런타임에 리본 메뉴의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)
- [Outlook에 대 한 리본 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)
- [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)
- [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [방법: 추가 기능 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)
