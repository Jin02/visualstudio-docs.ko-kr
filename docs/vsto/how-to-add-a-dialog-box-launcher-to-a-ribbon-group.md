---
title: '방법: 리본 그룹에 대화 상자 표시 아이콘 추가'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- dialog box launcher [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], dialog box launcher
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9d831cb629665e641394d011bd11eb74481c4f94
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60087185"
---
# <a name="how-to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>방법: 리본 그룹에 대화 상자 표시 아이콘 추가
  리본의 그룹에 대화 상자 표시 아이콘을 추가할 수 있습니다. 대화 상자 표시 아이콘은 그룹에 표시 되는 작은 아이콘입니다. 사용자 그룹에 관련 된 추가 옵션을 제공 하는 작업 창 또는 관련된 대화 상자를 열려면이 아이콘을 클릭 합니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>리본 그룹에 대화 상자 표시 아이콘을 추가 하려면

1. 리본 코드 파일을 선택 (*.vb* 하거나 *.cs* 파일)에서 **솔루션 탐색기**합니다.

2. 에 **뷰** 메뉴에서 클릭 **디자이너**합니다.

3. 리본 디자이너에서 모든 그룹을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **DialogBoxLauncher 추가**합니다.

     코드를 추가 하는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> 이벤트 그룹을 사용자 지정 또는 기본 제공 대화 상자를 엽니다.

## <a name="see-also"></a>참고자료
- [리본 개요](../vsto/ribbon-overview.md)
- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
- [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [방법: 리본 XML로 리본 디자이너에서 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)
- [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)
- [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [Outlook의 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)
- [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [방법: 추가 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [연습: 런타임에 리본의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)
- [연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
