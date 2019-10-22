---
title: 개체가 필요 합니다. | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5007
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d88c93d-e5b5-4b11-9bb5-bf1a5e41ccc3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1611596d844d43ef72663154dc48791830dfe29f
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573728"
---
# <a name="object-expected"></a>개체가 필요합니다.
`Object`가 아닌 다른 형식의 개체에 대해 메서드 또는 속성을 호출하려고 했거나, `Object`가 필요할 때 `Object`가 아닌 다른 형식의 인수를 전달했습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `Object` 형식의 개체에 대해서만 메서드 또는 속성을 호출합니다.  
  
- 개체가 아닌 인수에 대해 오류가 발생하는 경우 `Object` 형식의 개체를 전달합니다.  
  
- `Object` 형식의 개체 대신 정의되지 않았거나 null 참조가 호출되는지 여부를 확인합니다.  
  
     예를 들어 다음 코드의 myVar에서 이 오류가 발생하는 경우  
  
    ```JavaScript  
    var str = myVar.toString();  
    ```  
  
     다음 코드를 대신 사용할 수 있습니다.  
  
    ```JavaScript  
    if (myVar) {  
        var str = myVar.toString();  
    }  
    ```  
  
## <a name="see-also"></a>참조  
 [개체 개체](../../javascript/reference/object-object-javascript.md)    
 [개체 및 배열](../../javascript/objects-and-arrays-javascript.md)