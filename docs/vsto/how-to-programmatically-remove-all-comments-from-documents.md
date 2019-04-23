---
title: '방법: 프로그래밍 방식으로 문서에서 모든 메모 제거'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 78b73cfe13d2374afad22dd322a80fe69acfb838
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068979"
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>방법: 프로그래밍 방식으로 문서에서 모든 메모 제거
  `DeleteAllComments` 메서드를 사용하여 Microsoft Office Word 문서에서 모든 메모를 제거합니다.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>문서 수준 사용자 지정의 일부인 문서에서 모든 메모를 제거하려면

1. 프로젝트에서 <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> 클래스의 `ThisDocument` 메서드를 호출합니다. 이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]

## <a name="to-remove-all-comments-from-a-document-by-using-a-vsto-add-in"></a>VSTO 추가 기능을 사용 하 여 문서에서 모든 메모를 제거 하려면

1. 메모를 제거하려는 <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> 의 <xref:Microsoft.Office.Interop.Word.Document> 메서드를 호출합니다.

     다음 코드 예제에서는 활성 문서에서 모든 메모를 제거합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 문서의 텍스트에 주석 추가](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)
- [문서 호스트 항목](../vsto/document-host-item.md)
