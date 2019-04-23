---
title: 직접 실행 창 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ImmediateWindow
helpviewer_keywords:
- design-time expression evaluation
- Immediate window
- first-chance exception notifications
ms.assetid: d33e7937-73f3-4c69-9df0-777a8713c6f2
caps.latest.revision: 28
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 574b480cbdce0f038ba4d94be6dc2ba9cf46726c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59660296"
---
# <a name="immediate-window"></a>직접 실행 창
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**직접 실행** 창은 식을 디버깅 및 계산하고 문을 실행하며 가변 값을 인쇄하는 등에 사용됩니다. 디버깅 중에 개발 언어에 따라 실행되거나 계산되는 식을 입력할 수 있습니다. **직접 실행** 창을 표시하려면 편집할 프로젝트를 연 다음, **디버그** 메뉴에서 **창**을 선택하고 **즉시 실행**을 선택하거나 CTRL+ALT+I를 누릅니다.  
  
 이 창을 사용하여 개별 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 명령을 실행할 수 있습니다. 사용할 수 있는 명령에는 변수에 값을 할당하는 데 사용할 수 있는 `EvaluateStatement`이(가) 포함됩니다. **직접 실행** 창도 IntelliSense를 지원합니다.  
  
## <a name="displaying-the-values-of-variables"></a>변수 값 표시  
 이 창은 애플리케이션을 디버깅할 때 특히 유용할 수 있습니다. 예를 들어, `varA` 변수의 값을 확인하려면 [인쇄 명령](../../ide/reference/print-command.md)을 사용할 수 있습니다.  
  
```  
>Debug.Print varA  
```  
  
 물음표(?)는 `Debug.Print`에 사용되는 별칭이므로 이 명령은 다음과 같이 기록될 수도 있습니다.  
  
```  
>? varA  
```  
  
 이 명령의 두 버전은 모두 `varA` 변수의 값을 반환합니다.  
  
> [!NOTE]
>  **즉시 실행** 창에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 명령을 실행하려면 명령 앞에 보다 큼 기호(>)를 추가해야 합니다. 여러 개의 명령을 입력하려면 **명령** 창으로 전환합니다.  
  
## <a name="design-time-expression-evaluation"></a>디자인 타임 식 계산  
 **직접 실행** 창을 사용하여 디자인 타임에 함수 또는 서브루틴을 실행할 수 있습니다.  
  
#### <a name="to-execute-a-function-at-design-time"></a>디자인 타임에 함수를 실행하려면  
  
1. 다음 코드를 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] 콘솔 애플리케이션에 복사합니다.  
  
   ```  
   Module Module1  
  
       Sub Main()  
           MyFunction(5)  
       End Sub  
  
       Function MyFunction(ByVal input as Integer) As Integer  
           Return input * 2  
       End Function  
  
   End Module  
   ```  
  
2. **디버그** 메뉴에서 **창**을 클릭한 다음 **즉시 실행**을 클릭합니다.  
  
3. **직접 실행 창**에 `?MyFunction(2)`을 입력하고 Enter 키를 누릅니다.  
  
    **직접 실행** 창이 `MyFunction`을 실행하고 `4`를 표시합니다.  
  
   함수 또는 서브루틴에 중단점이 포함된 경우 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]는 적절한 지점에서 실행을 중단합니다. 그런 다음 디버거 창을 사용하여 프로그램 상태를 조사할 수 있습니다. 자세한 내용은 [연습: 디자인 타임에 디버깅](../../debugger/walkthrough-debugging-at-design-time.md)을 참조하세요.  
  
   [!INCLUDE[trprVSTOshort](../../includes/trprvstoshort-md.md)] 프로젝트, 웹 프로젝트, 스마트 장치 프로젝트 및 SQL 프로젝트를 포함해 실행 환경을 시작해야 하는 프로젝트 형식에서 디자인 타임 식 평가를 사용할 수 있습니다.  
  
### <a name="design-time-expression-evaluation-in-multi-project-solutions"></a>다중 프로젝트 솔루션에서 디자인 타임 식 계산  
 디자인 타임 식 계산에 대한 컨텍스트를 설정할 때 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]는 솔루션 탐색기에서 현재 선택된 프로젝트를 참조합니다. 솔루션 탐색기에서 선택된 프로젝트가 없는 경우 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]는 시작 프로젝트에 대해 함수를 평가하려고 합니다. 현재 컨텍스트에서 함수를 실행할 수 없는 경우 오류 메시지를 받게 됩니다. 솔루션을 위해 시작 프로젝트가 아닌 프로젝트에서 함수를 계산하려고 하는데 오류를 받은 경우 솔루션 탐색기에서 프로젝트를 선택하고 계산을 다시 시도하세요.  
  
## <a name="entering-commands"></a>명령 입력  
 **즉시 실행** 창에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 명령을 실행할 경우 보다 큼 기호(>)를 입력해야 합니다. 위쪽 화살표 및 아래쪽 화살표 키를 사용해서 이전에 실행된 명령을 스크롤합니다.  
  
|작업|솔루션|예제|  
|----------|--------------|-------------|  
|식을 계산합니다.|식 앞에 물음표(?)를 추가합니다.|`? a+b`|  
|직접 실행 모드(단일 명령 실행)에 있는 동안 명령 모드를 일시적으로 입력합니다.|앞에 보다 큼 기호(>)를 추가하여 명령을 입력합니다.|`>alias`|  
|명령 창으로 전환합니다.|앞에 보다 큼 기호(>)를 추가하여 창에 `cmd`를 입력합니다.|`>cmd`|  
|직접 실행 창으로 다시 전환합니다.|`immed`를 보다 큼 기호(>) 없이 창에 입력합니다.|`immed`|  
  
## <a name="mark-mode"></a>표시 모드  
 **즉시 실행** 창에서 이전 줄을 클릭하면 자동으로 표시 모드로 전환됩니다. 이 모드에서는 텍스트 편집기를 사용하는 것처럼 이전 명령의 텍스트를 선택, 편집 및 복사하고 현재 줄에 붙여넣을 수 있습니다.  
  
## <a name="the-equals--sign"></a>같음(=) 기호  
 `EvaluateStatement` 명령을 입력하는 데 사용되는 창에서는 같음 기호(=)를 비교 연산자 또는 대입 연산자로 해석할지 결정합니다.  
  
 **직접 실행** 창에서는 같음 기호(=)가 대입 연산자로 해석됩니다. 따라서 예를 들면  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 명령은 `varA` 변수에 `varB` 변수의 값을 할당합니다.  
  
 이와 달리 **명령** 창에서 같음 기호(=)는 비교 연산자로 해석됩니다. **명령** 창에서는 대입 연산자를 사용할 수 없습니다. 따라서 예를 들면 `varA` 및 `varB` 변수 값이 다른 경우  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 명령은 `False` 값을 반환합니다.  
  
## <a name="first-chance-exception-notifications"></a>첫째 예외 알림  
 일반 설정 구성에서 첫째 예외 알림이 **즉시 실행** 창에 표시됩니다.  
  
#### <a name="to-toggle-first-chance-exception-notifications-in-the-immediate-window"></a>직접 실행 창에서 첫째 예외 알림을 전환하려면  
  
1.  **보기** 메뉴에서 **기타 창**을 클릭하고 **출력**을 클릭합니다.  
  
2.  **출력** 창의 텍스트 영역을 마우스 오른쪽 단추로 클릭하고 **예외 메시지**를 선택 또는 선택 취소합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Navigating through Code with the Debugger](../../debugger/navigating-through-code-with-the-debugger.md) (디버거로 코드 탐색)  
 [명령 창](../../ide/reference/command-window.md)   
 [Visual Studio의 디버깅](../../debugger/debugging-in-visual-studio.md)   
 [Debugger Basics](../../debugger/debugger-basics.md) (디버거 기본 사항)  
 [연습: 디자인 타임에 디버깅](../../debugger/walkthrough-debugging-at-design-time.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)   
 [Visual Studio에서 정규식 사용](../../ide/using-regular-expressions-in-visual-studio.md)
