---
title: IDebugProcess3::GetEngineFilter | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetEngineFilter
- IDebugProcess3::GetEngineFilter
ms.assetid: ccb7ecb0-f189-4e80-b5b2-221a095e01f5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30dfd7b9605cf26f5cc562e6768d1f035f6b484e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917678"
---
# <a name="idebugprocess3getenginefilter"></a>IDebugProcess3::GetEngineFilter
사용할 디버그 엔진에 대 한 고유 식별자의 배열을 검색합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetEngineFilter(
   GUID_ARRAY *pEngineArray
);
```

```csharp
public int GetEngineFilter(
   out GUID_ARRAY[] pEngineArray
);
```

#### <a name="parameters"></a>매개 변수
 `pEngineArray`

 [out] 디버그 엔진에 대 한 고유 식별자가 포함 된 구조에 대 한 참조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md)