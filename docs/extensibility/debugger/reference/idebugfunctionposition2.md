---
title: IDebugFunctionPosition2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: faed38853aa7d0d925a3b1e598627cf1a55166d1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919223"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
이 인터페이스는 소스 문서에서 함수를 추상 위치를 나타냅니다.

## <a name="syntax"></a>구문

```
IDebugFunctionPosition2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 디버그 엔진 (DE)는 원본 문서 내에서 함수의 위치를 나타내는 데이 인터페이스를 구현 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 이 인터페이스의 일부로 제공 되는 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union (특히를 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) 구조) 이것은 부분에는 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 구조를 보류 중인 중단점을 만드는 데 사용 합니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 다음 표에서의 메서드를 보여 줍니다. `IDebugFunctionPosition2`합니다.

|메서드|설명|
|------------|-----------------|
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|이 위치에 상대적인는 함수의 이름을 가져옵니다.|
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|함수 시작 부분 으로부터의 오프셋을 가져옵니다.|

## <a name="remarks"></a>설명
 이 인터페이스를 나타내는 위치가 텍스트 기반 구체적으로 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조입니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)
- [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)