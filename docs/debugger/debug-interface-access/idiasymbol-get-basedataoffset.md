---
title: 'IDiaSymbol:: get_baseDataOffset | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bb2ff5ed-9293-4c37-9741-654058b571c5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 298903e4e76c34fe1013b0f26729fb900c7b3fea
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740979"
---
# <a name="idiasymbolget_basedataoffset"></a>IDiaSymbol::get_baseDataOffset
기본 데이터 오프셋을 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_baseDataOffset(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

제한이 기본 데이터 오프셋을 보유 하는 `DWORD`에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값
 성공 하면 `S_OK`을 반환 합니다. 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환 합니다.

## <a name="see-also"></a>참조
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)