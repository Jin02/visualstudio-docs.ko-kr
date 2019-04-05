---
title: 디버거 시작 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4ae4c7eed2ae5477be02384ebe7b7c45383eaffb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58970475"
---
# <a name="launching-the-debugger"></a>디버거 시작
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

디버거 시작 메서드 및 해당 적절 한 특성을 사용 하 여 이벤트의 순서를 전송 해야 합니다.  
  
## <a name="sequences-of-methods-and-events"></a>메서드 및 이벤트의 시퀀스  
  
1.  세션 디버그 관리자 SDM ()를 선택 하 여 라고 합니다 **디버그** 메뉴를 선택한 후 **시작**합니다. 참조 [프로그램을 실행할](../../extensibility/debugger/launching-a-program.md) 자세한 내용은 합니다.  
  
2.  SDM 호출 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드.  
  
3.  디버그 엔진 (DE) 프로세스 모델을 기반으로 합니다 `IDebugProgramNodeAttach2::OnAttach` 메서드 이후에 결정 하는 다음 방법 중 하나를 반환 합니다.  
  
     경우 `S_FALSE` 디버그 엔진 (DE)은 가상 컴퓨터 중 로드할 반환 됩니다.  
  
     또는  
  
     경우 `S_OK` 이 반환 되는 DE이 로드 되는 SDM의 프로세스. SDM는 다음 태스크를 수행합니다.  
  
    1.  호출 [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) 는 DE의 엔진 정보를 가져옵니다.  
  
    2.  배치는 DE를 만듭니다.  
  
    3.  호출 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)합니다.  
  
4.  DE 보냅니다는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 를 사용 하 여 SDM을 `EVENT_SYNC` 특성입니다.  
  
5.  DE 보냅니다는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 를 사용 하 여 SDM을 `EVENT_SYNC` 특성입니다.  
  
6.  DE 보냅니다는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 를 사용 하 여 SDM을 `EVENT_SYNC` 특성입니다.  
  
7.  DE 보냅니다는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 를 사용 하 여 SDM을 `EVENT_SYNC` 특성입니다.  
  
8.  DE 보냅니다는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 를 사용 하 여 SDM을 `EVENT_SYNC` 특성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)   
 [프로그램 시작](../../extensibility/debugger/launching-a-program.md)
