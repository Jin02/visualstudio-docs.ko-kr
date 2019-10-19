---
title: 활동 뷰 (레거시) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c7d8a13890814b56865200acf95c8e0565b52b5a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655217"
---
# <a name="activity-views-legacy"></a>활동 뷰(레거시)
[!INCLUDE[wf](../includes/wf-md.md)]에서 제공하는 많은 활동은 워크플로를 구성하는 데 사용되며 이러한 활동에는 레거시 [!INCLUDE[wfd1](../includes/wfd1-md.md)]에서 사용할 수 있는 몇 가지 디자인 뷰가 있습니다. 활동 디자이너를 **도구 상자** 에서 디자인 화면으로 끌어 오거나 그 이후에 활동을 선택할 때마다 **워크플로** 메뉴를 사용 하거나 선택 된를 마우스 오른쪽 단추로 클릭 하 여 다양 한 디자인 뷰 간을 전환할 수 있습니다. 활동이. 또한 선택된 항목의 이름 위로 포인터를 옮기면 드롭다운 탭 집합이 나타나 여러 뷰 사이를 전환할 때 사용할 수 있습니다.

 모든 활동에는 하나 이상의 뷰가 있습니다. 활동 디자이너를 **도구 상자** 에서 디자인 화면으로 끌어 올 때 표시 되는 기본 뷰입니다. 이 활동의 기본 보기는 메뉴 및 탭에서 **보기 [활동 유형]** 옵션으로 사용할 수 있습니다 (예: **병렬 보기**). 대부분의 활동에 추가 뷰가 있으며, 활동마다 서로 다른 뷰를 가질 수 있습니다. 예를 들어 [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) 활동에는 보상 뷰가 있고 [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) 활동에는 이벤트 뷰가 있습니다. 와 Windows Workflow Foundation 함께 제공 되는 대부분의 작업에는 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) 및 관련 된 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 을 볼 수 있는 뷰 **취소 처리기** 및 **뷰 오류** 디자인 뷰가 있습니다.

 다음 표에서는 각 뷰의 이름과 설명을 보여 줍니다.

|메뉴/탭 옵션|설명|
|----------------------|-----------------|
|**보기 [활동 유형]**|선택한 활동의 기본 그래픽 표현을 보려면 이 메뉴 또는 탭 옵션을 선택합니다.|
|**취소 처리기 보기**|선택한 활동과 연결 된 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) 을 보려면이 메뉴 또는 탭 옵션 보기를 선택 합니다.|
|**오류 처리기 보기**|선택한 활동과 연결 된 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 을 보려면이 메뉴 또는 탭 옵션 보기를 선택 합니다.|
|**보정 처리기 보기**|이 메뉴 또는 탭 옵션 보기를 선택 하 여 선택한 [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)연결 된 [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) 를 확인 합니다.|
|**이벤트 처리기 보기**|이 메뉴 또는 탭 옵션 보기를 선택 하 여 선택한 [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)와 연결 된 [EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) 를 확인 합니다.|

 유사한 뷰에 대 한 자세한 내용은 [순차 워크플로 뷰 (레거시)](../workflow-designer/sequential-workflow-views-legacy.md)를 참조 하세요.

## <a name="see-also"></a>관련 항목:
 [레거시 워크플로 작업](../workflow-designer/legacy-workflow-activities.md) [순차 워크플로 뷰 (레거시)](../workflow-designer/sequential-workflow-views-legacy.md)