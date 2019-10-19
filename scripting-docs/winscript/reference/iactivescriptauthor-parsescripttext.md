---
title: IActiveScriptAuthor::P arseScriptText | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.ParseScriptText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::ParseScriptText
ms.assetid: ebe212e8-6789-423d-ad22-92be984dc7ad
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 90d5ab0fa700ed29b5fb37b1c48617cedec871b9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576146"
---
# <a name="iactivescriptauthorparsescripttext"></a>IActiveScriptAuthor::ParseScriptText
스크립트 텍스트를 구문 분석 하 고, 스크립트 작성 엔진에 텍스트를 추가 하 고, 스크립트 블록에 해당 하는 `IScriptEntry` 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ParseScriptText(  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszCode`  
 진행 구문 분석할 스크립트 텍스트입니다.  
  
 `pszItemName`  
 진행 스크립트 블록과 연결 된 항목 이름을 포함 하는 버퍼 주소입니다.  
  
 `pszDelimiter`  
 진행 스크립트 블록 끝 구분 기호의 주소입니다. 텍스트 스트림에서 `pszCode` 구문 분석 되는 경우 호스트는 일반적으로 구분 기호 (예: 두 개의 작은따옴표)를 사용 하 여 스크립트 블록의 끝을 검색 합니다. 스크립트 블록의 끝을 식별할 구분 기호가 없으면이 매개 변수를 NULL로 설정 합니다.  
  
 `dwCookie`  
 진행 새 `IScriptEntry` 개체와 연결 된 응용 프로그램 정의 값입니다.  
  
 `dwFlags`  
 진행 사용 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참조  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)