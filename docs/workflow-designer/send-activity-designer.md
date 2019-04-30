---
title: 워크플로 디자이너-Send 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d27bd9be1b769215dd77d1e906a5698e17bd18b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009131"
---
# <a name="send-activity-designer"></a>Sent 활동 디자이너

**보낼** 활동 디자이너는 만들기 및 구성 하는 데 사용 되는 <xref:System.ServiceModel.Activities.Send> 활동입니다.

## <a name="the-send-activity"></a>Send 활동

 <xref:System.ServiceModel.Activities.Send> 활동은 서비스에 메시지를 보내는 데 사용됩니다. <xref:System.ServiceModel.Activities.ReceiveReply> 활동은 클라이언트측에서 요청/응답 메시지 교환 패턴 중 메시지를 받는 <xref:System.ServiceModel.Activities.Send> 활동에 바인딩될 수 있습니다.

### <a name="using-the-send-activity-designer"></a>Send 활동 디자이너 사용

액세스는 **보낼** 활동 디자이너를 **메시징** 범주의 **도구 상자**. **보낼** 활동 디자이너에서 끌 수 있습니다 합니다 **도구 상자** 일반적으로 활동을 배치 하는 위치는 워크플로 디자이너 화면에 끌어 놓 및. 그러면 기본 <xref:System.ServiceModel.Activities.Send>인 Send라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수 있습니다 합니다 **보낼** 활동 디자이너 또는 **DisplayName** 속성 그리드의 상자.

만들려면를 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 선택한에 바인딩합니다 <xref:System.ServiceModel.Activities.Send> 활동을 마우스 오른쪽 단추로 클릭는 **보내기** 활동 디자이너를 클릭 합니다 **ReceiveReply 만들기** 상황에 맞는 메뉴 항목 및 **ReceiveReplyForSend** 디자이너 아래에 표시 합니다 **보낼** 디자이너입니다. <xref:System.ServiceModel.Activities.ReceiveReply> 활동은 요청/응답 메시지 교환 패턴 중 클라이언트에서 메시지를 받는 활동입니다. 사용 하 여 구성할 수 있습니다 합니다 **ReceiveReplyForSend** 디자이너입니다.

또는 합니다 **SendAndReceiveReply** 템플릿 디자이너를 **메시징** 범주의 합니다 **도구 상자** 미리 구성 된 쌍을만드는데사용할수있습니다<xref:System.ServiceModel.Activities.Send>고 <xref:System.ServiceModel.Activities.ReceiveReply> 활동입니다. 사용에 대 한 자세한 합니다 **SendAndReceiveReply** 및 **ReceiveReplyForSend** 참조 하십시오.는 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목입니다.

### <a name="the-send-activity-properties"></a>Send 활동 속성

다음 표에서는 <xref:System.ServiceModel.Activities.Send> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 속성 표에서 또는 워크플로 디자이너 화면에서 이러한 속성을 편집할 수 있습니다.

| 속성 이름 | 필수 | 사용법 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.Send> 활동의 이름입니다. 기본값은 Send입니다. <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다. |
| <xref:System.ServiceModel.Activities.Send.OperationName%2A> | True | 이 <xref:System.ServiceModel.Activities.Send> 활동에 의해 호출되는 서비스 작업의 이름입니다. 이 속성의 기본값 생성을 사용 하는 **작업** 속성 경우 합니다 **작업** 속성이 명시적으로 설정 되어 있지. |
| <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> | True | 호출할 서비스가 구현하는 서비스 계약의 이름입니다. |
| <xref:System.ServiceModel.Activities.Send.Content%2A> | False | 받을 메시지 또는 매개 변수 콘텐츠를 지정합니다. <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동이거나 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동일 수 있습니다. 옆의 줄임표 단추를 선택 하 여이 속성을 편집 합니다 **콘텐츠** 클릭 하거나 속성 표의 필드를 **정의 하는 중...**  옆에 있는 단추를 **콘텐츠** 에 레이블 합니다 **수신** activity designer 화면. 모두 표시 합니다 **콘텐츠 정의** 대화 합니다. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> | False | 메시지를 적절한 워크플로 인스턴스로 라우팅하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다.<br /><br /> 다음 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> 열려면 속성 표에서 속성을 **식 편집기** 대화 상자. 이 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [방법: 식 편집기를 사용 하 여](../workflow-designer/how-to-use-the-expression-editor.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> | False | 워크플로 내에서 이 <xref:System.ServiceModel.Activities.CorrelationInitializer> 활동을 구성하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 여러 개 초기화하는 <xref:System.ServiceModel.Activities.Send> 개체 컬렉션을 지정합니다. 다음 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> 열려면 속성 표에서 속성을 **상관 관계 이니셜라이저 추가** 대화 상자. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> | False | 이 <xref:System.ServiceModel.Activities.Send> 활동으로 호출되는 서비스 작업에 대한 알려진 형식의 컬렉션입니다. 이 속성은 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>로 설정된 <xref:System.Runtime.Serialization.DataContractSerializer> 속성과 함께 사용해야 합니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 경우 무시됩니다.<br /><br /> 옆에 있는 줄임표 단추를 선택 합니다 **KnownTypes** 표시할 속성 표의 필드를 **형식 컬렉션 편집기** 대화는를 사용 하 여 관련 형식을 추가할 수 있습니다.<br /><br /> 옆에 있는 줄임표 단추를 선택 합니다 **KnownTypes** 표시할 속성 표의 필드를 **형식 컬렉션 편집기** 대화 상자를 사용 하 여 관련 형식을 추가할 수 있습니다. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목입니다. |
| <xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A> | True | 메시지의 <xref:System.Net.Security.ProtectionLevel>을 지정합니다.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> 인증만 의미 합니다.<br />2. <xref:System.Net.Security.ProtectionLevel> 수단으로 전송 되는 데이터의 무결성을 보장 하는 데 데이터를 서명 합니다.<br />3. <xref:System.Net.Security.ProtectionLevel> 암호화 및 전송 되는 데이터의 무결성 및 기밀성을 보장 하기 위해 데이터에 서명 합니다. |
| <xref:System.ServiceModel.Activities.Send.SerializerOption%2A> | True | <xref:System.ServiceModel.Activities.Send> 활동으로 호출되는 서비스 작업에 사용할 serializer입니다. 기본값은 <xref:System.Runtime.Serialization.DataContractSerializer>이며, 제공된 데이터 계약을 사용하여 형식 인스턴스를 XML 스트림 또는 문서로 serialize 및 deserialize합니다. |
| <xref:System.ServiceModel.Activities.Send.Action%2A> | False | 메시지의 동작 헤더를 지정합니다. 명시적으로 설정 하지 않으면 기본값인: https://tempuri.org/{service 계약 네임 스페이스} / {서비스 계약 이름} /} /{operation name}. <xref:System.ServiceModel.Activities.Send> 활동에 지정하는 경우 메시지를 받는 <xref:System.ServiceModel.Activities.Receive> 활동에 동일한 값이 있어야 메시지가 올바르게 배달됩니다. |
| <xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A> | | 메시지 수신자에게 허용되는 <xref:System.Security.Principal.TokenImpersonationLevel>입니다. 정도는 서버 프로세스를 대신할 수는 클라이언트 프로세스는 보안 가장 수준을 정의 합니다.<xref:System.Security.Principal.TokenImpersonationLevel> 가장 수준이 할당 되지 않은 것을 나타냅니다. <xref:System.Security.Principal.TokenImpersonationLevel>는 서버 프로세스에서 클라이언트의 식별 정보를 확보할 수 없어 해당 클라이언트를 가장할 수 없음을 의미합니다. <xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 보안 식별자 및 권한과 같은 클라이언트 관련 정보를 확보할 수 있지만 해당 클라이언트를 가장할 수 없음을 의미합니다. 이 기능은 자체 개체를 내보내는 서버(예: 테이블과 뷰를 내보내는 데이터베이스 제품)에 유용합니다. 서버는 검색된 클라이언트 보안 정보를 사용하여 클라이언트의 보안 컨텍스트를 사용하는 다른 서비스를 사용할 수는 없지만 액세스 위반 결정을 내릴 수 있습니다. <xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 로컬 시스템의 클라이언트 보안 컨텍스트를 가장할 수 있음을 의미합니다. 원격 시스템에서는 서버가 클라이언트를 가장할 수 없습니다. <xref:System.Security.Principal.TokenImpersonationLevel>은 서버 프로세스에서 원격 시스템의 클라이언트 보안 컨텍스트를 가장할 수 있음을 의미합니다. |
| <xref:System.ServiceModel.Activities.Send.Endpoint%2A> | | <xref:System.ServiceModel.Endpoint> 활동에서 메시지를 보내는 <xref:System.ServiceModel.Activities.Send>입니다. 이 속성을 설정 하는 경우는 <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> 속성은 같아야 **null**합니다. |
| <xref:System.ServiceModel.Activities.Send.EndpointAddress%2A> | | 메시지가 전달될 <xref:System.ServiceModel.EndpointAddress>입니다. |
| <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> | | 엔드포인트 구성의 이름입니다. 이 속성은 구성 파일에서 엔드포인트를 구성할 때 설정됩니다. 이 속성에 지정 된 이름으로 설정 해야 합니다  **\<끝점 >** 프로그램 구성 파일의 요소입니다. 이 속성을 설정 하는 경우는 <xref:System.ServiceModel.Activities.Send.Endpoint%2A> 속성은 같아야 **null**합니다. |

## <a name="see-also"></a>참고자료

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)