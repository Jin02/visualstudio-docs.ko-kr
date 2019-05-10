---
title: IEnumDebugModules2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 548bcd0328f7bdf52e47eb9a4295168ca47a2517
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226694"
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
이 인터페이스에는 모듈의 목록을 열거합니다.

## <a name="syntax"></a>구문

```
IEnumDebugModules2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 디버그 엔진 (DE) 프로그램에 대해 로드 된 모듈의 목록을 나타내는 데이 인터페이스를 구현 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 Visual Studio 호출 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 이 인터페이스를 가져올 수 있습니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugModules2`합니다.

|메서드|설명|
|------------|-----------------|
|[다음](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|열거형 시퀀스에서 모듈의 지정된 된 수를 검색 합니다.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|열거형 시퀀스에서 모듈의 지정된 된 수를 건너뜁니다.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|모듈의 수를 가져옵니다.|

## <a name="remarks"></a>설명
 Visual Studio 업데이트를 기본적으로이 인터페이스를 사용 합니다 **모듈** 창입니다.

 Visual Studio에서 디버깅을 위해 프로그램 따라서 모듈 경계를 넘나들 수 있는 코드 명령의 논리적 시퀀스는 단일 모듈 목록이 필요 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다. 목록의 첫 번째 모듈은 일반적으로 된 프로그램에 대 한 초기 진입점을 포함 합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고자료
- [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)