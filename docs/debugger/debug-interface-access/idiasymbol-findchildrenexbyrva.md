---
title: IDiaSymbol::findChildrenExByRVA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByRVA
ms.assetid: cbc57c6c-7d64-4469-a114-1dd6671e5ec5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e33f458b3c65d8765ba5cb62e635cf5d39819d60
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831782"
---
# <a name="idiasymbolfindchildrenexbyrva"></a>IDiaSymbol::findChildrenExByRVA
지정 된 상대 가상 주소 (RVA)에서 사용할 수 있는 기호 자식을 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT findChildrenExByRVA ( 
   enum SymTagEnum   symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   DWORD             address,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>매개 변수
 `symtag`

[in] 에 정의 된 대로 검색 되는 자식의 기호 태그를 지정 합니다 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)합니다. 로 `SymTagNull` 검색할 모든 자식에 대 한 합니다.

 `name`

[in] 검색할 자식 컨트롤의 이름을 지정 합니다. 로 `NULL` 검색할 모든 자식에 대 한 합니다.

 `compareFlags`

[in] 이름 일치에 적용할 비교 옵션을 지정 합니다. 값을 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.

 `address`

[in] RVA를 지정합니다.

 `ppResult`

[out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록을 포함 하는 개체 검색 합니다.

## <a name="return-value"></a>반환 값
 반환 `S_OK` 기호의 자식이 하나 이상 찾을 하거나 반환 하는 경우 `S_FALSE` 자식이 없는 경우; 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 반환 되는 로컬 기호 라이브 범위 정보를 포함 합니다.

## <a name="requirements"></a>요구 사항
 헤더: Dia2.h

 라이브러리: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)