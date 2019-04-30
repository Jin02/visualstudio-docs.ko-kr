---
title: PowerPoint 솔루션
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], PowerPoint
- templates [Office development in Visual Studio], PowerPoint
- solutions [Office development in Visual Studio], PowerPoint
- projects [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], PowerPoint
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee1e5eddf89e60434a083293cdc08998dfe1b41d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445226"
---
# <a name="powerpoint-solutions"></a>PowerPoint 솔루션
  Visual Studio에서는 Microsoft Office PowerPoint용 VSTO 추가 기능을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. VSTO 추가 기능을 사용하여 PowerPoint를 자동화하거나, PowerPoint 기능을 확장하거나, PowerPoint UI(사용자 인터페이스)를 사용자 지정할 수 있습니다.

 VSTO 추가 기능에 대 한 자세한 내용은 참조 하세요. [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md) 하 고 [Architecture of VSTO add-ins](../vsto/architecture-of-vsto-add-ins.md)합니다. Microsoft Office를 사용한 프로그래밍을 처음 접하는 경우 참조 [시작 &#40;Visual Studio에서 Office 개발&#41;](../vsto/getting-started-office-development-in-visual-studio.md)합니다.

 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]

> [!NOTE]
> Office 환경을 확장 하는 솔루션을 개발 하는 데 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 새 확인해 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능의 VSTO 추가 기능 및 솔루션에 비해 작은 사용 공간이 있고 거의 모든 웹 프로그래밍 기술을, HTML5, JavaScript, CSS3, XML 등을 사용 하 여 빌드할 수 있습니다.

 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? Microsoft PowerPoint 용 인 추가 기능 만들기 ](http://go.microsoft.com/fwlink/?LinkId=132767).

## <a name="automate-powerpoint-by-using-the-powerpoint-object-model"></a>PowerPoint 개체 모델을 사용 하 여 PowerPoint를 자동화 합니다.
 PowerPoint 개체 모델은 PowerPoint 자동화에 사용할 수 있는 다양한 형식을 노출합니다. 이러한 형식을 사용하여 일반적인 작업을 수행하는 코드를 작성할 수 있습니다.

- 프로그래밍 방식으로 프레젠테이션을 만들고 형식을 지정합니다.

- 프레젠테이션에 슬라이드를 추가하거나 제거합니다.

- 슬라이드에 도형을 추가하거나 변경합니다.

  VSTO 추가 기능에서 PowerPoint 개체 모델에 액세스 하려면 사용 합니다 `Application` 필드는 `ThisAddIn` 프로젝트에서 클래스입니다. `Application` 필드는 PowerPoint의 현재 인스턴스를 나타내는 <xref:Microsoft.Office.Interop.PowerPoint.Application> 개체를 반환합니다. 자세한 내용은 [프로그램 VSTO Add-ins](../vsto/programming-vsto-add-ins.md)합니다.

  PowerPoint 개체 모델을 호출할 때 PowerPoint의 주 Interop 어셈블리에서 제공되는 형식을 사용합니다. 주 interop 어셈블리는 VSTO 추가 기능의 관리 코드와 PowerPoint의 COM 개체 모델 간의 다리 역할을 합니다. PowerPoint 주 interop 어셈블리의 모든 형식은 <xref:Microsoft.Office.Interop.PowerPoint> 네임스페이스에서 정의됩니다. 주 interop 어셈블리에 대 한 자세한 내용은 참조 하세요. [Office 솔루션 개발 개요 &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) 하 고 [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md).

## <a name="WordOMDocumentation"></a> PowerPoint 개체 모델 설명서 사용
 PowerPoint 개체 모델에 대한 자세한 내용은 PowerPoint PIA(주 interop 어셈블리) 참조 및 VBA 개체 모델 참조를 참조할 수 있습니다.

### <a name="primary-interop-assembly-reference"></a>주 interop 어셈블리 참조
 PowerPoint PIA 참조 설명서에서는 PowerPoint에 대한 주 interop 어셈블리의 형식에 대해 설명합니다. 이 설명서는 다음 위치에서 제공 됩니다. [PowerPoint 2010 주 interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189588)합니다.

 클래스 및 인터페이스 간의 차이점에는 PIA, PIA의 이벤트 구현 방식 등 PowerPoint PIA의 디자인에 대 한 자세한 내용은 참조 하세요. [Office 주 interop 어셈블리의 클래스 및 인터페이스 개요 ](http://go.microsoft.com/fwlink/?LinkId=199885).

### <a name="vba-object-model-reference"></a>VBA 개체 모델 참조
 VBA 개체 모델 참조에서는 VBA(Visual Basic for Applications) 코드로 표시되는 PowerPoint 개체 모델에 대해 설명합니다. 자세한 내용은 참조 하세요. [PowerPoint 2010 개체 모델 참조](http://go.microsoft.com/fwlink/?LinkId=199770)

 VBA 개체 모델 참조의 모든 개체 및 멤버는 PowerPoint PIA(주 interop 어셈블리)의 형식 및 멤버에 해당합니다. 예를 들어 VBA 개체 모델 참조의 프레젠테이션 개체는 해당 하는 <xref:Microsoft.Office.Interop.PowerPoint.Presentation> 는 PowerPoint PIA의 형식입니다. VBA 개체 모델 참조에서는 대부분의 속성, 메서드 및 이벤트에 대한 코드 예제를 제공하지만 Visual Studio를 사용하여 만든 PowerPoint VSTO 추가 기능 프로젝트에서 사용하려면 이 참조의 VBA 코드를 Visual Basic 또는 Visual C#으로 변환해야 합니다.

## <a name="customize-the-user-interface-of-powerpoint"></a>PowerPoint의 사용자 인터페이스
 다음과 같은 방법으로 PowerPoint의 UI를 수정할 수 있습니다.

|작업|추가 정보|
|----------|--------------------------|
|사용자 지정 작업창을 만듭니다.|[사용자 지정 작업창](../vsto/custom-task-panes.md)|
|리본에 사용자 지정 탭을 추가합니다.|[리본 개요](../vsto/ribbon-overview.md)|
|리본의 기본 제공 탭에 사용자 지정 그룹을 추가합니다.|[방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)|

 PowerPoint의 UI 및 다른 Microsoft Office 응용 프로그램을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.

## <a name="see-also"></a>참고자료
- [연습: PowerPoint 용 첫 VSTO 추가 기능에 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)
- [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)
- [Office 솔루션 개발 개요 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)
- [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)
- [Office 솔루션에서 코드를 작성 합니다.](../vsto/writing-code-in-office-solutions.md)
- [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)
- [Office UI 사용자 지정](../vsto/office-ui-customization.md)
- [Office 개발의 PowerPoint 2010](http://go.microsoft.com/fwlink/?LinkId=199015)
