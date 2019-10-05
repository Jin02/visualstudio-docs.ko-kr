---
title: 'Idiasegment:: Get_write | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSegment::get_write method
ms.assetid: 5fcda988-6be1-4b2f-8660-b59aa78fc35d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 81e4721ea4db124f9161c69b4fced0dacca714c5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839422"
---
# <a name="idiasegmentgetwrite"></a>IDiaSegment::get_write
세그먼트를 수정할 수 있는지 여부를 나타내는 플래그를 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_write ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 반환 `TRUE` 세그먼트에 쓸 수 있으면이 고, 그렇지 않으면 반환 `FALSE`합니다.

## <a name="return-value"></a>반환 값
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="see-also"></a>참고 항목
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)