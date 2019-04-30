---
title: 'CA2233: 연산은 오버플로되지 않아야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- OperationsShouldNotOverflow
- CA2233
helpviewer_keywords:
- OperationsShouldNotOverflow
- CA2233
ms.assetid: 3a2b06ba-6d1b-4666-9eaf-e053ef47ffaa
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7c07dde4c3b992db30c9fc72a0dfa01f0f13b31e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806604"
---
# <a name="ca2233-operations-should-not-overflow"></a>CA2233: 연산은 오버플로되지 않아야 합니다.

|||
|-|-|
|TypeName|OperationsShouldNotOverflow|
|CheckId|CA2233|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

메서드가 산술 연산을 수행 하며 오버플로 방지 하기 위해 미리 피연산자를 확인 하지 않습니다.

## <a name="rule-description"></a>규칙 설명

피연산자는 아닌지 확인 하는 작업의 결과 관련 된 데이터 형식에 대 한 가능한 값의 범위를 벗어나는 첫 번째 유효성을 검사 하지 않고 산술 연산 수행 하지 마십시오. 실행 컨텍스트 및 관련 된 데이터 형식에 따라 산술 오버플로가 발생 하거나는 <xref:System.OverflowException?displayProperty=fullName> 또는 결과의 가장 중요 한 비트를 삭제 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 작업을 수행 하기 전에 피연산자 유효성을 검사 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

피연산자의 가능한 값은 산술 연산 오버플로 일으키지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example-of-a-violation"></a>위반의 예

다음 예제에서 메서드는이 규칙을 위반 하는 정수를 조작 합니다. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 필요 합니다 **제거** 정수 오버플로 옵션을 실행 하려면이 옵션에 대 한 해제 합니다.

[!code-vb[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_1.vb)]
[!code-csharp[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_1.cs)]

이 예제에서 메서드를 전달 하는 경우 <xref:System.Int32.MinValue?displayProperty=fullName>, 연산이 언더플로 됩니다. 이렇게 하면 삭제 될 결과의 가장 중요 한 비트. 다음 코드는이 발생 하는 방법을 보여 줍니다.

```csharp
public static void Main()
{
    int value = int.MinValue;    // int.MinValue is -2147483648
    value = Calculator.Decrement(value);
    Console.WriteLine(value);
}
```

```vb
Public Shared Sub Main()
    Dim value = Integer.MinValue    ' Integer.MinValue is -2147483648
    value = Calculator.Decrement(value)
    Console.WriteLine(value)
End Sub
```

출력:

```text
2147483647
```

## <a name="fix-with-input-parameter-validation"></a>입력된 매개 변수 유효성 검사를 사용 하 여 해결

다음 예제에서는 입력 값의 유효성을 검사 하 여 위반을 해결 합니다.

[!code-csharp[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_2.cs)]
[!code-vb[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_2.vb)]

## <a name="fix-with-a-checked-block"></a>검사 된 블록을 사용 하 여 해결

다음 예제에서는 작업 검사 된 블록에 래핑하여 위반을 해결 합니다. 작업의 결과로 오버플로가 발생 하면는 <xref:System.OverflowException?displayProperty=fullName> throw 됩니다.

선택한 요소에서 지원 되지 않습니다 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]합니다.

[!code-csharp[FxCop.Usage.OperationOverflowChecked#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_3.cs)]

## <a name="turn-on-checked-arithmetic-overflowunderflow"></a>설정에는 산술 연산 오버플로/언더플로 확인

확인 된 산술 연산 오버플로/언더플로 C#을 설정한 경우 모든 정수 연산 검사 된 블록에 배치를 같습니다.

설정 하려면 C#에서 산술 연산 오버플로/언더플로 확인 합니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

2. **빌드** 탭을 선택하고 **고급**을 클릭합니다.

3. 선택 **산술 연산 오버플로/언더플로 확인** 누릅니다 **확인**합니다.

## <a name="see-also"></a>참고자료

- <xref:System.OverflowException?displayProperty=fullName>
- [C# 연산자](/dotnet/csharp/language-reference/operators/index)
- [Checked 및 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)