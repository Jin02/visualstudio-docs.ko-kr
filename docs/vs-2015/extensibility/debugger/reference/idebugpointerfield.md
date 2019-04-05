---
title: IDebugPointerField | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPointerField
helpviewer_keywords:
- IDebugPointerField interface
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2c22d2570311885a3717190c871f0cca2d90756b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981858"
---
# <a name="idebugpointerfield"></a>IDebugPointerField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스에 대 한 포인터 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPointerField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자에 대 한 포인터를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 사용 하 여 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 에서이 인터페이스를 가져올 수 합니다 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_POINTER`합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 합니다 `IDebugField` 및 `IDebugContainerField` 인터페이스에서이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 포인터의 대상을 설명 하는 합니다.|  
  
## <a name="remarks"></a>설명  
 C/c + +에 대 한 포인터 배열 표기법을 사용 하 여 사용 하는 경우 컨테이너를 수 있습니다. 예를 들어 `char *pString`하십시오 `pString` 에 대 한 포인터 형식이 `char`합니다. `pString[3]` 컨테이너에 대 한 포인터는 형식이 `char` 해당 컨테이너의 네 번째 요소를 참조 하는 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
