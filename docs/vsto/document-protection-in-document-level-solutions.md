---
title: 문서 수준 솔루션의 문서 보호
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio], restricted permissions
- documents [Office development in Visual Studio], restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b6cc01c6506c4a3fca85029a8dcaf08607427ea4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62956207"
---
# <a name="document-protection-in-document-level-solutions"></a>문서 수준 솔루션의 문서 보호
  문서 수준 프로젝트에서 Microsoft Office Word 및 Microsoft Office Excel의 보호 기능을 사용할 수 있습니다. 이러한 기능에는 권한이 없는 사용자가 보호 된 문서 부분을 변경 하지 못하도록 차단 합니다.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Excel을 사용 하 여 설정할 수 있습니다 보호 설정 및 해제는 통합 문서가 디자이너에에서 열려 있는 동안. Word를 사용 하 여 보호 디자이너 외에 설정할 수 있습니다. 런타임 시 사용 수도 있고 Word 및 Excel에 프로그래밍 방식으로 보호를 사용 하지 않도록 설정할 수 있습니다.

 모든 컨트롤에서 제거 됩니다 문서 보호를 디자이너에 열려 있는 문서에서 사용 하는 경우는 **도구 상자** 없게 되며 또는 끌 수 없습니다는 **데이터 원본** 문서 창입니다.

## <a name="serverdocument-and-protected-documents"></a>ServerDocument 및 보호 된 문서
 문서가 보호 되는 경우 문서 외부에서 데이터 캐시에 액세스할 수 없습니다. 사용할 수 없습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 검색 하거나 보호 된 문서에 캐시 된 데이터를 조작 하거나의 다른 메서드를 사용 합니다 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> 클래스입니다.

## <a name="word-document-protection-in-the-designer"></a>디자이너에서 Word 문서 보호
 보호 기능을 Word 문서 또는 서식 파일에 추가 하면 Visual Studio에서 열려 있는 동안 디자이너에서 보호를 적용를 시작할 수 없습니다. Visual Studio에서 열려 있는 동안에 실행 해야 모드 보호를 적용 하기 전에 디자인 모드 문서가입니다.

 그러나 보호가 설정 된 기존 Word 문서를 사용 하는 프로젝트를 만들면 문서 디자이너에 열려 있는 동안 보호 됩니다. 보호 된 문서의 부분을 편집할 수 없습니다 않지만 작성할 수 있습니다 여전히 코드 코드 편집기에서 문서를 자동화할 수 있습니다. 또한 문서가 Visual Studio에서 열려 있는 동안 보호가 설정 된 경우 프로젝트를 빌드할 수 없습니다.

 문서를 편집 하 고 프로젝트를 빌드할 수 있도록 문서가 디자이너에에서 열려 있는 동안 보호를 해제할 수 있습니다. 디버깅 하는; 디자이너의 복사본에 대 한 보호 해제할 수 없습니다. 디버깅 하는 동안 열려 있는 문서에서 디자이너에서 열리는 별도 복사본 인 (출력 복사본에 저장 합니다 *\bin* Visual basic의 경우 디렉터리 및 *\bin\debug* 디렉터리 C# ).

 Visual Studio에서 프로젝트를 닫으면 프로젝트 디렉터리에 있는 문서 복사본을 열고 보호를 설정 하 여 디자이너에서 열려 있는 문서 복사본에 대해 보호를 사용할 수 있습니다.

## <a name="enforce-word-document-protection-on-build"></a>빌드에 대 한 Word 문서 보호를 적용 합니다.
 Visual Studio 시작 보호 디버깅에 대 한 문서를 열 때 사용할 수 있도록 빌드 프로세스 중에 Word 문서 및 템플릿에 대 한 보호를 적용 합니다. 문서는 빈 암호를 사용 하 여 보호 됩니다.

 보호는 빌드 중 이므로 하도록 활성화 문서의 코드 이면 <xref:Microsoft.Office.Tools.Word.Document.Startup> 예외가 발생 하거나 응용 프로그램의 동작을 변경할 수 있는 경우가이 코드가 올바르게 디버깅 될 수 있습니다. 문서를 연 후 보호를 사용 하는 경우 초기화 코드를 디버깅 하거나 테스트할 수 없습니다.

## <a name="setting-the-password"></a>암호를 설정합니다.
 Visual Studio는 자동으로 보호를 사용 하도록 설정 하지만 기본적으로 암호를 제공 합니다. 문서를 보호 하려면 암호를 하려는 경우 솔루션을 배포 하기 전에 추가 해야 합니다. 권한 있는 사용자가 문서에서 보호를 제거 하면 암호를 추가 합니다. 암호가 없으면 보호 쉽게 제거할 수 없습니다. 암호를 설정 하는 방법에 대 한 자세한 내용은 특정 Office 응용 프로그램에서 도움말을 참조 합니다.

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 문서 및 문서의 일부 보호](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)
- [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)
- [정보 권한 관리 및 관리 코드 확장명 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)
- [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)
- [방법: 제한 된 권한으로 문서 뒤에서 실행 하는 코드를 허용 합니다.](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)
- [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)
