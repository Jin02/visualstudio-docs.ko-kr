---
title: IDiaPropertyStorage::ReadLONG | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 08661272bea779ff0789619d58bf6f2837a21917
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984238"
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

읽고 `LONG` 속성 집합의 값입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT ReadDLONG (   
   PROPID id,  
   LONG*  pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 읽을 속성의 식별자 (`PROPID` 으로 WTypes.h에 정의 된 `ULONG`).  
  
 `pValue`  
 [out] 속성 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_INVALIDARG` 형식의 속성이 없는 경우 `LONG`합니다.  
  
## <a name="remarks"></a>설명  
 `LONG` Windows 32 비트 부호 있는 정수에 의해 정의 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
