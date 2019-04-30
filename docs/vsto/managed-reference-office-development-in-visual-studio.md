---
title: 관리 되는 참조 (Visual Studio에서 Office 개발)
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f8ff9a196fb459359502e4c9f8599fbdeff3e1ce
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438800"
---
# <a name="managed-reference-office-development-in-visual-studio"></a>관리 되는 참조 (Visual Studio에서 Office 개발)
  이 섹션에는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]대상의 Office 프로젝트에서 사용되는 네임스페이스 및 형식에 대한 API 참조 설명서가 포함되어 있습니다. 네임 스페이스 및.NET Framework 3.5를 대상으로 하는 Office 프로젝트에서 사용 되는 형식에 대 한 API 참조 설명서는 Visual Studio 설명서에서 다음 참조 섹션을 참조 하세요.: [ http://go.microsoft.com/fwlink/?LinkId=160658 ](http://go.microsoft.com/fwlink/?LinkId=160658)합니다.

> [!NOTE]
> Office 환경을 확장 하는 솔루션을 개발 하는 데 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 새 확인해 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능의 VSTO 추가 기능 및 솔루션에 비해 작은 사용 공간이 있고 거의 모든 웹 프로그래밍 기술을, HTML5, JavaScript, CSS3, XML 등을 사용 하 여 빌드할 수 있습니다.

## <a name="in-this-section"></a>단원 내용
 <xref:Microsoft.Office.Tools>

 Office 솔루션을 프로그래밍할 때 일반적으로 사용하는 클래스가 포함됩니다. 여기에는 VSTO 추가 기능용 기본 클래스, VSTO 추가 기능에서 사용자 지정 작업창을 만들기 위한 클래스, Excel 및 Word 솔루션에서 스마트 태그를 만들기 위한 클래스, 문서 수준 사용자 지정에서 작업 창을 만들기 위한 클래스가 포함됩니다.

 <xref:Microsoft.Office.Tools.Excel>

 Excel용 솔루션에서 사용할 수 있는 호스트 컨트롤 및 호스트 항목이 포함됩니다.

 <xref:Microsoft.Office.Tools.Excel.Controls>

 Excel용 솔루션에서 사용할 수 있는 Excel 컨트롤 및 Windows Forms 컨트롤이 포함됩니다.

 <xref:Microsoft.Office.Tools.Outlook>

 사용자 지정 양식 영역을 만드는 데 사용되는 클래스를 포함하여 Outlook용 VSTO 추가 기능에서 사용하는 클래스가 포함됩니다.

 <xref:Microsoft.Office.Tools.Ribbon>

 리본 디자이너를 사용하여 만들어진 리본 사용자 지정을 프로그래밍 방식으로 수정하는 데 사용되는 클래스가 포함됩니다.

 <xref:Microsoft.Office.Tools.Word>

 Word용 솔루션에 사용할 수 있는 호스트 컨트롤 및 호스트 항목이 포함됩니다.

 <xref:Microsoft.Office.Tools.Word.Controls>

 Word용 솔루션에서 사용할 수 있는 Word 컨트롤 및 Windows Forms 컨트롤이 포함됩니다.

 <xref:Microsoft.VisualStudio.Tools.Applications>

 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스 및 그와 관련된 캐시된 데이터 클래스 집합이 포함되어 있습니다. 이러한 클래스를 사용하면 Microsoft Office가 설치되지 않은 컴퓨터에서 문서 수준 사용자 지정의 여러 측면을 수정할 수 있습니다.

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>

 Office 솔루션에 대한 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> 배포 후 작업 *을 만들기 위해 구현할 수 있는* 인터페이스, Office 솔루션을 설치할 때 throw될 수 있는 예외 및 Visual Studio 인프라의 일부인 다른 API가 포함됩니다.

 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>

 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에 의해 throw될 수 있는 대부분의 예외, 문서 수준 사용자 지정에 데이터를 캐시하는 데 사용할 수 있는 여러 클래스 및 Visual Studio 인프라의 일부인 기타 API가 포함됩니다.

 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>

 Office 프로젝트를 빌드하는 데 사용되는 MSBuild 작업 클래스가 포함됩니다.

## <a name="see-also"></a>참고자료
- [Visual Studio tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [시작 &#40;Visual Studio에서 Office 개발&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)
- [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)
