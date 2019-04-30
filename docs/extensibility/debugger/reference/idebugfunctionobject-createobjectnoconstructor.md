---
title: IDebugFunctionObject::CreateObjectNoConstructor | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor
helpviewer_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor method
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6a5ecd42b0ddf0138e98e2159fae1236ca02b473
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919447"
---
# <a name="idebugfunctionobjectcreateobjectnoconstructor"></a>IDebugFunctionObject::CreateObjectNoConstructor
생성자를 사용 하 여 개체를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CreateObjectNoConstructor( 
   IDebugField*   pClassObject,
   IDebugObject** ppObject
);
```

```csharp
int CreateObjectNoConstructor(
   IDebugField      pClassField,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>매개 변수
 `pClassObject`

 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 만들려는 개체의 형식을 나타내는 개체입니다.

 `ppObject`

 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새로 만든된 개체를 나타내는입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 구조 또는 복잡 한 형식 (생성자는 필요 하지 않습니다)는 함수에 매개 변수는 표현 되는 인스턴스를 나타내는 개체를 만들려면이 메서드를 호출 합니다 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.

 개체 매개 변수를 생성자에 필요한 경우 호출 된 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
- [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)