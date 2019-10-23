---
title: 레이블 (Debug Interface Access SDK) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locations, in program code
- Label symbol
ms.assetid: 8cef7620-5bc8-4500-8bd0-e9e638bccb24
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d76238e11ebb30d98465836115505ab25d247524
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738685"
---
# <a name="label-debug-interface-access-sdk"></a>레이블(디버그 인터페이스 액세스 SDK)
프로그램 코드의 위치는 `SymTagLabel` 기호로 식별 됩니다.

## <a name="properties"></a>데이터 액세스
 다음 표에서는이 기호 형식에 유효한 속성을 보여 줍니다.

|속성|데이터 형식|설명|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|위치의 오프셋 부분 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)을 참조 하세요.|
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Location의 Section 부분 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)을 참조 하세요.|
|[IDiaSymbol::get_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|레이블에 사용자 지정 호출 규칙을 사용 하는 경우 `TRUE` 합니다.|
|[IDiaSymbol::get_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|레이블에서 먼 반환을 수행 하는 경우에 `TRUE` 합니다.|
|[IDiaSymbol::get_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|레이블에 인터럽트가 반환 되는 경우에 `TRUE` 합니다.|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 compiland, block 또는 함수에 대 한 기호입니다.|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호의 ID입니다.|
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|레이블에 정적 위치가 있습니다. 자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md) 열거를 참조 하세요.|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|레이블의 이름입니다.|
|[IDiaSymbol::get_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|레이블이 [noinline](/cpp/cpp/noinline) 특성으로 지정 된 경우 `TRUE` 합니다.|
|[IDiaSymbol::get_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|[noreturn](/cpp/cpp/noreturn) 특성을 사용 하 여 레이블을 지정 했는지 여부를 `TRUE` 합니다.|
|[IDiaSymbol::get_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|레이블이 호출 되지 않는 경우 `TRUE` 합니다.|
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|메모리의 기호 오프셋입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)`LocIsRegRel`를 참조 하세요.|
|[IDiaSymbol::get_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|코드에 최적화 된 코드에 대 한 디버그 정보가 있는지 여부를 `TRUE` 합니다.|
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|모듈 내에서이 레이블의 상대 위치입니다.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호의 인덱스 ID입니다.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|[SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값 중 하나인 `SymTagFuncDebugLabel` 반환 합니다.|
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|실행 가능 이미지 내에서이 레이블의 위치입니다.|

## <a name="see-also"></a>참조
- [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
- [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)