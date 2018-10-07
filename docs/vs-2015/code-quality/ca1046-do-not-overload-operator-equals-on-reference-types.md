---
title: 'CA1046: 참조 형식에 같음 연산자 오버 로드 하지 마십시오 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1f4f37f6d4c2662ca0b053e6737c57ba222b0b5e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591304"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1046: 참조 형식에 같음 연산자를 오버 로드 하지 않는](https://docs.microsoft.com/visualstudio/code-quality/ca1046-do-not-overload-operator-equals-on-reference-types)합니다.

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

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 참조 형식은 기본 제공 값 형식 처럼 동작 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 더하기 또는 빼기 형식의 인스턴스에서 작업을 수행 하는 의미 있는 경우 같음 연산자를 구현 하 여 위반을 표시 하지 않으려면 잘못 되었을 것입니다.

## <a name="example"></a>예제
 다음 예제에서는 두 개의 참조를 비교할 때 기본 동작을 보여 줍니다.

 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefTypesNoEqualityOp/cs/FxCop.Design.RefTypesNoEqualityOp.cs#1)]

## <a name="example"></a>예제
 다음 응용 프로그램 일부 참조를 비교 합니다.

 [!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefTypesNoEqualityOp/cs/FxCop.Design.TestRefTypesNoEqualityOp.cs#1)]

 이 예제의 결과는 다음과 같습니다.

 **새 (2, 2) 및 b = = 새 (2, 2) 같은지? 아니오**
**c 및 a가 같습니까? 예**
**되며 b = =? 아니오**
**되며 c = =? 예**
## <a name="related-rules"></a>관련된 규칙
 [CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>참고 항목
 <xref:System.Object.Equals%2A?displayProperty=fullName> [같음 연산자](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)


