---
title: 함수를 수백 번 호출하는 경우 어떤 호출이 실패했는지 어떻게 알 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.functions
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- conditional breakpoints
- errors [debugger], function calls
- breakpoints, troubleshooting
- errors [debugger], finding which function call failed
- failures
- location breakpoint call failures
- errors [Visual Studio], function calls
- hit counts
- function calls, failure
- functions [debugger]
- Skip Count
ms.assetid: 66cfac86-f5be-4d3a-9329-d44cd74bc586
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2655205c3e0c34d1063ce54793f49330ab7ccc2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550931"
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>함수를 수백 번 호출하는 경우 어떤 호출이 실패했는지 어떻게 알 수 있습니까?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [함수를 수백 번을 호출할 때 어떻게 알 수는 호출이 실패?](https://docs.microsoft.com/visualstudio/debugger/when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed-q)합니다.  
  
문제 설명  
 내 프로그램에서 특정 함수 `CnvtV`에 대한 호출에 실패합니다. 실패하기 전에 프로그램이 이 함수를 여러 번 호출하는 것 같습니다. `CnvtV`에 위치 중단점을 설정하면 해당 함수가 호출될 때마다 프로그램이 중지되기는 하지만 내가 원하는 것이 아닙니다. 어떤 조건 때문에 호출이 실패하는지 알 수 없기 때문에 조건부 중단점을 설정할 수 없습니다. 어떻게 해야 합니까?  
  
## <a name="solution"></a>솔루션  
 함수에 중단점을 설정할 수는 **적중 횟수** 필드를 도달할 수 없는 높은 값입니다. 이 경우 함수를 생각 `CnvtV` 호출 설정할 수 있는 백 번 **적중 횟수** 에 1,000 개 이상의 합니다. 프로그램을 실행한 다음 호출이 실패할 때까지 기다립니다. 호출에 실패하면 중단점 창을 열고 중단점 목록을 확인합니다. `CnvtV`에 설정한 중단점 다음에 적중 횟수와 남아 있는 반복 횟수가 표시됩니다.  
  
```  
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)  
```  
  
 이제 함수가 101번째 호출에서 실패한다는 것을 알 수 있습니다. 중단점에서 적중 횟수를 101로 설정하고 다시 프로그램을 실행하면 실패 원인이 된 `CnvtV` 함수가 호출될 때 프로그램이 중지됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그 Faq](../debugger/debugging-native-code-faqs.md)   
 [중단점 설정](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)


