---
title: FlowSwitch&lt;T&gt; 활동 디자이너 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ccd3e328a904540dd03c85f53634dc1eaab96c6e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984923"
---
# <a name="flowswitchlttgt-activity-designer"></a>FlowSwitch&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.FlowSwitch%601> 활동은 두 개 이상의 대안 분기가 필요할 때 일치 기준에 따라 제어 흐름에 대한 분기를 제공하는 조건 노드입니다. 흐름 분기에 두 경로만 필요한 경우 <xref:System.Activities.Statements.FlowDecision> 활동을 대신 사용합니다.  
  
## <a name="the-flowswitcht-activity"></a>FlowSwitch\<T > 활동  
 합니다 <xref:System.Activities.Statements.FlowSwitch%601> 활동에 포함는 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 형식의 값을 반환 *T* (제네릭 매개 변수에 의해 지정 됨) 평가 하는 경우. 또한 이 활동에는 가능한 계산 결과와 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 개체 집합 간의 고유 매핑을 지정하는 <xref:System.Activities.Statements.FlowNode> 집합도 포함되어 있습니다. 합니다 <xref:System.Activities.Statements.FlowNode> 실행은 한 형식의 개체가 *T* 계산된 된 값과 일치 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>합니다. 일치하는 항목이 없는 case에 대해 선택적으로 <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> case를 제공할 수 있습니다.  
  
### <a name="using-the-flowswitcht-activity-designer"></a>FlowSwitch를 사용 하 여\<T > 활동 디자이너  
 **FlowSwitch\<T >** 활동 디자이너에서 찾을 수 있습니다 합니다 **순서도** 범주의 **도구 상자**, 합니다 클릭하여액세스**도구 상자** 탭의 왼쪽에는 [!INCLUDE[wfd2](../includes/wfd2-md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴 또는 CTRL + ALT + X를 누릅니다.)  
  
 **FlowSwitch\<T >** 활동 디자이너에서 끌 수 있습니다는 **도구 상자** 삭제에 및를 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 내에서 화면을 **순서도** 활동 디자이너입니다. 사용 하 여는 **유형 선택** 표시 형식을 지정 하는 창 (코드에서 연결 된를 <xref:System.Activities.Statements.FlowSwitch%601> 제네릭 매개 변수에 의해) 평가에서 얻은 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>합니다. 이 프로시저를 만듭니다는 <xref:System.Activities.Statements.FlowSwitch%601> 레이블이 지정 된 활동 **스위치** 내는 <xref:System.Activities.Statements.Flowchart> 활동입니다. 합니다 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 에 입력할 수 있습니다 합니다 **식** 상자는 **속성** 힌트 텍스트를 "VB 식 입력" 이라고 표시를 클릭 하 여 창.  
  
 위로 마우스를 가져가면 합니다 **FlowSwitch\<T >** 활동 디자이너 연결 하는 데 사용 되는 정사각형 핸들이 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 가장자리 주위에 표시를 합니다. 위로 끌어 놓은 후 합니다 **FlowSwitch < T\>**  활동 디자이너와 기타 활동 디자이너를 합니다 **순서도**, <xref:System.Activities.Activity> 나타내는 개체를 함께 연결할 준비가 되었습니다. 실행 순서를 지정 합니다. 중 하나를 만드는 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 연관 합니다 <xref:System.Activities.Statements.FlowSwitch%601>의 경계에 있는 정사각형 case 핸들 중 하나를 클릭 합니다 **FlowSwitch\<T >** 놓습니다 (마우스 단추를 누른 채) 핸들 중 하나를 위치 디자이너 위로 마우스를 가져가면 대상 활동 주변 비슷한 방식으로 나타납니다. 릴리스가 마우스 단추 및에서 화살표를 **FlowSwitch\<T >** 대상 디자이너를 나타내는이 경우가 표시 됩니다. 이 경우 화살표를 표시 하 고에서 편집할 수의 기본값은 **사례** 상자를 **속성** 창입니다.  
  
### <a name="the-flowswitcht-properties"></a>FlowSwitch\<T > 속성  
 다음 표에서는 <xref:System.Activities.Statements.FlowSwitch%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|True|실행 경로에서 전환할 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>를 결정하기 위해 계산할 식을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산으로 얻은 가능한 결과와 <xref:System.Activities.Statements.FlowNode> 개체 집합 간의 고유 매핑을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|True|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산이 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 개체에 포함된 값 중 하나와 일치하지 않을 경우의 매핑을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Flowchart](../workflow-designer/flowchart-activity-designers.md)   
 [Flowchart](../workflow-designer/flowchart-activity-designer.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)