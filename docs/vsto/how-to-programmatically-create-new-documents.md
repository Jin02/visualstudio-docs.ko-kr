---
title: '방법: 프로그래밍 방식으로 새 문서 만들기'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4940b5f5064fdb47439ad6b38b855785ae06c781
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575132"
---
# <a name="how-to-programmatically-create-new-documents"></a>방법: 프로그래밍 방식으로 새 문서 만들기
  프로그래밍 방식으로 문서를 만드는 경우 새 문서는 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 개체입니다. 이 개체에는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목의 추가 이벤트 및 데이터 바인딩 기능이 없습니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)합니다.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 문서 수준 프로젝트를 개발하는 경우 프로그래밍 방식으로 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목을 프로젝트에 추가할 수 없습니다. VSTO 추가 기능 프로젝트에서 런타임에 <xref:Microsoft.Office.Interop.Word.Document> 개체를 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목으로 변환할 수 있습니다. 자세한 내용은 [확장 Word 문서 및 Excel 통합 런타임에 VSTO 추가 기능에서](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)합니다.

## <a name="to-create-a-new-document-based-on-the-normal-template"></a>기본 서식 파일을 기반으로 하여 새 문서를 만들려면

- <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드를 사용하여 기본 서식 파일을 기반으로 하는 새 문서를 만듭니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]

## <a name="use-custom-templates"></a>사용자 지정 템플릿 사용
 합니다 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드가 선택적 *템플릿* 기본 서식 파일 이외의 서식 파일을 기반으로 하는 인수는 새 문서를 만듭니다. 서식 파일의 파일 이름 및 정규화된 경로를 제공해야 합니다.

### <a name="to-create-a-new-document-based-on-a-custom-template"></a>사용자 지정 서식 파일을 기반으로 하여 새 문서를 만들려면

- <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션의 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 메서드를 호출하고 서식 파일의 경로를 지정합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)
- [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)
- [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)
