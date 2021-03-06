---
title: 'CA2222: 상속 된 멤버의 표시 유형을 줄이지 않습니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 04109e821d3a739b96ad63e1a441089a5d479cd8
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85540779"
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: 상속된 멤버 노출 수준을 낮추지 마세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|DoNotDecreaseInheritedMemberVisibility|
|CheckId|CA2222|
|범주|Microsoft 사용|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 봉인 되지 않은 형식의 private 메서드에는 기본 형식에 선언 된 공용 메서드와 동일한 시그니처가 있습니다. 전용 메서드가 최종이 아닙니다.

## <a name="rule-description"></a>규칙 설명
 상속된 멤버에 대한 액세스 한정자는 변경하면 안 됩니다. 상속된 멤버를 private으로 변경하더라도 호출자가 메서드의 기본 클래스 구현에 액세스하는 것을 막을 수 없습니다. 멤버가 private이 고 형식이 봉인 되지 않은 경우 상속 형식은 상속 계층 구조에서 메서드의 마지막 공용 구현을 호출할 수 있습니다. 액세스 한정자를 변경 해야 하는 경우 메서드가 final로 표시 되어야 합니다. 그렇지 않으면 메서드가 재정의 되지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 액세스를 개인이 아닌 것으로 변경 합니다. 또는 프로그래밍 언어에서 지 원하는 경우 메서드를 최종으로 만들 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.InheritedPublic#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/cs/FxCop.Usage.InheritedPublic.cs#1)]
 [!code-vb[FxCop.Usage.InheritedPublic#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/vb/FxCop.Usage.InheritedPublic.vb#1)]
