---
title: IDebugDisassemblyStream2::GetCodeLocationId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8aca9231f8b5024199e9ee2bc79cb2d33b31628c
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205006"
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
특정 코드 컨텍스트에 대 한 코드 위치 식별자를 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCodeLocationId( 
   IDebugCodeContext2* pCodeContext,
   UINT64*             puCodeLocationId
);
```

```csharp
int GetCodeLocationId( 
   IDebugCodeContext2 pCodeContext,
   out ulong          puCodeLocationId
);
```

## <a name="parameters"></a>매개 변수
`pCodeContext`\
[in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 식별자로 변환 될 개체입니다.

`puCodeLocationId` [out] 코드 위치 식별자를 반환합니다. 설명 부분을 참조하세요.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_CODE_CONTEXT_OUT_OF_SCOPE` 코드 컨텍스트에 유효 하지만 범위 밖에 있습니다.

## <a name="remarks"></a>설명
 코드 위치 식별자 디스어셈블리를 지 원하는 디버그 엔진 (DE)와 관련이 있습니다. 이 위치 식별자 코드의 위치를 추적 하는 DE에서 내부적으로 사용 및는 일반적으로 주소 또는 일종의 오프셋입니다. 유일한 요구 사항은 한 위치의 코드 컨텍스트를 사용 하면 다른 위치의 코드 컨텍스트 보다 작으면 첫 번째 코드 컨텍스트에서의 해당 코드 위치 식별자도 보다 작아야 두 번째 코드 컨텍스트의 코드 위치 식별자를 합니다.

 코드 위치 식별자의 코드 컨텍스트를 검색 하려면 호출을 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) 메서드.

## <a name="see-also"></a>참고자료
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)