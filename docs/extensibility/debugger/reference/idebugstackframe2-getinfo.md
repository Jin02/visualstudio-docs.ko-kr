---
title: IDebugStackFrame2::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetInfo
helpviewer_keywords:
- IDebugStackFrame2::GetInfo
ms.assetid: 19c6870b-b94e-453c-bf19-82ce95b79d26
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0aeb888b2cc81dac6157ef0944703227799e61e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868756"
---
# <a name="idebugstackframe2getinfo"></a>IDebugStackFrame2::GetInfo
스택 프레임에 대 한 설명을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetInfo ( 
   FRAMEINFO_FLAGS dwFieldSpec,
   UINT            nRadix,
   FRAMEINFO*      pFrameInfo
);
```

```csharp
int GetInfo ( 
   enum_FRAMEINFO_FLAGS dwFieldSpec,
   uint                 nRadix,
   FRAMEINFO[]          pFrameInfo
);
```

#### <a name="parameters"></a>매개 변수
 `dwFieldSpec`

 [in] 플래그의 조합을 합니다 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 의 필드를 지정 하는 열거형을 `pFrameInfo` 입력할 매개 변수는.

 `nRadix`

 [in] 모든 숫자 정보를 서식 지정 하는 데 사용할 기 수입니다.

 `pFrameInfo`

 [out] A [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 는 스택 프레임에 대 한 설명을 포함 하는 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)