---
title: 'IEnumDebugCodeContexts:: Skip | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Skip
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Skip
ms.assetid: ba917f57-f7a9-419f-96d6-8f4378b12c57
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a16343b24a640341009758345b17f86e94b7b2ed
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577197"
---
# <a name="ienumdebugcodecontextsskip"></a>IEnumDebugCodeContexts::Skip
열거형 시퀀스에서 지정 된 개수의 세그먼트를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 진행 건너뛸 열거 시퀀스의 세그먼트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 이 메서드는 열거형 시퀀스에서 지정 된 개수의 세그먼트를 건너뜁니다.  
  
## <a name="see-also"></a>참조  
 [IEnumDebugCodeContexts 인터페이스](../../winscript/reference/ienumdebugcodecontexts-interface.md)