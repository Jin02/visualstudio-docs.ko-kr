---
title: IDebugCustomAttribute::GetParentField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetParentField
helpviewer_keywords:
- IDebugCustomAttribute::GetParentField
ms.assetid: bcdfdf37-bfcf-4988-a7b8-4c731d0af1b0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 158887e9f2d7d7b250b435570d6780e460508816
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921661"
---
# <a name="idebugcustomattributegetparentfield"></a>IDebugCustomAttribute::GetParentField
사용자 지정 특성에 연결 된 필드를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetParentField( 
   IDebugField** ppField
);
```

```csharp
int GetParentField(
   out IDebugField ppField
);
```

#### <a name="parameters"></a>매개 변수
 `ppField`

 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 연결 되는 사용자 지정 특성 필드를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 호출을 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 메서드는 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 종류의 부모 필드를 결정 하는 개체입니다.

## <a name="see-also"></a>참고 항목
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)