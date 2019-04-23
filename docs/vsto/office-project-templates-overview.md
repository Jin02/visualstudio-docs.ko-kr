---
title: Office 프로젝트 템플릿 개요
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], about project templates
- Excel Workbook project template
- Word Template project template
- Excel [Office development in Visual Studio], project templates
- Project [Office development in Visual Studio], project templates
- project templates [Office development in Visual Studio]
- project templates, Word
- InfoPath [Office development in Visual Studio], project templates
- Excel Template project template
- project templates, 2007 Microsoft Office system
- project templates, Excel
- PowerPoint [Office development in Visual Studio], project templates
- Word [Office development in Visual Studio], Word project templates
- Office projects [Office development in Visual Studio], templates
- Excel projects in Visual Studio
- Word Document project template
- Visio [Office development in Visual Studio], project templates
- Word projects in Visual Studio
- Outlook [Office development in Visual Studio], project templates
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 49cb0af47f34abbda5bd212d8ce535e98c44d6b5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054575"
---
# <a name="office-project-templates-overview"></a>Office 프로젝트 템플릿 개요
  Visual Studio의 Microsoft Office 개발자 도구에는 다음 형식의 Office 솔루션을 만들기 위한 프로젝트 템플릿이 포함되어 있습니다.

- [문서 수준 사용자 지정](#DocLevel)

- [VSTO 추가 기능](#AppLevel)

  이러한 유형의 Office 솔루션의 자세한 비교를 참조 하세요. [Office 솔루션 개발 개요 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)합니다.

  Office 프로젝트 템플릿은 **새 프로젝트** 대화 상자에서 **Visual C#** 및 **Visual Basic** 언어 노드의 **Office** 노드에서만 사용할 수 있습니다. 각 템플릿은 어셈블리 참조 및 디버깅 설정을 비롯하여 대상 애플리케이션에 적절한 구성이 포함된 프로젝트를 생성합니다.

  프로젝트마다 특정 유형의 솔루션에 대한 작업을 시작하는 데 사용할 수 있는 파일 및 코드가 있습니다. 각 프로젝트의 생성된 코드에는 Startup 및 Shutdown 이벤트 처리기가 포함됩니다. 이러한 이벤트 처리기에 코드를 추가하여 솔루션이 로드될 때 솔루션을 초기화하고 솔루션이 언로드될 때 솔루션을 정리할 수 있습니다. 자세한 내용은 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md) 하 고 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)합니다.

> [!NOTE]
> Office 개발 도구는 일부 버전의 Visual Studio에 포함되어 있습니다. 자세한 내용은 [Office 솔루션을 개발 하도록 컴퓨터를 구성](../vsto/configuring-a-computer-to-develop-office-solutions.md)합니다.

## <a name="DocLevel"></a> 문서 수준 사용자 지정
 **새 프로젝트** 대화 상자의 **Office** 노드에는 Word 및 Excel용 문서 수준 사용자 지정을 만들 때 기초로 사용할 수 있는 프로젝트 템플릿이 있습니다.

- **Word 2013 및 2016 VSTO 문서**

- **Word 2013 및 2016 VSTO 서식 파일**

- **Excel 2013 및 2016 VSTO 통합 문서**

- **Excel 2013 및 2016 VSTO 서식 파일**

- **Word 2010 VSTO 문서**

- **Word 2010 VSTO 서식 파일**

- **Excel 2010 VSTO 통합 문서**

- **Excel 2010 VSTO 서식 파일**

  Word 문서 및 Excel 통합 문서 프로젝트 템플릿에는 특정 문서 또는 통합 문서를 기반으로 솔루션을 만드는 데 사용할 수 있는 코드가 있습니다. 이러한 형식의 솔루션에서는 연결된 문서가 Word나 Excel에서 열려 있는 경우에만 코드가 실행됩니다.

  Word 서식 파일 및 Excel 서식 파일 프로젝트 템플릿은 Word 문서 및 Excel 통합 문서 프로젝트 템플릿과 동일하게 동작합니다. 그러나 Word 서식 파일 및 Excel 서식 파일 프로젝트 템플릿을 사용하면 사용자가 솔루션의 사용자 지정된 서식 파일로 새 로컬 문서 또는 통합 문서 복사본을 손쉽게 만들 수 있습니다. 사용자가 서식 파일을 사용하여 만드는 새 문서에서도 솔루션의 기능을 사용할 수 있습니다.

> [!NOTE]
>  관리 코드 확장을 참조하는 Word 서식 파일은 전역 VSTO 추가 기능으로 사용할 수 없습니다. Word의 시작 디렉터리를 통해 서식 파일을 로드하는 경우 어셈블리가 호출되지 않습니다. 자세한 내용은 참조 하세요. [전역 서식 파일 및 Excel 추가 기능 (.xla 파일)의 제한 사항](#Limitations)

 이러한 프로젝트 형식에 대한 기초적인 내용은 다음 항목을 참조하십시오.

- [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)

- [Word 솔루션](../vsto/word-solutions.md)

- [Excel 솔루션](../vsto/excel-solutions.md)

- [연습: Word 용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)

- [연습: Excel 용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)

## <a name="AppLevel"></a> VSTO 추가 기능
 **새 프로젝트** 대화 상자의 **Office/SharePoint** 노드에는 VSTO 추가 기능을 만들기 시작할 때 사용할 수 있는 다음과 같은 프로젝트 템플릿이 있습니다.

- **Excel 2013 및 2016 VSTO 추가 기능**

- **InfoPath 2013 VSTO 추가 기능**

- **Outlook 2013 및 2016 VSTO 추가 기능**

- **PowerPoint 2013 및 2016 추가 기능**

- **Project 2013 및 2016 추가 기능**

- **Visio 2013 및 2016 추가 기능**

- **Word 2013 및 2016 추가 기능**

- **Excel 2010 추가 기능**

- **InfoPath 2010 추가 기능**

- **Outlook 2010 추가 기능**

- **PowerPoint 2010 추가 기능**

- **Project 2010 추가 기능**

- **Visio 2010 추가 기능**

- **Word 2010 추가 기능**

  이러한 프로젝트 템플릿 중 하나를 기반으로 하는 프로젝트를 만드는 경우 연결된 애플리케이션이 열릴 때 솔루션의 코드가 실행됩니다. 문서 수준 프로젝트와 달리 이 코드는 단일 문서와 연결되지 않습니다.

  이러한 프로젝트 형식에 대한 기초적인 내용은 다음 항목을 참조하십시오.

- [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)

- [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)

- [연습: Excel 용 첫 VSTO 추가 기능에 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)

- [연습: 첫 번째 VSTO 추가 기능에 Outlook에 대 한 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)

- [연습: PowerPoint 용 첫 VSTO 추가 기능에 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)

- [연습: 첫 번째에 VSTO 추가 기능 프로젝트 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)

- [연습: Word 용 첫 VSTO 추가 기능에 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)

## <a name="document-vs-template-solutions"></a>문서 서식 파일 솔루션 비교
 Word 문서 또는 Excel 통합 문서 기반 솔루션을 디자인할 때는 사용자에게 문서를 제공하는 데 가장 적합한 방식을 결정해야 합니다.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  

 일부 경우에는 각 사용자에게 문서의 복사본을 제공하는 것이 더 낫습니다. 이 경우 Excel 또는 Word 문서 프로젝트를 사용하여 솔루션을 만듭니다.

 각 사용자가 서식 파일을 열고 로컬 복사본을 문서로 저장할 수 있도록 서식 파일을 서버에 저장한 상태로 사용할 수 있게 하는 것이 더 나은 경우도 있습니다. 이 경우에는 Excel 또는 Word 서식 파일 프로젝트를 사용하여 솔루션을 만듭니다.

## <a name="comparison"></a>비교
 다음 표에는 문서와 서식 파일 간의 차이에 대한 개요가 나와 있습니다.

|문서|템플릿|
|---------------|---------------|
|문서가 읽기 전용으로 설정되어 있지 않은 경우 사용자가 문서를 열고 수정할 수 있습니다. 변경 사항을 저장하면 원본 문서에 저장됩니다.|사용자는 서식 파일을 열고 새 문서로 로컬 복사본을 만들 수 있습니다. 특별한 권한이 없으면 원본을 수정할 수 없습니다.|
|문서를 열면 <xref:Microsoft.Office.Tools.Word.Document.Open> 이벤트가 발생합니다.|서식 파일을 열면 <xref:Microsoft.Office.Tools.Word.Document.New> 이벤트가 발생합니다.|

## <a name="Limitations"></a> 전역 서식 파일 및 Excel 추가 기능 (.xla 파일)의 제한 사항
 문서, 통합 문서 및 서식 파일은 전역 서식 파일이나 Excel VSTO 추가 기능(.xla 파일)으로 제대로 작동하지 않을 수 있습니다.

## <a name="word-templates"></a>Word 서식 파일
 Microsoft Office Word 서식 파일에 관리 코드 확장이 있는 경우, 해당 서식 파일이 전역 서식 파일로 연결되거나 Word의 startup 디렉터리에서 로드되면 프로젝트 어셈블리는 호출되지 않습니다. 또한 문서에서는 Office 솔루션의 일부인 서식 파일 형식을 인식할 수 없습니다.

## <a name="excel-add-ins-xla-files"></a>Excel 추가 기능 (.xla 파일)
 Excel VSTO 추가 기능 만들기에 대 한 Office 프로젝트가 없습니다 (*.xla* 파일). 통합 문서를 .xla 파일로 저장할 수는 있지만 지원되는 작업이 아니므로 권장되지 않습니다. 관리 코드 확장이으로 통합 문서를 저장 하는 경우는 **Microsoft Office Excel 추가 기능에 (\*.xla)** 파일을 선택할 수 있습니다에 **Add-ins** 다른 통합 문서에 적용할 대화 상자. 경우에 따라 코드는 VSTO 추가 기능에 적용 되지만 이러한 Office 솔루션 사용 방식은 지원 되지 않습니다 후 대상 통합 문서에서 실행 됩니다.

## <a name="see-also"></a>참고자료
- [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)
- [Office 솔루션 개발](../vsto/developing-office-solutions.md)
- [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Excel 용 문서 수준 사용자 지정 프로그래밍 시작](../vsto/getting-started-programming-document-level-customizations-for-excel.md)
- [Word 용 문서 수준 사용자 지정 프로그래밍 시작](../vsto/getting-started-programming-document-level-customizations-for-word.md)
- [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)
