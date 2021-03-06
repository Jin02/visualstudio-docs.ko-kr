---
title: 상태 활동 디자이너 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
caps.latest.revision: 5
author: steved0x
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dff9793becc3e0619d42b642609273f328c6aa73
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656718"
---
# <a name="finalstate-activity-designer"></a>FinalState 활동 디자이너
<xref:System.Activities.Core.Presentation.FinalState> 디자이너는 상태 시스템 인스턴스를 종료하는 <xref:System.Activities.Statements.State>를 만드는 데 사용됩니다.

## <a name="using-the-finalstate-activity-designer"></a>FinalState 활동 디자이너 사용
 상태 시스템에서 종료 상태로 미리 구성 된 <xref:System.Activities.Statements.State>를 만드는 데는 **상태 디자이너가** 사용 됩니다. @No__t_1 activity designer를 사용 하 여 만든 <xref:System.Activities.Statements.State> <xref:System.Activities.Statements.State.IsFinal%2A> 속성이 **true**로 설정 되 고, <xref:System.Activities.Statements.State.Exit%2A> 활동이 없고 해당 활동에서 발생 하는 전환이 없습니다. @No__t_0 activity designer를 사용 하 여 상태 시스템에서 종료 상태로 미리 구성 된 <xref:System.Activities.Statements.State> 활동을 추가 하려면 **도구 상자** 의 **상태 시스템** 섹션에서 **상태 활동 디자이너를 끌어** 놓습니다. workflow designer. <xref:System.Activities.Core.Presentation.FinalState> 활동 디자이너를 <xref:System.Activities.Statements.StateMachine>에 끌어 놓고 나중에 전환을 추가하거나 <xref:System.Activities.Core.Presentation.FinalState> 활동 디자이너를 끌어 놓을 때 전환을 만들 수 있습니다. 전환 만들기에 대 한 자세한 내용은 [전환](../workflow-designer/transition-activity-designer.md)을 참조 하세요.

### <a name="state-activity-properties-in-the-workflow-designer"></a>Workflow Designer의 State 활동 속성
 다음 표에서는 <xref:System.Activities.Core.Presentation.FinalState> 디자이너를 사용하여 설정할 수 있는 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다. 이러한 일부 속성은 속성 표에서 편집할 수 있으며 일부 속성은 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필요한 공간|사용 현황|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.State> 활동 디자이너의 이름을 지정합니다. 기본값은 **State**입니다. 속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다. <xref:System.Activities.Statements.State.DisplayName%2A>은 워크플로 디자이너 상단에 표시되는 이동 경로 탐색에 사용됩니다.<br /><br /> <xref:System.Activities.Statements.State.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.State.Entry%2A>|False|이 상태가 전환될 때 발생하는 동작을 지정합니다. **도구 상자** 에서 활동을 끌어 상태의 <xref:System.Activities.Statements.State.Entry%2A> 섹션에 놓으면이 값을 설정할 수 있습니다.|

## <a name="see-also"></a>관련 항목:
 [StateMachine](../workflow-designer/statemachine-activity-designer.md) [상태](../workflow-designer/state-activity-designer.md) [전환](../workflow-designer/transition-activity-designer.md)