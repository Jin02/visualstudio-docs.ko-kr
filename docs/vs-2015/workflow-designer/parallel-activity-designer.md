---
title: 병렬 활동 디자이너 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a46a340ccdeacacb8f04b962313db18975447a67
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672632"
---
# <a name="parallel-activity-designer"></a>Parallel 활동 디자이너
<xref:System.Activities.Statements.Parallel> 활동은 자식 활동 컬렉션을 동시에 실행합니다.

## <a name="the-parallel-activity"></a>Parallel 활동
 <xref:System.Activities.Statements.Parallel> 활동은 자식 활동을 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 저장합니다. 일부 자식 활동이 유휴 상태가 될 수 있는 경우에는 <xref:System.Activities.Statements.Parallel> 활동 대신 <xref:System.Activities.Statements.Sequence> 활동을 사용합니다.

 <xref:System.Activities.Statements.Parallel> 활동에는 사용자가 지정한 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 식이 포함된 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 속성이 있습니다. <xref:System.Activities.Statements.Parallel> 활동은 각 분기가 완료된 후 이 속성을 평가합니다. **True**로 평가 되 면 다른 분기를 실행 하지 않고 <xref:System.Activities.Statements.Parallel> 작업이 완료 됩니다. @No__t_0이 **True**로 평가 되지 않으면 모든 자식 활동이 완료 되 면 <xref:System.Activities.Statements.Parallel> 활동이 완료 됩니다.

### <a name="using-the-parallel-activity-designer"></a>Parallel 활동 디자이너 사용
 **병렬** 활동 디자이너는 **도구 상자**의 **제어 흐름** 범주에 있습니다 .이 범주에 액세스 하려면 **[!INCLUDE[wfd2](../includes/wfd2-md.md)]의 왼쪽** 에 있는 **도구 상자** 탭을 클릭 하거나,  **보기** 메뉴 또는 CTRL + ALT + X.)

 **병렬** 활동 디자이너를 **도구 상자** 에서 끌어 활동 디자이너가 일반적으로 배치 되는 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 화면 (예: **시퀀스** 활동 디자이너 내부)에 놓을 수 있습니다. @No__t_0에 삭제 한 후에는 기본적으로 **병렬** <xref:System.Activities.Activity.DisplayName%2A>를 포함 하는 <xref:System.Activities.Statements.Parallel> 활동을 만듭니다.

 병렬 작업의 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 활동을 추가 하려면 **도구 상자** 의 다른 활동 디자이너를 **병렬** 활동 디자이너 내의 삼각형에 끌어 놓습니다. 이 삼각형은 분기에 포함된 활동 옆에 표시됩니다. 이 절차를 반복하여 다른 활동을 추가할 수 있습니다. 활동은 **병렬** 활동 디자이너 내에서 끌어서 놓는 방법으로 다시 정렬할 수 있습니다.

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>Workflow Designer의 Parallel 활동 속성
 다음 표에서는 가장 유용한 Parallel 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.

|속성 이름|필요한 공간|사용 현황|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다. 기본값은 **Parallel**입니다. 값은 선택적으로 **속성** 표에서 편집 하거나 activity designer 헤더에서 직접 편집할 수 있습니다.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|실행할 자식 활동의 컬렉션을 포함합니다.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|분기가 완료된 후 확인됩니다. **True**로 평가 되 면 예약 된 보류 중인 분기가 취소 됩니다. 이 속성이 설정 되지 않거나 **False**로 평가 되는 경우 모든 자식 활동이 완료 되 면 활동이 완료 됩니다. 기본값은 **null**합니다.|

## <a name="see-also"></a>관련 항목:
 [Sequence](../workflow-designer/sequence-activity-designer.md) [ParallelForEach \<T >](../workflow-designer/parallelforeach-t-activity-designer.md) [제어 흐름](../workflow-designer/control-flow-activity-designers.md)