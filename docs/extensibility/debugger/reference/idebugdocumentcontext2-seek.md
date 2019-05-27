---
title: IDebugDocumentContext2::Seek | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbba9b1208ced73c24fbb7050bb4d7e2f8266d52
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66201174"
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
문이나 줄의 지정된 된 수 만큼 문서 컨텍스트를 이동합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Seek( 
   int                      nCount,
   IDebugDocumentContext2** ppDocContext
);
```

```cpp
int Seek( 
   int                        nCount,
   out IDebugDocumentContext2 ppDocContext
);
```

## <a name="parameters"></a>매개 변수
`nCount`\
[in] 문 또는 문서 컨텍스트에 따라 미리 이동할 줄 수입니다.

`ppDocContext`\
[out] 반환 된 새 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 새 위치를 사용 하 여 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)