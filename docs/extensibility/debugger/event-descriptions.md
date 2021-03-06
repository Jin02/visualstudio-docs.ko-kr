---
title: 이벤트 설명 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3c2582717fd4da3b833da90a951f9b8f72a59f71
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80738796"
---
# <a name="event-descriptions"></a>이벤트 설명
각 이벤트 유형에는 특정 목적이 있습니다.

## <a name="events-and-the-reasons-for-their-use"></a>이벤트 및 그 사용 이유

|이벤트|설명|
|-----------|-----------------|
|문서 이벤트 활성화|디버그 엔진(DE)이 IDE가 문서를 열거나 포그라운드로 가져오기를 원할 때 발생합니다.|
|중단점 바운드 또는 중단점 오류 이벤트|중단점이 바인딩되거나 중단점이 바인딩할 수 없고 오류가 반환될 때 전송됩니다.|
|중단점 언바운드 이벤트|바인딩된 중단점이 코드에서 바인딩해제될 때 발생합니다.|
|이벤트를 중지할 수 있습니다.|사용자가 코드의 지정된 지점에서 중지할지 여부를 결정하기 위해 IDE로 전송됩니다.|
|중단점 이벤트|코드 또는 데이터 중단점이 적중할 때 발생합니다.|
|텍스트 이벤트 문서|문서의 텍스트가 변경될 때 발생합니다. 이러한 이벤트는 메서드를 `IDebugEventCallBack2::Event` 통해 전송되지 않습니다.|
|엔진 생성 이벤트|엔진이 처음 생성될 때 전송됩니다.|
|진입점 이벤트|디버깅 중인 프로그램이 초기화 코드를 실행하고 첫 번째 사용자 진입점에 도달할 때 전송됩니다.|
|예외 이벤트|실행 중인 프로그램이 예외에 도달하면 전송됩니다.|
|표현식 평가 전체 이벤트|비동기 식 평가가 완료되면 전송됩니다.|
|기호 이벤트 찾기|DE가 모듈에 대한 기호를 찾아달라고 사용자에게 요청해야 할 때마다 전송됩니다.|
|전체 이벤트 로드|초기 프로그램 로드가 완료되고 첫 번째 코드가 프로그램에서 실행될 때만 전송됩니다.|
|메시지 이벤트|메시지가 사용자에게 전송될 때 전송됩니다.|
|모듈 로드 이벤트|새 모듈이 로드되거나 언로드될 때 전송됩니다.|
|출력 문자열 이벤트|프로그램이 디버그 출력을 작성할 때 전송됩니다.|
|이벤트 만들기 및 삭제|Visual Studio IDE가 디버깅 중인 프로그램의 상태를 추적할 수 있도록 프로세스, 프로그램, 속성, 세션 및 스레드의 생성 또는 소멸을 알리기 위해 전송됩니다.|
|단계 완료 이벤트|단계가 완료되면 전송됩니다.|
|스레드 이름 변경 이벤트|사용자가 스레드이름을 변경할 때 전송됩니다.|
|프로그램 이름 변경 이벤트|사용자가 프로그램의 이름을 변경할 때 전송됩니다.|

## <a name="see-also"></a>참조
- [이벤트 전송](../../extensibility/debugger/sending-events.md)
