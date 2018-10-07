---
title: 필요한 포트 공급자 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 960cd5668fe49ba50e79f036848948ec8e0bbfc2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550234"
---
# <a name="required-port-supplier-interfaces"></a>필요한 포트 공급자 인터페이스
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [필요한 포트 공급자 인터페이스](https://docs.microsoft.com/visualstudio/extensibility/debugger/required-port-supplier-interfaces)합니다.  
  
포트 공급자 구현 해야 합니다 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스.[ IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 포트 공급자를 제공 하므로 포트, 해당 구현도 해야 합니다. 따라서 다음 인터페이스를 구현 해야 합니다.  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     포트를 설명 하 고 포트에서 실행 중인 모든 프로세스를 열거할 수 있습니다.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     시작 하 고 포트에서 프로세스 종료를 제공 합니다.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     프로그램 노드 생성 및 소멸 알려주는이 포트의이 컨텍스트 내에서 실행 되는 프로그램에 대 한 메커니즘을 제공 합니다. 자세한 내용은 [프로그램 노드](../../extensibility/debugger/program-nodes.md)합니다.  
  
-   `IConnectionPointContainer`  
  
     에 대 한 연결 지점을 제공 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)합니다.  
  
## <a name="port-supplier-operation"></a>포트 공급자 작업  
 합니다 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) 싱크 처리 될 때 알림을 받고 프로그램 생성 및 포트에서 제거 합니다. 포트는 보내도록 필요 [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) 프로세스를 만들 때와 [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) 포트에서 프로세스는 제거 하는 경우. 보낼 포트도 필요 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 프로그램의 인스턴스가 만들어질 때와 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 포트에서 실행 되는 프로세스의 프로그램은 제거 하는 경우.  
  
 포트를 일반적으로 전송 프로그램 생성 및 소멸 이벤트에 대 한 응답에는 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 하 고 [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 메서드를 각각.  
  
 포트를 시작 하 고 실제 프로세스와 논리 프로그램 종료 수, 있으므로 이러한 인터페이스 디버그 엔진에서 구현 해야 합니다.  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     실제 프로세스를 설명합니다. 적어도 다음 메서드를 구현 해야 합니다.  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     SDM 연결 및 자체 프로세스에서 분리 하는 방법을 제공 합니다.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     논리 프로그램을 설명합니다. 적어도 다음 메서드를 구현 해야 합니다.  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     SDM이이 프로그램에 연결 하는 방법을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)
