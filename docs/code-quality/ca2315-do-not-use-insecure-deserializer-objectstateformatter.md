---
title: 'CA2315: 안전하지 않은 역직렬 변환기 ObjectStateFormatter를 사용하지 마세요.'
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2315
- DoNotUseInsecureDeserializerObjectStateFormatter
ms.openlocfilehash: 30e9d55fa5aa9c909c29935988f76107a4b5556d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237682"
---
# <a name="ca2315-do-not-use-insecure-deserializer-objectstateformatter"></a>CA2315: 안전하지 않은 역직렬 변환기 ObjectStateFormatter를 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerObjectStateFormatter|
|CheckId|CA2315|
|범주|Microsoft.Security|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

Deserialization <xref:System.Web.UI.ObjectStateFormatter?displayProperty=nameWithType> 메서드를 호출 했거나 참조 했습니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙은 <xref:System.Web.UI.ObjectStateFormatter?displayProperty=nameWithType> deserialization 메서드 호출 또는 참조를 찾습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

[!INCLUDE[insecure-deserializers-fixes-for-always-insecure-deserializers](includes/insecure-deserializers-fixes-for-always-insecure-deserializers-md.md)]

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Web.UI;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        ObjectStateFormatter formatter = new ObjectStateFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Web.UI

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As ObjectStateFormatter = New ObjectStateFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```