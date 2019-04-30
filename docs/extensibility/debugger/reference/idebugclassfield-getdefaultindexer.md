---
title: IDebugClassField::GetDefaultIndexer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d884b8e066b539b925e50d4f49f65168ca6156c0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922819"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
기본 인덱서의 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetDefaultIndexer( 
   BSTR* pbstrIndexer
);
```

```csharp
int GetDefaultIndexer(
   out string pbstrIndexer
);
```

#### <a name="parameters"></a>매개 변수
 `pbstrIndexer`

 [out] 기본 인덱서 이름을 포함 하는 문자열을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 하거나 기본 인덱서가 없습니다 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="remarks"></a>설명
 로 표시 된 속성인 클래스의 기본 인덱서는 `Default` 배열 액세스에 대 한 속성입니다. 관련 된 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]합니다. 선언에서 기본 인덱서에의 예로 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] 사용 방법.

```vb
Imports System.Collections;

Public Class Class1
    Private myList as Hashtable

    Default Public Property Item(ByVal Index As Integer) As Integer
        Get
            Return CType(List(Index), Integer)
        End Get
        Set(ByVal Value As Integer)
            List(Index) = Value
        End Set
    End Property
End Class

Function GetItem(Index as Integer) as Integer
    Dim classList as Class1 = new Class1
    Dim value as Integer

    ' Access array through default indexer
    value = classList(2)

    ' Access array through explicit property
    value = classList.Item(2)

    Return value
End Function
```

## <a name="see-also"></a>참고 항목
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)