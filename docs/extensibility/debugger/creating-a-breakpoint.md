---
title: 중단점 만들기 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, creating
- debugging [Debugging SDK], creating breakpoints
ms.assetid: 6f9f87bb-192e-45e0-9a7a-ffe729e87f7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c682920c7e879d65dfddd3b4fee17a0f20b26b21
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411284"
---
# <a name="create-a-breakpoint"></a>중단점 만들기
다음 중단점을 만드는 과정을 설명 합니다.

## <a name="methods-in-breakpoint-creation"></a>중단점을 만드는 방법
 중단점을 바인딩할 필요한 모듈 로드 되 면 세션 디버그 관리자 (SDM) 다음 메서드를 호출 합니다.

1. [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)

2. [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)

3. [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)

    > [!NOTE]
    > **CanBind** 사용자가에서 중단점을 때에 호출 되는 **중단점** 창입니다.

4. [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)

5. [IDebugPendingBreakpoint2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)

## <a name="see-also"></a>참고자료
- [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)