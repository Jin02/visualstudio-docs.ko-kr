---
title: IDebugProgram2::GetName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetName
helpviewer_keywords:
- IDebugProgram2::GetName
ms.assetid: a54cbf13-b3e3-4c9f-8b8d-13573232dfb0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2f7faa4b864824a46e30f05f6465eee30f4a3e16
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210187"
---
# <a name="idebugprogram2getname"></a>IDebugProgram2::GetName
프로그램의 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName( 
   out string pbstrName
);
```

## <a name="parameters"></a>매개 변수
`pbstrName`\
[out] 프로그램의 이름을 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드에서 반환 된 이름은 항상 프로그램을 설명 하는 친숙 하 고 사용자 표시 이름이입니다.

## <a name="see-also"></a>참고자료
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)