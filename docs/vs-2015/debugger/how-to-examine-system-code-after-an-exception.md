---
title: '방법: 예외 발생 후 시스템 코드 검사 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c66e77a2e5cc7596bb8473678b84f962453df41
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541817"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>방법: 예외 발생 후 시스템 코드 검사
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: an 예외 후 시스템 코드 검사](https://docs.microsoft.com/visualstudio/debugger/how-to-examine-system-code-after-an-exception)합니다.  
  
예외가 발생하면 예외의 원인을 확인하기 위해 시스템 호출 내부 코드를 검사할 수 있습니다. 다음 절차에서는 시스템 코드에 대해 로드된 기호가 없거나 내 코드만을 사용하는 경우 이러한 작업을 수행하는 방법에 대해 설명합니다.  
  
### <a name="to-examine-system-code-following-an-exception"></a>예외 발생 후 시스템 코드를 검사하려면  
  
1.  에 **호출 스택** 창에서 마우스 오른쪽 단추로 클릭 한 다음 클릭 **외부 코드 포시**합니다.  
  
     내 코드만을 사용하지 않는 경우에는 바로 가기 메뉴에서 이 옵션을 사용할 수 없으며 기본적으로 시스템 코드가 표시됩니다.  
  
2.  에 표시 되는 외부 코드 프레임을 마우스 오른쪽 단추로 클릭 합니다 **호출 스택** 창입니다.  
  
3.  가리킨 **에서 기호 로드** 을 클릭 한 다음 **Microsoft 기호 서버**합니다.  
  
    1.  내 코드만을 사용하는 경우 내 코드만을 이제 사용하지 않는다는 대화 상자가 표시되는데 이는 시스템 호출을 한 단계씩 실행하는 데 필요한 조치입니다.  
  
    2.  합니다 **공용 기호 다운로드** 대화 상자가 나타납니다. 다운로드가 완료되면 이 대화 상자는 사라집니다.  
  
4.  이제 시스템 코드를 검사할 수 있습니다 합니다 **호출 스택** 창과 다른 합니다. 원본에서 코드를 보려면 호출 스택 프레임을 두 번 예를 들어, 또는 **디스어셈블리** 창입니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)




