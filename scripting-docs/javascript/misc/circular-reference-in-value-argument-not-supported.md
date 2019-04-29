---
title: 지원 되지 않는 값 인수에 순환 참조가 | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31b56b4b2d568b3bc3fd59f876f5052b9f6faff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946370"
---
# <a name="circular-reference-in-value-argument-not-supported"></a>값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다.
호출 하려고 `JSON.stringify` 유효 하지 않은 값입니다. `value` 인수, 배열 또는 개체 순환 참조가 포함 되어 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 인수에서 순환 참조를 제거 합니다.  
  
## <a name="example"></a>예제  
 이 예제의 코드에 런타임 오류가 발생 하기 때문에 `john` 에 대 한 참조가 `mary` 하 고 `mary` 를 참조 하는 `john`. 순환 참조를 제거 하려면 제거 하거나 또는 설정 되지 않은 속성 `brother` 에서 합니다 `mary` 개체 또는 `sister` 속성을는 `john` 개체입니다.  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)