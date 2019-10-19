---
title: 콘텐츠 정의 대화 상자 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d989f5a0c57e381041e8fe9c200aae1a76316ad8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656954"
---
# <a name="content-definition-dialog-box"></a>콘텐츠 정의 대화 상자
**콘텐츠 정의** 대화 상자는 [!INCLUDE[wfd1](../includes/wfd1-md.md)]에서 <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동의 **콘텐츠** 속성을 구성 하는 데 사용 됩니다. 이 상자를 사용 하는 activity designer [!INCLUDE[crabout](../includes/crabout-md.md)] [Send](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)및 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목을 참조 하세요.

 다음 표에서는 **상관 관계 초기화** 대화 상자의 UI (사용자 인터페이스) 요소에 대해 설명 합니다.

|UI 요소|설명|
|----------------|-----------------|
|**메시지**|메시지 **데이터** 식 텍스트 상자와 메시지 **유형** 드롭다운 목록 상자를 사용 하 여 유형을 사용 하 여 메시지 내용을 지정 합니다. 기본적으로 **콘텐츠 정의** 는 <xref:System.ServiceModel.Channels.Message> 또는 워크플로 서비스 정의 내에 메시지 계약 형식이 필요한 <xref:System.ServiceModel.Activities.ReceiveMessageContent>를 사용 합니다.|
|**매개 변수**|데이터 계약이 필요한 <xref:System.ServiceModel.Activities.ReceiveParametersContent>을 사용 하려면 **매개 변수** 라디오 단추를 클릭 합니다. 데이터 표를 사용하여 현재 워크플로의 가변 매개 변수에 값을 지정할 <xref:System.Activities.OutArgument> 키/값 쌍의 제네릭 컬렉션을 설정합니다.|

 **콘텐츠 정의** 대화 상자는 **Send**, **Receive**, **ReceiveAndSendReply**및 **SendAndReceiveReply** 디자이너에서 사용 됩니다. 비슷한 방법으로 각각의 디자이너에 액세스할 수 있으며 여기서는 Receive 디자이너로 액세스 절차를 설명하겠습니다.

 **Receive** 활동 디자이너를 **도구 상자** 에서 끌어다가 일반적으로 활동을 배치 하는 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 화면에 놓을 수 있습니다. 그러면 기본 <xref:System.ServiceModel.Activities.Receive>인 Receive라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. **Receive** 활동 디자이너를 선택 하 고 속성 표에서 **콘텐츠** 속성의 (내용) 텍스트 옆에 있는 줄임표 단추를 클릭 하 여 **콘텐츠 정의** 대화 상자를 표시 합니다.

 콘텐츠는 <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동의 **메시지** 섹션 또는 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동의 **매개 변수** 섹션 내에서 지정할 수 있습니다.

## <a name="see-also"></a>관련 항목:
 [워크플로 디자이너 UI 도움말](../workflow-designer/workflow-designer-ui-help.md)