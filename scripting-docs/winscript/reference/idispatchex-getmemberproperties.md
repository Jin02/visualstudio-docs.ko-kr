---
title: 'IDispatchEx:: GetMemberProperties | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetMemberProperties
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetMemberProperties method
ms.assetid: 20d43209-12e2-472a-9bf3-81eced137b71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8016eef7b6e0da9b9fc88695db845cba7f608ff3
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574091"
---
# <a name="idispatchexgetmemberproperties"></a>IDispatchEx::GetMemberProperties
멤버의 속성을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetMemberProperties(  
   DISPID id,  
   DWORD grfdexFetch,  
   DWORD *pgrfdex  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 멤버를 식별합니다. @No__t_0 또는 `GetNextDispID`를 사용 하 여 디스패치 식별자를 가져옵니다.  
  
 `grfdexFetch`  
 검색할 속성을 결정 합니다. @No__t_0 및/또는 다음 값의 조합에 나열 된 값을 조합 하 여 사용할 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|grfdexPropCanAll|FdexPropCanGet, fdexPropCanPut, Fdexpropcanget, fdexPropCanCall, Fdexpropcan구문과 Fdexpropcanget를 결합 합니다.|  
|grfdexPropCannotAll|FdexPropCannotGet, Fdexpropcannotget, fdexPropCannotPutRef, Fdexpropcannotget, Fdexpropcannotget fdexPropCannotSourceEvents를 결합 합니다.|  
|grfdexPropExtraAll|FdexPropNoSideEffects와 fdexPropDynamicType를 결합 합니다.|  
|grfdexPropAll|GrfdexPropCanAll, grfdexPropCannotAll 및 grfdexPropExtraAll를 결합 합니다.|  
  
 `pgrfdex`  
 요청 된 속성을 수신 하는 `DWORD`의 주소입니다. 다음 값을 조합 하 여 사용할 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|fdexPropCanGet|DISPATCH_PROPERTYGET를 사용 하 여 멤버를 가져올 수 있습니다.|  
|fdexPropCannotGet|DISPATCH_PROPERTYGET를 사용 하 여 멤버를 가져올 수 없습니다.|  
|fdexPropCanPut|DISPATCH_PROPERTYPUT를 사용 하 여 멤버를 설정할 수 있습니다.|  
|fdexPropCannotPut|DISPATCH_PROPERTYPUT를 사용 하 여 멤버를 설정할 수 없습니다.|  
|fdexPropCanPutRef|DISPATCH_PROPERTYPUTREF를 사용 하 여 멤버를 설정할 수 있습니다.|  
|fdexPropCannotPutRef|DISPATCH_PROPERTYPUTREF를 사용 하 여 멤버를 설정할 수 없습니다.|  
|fdexPropNoSideEffects|멤버에 부작용이 없습니다. 예를 들어 디버거는 디버깅 중인 스크립트의 상태를 변경 하지 않고이 멤버를 안전 하 게 가져오거나 설정 하거나 호출할 수 있습니다.|  
|fdexPropDynamicType|멤버는 동적 이며 개체의 수명 동안 변경 될 수 있습니다.|  
|fdexPropCanCall|DISPATCH_METHOD를 사용 하 여 멤버를 메서드로 호출할 수 있습니다.|  
|fdexPropCannotCall|DISPATCH_METHOD를 사용 하 여 멤버를 메서드로 호출할 수 없습니다.|  
|fdexPropCanConstruct|멤버는 DISPATCH_CONSTRUCT을 사용 하 여 생성자로 호출 될 수 있습니다.|  
|fdexPropCannotConstruct|DISPATCH_CONSTRUCT를 사용 하 여 멤버를 생성자로 호출할 수 없습니다.|  
|fdexPropCanSourceEvents|멤버가 이벤트를 발생 시킬 수 있습니다.|  
|fdexPropCannotSourceEvents|멤버가 이벤트를 발생 시킬 수 없습니다.|  
  
## <a name="return-value"></a>반환 값  
 는 다음 값 중 하나를 반환 합니다.  
  
|||  
|-|-|  
|`S_OK`|성공할.|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## <a name="example"></a>예제  
  
```cpp
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
   DWORD dwProps;  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)) &&  
      SUCCEEDED(pdex->GetMemberProperties(dispid, grfdexPropAll, &dwProps)) &&  
         (dwProps & fdexPropCanPut))  
   {  
      // Assign to member  
   }  
```  
  
## <a name="see-also"></a>참조  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)    
 [IDispatchEx:: GetDispID](../../winscript/reference/idispatchex-getdispid.md)    
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)