---
title: 'CA2224: 오버 로드 연산자 equals에 대 한 Override equals | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 39272790b6ef366c64d45e0aea238606d0b62bf4
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85538638"
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|
|CheckId|CA2224|
|범주|Microsoft 사용|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 형식은 같음 연산자를 구현 하지만는 재정의 하지 않습니다 <xref:System.Object.Equals%2A?displayProperty=fullName> .

## <a name="rule-description"></a>규칙 설명
 같음 연산자는 구문상 편리 하 게 메서드 기능에 액세스 하는 방법입니다 <xref:System.Object.Equals%2A> . 같음 연산자를 구현 하는 경우 해당 논리는의 해당 논리와 동일 해야 합니다 <xref:System.Object.Equals%2A> .

 코드가이 규칙을 위반 하는 경우 c # 컴파일러에서 경고를 발생 시킵니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 같음 연산자의 구현을 제거 하거나를 재정의 하 <xref:System.Object.Equals%2A> 고 두 메서드가 같은 값을 반환 하도록 해야 합니다. 같음 연산자에서 일관 되지 않은 동작이 발생 하지 않는 경우 <xref:System.Object.Equals%2A> <xref:System.Object.Equals%2A> 기본 클래스의 메서드를 호출 하는의 구현을 제공 하 여 위반을 해결할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 같음 연산자가의 상속 된 구현과 동일한 값을 반환 하는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 <xref:System.Object.Equals%2A> 합니다. 예제 섹션에는이 규칙에서 경고를 안전 하 게 표시 하지 않을 수 있는 형식이 포함 되어 있습니다.

## <a name="examples-of-inconsistent-equality-definitions"></a>일치 하지 않는 같음 정의의 예

### <a name="description"></a>설명
 다음 예제에서는 일치 하는 정의가 일치 하지 않는 형식을 보여 줍니다. `BadPoint`같음 연산자의 사용자 지정 구현을 제공 하 여 같음의 의미를 변경 하지만 동일 하 게 동작 하도록를 재정의 하지는 않습니다 <xref:System.Object.Equals%2A> .

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OperatorEqualsRequiresEquals/cs/FxCop.Usage.OperatorEqualsRequiresEquals.cs#1)]

## <a name="example"></a>예제
 다음 코드에서는의 동작을 테스트 합니다 `BadPoint` .

 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestOperatorEqualsRequiresEquals/cs/FxCop.Usage.TestOperatorEqualsRequiresEquals.cs#1)]

 이 예제의 결과는 다음과 같습니다.

 **a = ([0] 1, 1) 및 b = ([1] 2, 2)가 동일 한가요? 아니요** 
 **= = b? ** 
 **A1과 a가 같지 않나요? 예** 
 **a1 = = a? 예** 
 **b와 bcopy는 동일 합니까? ** 
 **B = = bcopy가 없나요? 예**
## <a name="example"></a>예제
 다음 예제에서는 기술적으로이 규칙을 위반 하지만 일관 되지 않은 방식으로 동작 하지 않는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ValueTypeEquals/cs/FxCop.Usage.ValueTypeEquals.cs#1)]

## <a name="example"></a>예제
 다음 코드에서는의 동작을 테스트 합니다 `GoodPoint` .

 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestValueTypeEquals/cs/FxCop.Usage.TestValueTypeEquals.cs#1)]

 이 예제의 결과는 다음과 같습니다.

 **a = (1, 1) 및 b = (2, 2)가 동일 한가요? 아니요** 
 **= = b? ** 
 **A1과 a가 같지 않나요? 예** 
 **a1 = = a? 예** 
 **b와 bcopy는 동일 합니까? 예** 
 **b = = bcopy? 예**
## <a name="class-example"></a>클래스 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 클래스 (참조 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassViolation/cs/FxCop.Usage.OverrideEqualsClassViolation.cs#1)]

## <a name="example"></a>예제
 다음 예에서는를 재정의 하 여 위반을 수정 합니다 <xref:System.Object.Equals%2A?displayProperty=fullName> .

 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassFixed/cs/FxCop.Usage.OverrideEqualsClassFixed.cs#1)]

## <a name="structure-example"></a>구조 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 구조체 (값 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructViolation/cs/FxCop.Usage.OverrideEqualsStructViolation.cs#1)]

## <a name="example"></a>예제
 다음 예에서는를 재정의 하 여 위반을 수정 합니다 <xref:System.ValueType.Equals%2A?displayProperty=fullName> .

 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructFixed/cs/FxCop.Usage.OverrideEqualsStructFixed.cs#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마세요.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2218: Equals를 재정할 때 GetHashCode를 재정의하세요.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
