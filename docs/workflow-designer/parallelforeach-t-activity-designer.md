---
title: 워크플로 디자이너-ParallelForEach &lt;T &gt; Activity Designer
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b68cd543ed41408e7510708367c8e539c0702ea1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650085"
---
# <a name="parallelforeach-activity-designer"></a>ParallelForEach 활동 디자이너

<xref:System.Activities.Statements.ParallelForEach%601> 활동은 컬렉션의 요소를 열거하고 컬렉션의 각 요소에 대해 포함 문을 병렬로 실행합니다. 각 요소는 동일 스레드에서 비동기적입니다. <xref:System.Activities.Statements.Sequence> 활동의 자식 활동이 유휴 상태가 되는 경우 이 활동 대신 이 흐름 제어 활동을 사용합니다.

@No__t_0 작업에는 사용자가 지정한 Visual Basic 식이 포함 된 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 속성이 있습니다. <xref:System.Activities.Statements.ParallelForEach%601> 활동은 각 분기가 완료된 후 이 속성을 평가합니다. **True**로 평가 되 면 다른 분기를 실행 하지 않고 <xref:System.Activities.Statements.ParallelForEach%601> 작업이 완료 됩니다. @No__t_0이 **true**로 평가 되지 않으면 모든 자식 활동이 완료 되 면 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 완료 됩니다.

## <a name="the-parallelforeacht-activity"></a>ParallelForEach < T \> 활동

<xref:System.Activities.Statements.ParallelForEach%601>은 값을 열거하고 열거되는 모든 값에 대해 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>을 예약합니다. <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>만 예약합니다. <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되는지 여부에 따라 본문의 실행 방법이 달라집니다.

<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되지 않는 경우에는 예약된 활동이 스택으로 처리되기 때문에 역순으로 실행됩니다. 즉, 마지막으로 예약된 활동이 가장 먼저 실행됩니다. 예를 들어 {1,2,3,4}in <xref:System.Activities.Statements.ParallelForEach%601> 컬렉션이 있고 **WriteLine** 을 본문으로 사용 하 여 값을 쓸 수 있습니다. 콘솔에 4, 3, 2, 1이 출력 됩니다. 이는 **writeline** 이 유휴 상태로 전환 되지 않으므로 4 개의 **writeline** 활동이 예약 된 후 스택 동작을 사용 하 여 실행 됩니다 (처음에는 마지막으로 실행 됨).

<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>에 유휴 상태로 전환될 수 있는 활동(예: <xref:System.ServiceModel.Activities.Receive> 활동 또는 <xref:System.Activities.Statements.Delay> 활동)이 있는 경우에는 활동이 완료될 때까지 기다릴 필요가 없습니다. <xref:System.Activities.Statements.ParallelForEach%601>은 예약된 다음 본문 활동으로 이동하여 해당 활동을 실행합니다. 이 활동도 유휴 상태가 될 경우 <xref:System.Activities.Statements.ParallelForEach%601>은 다시 다음 본문 활동으로 넘어갑니다.

### <a name="using-the-parallelforeacht-activity-designer"></a>ParallelForEach \<T > 활동 디자이너 사용

**도구 상자**의 **제어 흐름** 범주에 있는 **ParallelForEach \<T >** 활동 디자이너에 액세스 합니다.

**ParallelForEach \<T >** 활동 디자이너를 **도구 상자** 에서 끌어 활동 디자이너가 일반적으로 배치 되는 워크플로 디자이너 화면 (예: **시퀀스** 활동의 내부)에 놓을 수 있습니다. 디자이너. 워크플로 디자이너에 삭제 한 후 <xref:System.Activities.Statements.ParallelForEach%601> 활동을 만듭니다 .이 활동에는 기본적으로 **ParallelForEach < Int32 \>** 의 <xref:System.Activities.Activity.DisplayName%2A> 포함 됩니다.

### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach < T \> 속성을 워크플로 디자이너

다음 표에서는 가장 유용한 <xref:System.Activities.Statements.ParallelForEach%601> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.

|속성 이름|필요한 공간|사용 현황|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다. 기본값은 **ParallelForEach \<Int32 >** 입니다. 값은 선택적으로 **속성** 표에서 편집 하거나 activity designer 헤더에서 직접 편집할 수 있습니다.|
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|컬렉션의 각 항목에 대해 실행할 활동입니다. @No__t_0 활동을 추가 하려면 도구 상자의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **ParallelForEach \<T >** 활동 디자이너의 **본문** 상자로 끌어 놓습니다.|
|**TypeArgument**|True|제네릭 매개 변수 *t*로 지정 된 <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> 컬렉션에 있는 항목의 형식입니다. 기본적으로 **Typeargument** 는 **Int32**로 설정 됩니다. **ParallelForEach < t \>** activity designer에서 형식 T를 변경 하려면 속성 표에서 **typeargument** 콤보 상자의 값을 변경 합니다.|
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|True|반복할 항목의 컬렉션입니다. @No__t_0 설정 하려면 **속성** 창의 "VB 식 입력" 또는 **값** 상자에 있는 상자에 **ForEach < t \>** activity designer의 **값** 상자에 Visual Basic 식을 입력 합니다.|
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||각 반복이 완료된 후 평가됩니다. true이면 예약된 보류 중인 반복이 취소됩니다. 이 속성을 설정 하지 않으면 모든 예약 된 문이 완료 될 때까지 실행 됩니다.|

루프 반복기는 기본적으로 이름이 지정된 항목입니다. **ParallelForEach \<T >** activity Designer의 **ForEach** 상자에서 반복기 변수의 이름을 변경할 수 있습니다. 루프 반복기는 <xref:System.Activities.Statements.ParallelForEach%601> 활동의 자식에 포함된 식에서 사용할 수 있습니다.

## <a name="see-also"></a>참조

- [Sequence](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [제어 흐름](../workflow-designer/control-flow-activity-designers.md)