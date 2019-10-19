---
title: 'CA2202: 개체를 여러 번 삭제 하지 마십시오. Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e0be715d8aea84fac53ea2a796e71850b961730c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667395"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: 개체를 여러 번 삭제하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDisposeObjectsMultipleTimes|
|CheckId|CA2202|
|범주|Microsoft 사용|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 메서드 구현에는 동일한 개체의 일부 형식에 대 한 Close () 메서드와 같이 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>에 대 한 여러 호출을 발생 시킬 수 있는 코드 경로가 포함 되어 있습니다.

## <a name="rule-description"></a>규칙 설명
 올바르게 구현 된 <xref:System.IDisposable.Dispose%2A> 메서드는 예외를 throw 하지 않고 여러 번 호출할 수 있습니다. 그러나이는 보장 되지 않으며 <xref:System.ObjectDisposedException?displayProperty=fullName> 생성 하지 않기 위해 개체에서 <xref:System.IDisposable.Dispose%2A>를 두 번 이상 호출 하면 안 됩니다.

## <a name="related-rules"></a>관련 규칙
 [CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 코드 <xref:System.IDisposable.Dispose%2A> 경로에 관계 없이 개체에 대해 한 번만 호출 되도록 구현을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 개체에 대 한 <xref:System.IDisposable.Dispose%2A>를 안전 하 게 여러 번 호출할 수 있는 것으로 알려진 경우에도 나중에 구현이 변경 될 수 있습니다.

## <a name="example"></a>예제
 중첩 된 `using` 문 (Visual Basic의 `Using`)은 CA2202 경고 위반을 일으킬 수 있습니다. 중첩 된 내부 `using` 문의 IDisposable 리소스가 외부 `using` 문의 리소스를 포함 하는 경우 중첩 된 리소스의 `Dispose` 메서드는 포함 된 리소스를 해제 합니다. 이러한 상황이 발생 하면 외부 `using` 문의 `Dispose` 메서드에서 해당 리소스를 두 번째로 삭제 하려고 시도 합니다.

 다음 예제에서는 외부 using 문에 생성 된 <xref:System.IO.Stream> 개체가 `stream` 개체를 포함 하는 <xref:System.IO.StreamWriter> 개체의 Dispose 메서드에서 내부 using 문 끝에 릴리스됩니다. 외부 `using` 문이 끝날 때 `stream` 개체가 두 번째로 해제 됩니다. 두 번째 릴리스는 CA2202를 위반 하는 것입니다.

```
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}
```

## <a name="example"></a>예제
 이 문제를 해결 하려면 외부 `using` 문 대신 `finally` 블록 / `try`을 사용 합니다. @No__t_0 블록에서 `stream` 리소스가 null이 아닌지 확인 합니다.

```
Stream stream = null;
try
{
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);
    using (StreamWriter writer = new StreamWriter(stream))
    {
        stream = null;
        // Use the writer object...
    }
}
finally
{
    if(stream != null)
        stream.Dispose();
}
```

## <a name="see-also"></a>관련 항목:
 <xref:System.IDisposable?displayProperty=fullName> [Dispose 패턴](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
