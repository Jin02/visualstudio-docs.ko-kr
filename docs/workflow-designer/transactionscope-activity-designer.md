---
title: 워크플로 디자이너-TransactionScope 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eef35457b9f28864929ad42919fff4e9afdcb0d5
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76114814"
---
# <a name="transactionscope-activity-designer"></a>TransactionScope 활동 디자이너

**TransactionScope** 활동 디자이너는 <xref:System.Activities.Statements.TransactionScope> 활동을 만들고 구성 하는 데 사용 됩니다.

## <a name="the-transactionscope-activity"></a>TransactionScope 활동

<xref:System.Activities.Statements.TransactionScope> 활동은 단일 트랜잭션에 포함된 활동을 실행합니다. 해당 트랜잭션의 <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동 및 다른 모든 참가자가 성공적으로 완료되면 트랜잭션이 커밋됩니다.

### <a name="using-the-transactionscope-activity-designer"></a>TransactionScope 활동 디자이너 사용

**도구 상자**의 **트랜잭션** 범주에서 **TransactionScope** 활동 디자이너에 액세스 합니다. **TransactionScope** 활동 디자이너를 **도구 상자** 에서 끌어와 같이 일반적으로 활동을 <xref:System.Activities.Statements.Sequence>배치 하는 아무 곳에 나 워크플로 디자이너 화면에 놓을 수 있습니다. 그러면 기본 <xref:System.Activities.Statements.TransactionScope>인 TransactionScope라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 **TransactionScope** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 편집할 수 있습니다.

### <a name="the-transactionscope-properties"></a>TransactionScope 속성

다음 표에서는 <xref:System.Activities.Statements.TransactionScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. <xref:System.Activities.Activity.DisplayName%2A> 및 <xref:System.Activities.Statements.TransactionScope.Body%2A> 속성은 워크플로 디자이너 화면에서 편집할 수 있습니다. 그러나 다른 속성은 속성 표에서 편집해야 합니다.

|속성 이름|필수|용도|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TransactionScope> 활동의 선택적 이름입니다. 기본값은 TransactionScope입니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|단일 트랜잭션에서 실행할 활동을 지정합니다. <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동을 추가 하려면 **도구 상자** 의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **TransactionScope** 활동 디자이너의 **본문** 상자로 끌어 놓습니다.|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|이 <xref:System.Transactions.IsolationLevel>의 <xref:System.Activities.Statements.TransactionScope>을 지정합니다.|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|트랜잭션을 완료해야 하는 시간 간격(시:분:초를 의미하는 00:00:00 형식)을 지정합니다. 기본값은 1분입니다(00:01:00).|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|True|트랜잭션이 중단되면 워크플로를 중단할지 여부를 나타내는 값을 지정합니다.|

## <a name="see-also"></a>참조

- [트랜잭션](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)
