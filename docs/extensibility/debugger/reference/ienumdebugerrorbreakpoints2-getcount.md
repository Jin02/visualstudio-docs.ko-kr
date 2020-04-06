---
title: IEnumDebug오류 중단점2::겟카운트 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
ms.assetid: 56f7bb70-d55b-471c-8c65-09a9e7f4938e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 867b0e699ac1e4874a6ac3db12eb52daa27758d8
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80716998"
---
# <a name="ienumdebugerrorbreakpoints2getcount"></a>IEnumDebugErrorBreakpoints2::GetCount
열거형의 요소 수를 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

## <a name="parameters"></a>매개 변수
`pcelt`\
【아웃】 열거형의 요소 수를 반환합니다.

## <a name="return-value"></a>Return Value
 성공하면 반환합니다. `S_OK` 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 이 메서드는 `Next`"에 `Clone` `Skip`이 및 `Reset` 메서드만 구현해야 하는 지정하는 관습COM 열거 인터페이스의 일부가 아닙니다.

## <a name="see-also"></a>참조
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
