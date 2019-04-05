---
title: LocationType | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 28bcaa626797313f6ea68a17da33ef9ea192a856
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984008"
---
# <a name="locationtype"></a>LocationType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

기호에 포함 된 위치 정보의 종류를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>요소  
 `LocIsNull`  
 위치 정보를 사용할 수 없는 경우  
  
 `LocIsStatic`  
 위치는 정적입니다.  
  
 `LocIsTLS`  
 스레드 로컬 저장소의 위치는입니다.  
  
 `LocIsRegRel`  
 위치는 레지스터 상대입니다.  
  
 `LocIsThisRel`  
 위치가 `this`-상대 합니다.  
  
 `LocIsEnregistered`  
 레지스터에 위치가 있습니다.  
  
 `LocIsBitField`  
 위치는 비트 필드입니다.  
  
 `LocIsSlot`  
 위치는 Microsoft 중간 언어 (MSIL) 슬롯입니다.  
  
 `LocIsIlRel`  
 위치는 MSIL 상대적입니다.  
  
 `LocInMetaData`  
 위치는 메타 데이터입니다.  
  
 `LocIsConstant`  
 위치는 상수 값입니다.  
  
 `LocTypeMax`  
 이 열거형의 위치 형식의 수입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수 있는 속성을 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 인터페이스 내 이미지 파일에서 기호 위치에 따라 달라 집니다. 자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)합니다.  
  
 이 열거형의 값에는 호출에서 반환 되는 [idiasymbol:: Get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)
