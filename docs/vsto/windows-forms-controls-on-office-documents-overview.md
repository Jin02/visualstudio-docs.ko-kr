---
title: Windows Forms 컨트롤에 대 한 Office 문서 개요
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- old data showing in error [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], Word
- Windows Forms controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], arranging
- data [Office development in Visual Studio], old data showing in error
- user controls [Office development in Visual Studio], Windows Forms
- Windows Forms controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], removing
- application development [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Windows Forms controls
- Office [Office development in Visual Studio], Windows Forms controls
- Office documents [Office development in Visual Studio, controls
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], about Windows Forms controls
- Office applications [Office development in Visual Studio], Windows Forms
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 927451ed35ce4bbdfbff7531b2828b0571354f34
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445360"
---
# <a name="windows-forms-controls-on-office-documents-overview"></a>Windows Forms 컨트롤에 대 한 Office 문서 개요
  Windows Forms 컨트롤은 사용자가 데이터를 입력하거나 조작하는 데 사용할 수 있는 개체입니다. Microsoft Office Excel 및 Microsoft Office Word 용 문서 수준 프로젝트에서는 디자인 타임에 프로젝트에서 Windows Forms 컨트롤을 문서 또는 통합 문서를 추가할 수 또는 런타임 시 이러한 컨트롤을 프로그래밍 방식으로 추가할 수 있습니다. Excel 또는 Word에 대 한 열려 있는 문서 또는 VSTO 추가 기능에서 런타임에 워크시트에 이러한 컨트롤을 프로그래밍 방식으로 추가할 수 있습니다.

 자세한 내용은 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)합니다.

 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="use-windows-forms-controls"></a>Windows Forms 컨트롤 사용

작업 창, 사용자 지정 작업창 및 Windows Forms 등의 사용자 지정 가능한 UI(사용자 인터페이스) 요소 및 문서에 Windows Forms 컨트롤을 추가할 수 있습니다. Windows Forms 컨트롤은 문서에서 일반적으로 다른 UI 요소와 동일한 동작을 수행하지만 몇 가지 차이점이 있습니다. 정보를 참조 하세요 [Office 문서의 Windows Forms의 제한 사항 제어](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)입니다.

Windows Forms 컨트롤을 문서에 추가할지 또는 기타 다른 UI 요소에 추가할지에 대한 결정은 여러 가지 요인에 따라 달라집니다. 솔루션의 UI를 디자인할 때는 다음 표에 설명된 Windows Forms 컨트롤의 용도를 고려해야 합니다.

문서에서
- 항상 컨트롤을 표시하려는 경우

- 사용자가 문서(예: 편집 화면이 잠긴 폼 기반 문서)에 직접 데이터를 입력하도록 하려는 경우

- 컨트롤을 문서의 데이터에 맞춰 표시하려는 경우. 예를 들어 목록 개체의 각 행에 단추를 추가하는 경우 각 목록 항목에 맞추려고 할 수 있습니다.

작업 창 또는 사용자 지정 작업창에서
- 사용자에게 상황에 맞는 정보를 제공하려는 경우

- 문서에 쿼리 컨트롤 및 데이터를 제외한 결과만 표시하려는 경우

- 컨트롤이 문서와 함께 인쇄되지 않도록 설정하려는 경우

- 문서를 볼 때 컨트롤이 방해되지 않도록 설정하려는 경우

Windows Form에서
- UI의 크기를 제어하려는 경우

- 사용자가 컨트롤을 숨기거나 삭제하지 못하게 하려는 경우

- 사용자의 입력을 허용하고 입력이 수신될 때까지 문서에서 작업을 수행할 수 없게 하려는 경우

## <a name="add-windows-forms-controls-programmatically"></a>Windows Forms 컨트롤을 프로그래밍 방식으로 추가
 Word 문서 및 런타임 시 Excel 워크시트에 Windows Forms 컨트롤을 추가할 수 있습니다. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 은 가장 일반적인 Windows Forms 컨트롤을 추가하는 데 필요한 도우미 메서드를 제공합니다. 이러한 도우미 메서드를 사용하면 Office 문서에 신속하게 컨트롤을 추가하고 결합된 Windows Forms 컨트롤 기능과 이러한 컨트롤의 Office 관련 기능에 액세스할 수 있습니다.

 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.

## <a name="use-windows-forms-controls-in-document-level-projects"></a>문서 수준 프로젝트에서 Windows Forms 컨트롤 사용
 문서에서의 Windows Forms 컨트롤 사용은 문서 수준 프로젝트마다 고유하므로 Visual Studio 디자이너를 사용하여 문서의 UI를 디자인할 수 있습니다.

### <a name="create-custom-user-controls"></a>사용자 지정 사용자 컨트롤 만들기
 프로젝트에 사용자 정의 컨트롤을 추가한 다음 **도구 상자**에 추가합니다. 그런 다음 Windows Forms 컨트롤을 문서에 추가할 때와 같은 방법으로 문서에 사용자 정의 컨트롤을 직접 끌어 놓을 수 있습니다. 다음은 사용자 정의 컨트롤을 만들 때 기억해야 할 몇 가지 사항들입니다.

- **sealed** 사용자 정의 컨트롤을 만들지 마세요. 컨트롤을 문서로 끌어 오는 경우 Visual Studio에서는 사용자 정의 컨트롤에서 파생된 래퍼 클래스를 생성하여 확장하고 해당 문서에서 사용할 수 있도록 지원합니다. 사용자 정의 컨트롤이 **sealed**인 경우 Visual Studio에서 래퍼 클래스를 생성할 수 없습니다.

- 사용자 정의 컨트롤에는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정된 **T:System.Runtime.InteropServices.ComVisibleAttribute**을 참조하세요. Office 프로젝트 내에서 만들어진 사용자 정의 컨트롤에서는 이 특성이 기본적으로 **true** 로 설정되지만 외부 프로젝트의 일부인 사용자 정의 컨트롤에서는 이 특성이 **true**로 설정되지 않을 수 있습니다.

- 문서에 사용자 정의 컨트롤을 추가한 다음에는 프로젝트에서 <xref:System.Windows.Forms.UserControl> 클래스의 이름을 변경하거나 삭제하지 마세요. 사용자 정의 컨트롤의 이름을 변경해야 하는 경우에는 먼저 문서에서 삭제하고 이름을 변경한 다음 다시 추가합니다.

### <a name="arrange-controls-at-design-time"></a>디자인 타임에 컨트롤을 정렬 합니다.
 디자인 타임에 여러 컨트롤을 Word 및 Excel 문서에 추가하는 경우 Visual Studio의 **Microsoft Office Word** 및 **Microsoft Office Excel** 도구 모음을 사용하여 선택된 모든 컨트롤의 맞춤을 신속하게 설정할 수 있습니다. 이러한 도구 모음은 문서 또는 워크시트가 디자이너에 열려 있는 경우에만 사용할 수 있습니다.

 디자이너에서 여러 컨트롤을 선택할 때는 이러한 도구 모음에서 다음 단추를 사용하여 컨트롤을 정렬할 수 있습니다.

- **왼쪽 맞춤**

- **가운데 맞춤**

- **오른쪽 맞춤**

- **위쪽 맞춤**

- **중간 맞춤**

- **아래쪽 맞춤**

- **가로 간격 같게**

- **세로 간격 같게**

> [!NOTE]
> Word 프로젝트에서 이러한 단추는 선택된 컨트롤이 텍스트에 맞춰지지 않은 경우에만 활성화됩니다. 기본적으로 디자인 타임에 문서에 추가된 컨트롤은 텍스트와 맞춰집니다.

### <a name="prevent-old-data-from-appearing-in-excel-workbooks-during-loading"></a>이전 데이터를 로드 하는 동안 Excel 통합 문서에 표시 하지 않도록 방지
 디자인 타임에 Windows Forms 컨트롤을 문서 또는 워크시트에 추가하면 사용자가 문서를 닫아도 컨트롤이 문서에 유지됩니다. 디자인 타임에 추가된 컨트롤을 *정적 컨트롤*이라고 합니다.

 정적 컨트롤이 포함된 Excel 통합 문서를 열면 사용자 지정 코드가 실행되고 실제 컨트롤이 로드될 때까지 통합 문서의 ActiveX 컨트롤에 컨트롤의 비트맵이 표시됩니다. 통합 문서를 저장할 때마다 Excel에서 이 비트맵을 만들고 통합 문서에 저장합니다. 비트맵은 컨트롤이 표시 중인 데이터를 포함하여 통합 문서가 마지막으로 저장될 때의 모양으로 컨트롤을 표시합니다. Windows Forms 컨트롤 및 비트맵을 포함 하는 ActiveX 컨트롤에 대 한 자세한 내용은 참조 하세요. [Office 문서의 Windows Forms의 제한 사항 제어](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)입니다.

 사용자가 디자인 모드로 통합 문서를 여는 등 특정 조건에서는 코드가 로드되지 않으며 비트맵만 표시됩니다. 또한 사용자가 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 이 설치되지 않은 컴퓨터에서 통합 문서를 열면 사용자 지정을 실행할 수 없어 컨트롤이 로드되지 않으므로 컨트롤의 비트맵만 표시됩니다. 통합 문서를 저장하여 다른 사용자에게 보내기 전에는 항상 통합 문서의 컨트롤에서 개인 정보를 제거하여 개인 정보가 실수로 공개되는 일을 방지해야 합니다.

### <a name="match-control-size-to-cell-size-on-an-excel-worksheet"></a>Excel 워크시트에서 셀 크기를 일치 컨트롤 크기
 부모 셀의 크기가 변경될 때 자동으로 컨트롤의 크기가 조정되도록 설정할 수 있습니다. 자세한 내용은 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)합니다.

### <a name="add-components-that-are-shared-by-all-worksheets"></a>모든 워크시트에서 공유 되는 구성 요소를 추가 합니다.
 <xref:System.Data.DataSet>등 모든 워크시트에서 공유하려는 구성 요소는 워크시트 대신 통합 문서 디자이너에 추가할 수 있습니다. 이러한 구성 요소는 구성 요소 트레이에 표시됩니다.

### <a name="formula-for-embedding-controls-on-an-excel-worksheet"></a>Excel 워크시트에서 컨트롤 포함 수식
 Excel에서 컨트롤을 선택하는 경우 **수식 입력줄** 에 **=EMBED("WinForms.Control.Host","")** 가 표시됩니다. 이 텍스트는 필요하며 삭제하면 안 됩니다.

### <a name="layout-style-of-controls-on-a-word-document"></a>Word 문서에서 컨트롤의 레이아웃 스타일
 Visual Studio 디자이너를 사용하여 문서 수준 프로젝트에서 Word 문서에 컨트롤을 추가하면 컨트롤이 텍스트에 맞춰 추가됩니다. 컨트롤의 레이아웃 스타일을 변경하려면 컨트롤을 마우스 오른쪽 단추로 클릭하고 **컨트롤 서식**을 클릭합니다. **개체 서식** 대화 상자의 **레이아웃** 페이지에서 배치 스타일을 선택합니다.

 런타임 시 Word 문서에 컨트롤을 추가 하면 다른을 사용 하 여 새 컨트롤의 레이아웃 스타일을 지정할 수 있습니다 `Add` \< *컨트롤 클래스*> 메서드 오버 로드는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 클래스:

- 컨트롤을 텍스트에 맞춰 추가하려면 컨트롤의 위치가 지정된 <xref:Microsoft.Office.Interop.Word.Range> 를 사용하는 오버로드를 사용합니다.

- 컨트롤을 부동 셰이프로 추가하려면 컨트롤의 왼쪽 및 위쪽 좌표를 사용하는 오버로드를 사용합니다.

  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.

  Visual Studio 디자이너에서 Word 서식 파일을 여는 경우 **기본** 보기에서 열리므로 인라인이 아닌 컨트롤은 이 서식 파일에 표시되지 않을 수 있습니다. 컨트롤을 표시하려면 보기를 **인쇄 레이아웃**으로 변경합니다.

### <a name="controls-outside-the-main-document-body"></a>주 문서 본문 외부 컨트롤
 Windows Forms 컨트롤은 머리글 또는 바닥글 내부 또는 하위 문서 내에서 지원되지 않습니다.

### <a name="add-components-at-design-time"></a>디자인 타임 구성 요소를 추가 합니다.
 특정 컨트롤 또는 구성 요소는 문서에 표시되지 않고 구성 요소 트레이에 표시됩니다. Visual Studio는 각 문서 창에 대한 구성 요소 트레이를 제공합니다. 구성 요소 트레이는 해당 문서에 구성 요소가 있는 경우에만 화면에 나타납니다.

## <a name="see-also"></a>참고자료
- [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)
- [작업 창 개요](../vsto/actions-pane-overview.md)
- [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index)
- [Office 문서의 Windows Forms 컨트롤의 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)
- [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)
- [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)
- [방법: 인쇄할 때 워크시트에서 컨트롤 숨기기](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)
- [연습: CheckBox 컨트롤을 사용 하 여 워크시트 서식 변경](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)
- [연습: CheckBox 컨트롤을 사용 하 여 문서 서식 변경](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)
- [연습: 단추를 사용 하 여 워크시트에 텍스트 상자에 텍스트를 표시 합니다.](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)
- [연습: 단추를 사용 하 여 문서에서 텍스트 상자에 텍스트를 표시 합니다.](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md)
- [Office 문서의 Windows Forms 컨트롤의 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)
- [연습: 라디오 단추를 사용 하 여 문서에서 차트를 업데이트 합니다.](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md)
- [연습: 라디오 단추를 사용 하 여 워크시트에 차트를 업데이트 합니다.](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)
