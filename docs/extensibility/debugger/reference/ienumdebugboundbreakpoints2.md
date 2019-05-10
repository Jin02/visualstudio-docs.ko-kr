---
title: IEnumDebugBoundBreakpoints2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugBoundBreakpoints2
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2
ms.assetid: ea03e7e1-28d6-40b7-8097-bbb61d3b7caa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5eb63aea8adef546e9266d2c1eaccc842f89feb6
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223470"
---
# <a name="ienumdebugboundbreakpoints2"></a>IEnumDebugBoundBreakpoints2
이 인터페이스는 보류 중단점과 연결 된 바인딩된 중단점 열거 또는 중단점이 바인딩된 이벤트입니다.

## <a name="syntax"></a>구문

```
IEnumDebugBoundBreakpoints2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 디버그 엔진 (DE) 중단점에 대 한 지원의 일부로이 인터페이스를 구현합니다. 중단점 지원 되는 경우이 인터페이스를 구현 해야 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 Visual Studio를 호출합니다.

- [EnumBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 트리거된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.

- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) 바인딩된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.

- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md) 해당 보류 중인 중단점에 바인딩된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugBoundBreakpoints2`합니다.

|메서드|설명|
|------------|-----------------|
|[다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)|열거형 시퀀스에 대 한 바인딩된 중단점의 지정된 된 수를 검색 합니다.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-skip.md)|열거형 시퀀스에 대 한 바인딩된 중단점의 지정된 된 수를 건너뜁니다.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-getcount.md)|열거자에서 바인딩된 중단점의 수를 가져옵니다.|

## <a name="remarks"></a>설명
 Visual Studio IDE에서 중단점의 표시 내용을 업데이트 하려면이 인터페이스를 나타내는 바인딩된 중단점을 사용 합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고자료
- [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)