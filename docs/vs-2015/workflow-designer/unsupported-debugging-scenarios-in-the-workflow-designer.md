---
title: 워크플로 디자이너에서 시나리오를 디버깅 하는 지원 되지 않는 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
caps.latest.revision: 4
author: steved0x
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7b3b47264190afcc75431a55ad6b8b4512f26ea0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082693"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Workflow Designer에서 지원되지 않는 디버깅 시나리오
[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]의 워크플로 디자이너에는 새로운 여러 기능이 추가되었지만 여전히 지원되지 않는 몇 가지 디버깅 시나리오가 있습니다. 이 문서에서는 워크플로 디자이너에서 지원되지 않는 디버깅 시나리오에 대해 자세히 설명합니다.  
  
- 코드를 편집한 후에는 실행을 계속할 수 없습니다.  
  
- 워크플로의 임의의 지점에서 실행을 계속할 수 없습니다(다음 설정).  
  
- 커서에 도달할 때까지 실행을 계속할 수 없습니다(커서까지 실행).  
  
- Workflow Designer를 사용하지 않고 코드로 만든 워크플로는 Workflow Designer를 사용하여 디버깅할 수 없습니다.  
  
- 이전 버전의 [!INCLUDE[wf](../includes/wf-md.md)]에서 만든 워크플로는 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 디자이너에서 디버깅할 수 없습니다.  
  
- 활동 또는 <xref:System.Activities.Statements.Flowchart> 노드 간 링크에는 중단점을 정의할 수 없습니다.  
  
- 디버깅하는 동안에는 클립보드를 사용할 수 없습니다.  
  
- 활동을 복사하거나 붙여 넣으면 중단점이 유지되지 않습니다.  
  
- 호출 스택 창에서는 워크플로 중단점을 설정할 수 없습니다.  
  
- 디자이너에서 중단점을 만들 때 합니다 **줄** 및 **문자** 설정에는 **새 중단점** 대화 상자는 사용 되지 않습니다.  
  
- 중단점 창 또는 바로 가기 메뉴에서는 워크플로 디버깅에 다음과 같은 열 또는 옵션을 사용할 수 없습니다.  
  
    - 조건  
  
    - 적중 횟수  
  
    - 적중될 때  
  
    - 함수  
  
    - 데이터  
  
    - 프로세스  
  
    - 디스어셈블리로 이동