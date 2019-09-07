---
title: 'CA2213: 삭제 가능한 필드는 삭제해야 합니다.'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 675206bb58e27110af79c46b1d61e9489f7661f2
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766091"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: 삭제 가능한 필드는 삭제해야 합니다.

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

을 구현 <xref:System.IDisposable?displayProperty=fullName> 하는 형식은도 구현 <xref:System.IDisposable>하는 형식의 필드를 선언 합니다. <xref:System.IDisposable.Dispose%2A> 필드의 <xref:System.IDisposable.Dispose%2A> 메서드는 선언 형식의 메서드에서 호출 되지 않습니다.

## <a name="rule-description"></a>규칙 설명

형식은 관리 되지 않는 모든 리소스의 삭제를 담당 합니다. 규칙 CA2213 삭제 가능한 형식 (즉,을 <xref:System.IDisposable>구현 하는 형식) `T` 이 삭제 가능한 형식의 `FT`인스턴스인 필드 `F` 를 선언 하는지 여부를 확인 합니다. 포함 하는 `F` 형식의 `T`메서드 또는 이니셜라이저 내에서 로컬로 만든 개체가 할당 된 각 필드에 대 한 호출 `FT.Dispose`을 찾으려고 시도 합니다. 규칙은에 의해 `T.Dispose` 호출 되는 메서드와 한 수준 낮은 (즉,에 의해 `T.Dispose`호출 되는 메서드에 의해 호출 되는 메서드)를 검색 합니다.

> [!NOTE]
> [특수 한 경우](#special-cases)를 제외 하 고, 규칙 CA2213 포함 하는 형식의 메서드 및 이니셜라이저 내에서 로컬로 생성 된 삭제 가능 개체를 할당 한 필드에 대해서만 발생 합니다. 개체를 만들거나 형식 `T`외부에서 할당 한 경우에는 규칙이 실행 되지 않습니다. 이렇게 하면 포함 하는 형식이 개체의 삭제를 담당 하지 않는 경우의 노이즈가 줄어듭니다.

### <a name="special-cases"></a>특수 한 경우

CA2213 규칙은 할당 된 개체가 로컬로 생성 되지 않은 경우에도 다음 형식의 필드에 대해 발생 합니다.

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

이러한 형식 중 하나의 개체를 생성자에 전달 하 고 필드에 할당 하면 새로 생성 된 형식에 대 한 *삭제 소유권 전송이* 표시 됩니다. 즉, 새로 생성 된 형식이 이제 개체의 삭제를 담당 합니다. 개체가 삭제 되지 않으면 CA2213 위반이 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면를 구현 <xref:System.IDisposable.Dispose%2A> <xref:System.IDisposable>하는 형식의 필드에 대해를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

다음 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

- 플래그가 지정 된 형식은 필드에서 보유 하는 리소스를 해제 하는 일을 담당 하지 않습니다. 즉, 형식에 *삭제 소유권이*없습니다.
- 에 대 <xref:System.IDisposable.Dispose%2A> 한 호출은 규칙 검사 보다 더 깊은 호출 수준에서 발생 합니다.

## <a name="example"></a>예제

다음 코드 조각에서는을 구현 `TypeA` <xref:System.IDisposable>하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

다음 코드 조각은 필드에 대해 `TypeB` 를 호출 <xref:System.IDisposable.Dispose%2A> 하지 않고 필드 `aFieldOfADisposableType` 를 삭제 가능한 형식 (`TypeA`)으로 선언 하 여 규칙 CA2213를 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

위반 문제를 해결 하려면 삭제 `Dispose()` 가능한 필드에 대해를 호출 합니다.

```csharp
protected virtual void Dispose(bool disposing)
{
   if (!disposed)
   {
      // Dispose of resources held by this instance.
      aFieldOfADisposableType.Dispose();

      disposed = true;

      // Suppress finalization of this disposed instance.
      if (disposing)
      {
          GC.SuppressFinalize(this);
      }
   }
}
```

## <a name="see-also"></a>참고자료

- <xref:System.IDisposable?displayProperty=fullName>
- [Dispose 패턴](/dotnet/standard/design-guidelines/dispose-pattern)