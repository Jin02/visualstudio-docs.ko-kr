---
title: '방법: 콘텐츠 컨트롤을 사용 하 여 문서 부분 보호'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- partial document protection [Office development in Visual Studio]
- content controls [Office development in Visual Studio], protecting documents
- Word [Office development in Visual Studio], partial document protection
- document protection [Office development in Visual Studio]
- Word [Office development in Visual Studio], restricted permissions
- GroupContentControl
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 25b30db78706dce95188289187ce55011ce1362d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441735"
---
# <a name="how-to-protect-parts-of-documents-by-using-content-controls"></a>방법: 콘텐츠 컨트롤을 사용 하 여 문서 부분 보호
  문서의 일부를 보호하는 경우 사용자가 문서의 해당 부분에서 내용을 변경하거나 삭제할 수 없습니다. 콘텐츠 컨트롤을 사용하여 Microsoft Office Word 문서 부분을 보호할 수 있는 여러 가지 방법이 있습니다.

- 콘텐츠 컨트롤을 보호할 수 있습니다.

- 콘텐츠 컨트롤에 없는 문서 부분을 보호할 수 있습니다.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="EditDeleteControl"></a> 콘텐츠 컨트롤을 보호
 사용자가 편집 하거나 콘텐츠 컨트롤을 디자인 타임 또는 런타임에 문서 수준 프로젝트에서 컨트롤의 속성을 설정 하 여 삭제를 방지할 수 있습니다.

 VSTO 추가 기능 프로젝트를 사용하여 런타임에 문서에 추가하는 콘텐츠 컨트롤을 보호할 수도 있습니다. 자세한 내용은 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)합니다.

### <a name="to-protect-a-content-control-at-design-time"></a>디자인 타임에 콘텐츠 컨트롤을 보호하려면

1. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 보호하려는 콘텐츠 컨트롤을 선택합니다.

2. 에 **속성** 창에서 다음 속성 중 하나 또는 모두를 설정 합니다.

    - 사용자가 컨트롤을 편집 하지 못하도록 설정 **LockContents** 하 **True**합니다.

    - 사용자가 컨트롤을 삭제 하지 못하도록 설정 **LockContentControl** 하 **True**합니다.

3. **확인**을 클릭합니다.

### <a name="to-protect-a-content-control-at-runtime"></a>런타임에 콘텐츠 컨트롤을 보호 하려면

1. 설정 합니다 `LockContents` 콘텐츠 컨트롤의 속성 **true** 사용자가 컨트롤을 편집 하지 못하도록 설정 하는 `LockContentControl` 속성을 **true** 사용자가 컨트롤을 삭제 하지 못하도록 합니다.

     다음 코드 예제에서는 문서 수준 프로젝트에서 두 가지 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 개체의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> 및 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> 속성을 사용하는 방법을 보여 줍니다. 이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `AddProtectedContentControls` 이벤트 처리기에서 `ThisDocument_Startup` 메서드를 호출합니다.

     [!code-csharp[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#2)]

     다음 코드 예제에서는 VSTO 추가 기능 프로젝트에서 두 가지 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 개체의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> 및 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> 속성을 사용하는 방법을 보여 줍니다. 이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `AddProtectedContentControls` 이벤트 처리기에서 `ThisAddIn_Startup` 메서드를 호출합니다.

     [!code-vb[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#14)]
     [!code-csharp[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#14)]

## <a name="protect-a-part-of-a-document-that-is-not-in-a-content-control"></a>콘텐츠 컨트롤에 없는 문서 부분 보호
 <xref:Microsoft.Office.Tools.Word.GroupContentControl>에 영역을 배치하여 사용자가 문서 영역을 변경하는 것을 방지할 수 있습니다. 이는 다음과 같은 시나리오에서 유용합니다.

- 콘텐츠 컨트롤을 포함하지 않는 영역을 보호하려고 합니다.

- 이미 콘텐츠 컨트롤을 포함하는 영역을 보호하려고 하지만 텍스트 또는 보호하려는 기타 항목이 콘텐츠 컨트롤에 없습니다.

> [!NOTE]
> 포함된 콘텐츠 컨트롤을 포함하는 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 만드는 경우 포함된 콘텐츠 컨트롤은 자동으로 보호되지 않습니다. 사용자가 포함 된 콘텐츠 컨트롤을 편집 하지 못하도록 하려면 사용 합니다 **LockContents** 컨트롤의 속성입니다.

### <a name="to-protect-an-area-of-a-document-at-design-time"></a>디자인 타임에 문서 영역을 보호하려면

1. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 보호하려는 영역을 선택합니다.

2. 리본에서 **개발자** 탭을 클릭합니다.

    > [!NOTE]
    > **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)합니다.

3. 에 **컨트롤** 그룹에서 클릭 합니다 **그룹** 드롭다운 단추를 클릭 한 다음 **그룹**합니다.

     보호된 영역을 포함하는 <xref:Microsoft.Office.Tools.Word.GroupContentControl>이 프로젝트의 `ThisDocument` 클래스에 자동으로 생성됩니다. 그룹 컨트롤을 나타내는 테두리는 디자인 타임에 표시 됩니다. 하지만 있습니다 런타임에 테두리가 표시 되지 않습니다.

### <a name="to-protect-an-area-of-a-document-at-runtime"></a>런타임에 문서 영역을 보호 하기 위해

1. 보호하려는 영역을 프로그래밍 방식으로 선택하고 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> 메서드를 호출하여 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 만듭니다.

     문서 수준 프로젝트에 대한 다음 코드 예제에서는 문서의 첫 단락에 텍스트를 추가하고, 첫 단락을 선택한 다음 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 인스턴스화합니다. 이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ProtectFirstParagraph` 이벤트 처리기에서 `ThisDocument_Startup` 메서드를 호출합니다.

     [!code-csharp[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#1)]

     VSTO 추가 기능 프로젝트에 대한 다음 코드 예제에서는 활성 문서의 첫 단락에 텍스트를 추가하고, 첫 단락을 선택한 다음 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 인스턴스화합니다. 이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `ProtectFirstParagraph` 이벤트 처리기에서 `ThisAddIn_Startup` 메서드를 호출합니다.

     [!code-vb[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#15)]
     [!code-csharp[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#15)]

## <a name="see-also"></a>참고자료
- [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)
- [콘텐츠 컨트롤](../vsto/content-controls.md)
- [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)
- [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)
- [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
