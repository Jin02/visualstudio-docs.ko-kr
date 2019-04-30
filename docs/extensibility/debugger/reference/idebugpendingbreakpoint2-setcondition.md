---
title: IDebugPendingBreakpoint2::SetCondition | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::SetCondition
helpviewer_keywords:
- SetCondition method
- IDebugPendingBreakpoint2::SetCondition method
ms.assetid: 0534224f-654f-4862-bc4d-a9a81a5f8899
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4a67286b4732436c2a680e13e90740ca9faff299
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842765"
---
# <a name="idebugpendingbreakpoint2setcondition"></a>IDebugPendingBreakpoint2::SetCondition
설정 하거나 연결 된 보류 중인 중단점 조건을 변경 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetCondition( 
   BP_CONDITION bpCondition
);
```

```csharp
int SetCondition( 
   BP_CONDITION bpCondition
);
```

#### <a name="parameters"></a>매개 변수
 `bpCondition`

 [in] A [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 설정 하는 조건을 지정 하는 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 보류 중인 중단점을 사용 하 여 이전에 연관 된 모든 상태는 손실 됩니다. 중단점 보류 중인이 바인딩된 모든 중단점 해당 조건에 지정 된 값으로 설정 하기 위해 호출 되는 `bpCondition` 매개 변수입니다.

## <a name="see-also"></a>참고 항목
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)