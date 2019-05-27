---
title: IDebugObject2::IsUserData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c9d791a181227b481f27f9347897fce4dda158a2
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66209778"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
개체 사용자 데이터를 나타내는지 여부를 확인 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsUserData(
   BOOL* pfUser
);
```

```csharp
int IsUserData(
   out int pfUser
);
```

## <a name="parameters"></a>매개 변수
`pfUser`\
[out] 0이 아닌 값을 반환 합니다 (`TRUE`) 개체가 사용자 데이터를 나타내는 0 (`FALSE`) 그렇지 않은 경우.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 사용자 데이터는 JustMyCode (사용자 코드 및 스택 추적에 표시 되므로 모듈을 표시 하는 사용자 구성 가능 옵션)로 지정 된 모듈의 일부인 모든 개체입니다.

## <a name="see-also"></a>참고자료
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)