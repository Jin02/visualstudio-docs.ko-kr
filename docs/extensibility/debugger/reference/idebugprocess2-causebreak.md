---
title: 아이디버그프로세스2:원인중단 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::CauseBreak
helpviewer_keywords:
- IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 298312ae285eed1de29a3092db900f06e8f7d19a
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80724165"
---
# <a name="idebugprocess2causebreak"></a>IDebugProcess2::CauseBreak
이 프로세스에서 코드를 실행 중인 다음 프로그램이 중지하고 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 이벤트 개체를 보내도록 요청합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CauseBreak( 
   void
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>Return Value
 성공하면 반환합니다. `S_OK` 그렇지 않으면 오류 코드를 반환합니다.

## <a name="see-also"></a>참조
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
