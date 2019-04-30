---
title: SetNotificationForWaitCompletion 메서드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 468850a441cfd0bc87155fd746d8578c6b763e66
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912928"
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion 메서드
설정 하거나 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 상태 비트를 지웁니다.

 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **어셈블리:** mscorlib (에서 *mscorlib.dll*)

## <a name="syntax"></a>구문

```vb
internal void SetNotificationForWaitCompletion(bool enabled)
```

### <a name="parameters"></a>매개 변수
 `enabled`

 `true` 비트; 설정 하려면 `false` 에 설정 되지 않은 비트입니다.

## <a name="exceptions"></a>예외

## <a name="remarks"></a>설명
 디버거는 비동기 메서드 본문에서 나갈 수 있도록이 비트를 설정 합니다. 하는 경우 `enabled` 는 `true`, 아직 완료 되지 않은 작업에만이 메서드를 호출 해야 합니다. 때 `enabled` 는 `false`, 완료 된 작업에서이 메서드를 호출할 수 있습니다. 하거나 이벤트에 사용할 약속 스타일 작업에 대 한 합니다.

## <a name="requirements"></a>요구 사항

## <a name="see-also"></a>참고자료
- [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)