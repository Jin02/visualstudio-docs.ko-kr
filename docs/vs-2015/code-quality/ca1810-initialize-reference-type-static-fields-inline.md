---
title: 'CA1810: 참조 형식 정적 필드를 인라인으로 초기화 하십시오. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: c4ad2f4db9290430bb8a378bd264078370ca7b66
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85543834"
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: 참조 형식 정적 필드를 인라인으로 초기화하세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|InitializeReferenceTypeStaticFieldsInline|
|CheckId|CA1810|
|범주|Microsoft 성능|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 참조 형식은 명시적인 정적 생성자를 선언 합니다.

## <a name="rule-description"></a>규칙 설명
 형식이 명시적인 정적 생성자를 선언하면 JIT(Just-in-Time) 컴파일러는 형식의 각 정적 메서드와 인스턴스 생성자에 검사를 추가하여 정적 생성자를 이전에 호출했는지 확인합니다. 정적 멤버에 액세스 하거나 형식의 인스턴스를 만들 때 정적 초기화가 트리거됩니다. 그러나 형식의 변수를 선언 하지만 사용 하지 않는 경우 정적 초기화는 트리거되지 않습니다 .이는 초기화가 전역 상태를 변경 하는 경우 중요할 수 있습니다.

 모든 정적 데이터를 인라인으로 초기화 하 고 명시적인 정적 생성자를 선언 하지 않은 경우 MSIL (Microsoft 중간 언어) 컴파일러는 `beforefieldinit` 플래그 및 정적 데이터를 초기화 하는 암시적 정적 생성자를 msil 형식 정의에 추가 합니다. JIT 컴파일러가 플래그를 발견 하면 `beforefieldinit` 정적 생성자가 확인 하는 대부분의 시간이 추가 되지 않습니다. 정적 메서드 또는 인스턴스 생성자가 호출 되기 전에는 정적 필드에 액세스 하기 전에 특정 시간에 정적 초기화가 수행 됩니다. 정적 초기화는 형식의 변수가 선언 된 후 언제 든 지 발생할 수 있습니다.

 정적 생성자 검사로 인해 성능이 저하될 수 있습니다. 정적 생성자는 정적 필드를 초기화 하는 데만 사용 됩니다 .이 경우 정적 필드에 대 한 첫 번째 액세스 전에 정적 초기화만 발생 해야 합니다. `beforefieldinit`동작은 이러한 및 대부분의 다른 형식에 적합 합니다. 정적 초기화는 글로벌 상태에 영향을 주고 다음 중 하나에 해당 하는 경우에만 적합 합니다.

- 전역 상태에 미치는 영향은 비용이 많이 들고 형식이 사용 되지 않는 경우에는 필요 하지 않습니다.

- 전역 상태 효과는 형식의 정적 필드에 액세스 하지 않고 액세스할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 성능이 중요 하지 않은 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다. 또는 정적 초기화로 인해 발생 하는 전역 상태 변경에 비용이 많이 들며 형식의 정적 메서드를 호출 하거나 형식의 인스턴스를 만들기 전에 발생 해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식,를 사용 하 여 `StaticConstructor` `NoStaticConstructor` 정적 생성자를 인라인 초기화로 대체 하 여 규칙을 충족 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RefTypeStaticCtor/cs/FxCop.Performance.RefTypeStaticCtor.cs#1)]
 [!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.RefTypeStaticCtor/vb/FxCop.Performance.RefTypeStaticCtor.vb#1)]

 `beforefieldinit`클래스에 대 한 MSIL 정의에 플래그를 추가 합니다 `NoStaticConstructor` .

 **. class public auto ansi staticconstructor** 는 staticconstructor 클래스의 **[mscorlib] system.object** 
 **{** 
 **}//end를**확장 
 **합니다. class public auto ansi beforefieldinit nostaticconstructor** 는 **[mscorlib] system.object** 
 **{** 
 **}//클래스의 nostaticconstructor를** 확장 합니다.
## <a name="related-rules"></a>관련 규칙
 [CA2207: 값 형식 정적 필드 인라인을 초기화하십시오.](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)
