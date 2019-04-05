---
title: IEnumDebugPropertyInfo2::Skip | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugPropertyInfo2::Skip
helpviewer_keywords:
- IEnumDebugPropertyInfo2::Skip
ms.assetid: 0366c778-18eb-4065-a452-64b70c751a58
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b6cac15899adef12a4a06ab0b2dca3c051ecbd5e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58980703"
---
# <a name="ienumdebugpropertyinfo2skip"></a>IEnumDebugPropertyInfo2::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

지정 된 개수의 요소를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 요소 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우 `celt` 나머지 요소 수보다 큽니다; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 하는 경우 `celt` 수보다 큰 값 끝에 설정 되어 나머지 요소를 열거 및 `S_FALSE` 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)
