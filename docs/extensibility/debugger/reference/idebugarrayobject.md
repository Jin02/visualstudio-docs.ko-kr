---
title: IDebugArrayObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject
helpviewer_keywords:
- IDebugArrayObject method
ms.assetid: a1c8e77e-dee1-4748-a516-6ab032a8f54f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 13e010f028d36548b58f09b26d3240a05bf96d92
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63414107"
---
# <a name="idebugarrayobject"></a>IDebugArrayObject
> [!IMPORTANT]
> Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.

 이 인터페이스는 배열 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
IDebugArrayObject : IDebugObject
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 식 계산기는 배열을 나타내는 데이 인터페이스를 구현 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 합니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스를 사용 하 여이 인터페이스를 가져올 수 있습니다 [QueryInterface](/cpp/atl/queryinterface) 개체가 나타내는 배열입니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 메서드 외에 `IDebugObject` 인터페이스를 다음 방법으로 구현 됩니다는 `IDebugArrayObject` 인터페이스입니다.

|메서드|설명|
|------------|-----------------|
|[GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)|배열의 요소 개수를 가져옵니다.|
|[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)|배열의 요소를 가져옵니다.|
|[GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)|배열의 모든 요소를 가져옵니다.|
|[GetRank](../../../extensibility/debugger/reference/idebugarrayobject-getrank.md)|배열의 차수를 가져옵니다.|
|[GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md)|배열의 차수를 가져옵니다.|

## <a name="remarks"></a>설명
 식 계산기를이 인터페이스를 사용 하 여 배열에서 구문 분석 트리를 나타냅니다.

## <a name="requirements"></a>요구 사항
 헤더: ee.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)