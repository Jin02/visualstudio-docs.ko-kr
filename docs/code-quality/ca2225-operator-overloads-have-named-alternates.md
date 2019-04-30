---
title: 'CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a8a1c7015421b686d47bfea4c3341ec76748f8ad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806617"
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.

|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

연산자 오버 로드 된 검색 및 예상 되는 이름의 대체 메서드를 찾을 수 없습니다.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

연산자 오버 로드는 형식에 대 한 계산을 나타내는 기호를 사용할 수 있습니다. 예를 들어 더하기 기호 (+)를 추가 하기 위해 오버 로드 하는 형식 이름이 'Add' 인 멤버를 대체 해야 일반적으로 합니다. 명명 된 대체 멤버 연산자와 동일한 기능에 대 한 액세스를 제공 하 고 오버 로드 된 연산자를 지원 하지 않는 언어로 프로그래밍 하는 개발자를 위한 제공 됩니다.

이 규칙에는 다음 표에 나열 된 연산자를 검사 합니다.

|C#|Visual Basic|C++|대체 이름|
|---------|------------------|-----------|--------------------|
|+ (이진)|+|+ (이진)|Add|
|+=|+=|+=|Add|
|&|And|&|BitwiseAnd|
|&=|=|&=|BitwiseAnd|
|&#124;|Or|&#124;|BitwiseOr|
|&#124;=|또는 =|&#124;=|BitwiseOr|
|--|N/A|--|감소|
|/|/|/|나누기|
|/=|/=|/=|나누기|
|==|=|==|같음|
|^|Xor|^|Xor|
|^=|Xor=|^=|Xor|
|>|>|>|비교|
|>=|>=|>=|비교|
|++|N/A|++|증가|
|<>|!=|같음|
|<<|<<|<<|LeftShift|
|<<=|<<=|<<=|LeftShift|
|<|<|<|비교|
|<=|<=|\<=|비교|
|&&|N/A|&&|LogicalAnd|
|&#124;&#124;|N/A|&#124;&#124;|LogicalOr|
|!|N/A|!|LogicalNot|
|%|Mod|%|나머지 또는 mod|
|%=|N/A|%=|Mod|
|* (이진)|*|*|곱하기|
|*=|N/A|*=|곱하기|
|~|not|~|OnesComplement|
|>>|>>|>>|RightShift|
=|N/A|>>=|RightShift|
|-(이진)|-(이진)|-(이진)|빼기|
|-=|N/A|-=|빼기|
|true|IsTrue|N/A|IsTrue (속성)|
|-(단항)|N/A|-|negate|
|+ (단항)|N/A|+|더하기|
|False|IsFalse|False|IsTrue (속성)|

해당 사항 없음 = = 선택한 언어로 오버 로드할 수 없습니다.

규칙 확인 형식의 암시적 및 명시적 캐스트 연산자 (`SomeType`) 라는 메서드를 검사 하 여 `ToSomeType` 고 `FromSomeType`입니다.

C#, 이항 연산자가 오버 로드 되 면 해당 대입 연산자도 있는 경우 이기도 암시적으로 오버 로드 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 연산자에 대 한 대체 메서드를 구현 권장 되는 대체 이름을 사용 하 여 이름을 지정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

공유 라이브러리를 구현 하는 경우에이 규칙에서 경고를 표시 하지 마십시오. 응용 프로그램에서이 규칙 경고를 무시 해도 됩니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca2225.api_surface = private, internal
```

이 범주 (사용량)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반 하는 구조체를 정의 합니다. 예제를 수정 하려면 추가 공용 `Add(int x, int y)` 구조 방법입니다.

[!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1046: 참조 형식에 같음 연산자 오버 로드 하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: 같음 연산자를 오버 로드할 때 equals 재정의](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Equals GetHashCode를 재정의 합니다.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)