---
title: IDebugSettingsCallback2::GetMetricDword | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricDword
ms.assetid: 831a5a1a-c4af-4520-9fdf-3a731aeff85c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f52205cd530e638146abe423890d6477fe62b45d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457328"
---
# <a name="idebugsettingscallback2getmetricdword"></a>IDebugSettingsCallback2::GetMetricDword
이름이 지정 된 메트릭 값을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetMetricDword(
   LPCWSTR pszType,
   REFGUID guidSection,
   LPCWSTR pszMetric,
   DWORD*  pdwValue
);
```

```csharp
private int GetMetricDword(
   string   pszType,
   ref Guid guidSection,
   string   pszMetric,
   out uint pdwValue
);
```

## <a name="parameters"></a>매개 변수
 `pszType`\

 [in] 메트릭의 유형입니다.

 `guidSection`\

 [in] 섹션의 고유 식별자입니다.

 `pszMetric`\

 [in] 메트릭의 이름입니다.

 `pdwValue`\

 [out] 메트릭 값을 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)