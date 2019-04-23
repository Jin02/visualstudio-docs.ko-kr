---
title: 예상 ']' 정규식 (JavaScript) | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c49ab90dae8f30dae075906bb9c7ecb7881428f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065079"
---
# <a name="expected--in-regular-expression-javascript"></a>정규식에 ']'가 필요합니다.(JavaScript)
정규식 일치를 사용 하는 문자 클래스를 만들려고 하지만 오른쪽 대괄호를 포함 하지 않은 있습니다. 괄호 안에 배치 하 여 개별 문자 조합 문자 클래스를 조합할 수 있습니다. 문자 클래스는 포함 된 하나의 문자를 찾습니다. 예를 들어 / [abc] "a", "b", 문자 중 하 나와 일치 하는 / 또는 "c"입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 정규식에 오른쪽 대괄호를 추가 합니다.  
  
    > [!NOTE]
    >  한쪽 대괄호 일치 하도록 하려는 경우-백슬래시로 이스케이프 \\[에서 특수 문자로 해석 되지 않습니다 있도록- [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](https://msdn.microsoft.com/library/1400241x)