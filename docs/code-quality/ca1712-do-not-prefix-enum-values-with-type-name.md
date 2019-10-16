---
title: 'CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
helpviewer_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f151296fce00ca92209c588c4be0361f9adfc7fd
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72348931"
---
# <a name="ca1712-do-not-prefix-enum-values-with-type-name"></a>CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.

|||
|-|-|
|TypeName|DoNotPrefixEnumValuesWithTypeName|
|CheckId|CA1712|
|범주|Microsoft. 이름 지정|
|주요 변경 내용|주요 변경|

## <a name="cause"></a>원인
열거형은 이름이 열거형의 형식 이름으로 시작 하는 멤버를 포함 합니다.

## <a name="rule-description"></a>규칙 설명
형식 정보는 개발 도구에서 제공 되어야 하므로 열거형 멤버의 이름에는 형식 이름이 접두사로 사용 되지 않습니다.

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이렇게 하면에서 새 소프트웨어 라이브러리를 학습 하는 데 필요한 시간을 줄이고 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 했다는 확신을 높일 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 열거형 멤버에서 형식 이름 접두사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예에서는 잘못 명명 된 열거와 수정 된 버전을 보여 줍니다.

[!code-csharp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CSharp/ca1712-do-not-prefix-enum-values-with-type-name_1.cs)]
[!code-cpp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CPP/ca1712-do-not-prefix-enum-values-with-type-name_1.cpp)]
[!code-vb[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/VisualBasic/ca1712-do-not-prefix-enum-values-with-type-name_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

[CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

[CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217.md)

## <a name="see-also"></a>참조

- <xref:System.Enum?displayProperty=fullName>