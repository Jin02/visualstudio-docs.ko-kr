---
title: 'IActiveScriptSiteDebug:: GetDocumentContextFromPosition | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetDocumentContextFromPosition
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetDocumentContextFromPosition
ms.assetid: ba5f7348-0107-4b12-b949-79a012476cf7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61bc36b98fee31ced1f3e8e00d084b5dabcd2124
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570164"
---
# <a name="iactivescriptsitedebuggetdocumentcontextfromposition"></a>IActiveScriptSiteDebug::GetDocumentContextFromPosition
언어 엔진이 `IDebugCodeContext::GetSourceContext`를 위임 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetDocumentContextFromPosition(  
   DWORD_PTR                dwSourceContext,  
   ULONG                    uCharacterOffset,  
   ULONG                    uNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSourceContext`  
 진행 @No__t_0 또는 `AddScriptlet`에 제공 되는 소스 콘텐츠입니다.  
  
 `uCharacterOffset`  
 진행 스크립트 블록 또는 scriptlet의 시작을 기준으로 하는 문자 오프셋입니다.  
  
 `uNumChars`  
 진행 이 컨텍스트의 문자 수입니다.  
  
 `ppsc`  
 제한이 이 문자 위치 범위에 해당 하는 문서 컨텍스트입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 언어 엔진은이 메서드를 사용 하 여 `IDebugCodeContext::GetSourceContext`을 위임 합니다.  
  
## <a name="see-also"></a>참조  
 [IActiveScriptSiteDebug 인터페이스](../../winscript/reference/iactivescriptsitedebug-interface.md)