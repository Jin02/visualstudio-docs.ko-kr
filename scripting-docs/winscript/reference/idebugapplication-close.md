---
title: 'IDebugApplication:: Close | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.Close
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::Close
ms.assetid: d19baa07-3f3b-47de-8185-5eb3e7ac8b46
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0445e9aed990da684efac6675e05183fd939973f
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575571"
---
# <a name="idebugapplicationclose"></a>IDebugApplication::Close
이 응용 프로그램이 모든 참조를 해제 하 고 비활성 상태로 전환 되도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Close();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수를 사용 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 일반적으로 응용 프로그램의 소유자는 응용 프로그램이 종료 될 때이 메서드를 호출 합니다.  
  
 이 메서드를 호출 하면 `IApplicationDebugger::onClose` 호출 됩니다.  
  
## <a name="see-also"></a>참조  
 [Idebugapplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)    
 [IApplicationDebugger::onClose](../../winscript/reference/iapplicationdebugger-onclose.md)