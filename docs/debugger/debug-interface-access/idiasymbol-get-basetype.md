---
title: 'Idiasymbol:: Get_basetype | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_baseType method
ms.assetid: 5c69a241-a8d3-48ed-8b36-27463a196572
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1d38e39fd7687de3ff87737b49972cb389187aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837609"
---
# <a name="idiasymbolgetbasetype"></a>IDiaSymbol::get_baseType
이 기호에 대 한 기본 형식을 검색<em>합니다.</em>

## <a name="syntax"></a>구문

```C++
HRESULT get_baseType (
    DWORD* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
`pRetVal`

[out] 값을 반환 합니다 [BasicType 열거형](../../debugger/debug-interface-access/basictype.md) 기호의 기본 형식을 지정 하는 열거형입니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.

## <a name="remarks"></a>설명
기호에 대 한 기본 형식은 먼저 기호의 형식을 가져오고 다음 기본 형식에 대 한 형식을 반환 하는 조회 하 여 확인할 수 있습니다. 참고 일부 기호는 기본 형식에 없을 수 있습니다-예를 들어 구조 이름입니다.

## <a name="example"></a>예제

```C++
IDiaSymbol* pType;
CComPtr<IDiaSymbol> pBaseType;
if (pType->get_type( &pBaseType ) == S_OK)
{
    BasicType btBaseType;
    if (pBaseType->get_baseType((DWORD *)&btBaseType) == S_OK)
    {
        // Do something with basic type.
    }
}
```

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v7.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [BasicType 열거형](../../debugger/debug-interface-access/basictype.md)
- [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)
