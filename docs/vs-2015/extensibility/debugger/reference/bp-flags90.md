---
title: BP_FLAGS90 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9f7192eb7b2fa6d8bc886c0e601788ecba8eebcd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981232"
---
# <a name="bpflags90"></a>BP_FLAGS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

선택적 플래그에 대 한 유효한 값을 열거합니다. 중단점을 설정 하는 경우 추가 정보를 지정 하는 선택적 플래그를 사용할 수 있습니다. 이 열거형을 확장 합니다 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) 열거형입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 BP90_FLAG_NONE  
 중단점 플래그가 지정합니다.  
  
 BP90_FLAG_MAP_DOCPOSITION  
 디버그 엔진 (DE) 문서 위치를 사용 하 여 중단점을 매핑하는 것을 지정 합니다. 스크립트 기반 소스 파일 등 ASP Active Server Pages ()에서 설정 된 중단점에만 적용 됩니다.  
  
 BP90_FLAG_DONT_STOP  
 중단점 디버그 엔진에 의해 처리 되어야 한다는 지정 디버그 엔진 궁극적으로 중지 해야 함을 하지 있습니다. 즉, 한 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 이벤트 개체 보내지 않아야 합니다. 이 플래그는 추적 지점과 기본적으로 사용 하도록 설계 되었습니다.  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 네이티브 디버그 엔진 단계별 실행 상태를 지워야 하는지 여부를 결정 하기 위해 사용 합니다. BP90_FLAG_DONT_STOP 추적 지점 매크로 실행 하는 경우 설정 되어 있지 않으므로 BP90_FLAG_DONT_STOP에서 다릅니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg90.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
