---
title: IDiaSymbol::get_type | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fa57b1f289f9cc5e8c57c08b6d51bb1677c3db4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62835374"
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
이 기호에 대 한 형식을 나타내는 기호를 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_type (
    IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>매개 변수
`pRetVal`

[out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 이 기호의 형식을 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="remarks"></a>설명
기호는 형식을 확인 하려면이 메서드를 호출 하며 결과 검사할 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다. 형식 없는 기호에 대 한 수 있다는 것을 참고 합니다. 예를 들어 구조의 이름 형식이 있지만 자식 기호를 가질 수 있습니다 (사용 된 [idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md) 해당 자식 항목을 검사 하는 방법).

## <a name="example"></a>예제

```C++
IDiaSymbol*         pType;
CComPtr<IDiaSymbol> pBaseType;
if (SUCCEEDED(pType->get_type( &pBaseType ))) {
    BasicType btBaseType;
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {
        // Do something with basic type.
    }
}
```

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)
- [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)
