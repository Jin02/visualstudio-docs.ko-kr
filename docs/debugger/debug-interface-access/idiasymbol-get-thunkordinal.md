---
title: IDiaSymbol::get_thunkOrdinal | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3bc8c523886d694ea413dedcf9a28e53e361882b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72739131"
---
# <a name="idiasymbolget_thunkordinal"></a>IDiaSymbol::get_thunkOrdinal
함수의 썽크 형식을 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_thunkOrdinal ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

제한이 함수의 썽크 유형을 지정 하는 [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md) 열거형의 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 `S_OK`을 반환 합니다. 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환 합니다.

> [!NOTE]
> @No__t_0의 반환 값은 해당 기호에 대해 속성을 사용할 수 없음을 의미 합니다.

## <a name="remarks"></a>주의
 이 속성은 기호가 `SymTagThunk`의 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값인 경우에만 유효 합니다.

 "썽크"는 32 비트 메모리 주소 공간 (플랫 주소 공간이 라고도 함)과 16 비트 주소 공간 (분할 된 주소 공간 이라고 함) 간에 변환 되는 코드 조각입니다.

## <a name="see-also"></a>참조
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)
- [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)