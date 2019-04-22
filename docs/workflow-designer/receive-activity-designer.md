---
title: 워크플로 디자이너-Receive 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bcab59a631b1dbf9c85c7bff2454a42e97accff8
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59649218"
---
# <a name="receive-activity-designer"></a>Receive 활동 디자이너

합니다 **수신** 활동 디자이너는 만들기 및 구성 하는 데 사용 되는 <xref:System.ServiceModel.Activities.Receive> 활동입니다. <xref:System.ServiceModel.Activities.Receive> 활동은 기본 제공 형식(예:  <xref:System.ServiceModel.Channels.Message>, <xref:System.IO.Stream> 또는 <xref:System.Xml.Linq.XElement>)이거나 serialize될 수 있는 응용 프로그램 정의 데이터 계약, 메시지 계약 또는 XML 클래스 중 하나인 메시지를 수신하는 활동입니다.

## <a name="the-receive-activity"></a>Receive 활동

<xref:System.ServiceModel.Activities.Receive> 활동은 사용되는 수신 콘텐츠의 형식에 따라 단일 항목 또는 여러 항목을 수신할 수 있습니다. <xref:System.ServiceModel.Activities.SendReply> 활동은 서비스에 대한 요청/응답 메시지 교환 패턴 중 메시지를 받는 <xref:System.ServiceModel.Activities.Receive> 활동에 바인딩될 수 있습니다.

### <a name="using-the-receive-activity-designer"></a>Receive 활동 디자이너 사용

액세스는 **수신** 활동 디자이너를 **메시징** 범주의 합니다 **도구 상자**. 합니다 **수신** 활동 디자이너에서 끌 수 있습니다 합니다 **도구 상자** 일반적으로 활동을 배치 하는 위치는 워크플로 디자이너 화면에 끌어 놓 및 합니다. 그러면 기본 <xref:System.ServiceModel.Activities.Receive>인 Receive라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수 있습니다 합니다 **수신** 활동 디자이너 또는 합니다 **DisplayName** 속성 그리드의 상자.

만들려면를 <xref:System.ServiceModel.Activities.SendReply> 활동 선택한에 바인딩합니다 <xref:System.ServiceModel.Activities.Receive> 활동을 마우스 오른쪽 단추로 클릭는 **수신** 활동 디자이너를 클릭 합니다 **SendReply 만들기** 상황에 맞는 메뉴 항목 및 **SendReplyToReceive** 디자이너 아래에 표시 된 **수신** 디자이너입니다. <xref:System.ServiceModel.Activities.SendReply> 활동은 서비스측에 대한 요청/응답 메시지 교환 패턴 중 응답 메시지를 보내는 활동입니다. 사용 하 여 구성할 수 있습니다 합니다 **SendReplyToReceive** 디자이너입니다.

또는 합니다 **ReceiveAndSendReply** 템플릿 디자이너를 **메시징** 범주의 합니다 **도구 상자** 미리 구성 된 쌍을만드는데사용할수있습니다<xref:System.ServiceModel.Activities.Receive>고 <xref:System.ServiceModel.Activities.SendReply> 활동입니다. 사용에 대 한 자세한 합니다 **ReceiveAndSendReply** 및 **SendReplyToReceive** 템플릿을 참조 합니다 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md) 항목입니다.

### <a name="the-receive-activity-properties"></a>Receive 활동 속성

다음 표에서는 <xref:System.ServiceModel.Activities.Receive> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 속성 표에서 또는 워크플로 디자이너 화면에서 이러한 속성을 편집할 수 있습니다. 필수 속성은 <xref:System.ServiceModel.Activities.Receive.OperationName%2A> 속성뿐입니다.

| 속성 이름 | 필수 | 사용법 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.Receive> 활동의 이름을 지정합니다. 기본값은 Receive입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>에 꼭 기본값 이외의 값을 사용할 필요는 없지만 그런 값을 사용하는 것이 좋습니다. |
| <xref:System.ServiceModel.Activities.Receive.OperationName%2A> | True | 이 <xref:System.ServiceModel.Activities.Receive> 활동에 의해 구현되는 서비스 작업의 이름을 지정합니다. 이 속성의 기본값 생성을 사용 하는 **작업** 속성 경우 합니다 **작업** 속성이 명시적으로 설정 되어 있지. |
| <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> | False | 서비스 계약의 이름을 지정합니다. 이 속성은 서비스 작업을 개별 서비스 계약으로 그룹화하는 데 사용됩니다. 동일한 <xref:System.ServiceModel.Activities.Receive>을 가진 모든 <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> 활동은 동일한 서비스 계약(WSDL 포트 형식)으로 그룹화됩니다. 기본값은 최상위 (루트) 활동의 정규화 된 CLR 이름입니다. |
| <xref:System.ServiceModel.Activities.Receive.Content%2A> | False | 받을 메시지 또는 매개 변수 콘텐츠를 지정합니다. <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동이거나 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동일 수 있습니다. 옆의 줄임표 단추를 선택 하 여이 속성을 편집 합니다 **콘텐츠** 클릭 하거나 속성 표의 필드를 **정의 하는 중...**  옆에 있는 단추를 **콘텐츠** 에 레이블 합니다 **수신** activity designer 화면. 모두 표시 합니다 **콘텐츠 정의** 대화 합니다. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> | False | <xref:System.ServiceModel.Activities.Receive> 개체가 있는 워크플로의 서비스 작업에 포함된 <xref:System.ServiceModel.MessageQuerySet> 활동 간의 상관 관계를 지정합니다. 다음 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 열려면 속성 표에서 속성을 **CorrelatesOn 정의** 대화 상자. 이 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> | False | 메시지를 적절한 워크플로 인스턴스로 라우팅하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다.<br /><br /> 다음 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> 열려면 속성 표에서 속성을 **식 편집기** 대화 상자. 이 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [방법: 식 편집기를 사용 하 여](../workflow-designer/how-to-use-the-expression-editor.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> | False | 워크플로 내에서 이 <xref:System.ServiceModel.Activities.CorrelationInitializer> 활동을 구성하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 여러 개 초기화하는 <xref:System.ServiceModel.Activities.Receive> 개체 컬렉션을 지정합니다. 다음 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 열려면 속성 표에서 속성을 **상관 관계 이니셜라이저 추가** 대화 상자. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> | False | 메시지가 기존 워크플로 인스턴스와 연관되지 않은 경우 메시지를 처리하기 위해 새 워크플로 인스턴스를 만들지 여부를 결정하는 값을 지정합니다. 값 설정 된 경우 **true**, 메시지가 기존 워크플로 인스턴스와 상관 관계가 없는 것 때 메시지를 처리 하는 데 새 워크플로 인스턴스가 만들어집니다. |
| <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> | False | 이 <xref:System.ServiceModel.Activities.Receive> 활동에 의해 구현되는 서비스 작업의 알려진 형식 컬렉션을 지정합니다. 이 속성은 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>로 설정된 <xref:System.Runtime.Serialization.DataContractSerializer> 속성과 함께 사용해야 합니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 경우 무시됩니다.<br /><br /> 옆에 있는 줄임표 단추를 선택 합니다 **KnownTypes** 표시할 속성 표의 필드를 **형식 컬렉션 편집기** 대화 상자를 사용 하 여 관련 형식을 추가할 수 있습니다. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> | False | 메시지의 <xref:System.Net.Security.ProtectionLevel>을 지정합니다.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> 인증만 의미 합니다.<br />2. <xref:System.Net.Security.ProtectionLevel> 수단으로 전송 되는 데이터의 무결성을 보장 하는 데 데이터를 서명 합니다.<br />3. <xref:System.Net.Security.ProtectionLevel> 암호화 및 전송 되는 데이터의 무결성 및 기밀성을 보장 하기 위해 데이터에 서명 합니다. |
| <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> | False | <xref:System.ServiceModel.Activities.Receive> 활동에 의해 구현되는 서비스 작업에 사용할 serializer의 형식을 지정합니다. 기본값은 <xref:System.Runtime.Serialization.DataContractSerializer>이며, 제공된 데이터 계약을 사용하는 XML 스트림 또는 문서에 형식 인스턴스를 serialize 및 deserialize합니다. XML에 대한 제어를 강화해야 하는 경우에도 <xref:System.Xml.Serialization.XmlSerializer>를 사용할 수 있습니다. |
| <xref:System.ServiceModel.Activities.Receive.Action%2A> | False | 메시지의 동작 헤더를 지정합니다. 명시적으로 설정 하지 않으면 기본값인: `https://tempuri.org/{service contract namespace}/{service contract name}/{operation name}`합니다. |

## <a name="see-also"></a>참고자료

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
