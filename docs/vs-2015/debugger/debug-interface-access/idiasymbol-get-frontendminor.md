---
title: 'Idiasymbol:: Get_frontendminor | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMinor method
ms.assetid: 40792153-827c-4859-be7c-6aa16d5abab6
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 12e5956f880a79d7946ff9655ec1ef3d1a79ff22
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435410"
---
# <a name="idiasymbolgetfrontendminor"></a>IDiaSymbol::get_frontEndMinor
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

프런트 엔드 부 버전 번호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_frontEndMinor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] Front.end 부 버전 번호를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 일반적으로 두 가지 기본 요소 이루어져: 소스 코드를 중간 형식으로 구문 분석을 처리 하는 프런트 엔드 (파서) 및 어셈블리로 중간 형식으로 변환 하는 백 엔드 (코드 생성기). 백 엔드가 아닌 다른 버전에 프런트 엔드에 대 한 일반적이 지 않은 것입니다.  
  
 프런트 엔드 또는 백 엔드 버전 번호를 세 부분으로 구성 됩니다. \<주요 >.\< 부 버전 >. \<빌드 >, 여기서 \<주요 >는 주 버전 번호 이며 \<부 >는 부 버전 번호 이며 및 \<빌드 >는 빌드 번호입니다. 예를 들어 13.10.3077.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
