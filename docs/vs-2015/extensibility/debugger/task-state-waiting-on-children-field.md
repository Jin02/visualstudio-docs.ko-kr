---
title: TASK_STATE_WAITING_ON_CHILDREN 필드 | Microsoft Docs
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
- TASK_STATE_WAITING_ON_CHILDREN field, Task class [.NET Framework debug engines]
ms.assetid: 6f26b098-84ad-4f6e-ba27-6136581ba630
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e69d8473e877807a6f1d80ca7844d78a38aa82d7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550199"
---
# <a name="taskstatewaitingonchildren-field"></a>TASK_STATE_WAITING_ON_CHILDREN 필드
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [TASK_STATE_WAITING_ON_CHILDREN 필드](https://docs.microsoft.com/visualstudio/extensibility/debugger/task-state-waiting-on-children-field)합니다.  
  
해당 대리자 실행을 마친 작업과 연결 된 자식 작업이 완료 되기를 기다리는 암시적으로 합니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (mscorlib.dll)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.field static assembly literal int32 TASK_STATE_WAITING_ON_CHILDREN = int32(0x01000000)  
```  
  
## <a name="remarks"></a>설명  
 경우는 [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md) 이 값을 포함 하는 필드를 <xref:System.Threading.Tasks.Task.Status%2A> 속성에서 반환 <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)
