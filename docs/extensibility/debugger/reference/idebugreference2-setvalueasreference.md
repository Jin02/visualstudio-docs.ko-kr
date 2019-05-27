---
title: IDebugReference2::SetValueAsReference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsReference
helpviewer_keywords:
- IDebugReference2::SetValueAsReference
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 203e9741afa832ba0515a06b21ba1899e1355e1c
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211879"
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
다른 참조에서 참조의 값을 설정 합니다. 나중에 사용하기 위해 예약되어 있습니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetValueAsReference ( 
   IDebugReference2** rgpArgs,
   DWORD              dwArgCount,
   IDebugReference2*  pValue,
   DWORD              dwTimeout
);
```

```cpp
int SetValueAsReference ( 
   IDebugReference2[] rgpArgs,
   uint               dwArgCount,
   IDebugReference2   pValue,
   uint               dwTimeout
);
```

## <a name="parameters"></a>매개 변수
`rgpArgs`\
[in] 배열을 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체 참조 값을 설정 하는 방법을 결정 하는 데 사용 합니다.

`dwArgCount`\
[in] 배열에 대 한 참조의 수입니다.

`pValue`\
[in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 속성 값을 설정 하는 개체입니다.

`dwTimeout`\
[in] 이 메서드에서 반환 되기 전에 대기할 밀리초에서는 최대 시간입니다. 사용 하 여 `INFINITE` 무기한 대기 합니다.

## <a name="return-value"></a>반환 값
 항상 `E_NOTIMPL`를 반환합니다.

## <a name="see-also"></a>참고자료
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)