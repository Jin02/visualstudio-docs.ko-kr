---
title: 'CA1820: 문자열 길이를 사용하여 빈 문자열을 테스트하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b197cacc764f1f5472d3eb074ac89199db508408
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233424"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: 문자열 길이를 사용하여 빈 문자열을 테스트하세요.

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|범주|Microsoft.Performance|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

를 사용 <xref:System.Object.Equals%2A?displayProperty=nameWithType>하 여 문자열을 빈 문자열과 비교 합니다.

## <a name="rule-description"></a>규칙 설명

속성이 나 메서드를 사용 하 여 <xref:System.Object.Equals%2A>문자열을 비교 하는 것은를 사용 하는 것 보다 빠릅니다. <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> <xref:System.String.Length%2A?displayProperty=nameWithType> 이는 <xref:System.String.Length%2A> 속성 <xref:System.Object.Equals%2A> 값을 검색 하기 위해 실행 되 <xref:System.String.IsNullOrEmpty%2A> 는 명령 수보다 훨씬 더 많은 MSIL 명령이 실행 되 고이를 0과 비교 하기 때문입니다.

Null 문자열의 경우 <xref:System.Object.Equals%2A> 와 `<string>.Length == 0` 가 다르게 동작 합니다. Null 문자열의 <xref:System.String.Length%2A> 속성 값을 가져오려고 하면 공용 언어 런타임에서이 <xref:System.NullReferenceException?displayProperty=fullName>throw 됩니다. Null 문자열과 빈 문자열을 비교 하는 경우 공용 언어 런타임에서는 예외를 throw 하지 않고를 반환 `false`합니다. Null에 대 한 테스트는 이러한 두 방법의 상대적 성능에 크게 영향을 주지 않습니다. .NET Framework 2.0 이상을 대상으로 하는 <xref:System.String.IsNullOrEmpty%2A> 경우 메서드를 사용 합니다. 그렇지 않으면 가능한 경우 <xref:System.String.Length%2A> = = 0 비교를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 <xref:System.String.IsNullOrEmpty%2A> 메서드를 사용 하도록 비교를 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

성능이 문제가 되지 않는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제

다음 예에서는 빈 문자열을 검색 하는 데 사용 되는 다양 한 기술을 보여 줍니다.

[!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]