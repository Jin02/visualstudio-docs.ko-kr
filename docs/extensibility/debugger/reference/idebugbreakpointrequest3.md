---
title: IDebugBreakpointRequest3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3
helpviewer_keywords:
- IDebugBreakpointRequest3
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c45b1bae11710063d089aeca61a9d20fb6e907a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923170"
---
# <a name="idebugbreakpointrequest3"></a>IDebugBreakpointRequest3
이 인터페이스를 만들고 모든 중단점 유형에 바인딩하는 데 필요한 정보를 나타냅니다. 확장 이기 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)합니다.

## <a name="syntax"></a>구문

```
IDebugBreakpointRequest3 : IDebugBreakpointRequest2
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 세션 디버그 관리자 SDM ()는 일반적으로이 인터페이스를 구현합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 디버그 엔진 (DE)를 호출 하 여이 인터페이스에 액세스 [QueryInterface](/cpp/atl/queryinterface) 에 대 한 호출에서 받은 IDebugBreakpointRequest2 인터페이스 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)합니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 상속 된 메서드 외에도 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md), `IDebugBreakpointRequest3` 인터페이스는 다음 메서드를 노출 합니다.

|메서드|설명|
|------------|-----------------|
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|이 중단점 요청을 설명 하는 중단점 요청 정보를 가져옵니다.|

## <a name="remarks"></a>설명
 이 인터페이스를 통해 DE 추가 정보를 제공 되는 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다. 이 추가 정보는 DE의 공급 업체 ID (GUID 형식), 추적점의 이름 및 중단점 제약 조건의 이름을 포함합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)