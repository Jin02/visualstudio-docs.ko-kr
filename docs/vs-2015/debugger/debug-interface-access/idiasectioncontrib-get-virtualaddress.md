---
title: 'Idiasectioncontrib:: Get_virtualaddress | Microsoft Docs'
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
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_virtualAddress method
ms.assetid: e5b44a81-0804-429b-97d8-467cbba3132a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a02b60845353bd8c77945ed786e507cc75d671b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564529"
---
# <a name="idiasectioncontribgetvirtualaddress"></a>IDiaSectionContrib::get_virtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasectioncontrib:: Get_virtualaddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress)합니다.  
  
에 대 한 기여도의 가상 주소 (VA)를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] VA 기여도 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)


