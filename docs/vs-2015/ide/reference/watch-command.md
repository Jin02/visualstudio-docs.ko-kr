---
title: 조사식 명령 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bd362c01c996dc6a32197b9acd88f11b26c034bf
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59655806"
---
# <a name="watch-command"></a>조사식 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**조사식** 창의 지정된 인스턴스를 만들고 엽니다. **조사식** 창을 사용하여 변수, 식 및 레지스터의 값을 계산하고, 이러한 값을 편집하고, 결과를 저장할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>인수  
 `index`  
 필수 요소. 조사식 창의 인스턴스 번호입니다.  
  
## <a name="remarks"></a>주의  
 `index`는 정수여야 합니다. 유효한 값은 1, 2, 3 또는 4입니다.  
  
## <a name="example"></a>예제  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>참고 항목  
 [자동 및 지역 창](../../debugger/autos-and-locals-windows.md)   
 [방법: 변수 창에서 값 편집](http://msdn.microsoft.com/library/36f464ab-c900-4c0b-9ab3-557b3d9cdab5)   
 [방법: 간략한 조사식 대화 상자 사용](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
