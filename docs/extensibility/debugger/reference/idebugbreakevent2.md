---
title: IDebugBreakEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakEvent2
helpviewer_keywords:
- IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fdefbfa71ed220eed6e3f32ee95c02197f58a85d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923429"
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
이 인터페이스는 비동기 중단 성공적으로 완료 되었음을 나타내는 세션 디버그 관리자 SDM ()를 알려 줍니다.

## <a name="syntax"></a>구문

```
IDebugBreakEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 DE 프로그램에서 사용자 중단을 지원 하기 위해이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 (SDM 사용 [QueryInterface](/cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스).

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 SDM 호출 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 사용자가 일시 중지 하려면 디버깅 중인 프로그램을 요청 하는 경우. 프로그램이 성공적으로 일시 중지 된 경우는 DE 보냅니다는 `IDebugBreakEvent2` 이벤트입니다. 이 이벤트를 사용 하 여 보냅니다 합니다 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM를 디버깅 중인 프로그램에 연결할 때 제공한 콜백 함수입니다.

## <a name="remarks"></a>설명
 예를 들어, 선택할 수 있는 합니다 **모두 중단** 명령을 합니다 **디버그** 무한 루프를 실행 하는 프로그램을 중단 하는 메뉴입니다. SDM 호출 하 여 중지 하도록 프로그램에 지시 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)합니다. DE 보냅니다 `IDebugBreakEvent2` 프로그램을 마지막으로 중지 합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)