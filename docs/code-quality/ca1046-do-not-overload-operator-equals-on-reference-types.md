---
title: 'CA1046: 참조 형식에 같음 연산자를 오버로드하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9f9304fcd86a9b36a729b1436fe16471b449ac0d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778725"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: 참조 형식에 같음 연산자를 오버로드하지 마세요.

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 중첩 된 공용 참조 형식이 같음 연산자를 오버 로드합니다.

## <a name="rule-description"></a>규칙 설명
 참조 형식의 경우 같음 연산자의 기본 구현은 대부분 항상 올바릅니다. 기본적으로 두 참조는 같은 개체를 가리킬 경우에만 같습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 같음 연산자 구현의 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 참조 형식은 기본 제공 값 형식 처럼 동작 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 더하기 또는 빼기 형식의 인스턴스에서 작업을 수행 하는 의미 있는 경우 같음 연산자를 구현 하 여 위반을 표시 하지 않으려면 잘못 되었을 것입니다.

## <a name="example"></a>예제
 다음 예제에서는 두 개의 참조를 비교할 때 기본 동작을 보여 줍니다.

 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]

## <a name="example"></a>예제

다음 응용 프로그램 일부 참조를 비교 합니다.

[!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
a = new (2,2) and b = new (2,2) are equal? No
c and a are equal? Yes
b and a are == ? No
c and a are == ? Yes
```

## <a name="related-rules"></a>관련된 규칙

[CA1013: 오버 로드에 같음 연산자를 오버 더하기 및 빼기](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)