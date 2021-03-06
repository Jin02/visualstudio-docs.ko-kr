---
title: IDebugThread2::GetlogicalThread | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e148fb0b9b043fc1717effca00d698ee14beb2f1
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80718846"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
디버그 엔진은 이 메서드를 구현하지 않습니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetLogicalThread( 
   IDebugStackFrame2*     pStackFrame,
   IDebugLogicalThread2** ppLogicalThread
);
```

```csharp
int GetLogicalThread( 
   IDebugStackFrame2        pStackFrame,
   out IDebugLogicalThread2 ppLogicalThread
);
```

## <a name="parameters"></a>매개 변수
`pStackFrame`\
【인】 스택 프레임을 나타내는 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 개체입니다.

`ppLogicalThread`\
【아웃】 연결된 `IDebugLogicalThread2` 논리 스레드를 나타내는 인터페이스를 반환합니다. 디버그 엔진 구현은 이 값을 null 값으로 설정해야 합니다.

## <a name="return-value"></a>Return Value
 디버그 엔진 구현은 `E_NOTIMPL`항상 반환됩니다.

## <a name="see-also"></a>참조
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
