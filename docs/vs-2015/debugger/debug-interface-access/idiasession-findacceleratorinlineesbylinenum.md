---
title: IDiaSession::findAcceleratorInlineesByLinenum | Microsoft Docs
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
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 99f344a1f6de8dba9dc14d1720515319796f629f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554297"
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaSession::findAcceleratorInlineesByLinenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findacceleratorinlineesbylinenum)합니다.  
  
지정한 원본 위치에 해당 하는 인라인 프레임에 대 한 기호의 열거형을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] `IDiaSymbol` 검색 해야 하는 가속기 스텁 함수에 해당 하는 합니다.  
  
 `file`  
 [in] `IDiaSourceFile` 원본 위치입니다.  
  
 `linenum`  
 [in] 원본 위치의 줄 번호입니다.  
  
 `colnum`  
 [in] 원본 위치의 열 번호입니다.  
  
 `ppResult`  
 [out] 에 대 한 포인터는 `IDiaEnumLineNumbers` 결과 사용 하 여 초기화 된 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)


