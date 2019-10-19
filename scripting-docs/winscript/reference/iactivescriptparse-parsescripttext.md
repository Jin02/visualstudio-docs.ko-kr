---
title: IActiveScriptParse::P arseScriptText | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.ParseScriptText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_ParseScriptText
ms.assetid: 2d237d6c-cc65-415b-8808-72791304a136
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4f35b398a7348f4e2bdbaaa9ab3e322bf69ddb6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561613"
---
# <a name="iactivescriptparseparsescripttext"></a>IActiveScriptParse::ParseScriptText
지정 된 코드 scriptlet를 구문 분석 하 여 네임 스페이스에 선언을 추가 하 고 코드를 적절 하 게 평가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ParseScriptText(  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // cookie for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    VARIANT *pvarResult,             // address of buffer for results  
    EXCEPINFO *pexcepinfo            // address of buffer for error data  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|`pstrCode`|진행 평가할 scriptlet 텍스트의 주소입니다. 이 문자열의 해석은 스크립팅 언어에 따라 달라 집니다.|  
|`pstrItemName`|진행 Scriptlet을 평가할 컨텍스트를 제공 하는 항목 이름의 주소입니다. 이 매개 변수가 NULL 이면 스크립팅 엔진의 전역 컨텍스트에서 코드가 평가 됩니다.|  
|`punkContext`|진행 컨텍스트 개체의 주소입니다. 이 개체는 디버깅 환경에서 사용 하도록 예약 되어 있습니다. 이러한 컨텍스트는 디버거에서 활성 런타임 컨텍스트를 나타내는 컨텍스트를 제공할 수 있습니다. 이 매개 변수가 NULL 인 경우 엔진은 `pstrItemName`를 사용 하 여 컨텍스트를 식별 합니다.|  
|`pstrDelimiter`|진행 Scriptlet 끝 구분 기호의 주소입니다. 텍스트 스트림에서 `pstrCode` 구문 분석 되는 경우 호스트는 일반적으로 두 개의 작은따옴표 (' ')와 같은 구분 기호를 사용 하 여 scriptlet의 끝을 검색 합니다. 이 매개 변수는 호스트에서 사용 하는 구분 기호를 지정 하 여 스크립팅 엔진에서 일부 조건부 기본 전처리를 제공할 수 있도록 합니다. 예를 들어 작은따옴표 [']를 구분 기호로 사용 하기 위한 두 개의 작은따옴표로 바꿉니다. 스크립팅 엔진에서이 정보를 사용 하는 정확한 방법 (및)은 스크립팅 엔진에 따라 달라 집니다. 호스트가 scriptlet의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우이 매개 변수를 `NULL`으로 설정 합니다.|  
|`dwSourceContextCookie`|진행 디버깅 목적으로 사용 되는 쿠키입니다.|  
|`ulStartingLineNumber`|진행 구문 분석이 시작 되는 줄을 지정 하는 0부터 시작 하는 값입니다.|  
|`dwFlags`|진행 Scriptlet와 연결 된 플래그입니다. 는 다음과 같은 값을 조합 하 여 사용할 수 있습니다.|  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTTEXT_ISEXPRESSION|계산 식과 문 간의 차이가 중요 하지만 스크립트 언어에서 구문상 모호한 경우이 플래그는 scriptlet이 문 또는 문 목록이 아니라 식으로 해석 되도록 지정 합니다. 기본적으로 scriptlet 텍스트의 구문에서 올바른 선택 항목을 결정할 수 없으면 문이 가정 됩니다.|  
|SCRIPTTEXT_ISPERSISTENT|이 호출 중에 추가 된 코드는 스크립팅 엔진이 저장 된 경우 (예: `IPersist*::Save`에 대 한 호출을 통해) 또는 스크립팅 엔진이 초기화 된 상태로 전환 되는 방식으로 다시 설정 된 경우 저장 되어야 함을 나타냅니다.|  
|SCRIPTTEXT_ISVISIBLE|스크립트 텍스트를 스크립트의 이름 공간에서 전역 메서드로 표시 하 고, 따라서 이름으로 호출할 수 있음을 나타냅니다.|  
  
|||  
|-|-|  
|`pvarResult`|제한이 Scriptlet 처리 결과를 수신 하는 버퍼의 주소 이거나, 호출자가 결과를 기대 하지 않는 경우 (즉, SCRIPTTEXT_ISEXPRESSION 값이 설정 되지 않은 경우) `NULL`입니다.|  
|`pexcepinfo`|제한이 예외 정보를 받는 구조체의 주소입니다. 이 구조는 `IActiveScriptParse::ParseScriptText`에서 DISP_E_EXCEPTION를 반환 하는 경우에 채워집니다.|  
  
## <a name="return-value"></a>반환 값  
 는 다음 값 중 하나를 반환 합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|성공할.|  
|`DISP_E_EXCEPTION`|Scriptlet를 처리 하는 동안 예외가 발생 했습니다. @No__t_0 매개 변수에는 예외에 대 한 정보가 포함 되어 있습니다.|  
|`E_INVALIDARG`|인수가 잘못 되었습니다.|  
|`E_POINTER`|잘못 된 포인터가 지정 되었습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다. 스크립팅 엔진은 식 또는 문의 런타임 계산을 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출을 사용할 수 없습니다. 예를 들어 스크립팅 엔진이 초기화 되지 않음 또는 닫힘 상태 이거나 SCRIPTTEXT_ISEXPRESSION 플래그가 설정 되었고 스크립팅 엔진이 초기화 된 상태에 있습니다.|  
|`OLESCRIPT_E_SYNTAX`|Scriptlet에서 지정 되지 않은 구문 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>주의  
 스크립팅 엔진이 초기화 된 상태 이면 실제로이 호출 중에 코드는 계산 되지 않습니다. 대신 이러한 코드는 스크립팅 엔진이 시작 됨 상태로 전환 될 때 큐에 대기 되 고 실행 됩니다. 초기화 된 상태에서는 실행이 허용 되지 않으므로 초기화 된 상태에서 SCRIPTTEXT_ISEXPRESSION 플래그를 사용 하 여이 메서드를 호출 하면 오류가 발생 합니다.  
  
 Scriptlet는 식, 문 목록 또는 스크립트 언어에서 허용 하는 모든 것이 될 수 있습니다. 예를 들어이 메서드는 html \<SCRIPT > 태그를 평가 하는 데 사용 됩니다 .이 태그를 사용 하면 HTML 페이지가 생성 될 때 문을 스크립트 상태로 컴파일하지 않고 실행할 수 있습니다.  
  
 이 메서드에 전달 된 코드는 유효한 전체 코드 부분 이어야 합니다. 예를 들어 VBScript에서 Sub 함수 (x)를 사용 하 여이 메서드를 한 번 호출한 다음 `End Sub`를 사용 하 여이 메서드를 두 번 호출할 수 없습니다. 파서는 서브루틴을 완료 하기 위해 두 번째 호출이 대기 하지 않고 서브루틴 선언이 시작 되었지만 완료 되지 않았기 때문에 구문 분석 오류를 생성 해야 합니다.  
  
 스크립트 상태에 대 한 자세한 내용은 [Windows 스크립트](../../winscript/windows-script-engines.md)엔진의 스크립트 엔진 상태 섹션을 참조 하십시오.  
  
## <a name="see-also"></a>참조  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)