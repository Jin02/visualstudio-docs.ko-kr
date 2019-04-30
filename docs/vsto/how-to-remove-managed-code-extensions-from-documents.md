---
title: '방법: 문서에서 관리 코드 확장명 제거'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], removing
- documents [Office development in Visual Studio], managed code extensions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 438658af3f182ea732d0fefef0f5a5d6ecbefa03
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62961594"
---
# <a name="how-to-remove-managed-code-extensions-from-documents"></a>방법: 문서에서 관리 코드 확장명 제거
  프로그래밍 방식으로 문서 또는 Microsoft Office Word 또는 Microsoft Office Excel 용 문서 수준 사용자 지정을 포함 된 통합 문서에서 사용자 지정 어셈블리를 제거할 수 있습니다. 사용자가 다음 문서를 열 고 볼 수 있으며 콘텐츠를 하지만 문서에 추가한 모든 사용자 지정 사용자 인터페이스 (UI)는 표시 되지 코드가 실행 되지 않습니다.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 하나를 사용 하 여 사용자 지정 어셈블리를 제거할 수 있습니다 합니다 `RemoveCustomization` 에서 제공 하는 메서드는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 어떤 방법을 사용 하 여 런타임에 사용자 지정을 제거 하려는 여부에 따라 달라 집니다 (즉, 단어 하는 동안 사용자 지정에서 코드를 실행 하 여 문서 또는 Excel 통합 문서 연 경우) 또는 닫힌된 문서 또는 문서에서 사용자 지정을 제거 하려는 경우 해당 i Microsoft Office가 설치 되지 않은 서버에 대 한 s입니다.

 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요 연결 또는 분리를 VSTO 어셈블리 Word 문서에서? ](http://go.microsoft.com/fwlink/?LinkId=136782).

## <a name="to-remove-the-customization-assembly-at-runtime"></a>런타임 시 사용자 지정 어셈블리를 제거 하려면

1. 사용자 지정 코드에서 호출 된 <xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A> (Word 용) 메서드 또는 <xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A> 메서드 (Excel 용). 더 이상 필요 없는 사용자 지정 후에이 메서드를 호출 해야 합니다.

     코드에서이 메서드를 호출 하는 위치는 사용자 지정을 사용 하는 방법에 따라 달라 집니다. 예를 들어 경우 문서 자체 (사용자 지정 하지 함)만 해야 하는 다른 클라이언트에 문서를 보낼 준비가 될 때까지 사용자 지정의 기능을 사용 하는 고객을 제공할 수 있습니다를 호출 하는 몇 가지 UI `RemoveCustomization` 고객이 경우 클릭 합니다. 또는 사용자 지정 사용자 지정 고객에 게 직접 액세스할 수 있는 다른 기능을 제공 하지 않습니다 하지만 처음 열 때 데이터를 사용 하 여 문서를 채웁니다, 그런 다음 호출할 수 있습니다 RemoveCustomization 사용자 지정 되 자 마자 완료 된 문서를 초기화 합니다.

## <a name="to-remove-the-customization-assembly-from-a-closed-document-or-a-document-on-a-server"></a>닫힌된 문서 또는 문서에는 서버에서 사용자 지정 어셈블리를 제거 하려면

1. 콘솔 응용 프로그램 또는 Windows Forms 프로젝트와 같은 Microsoft Office를 필요 하지 않은 프로젝트에 대 한 참조를 추가 합니다 *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* 어셈블리입니다.

2. 다음을 추가 합니다 **가져오기를** 또는 **사용 하 여** 문을 코드 파일의 맨 위에 있습니다.

     [!code-csharp[Trin_VstcoreDeployment#1](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#1)]

3. 정적 호출 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 메서드는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스 및 솔루션의 문서 경로 매개 변수를 지정 합니다.

     다음 코드 예제에서는 명명 된 문서에서 사용자 지정 제거 된다고 가정 *WordDocument1.docx* 바탕 화면입니다.

     [!code-csharp[Trin_VstcoreDeployment#2](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#2)]

4. 프로젝트를 빌드하고 사용자 지정을 제거 하려는 컴퓨터의 응용 프로그램을 실행 합니다. 컴퓨터에는 Visual Studio 2010 Tools for Office 런타임 설치 되어 있어야 합니다.

## <a name="see-also"></a>참고자료
- [ServerDocument 클래스를 사용 하 여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [방법: 문서에 관리 코드 확장명 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)
