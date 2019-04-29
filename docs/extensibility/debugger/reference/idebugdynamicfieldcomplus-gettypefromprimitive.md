---
title: IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive
- GetTypeFromPrimitive
ms.assetid: d7f51e2a-1b72-489c-b7b6-4af7b7e4d663
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6f29a1d77e4bb56608750c1f277fc6d58b81c255
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921134"
---
# <a name="idebugdynamicfieldcomplusgettypefromprimitive"></a>IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive
해당 기본 형식이 지정 된 형식을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetTypeFromPrimitive(
   DWORD         dwCorElementType,
   IDebugField** ppType
);
```

```csharp
int GetTypeFromPrimitive(
   uint            dwCorElementType,
   out IDebugField ppType
);
```

#### <a name="parameters"></a>매개 변수
 `dwCorElementType`

 [in] 값을 [CorElementType 열거형](/dotnet/framework/unmanaged-api/metadata/corelementtype-enumeration) 기본 형식을 나타내는입니다.

 `ppType`

 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 형식을 나타내는입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)