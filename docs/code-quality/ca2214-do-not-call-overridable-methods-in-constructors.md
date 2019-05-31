---
title: 'CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.'
ms.date: 05/29/2016
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8e05e6925085b27de3001c8ff62d8a3c6e69a88f
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401307"
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.

|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

봉인 되지 않은 형식의 생성자는 해당 클래스에 정의 된 가상 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명

가상 메서드가 호출 되 면 런타임까지 메서드를 실행 하는 실제 형식을 선택 하지 않았습니다. 생성자는 가상 메서드를 호출 하는 경우 가능 메서드를 호출 하는 인스턴스에 대해 생성자가 실행 되지 않도록 합니다.

> [!NOTE]
> 이 규칙의 이진 분석 구현에는 다양 한 진단 메시지의 " **\[생성자 이름] 클래스에 의해 정의 된 가상 메서드 호출에서 발생 하는 호출 체인이 포함 되어 있습니다. 의도 하지 않은 결과 대 한 다음 호출 스택을 검토**"입니다. 합니다 [FxCop 분석기](install-fxcop-analyzers.md) 이 규칙의 구현을의 진단 메시지에 "**생성자에 재정의 가능한 메서드를 호출 하지 마십시오**"입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 형식의 생성자 내에서 형식의 가상 메서드를 호출 하지 마세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다. 생성자는 가상 메서드에 대 한 호출을 제거 하기 위해 다시 디자인 해야 합니다.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반의 효과 보여 줍니다. 테스트 응용 프로그램의 인스턴스를 만듭니다 `DerivedType`, 기본 클래스인 경우 (`BadlyConstructedType`) 생성자를 실행 합니다. `BadlyConstructedType`생성자의 가상 메서드를 올바르게 호출 `DoSomething`합니다. 출력에서 볼 수 있듯이 `DerivedType.DoSomething()` 하기 전에 실행 `DerivedType`의 생성자를 실행 합니다.

[!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
[!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Calling base ctor.
Derived DoSomething is called - initialized ? No
Calling derived ctor.
```