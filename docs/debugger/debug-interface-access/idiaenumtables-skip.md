---
title: 'IDiaEnumTables:: Skip | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Skip method
ms.assetid: 5c9db956-0654-4f1a-8775-530aa980d8ec
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48e4da48699bc9797c7ccbfb0f21bb0b2007c752
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743709"
---
# <a name="idiaenumtablesskip"></a>IDiaEnumTables::Skip
열거형 시퀀스에서 지정 된 수의 테이블을 건너뜁니다.

## <a name="syntax"></a>구문

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>매개 변수
 `celt`

진행 건너뛸 열거 시퀀스의 테이블 수입니다.

## <a name="return-value"></a>반환 값
 성공 하면 `S_OK`을 반환 합니다. 그렇지 않으면 건너뛸 테이블이 더 이상 없는 경우 `S_FALSE`을 반환 합니다.

## <a name="see-also"></a>참조
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)