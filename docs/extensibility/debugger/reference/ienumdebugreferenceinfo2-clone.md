---
title: IEnumDebug참조정보2::클론 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2::Clone
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Clone
ms.assetid: 49c5a301-a33a-428f-b83b-e734c71af4ef
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d522fb7a9b63f634f312924e3c0b0337688aa430
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80715315"
---
# <a name="ienumdebugreferenceinfo2clone"></a>IEnumDebugReferenceInfo2::Clone
현재 열거형의 복사본을 별도의 개체로 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Clone(
   IEnumDebugReferenceInfo2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugReferenceInfo2 ppEnum
);
```

## <a name="parameters"></a>매개 변수
`ppEnum`\
【아웃】 이 열거형의 복사본을 별도의 개체로 반환합니다.

## <a name="return-value"></a>Return Value
 성공하면 반환합니다. `S_OK` 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 열거형의 복사본은 이 메서드가 호출될 때원본과 동일한 상태를 가짐입니다. 그러나 복사본과 원본의 상태는 분리되어 개별적으로 변경할 수 있습니다.

## <a name="see-also"></a>참조
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
