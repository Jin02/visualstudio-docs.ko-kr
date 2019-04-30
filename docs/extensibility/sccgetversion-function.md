---
title: SccGetVersion 함수 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7e2b3818aaa5097313d9150b365544267768507f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62802557"
---
# <a name="sccgetversion-function"></a>SccGetVersion 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 함수에는 소스 제어 플러그 인에서 지 원하는 원본 제어 플러그 인 API의 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 `LONG` 지원 되는 원본 제어 플러그 인 API의 버전 번호를 포함 하는 데이터 형식:  
  
|WORD|설명|  
|----------|-----------------|  
|HIWORD|주 버전|  
|LOWORD|부 버전|  
  
## <a name="remarks"></a>설명  
 예를 들어, 소스 제어 플러그 인을 원본 제어 플러그 인 API의 버전 1.3을 지 원하는 경우이 함수는 0x0103를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
