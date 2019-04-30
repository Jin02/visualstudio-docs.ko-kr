---
title: IDebugStackFrame2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2
helpviewer_keywords:
- IDebugStackFrame2 interface
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ae9cad7102fb9a82deb43b2c8820ef52e77deeed
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547005"
---
# <a name="idebugstackframe2"></a>IDebugStackFrame2
이 인터페이스는 특정 스레드에서 호출 스택에서 단일 스택 프레임을 나타냅니다.

## <a name="syntax"></a>구문

```
IDebugStackFrame2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 디버그 엔진 (DE) 스택 프레임을 나타내는 데이 인터페이스를 구현 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 호출 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 검색 하는 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 인터페이스입니다. 호출 [다음](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md) 검색 하는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 포함 하는 구조는 `IDebugStackFrame2` 인터페이스입니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 다음 표에서의 메서드를 보여 줍니다. `IDebugStackFrame2`합니다.

|메서드|설명|
|------------|-----------------|
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|이 스택 프레임에 대 한 코드 컨텍스트를 가져옵니다.|
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|이 스택 프레임에 대 한 문서 컨텍스트를 가져옵니다.|
|[GetName](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|스택 프레임의 이름을 가져옵니다.|
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|스택 프레임에 대 한 설명을 가져옵니다.|
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|스택 프레임과 연결 된 물리적 주소 범위의 컴퓨터 종속 표현을 가져옵니다.|
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|스레드를 스택 프레임의 현재 컨텍스트 내에서 식 평가 작업을 수행 하는 계산 컨텍스트를 가져옵니다.|
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|스택 프레임과 연결 된 언어를 가져옵니다.|
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|스택 프레임과 연결 된 속성에 대 한 설명을 가져옵니다.|
|[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|프레임 속성 스택에 대 한 열거자를 만듭니다.|
|[GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|스택 프레임과 연결 된 스레드를 가져옵니다.|

## <a name="remarks"></a>설명
 이 인터페이스는 디버그 중인 프로그램 (발생 한 사용자가 설정한 중단점 또는 예외가) 중단점에서 중지 되었을 때에 가져옵니다. 이 인터페이스에서 식을 평가 하는 식 컨텍스트를 가져올 수 있습니다, 레지스터의 목록을 반환할 수 있습니다, 또는 호출 스택의 검사 합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)