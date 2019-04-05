---
title: IDebugMemoryContext2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6f5a0533e2f7ce50dce7ccdf1285e4ab28a4b7a4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985239"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스는 디버그 중인 프로그램을 실행 하는 컴퓨터의 주소 공간에서 위치를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 메모리의 주소를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 에 대 한 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 하거나 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) 이 인터페이스를 반환 합니다. 또한 호출 [추가](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) 하 고 [Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) 적절 한 산술 연산을 적용 한 후이 인터페이스의 새 복사본을 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugMemoryContext2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|이 컨텍스트에 대 한 사용자 표시 이름을 가져옵니다.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|이 컨텍스트를 설명 하는 정보를 가져옵니다.|  
|[추가](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|새 컨텍스트를 만들려면 현재 컨텍스트의 주소에 지정된 된 값을 추가 합니다.|  
|[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|새 컨텍스트를 만들려면 현재 컨텍스트의 주소에서 지정 된 값을 뺍니다.|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|두 컨텍스트 방식에서으로 표시 하는 비교 플래그를 비교 합니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio **메모리** 창 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 가져오려고 합니다 `IDebugMemoryContext2` 메모리 주소에 사용 되는 계산된 된 식을 포함 하는 인터페이스입니다. 이 컨텍스트에 전달 되어 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) 하 고 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) 읽기 또는 쓰기에 대 한 주소를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)
