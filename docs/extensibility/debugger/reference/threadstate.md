---
title: THREADSTATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3019671b98d3eb17c92d97c368f2f7338ee55a1d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460707"
---
# <a name="threadstate"></a>THREADSTATE
스레드의 상태를 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
typedef DWORD THREADSTATE;
```

```csharp
public enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
```

## <a name="fields"></a>필드
 `THREADSTATE_RUNNING`\
 스레드가 실행 중임을 나타냅니다.

 `THREADSTATE_STOPPED`\
 스레드가 중단점으로 인해 중지 되었음을 나타냅니다.

 `THREADSTATE_FRESH`\
 스레드를 만든 했지만 코드가 아직 실행 되지 않음을 나타냅니다.

 `THREADSTATE_DEAD`\
 스레드 소멸 임을 나타냅니다.

 `THREADSTATE_FROZEN`\
 스레드를 고정 나타냅니다 (없습니다 실행을 수행할 수 있습니다.).

## <a name="remarks"></a>설명
 에 사용 되는 합니다 `dwThreadState` 필드를 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)