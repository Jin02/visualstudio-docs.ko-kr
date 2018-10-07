---
title: 'Idiasession:: Findfilebyid | Microsoft Docs'
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
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e54267e86854098e263c74a9d0e7042540e02025
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554306"
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasession:: Findfilebyid](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findfilebyid)합니다.  
  
원본 파일 식별자에서 소스 파일을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uniqueId`  
 [in] 소스 파일 식별자를 지정합니다.  
  
 `ppResult`  
 [out] 반환을 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 소스 파일을 나타내는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 소스 파일 식별자에는 모든 소스 파일을 고유 하 게 DIA SDK를 내부적으로 사용 되는 고유 값입니다. 이 메서드는 일반적으로 DIA SDK를 내부적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession:: Findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)


