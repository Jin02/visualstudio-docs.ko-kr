---
title: IDiaSymbol::findInlineeLinesByVA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61427d33-30d2-4ac9-9bd6-c58c6c705072
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 81ae02877b7e81e0d2240ab2c6eea68f22f0e2d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837864"
---
# <a name="idiasymbolfindinlineelinesbyva"></a>IDiaSymbol::findInlineeLinesByVA
클라이언트가 없는 인라인을 직접 또는 간접적으로이 기호는 지정 된 가상 주소 (VA) 내에서 모든 함수의 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT findInlineeLinesByVA ( 
   ULONGLONG             va,
   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>매개 변수
 `va`

[in] VA.로 주소를 지정합니다.

 `length`

[in] 이 쿼리를 처리 하기 위해 바이트 수의 주소 범위를 지정 합니다.

 `ppResult`

[out] 보유 한 `IDiaEnumLineNumbers` 검색 되는 줄 번호의 목록을 포함 하는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)