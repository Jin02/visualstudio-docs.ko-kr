---
title: 잘못 된 문자 범위 설정 (JavaScript) | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5021
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 971e9d5a-f88a-47a8-af94-f3c7c4aed5ab
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1cbfa4de401c2a1dc0626f8f00dbb0bd1bf24408
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079593"
---
# <a name="invalid-range-in-character-set-javascript"></a>문자 집합의 범위가 잘못되었습니다.(JavaScript)
잘못 된 문자 집합 범위를 사용 하 여 정규식을 작성 하려고 했습니다. A-z 또는 0-9;와 같은 단일 문자만에서 문자 집합 사이 여야 합니다. 문자 집합에서 \w 등의 문자 클래스를 포함할 수 없습니다. 범위에서 첫 번째 문자 범위에서 두 번째 문자 앞 이어야 합니다. 예를 들어:  
  
```JavaScript  
var good = /[a-z]/;     // A valid character range - a comes before z.  
var notGood = /[z-a]/;  // An invalid character range - z does not come before a.  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 에 정규식 문자 집합을 작성 하 고 올바른 순서로 되는지 확인 하려면 단일 문자를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](https://msdn.microsoft.com/library/1400241x)