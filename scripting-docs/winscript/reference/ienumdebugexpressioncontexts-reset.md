---
title: 'IEnumDebugExpressionContexts:: Reset | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExpressionContexts.Reset
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugExpressionContexts::Reset
ms.assetid: b471954f-d3b5-4c99-88e1-1de3e3f72c7f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c86f7095cb242f96737e4744f5056f9fb36d384
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577136"
---
# <a name="ienumdebugexpressioncontextsreset"></a>IEnumDebugExpressionContexts::Reset
열거형 시퀀스를 시작 부분으로 다시 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Reset();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수를 사용 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 이 메서드는 열거 시퀀스를 시작 부분으로 다시 설정 합니다.  
  
## <a name="see-also"></a>참조  
 [IEnumDebugExpressionContexts 인터페이스](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)