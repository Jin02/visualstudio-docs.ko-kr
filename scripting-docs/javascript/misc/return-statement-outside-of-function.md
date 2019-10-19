---
title: 함수 외부에 ' return ' 문이 있습니다. | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a90af6de8e2c238e3660111b19d13c1eaf628c9e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573693"
---
# <a name="return-statement-outside-of-function"></a>함수 외부에 'return' 문이 있습니다.
코드의 전역 범위에서 `return` 문을 사용 했습니다. @No__t_0 문은 함수 본문 내에만 표시 되어야 합니다.  
  
 @No__t_0 연산자를 사용 하 여 함수를 호출 하는 것은 식입니다. 모든 식에는 값이 있습니다. `return` 문은 함수에서 반환 되는 값을 지정 하는 데 사용 됩니다. 일반적인 형식은 다음과 같습니다.  
  
```js
  
return [ expression ];  
```  
  
 @No__t_0 문을 실행 하는 경우 *식이* 계산 되 고 함수 값으로 반환 됩니다. 식이 없으면 **undefined** 가 반환 됩니다.  
  
 함수 본문에 남아 있는 다른 문이 있더라도 `return` 문이 실행 되 면 함수 실행이 중지 됩니다. 이 규칙의 예외는 **return** 문이 **try** 블록 내에서 발생 하 고 해당 **finally** 블록이 있는 경우 함수가 반환 되기 전에 **finally** 블록의 코드가 실행 됩니다.  
  
 함수가 `return` 문을 실행 하지 않고 함수 본문의 끝에 도달 하 여를 반환 하는 경우 반환 되는 값은 **정의 되지 않은** 값입니다 .이는 함수 결과를 큰 식의 일부로 사용할 수 없음을 의미 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 코드의 주 본문에서 (전역 범위) `return` 문을 제거 합니다.  
  
## <a name="see-also"></a>참조  
 [return 문](../../javascript/reference/return-statement-javascript.md)   
 [함수 개체](../../javascript/reference/function-object-javascript.md)    
 [caller 속성(Function)](../../javascript/reference/caller-property-function-javascript.md)