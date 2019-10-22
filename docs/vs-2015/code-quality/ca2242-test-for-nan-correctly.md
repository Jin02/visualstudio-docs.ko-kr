---
title: 'CA2242: NaN을 올바르게 테스트 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 8433ac081a45e3dbab80ffcd6f96e6d1db914337
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672014"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: NaN에 대해 정확하게 테스트하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|범주|Microsoft 사용|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 식은 <xref:System.Single.NaN?displayProperty=fullName> 또는 <xref:System.Double.NaN?displayProperty=fullName>에 대해 값을 테스트 합니다.

## <a name="rule-description"></a>규칙 설명
 숫자가 아닌 값을 나타내는 <xref:System.Double.NaN?displayProperty=fullName>는 산술 연산이 정의 되지 않은 경우에 발생 합니다. 값과 <xref:System.Double.NaN?displayProperty=fullName>이 같은지 여부를 테스트 하는 모든 식은 항상 `false`를 반환 합니다. 값과 <xref:System.Double.NaN?displayProperty=fullName>가 같지 않은지 테스트 하는 모든 식은 항상 `true`를 반환 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하 고 값이 <xref:System.Double.NaN?displayProperty=fullName>를 나타내는지 여부를 정확 하 게 확인 하려면 <xref:System.Single.IsNaN%2A?displayProperty=fullName> 또는 <xref:System.Double.IsNaN%2A?displayProperty=fullName>를 사용 하 여 값을 테스트 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예에서는 <xref:System.Double.NaN?displayProperty=fullName>에 대 한 값을 잘못 테스트 하는 두 개의 식 및 <xref:System.Double.IsNaN%2A?displayProperty=fullName>를 사용 하 여 값을 테스트 하는 데 올바르게 사용 되는 식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.TestForNaN#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/cs/FxCop.Usage.TestForNaN.cs#1)]
 [!code-vb[FxCop.Usage.TestForNaN#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/vb/FxCop.Usage.TestForNaN.vb#1)]
