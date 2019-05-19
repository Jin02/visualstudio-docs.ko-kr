---
title: 'CA1027: 열거형을 FlagsAttribute로 표시하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: acdb8406d43f90414cf255abae6f1ca5f549e92e
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842476"
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: 열거형을 FlagsAttribute로 표시하세요.

|||
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

열거형의 값은 2의 거듭제곱 또는 열거형에 정의 된 다른 값의 조합이 개 및 <xref:System.FlagsAttribute?displayProperty=fullName> 특성이 존재 합니다. 가양성을 줄이기 위해이 규칙에는 연속 값이 있는 열거형에 대 한 위반을 보고 하지 않습니다.

기본적으로이 규칙만 살펴봅니다 공용 열거형 이지만 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 적용 <xref:System.FlagsAttribute> 열거형 때 명명 된 상수를 의미 있게 조합할 수 있습니다. 예를 들어 추적 하는 날짜의 리소스가 사용 가능한 응용 프로그램에서 요일의 열거형입니다. 각 리소스의 가용성에는 열거형을 사용 하 여 인코딩된 경우 <xref:System.FlagsAttribute> 현재 일의 조합을 나타낼 수 있습니다. 특성이 없으면만 1 일 주를 나타낼 수 있습니다.

Combinable 열거형을 저장 하는 필드에 대 한 개별 열거형 값은 비트 필드에 그룹으로 처리 됩니다. 따라서 이러한 필드는 라고도 *비트 필드*합니다. 비트 필드의 저장소에 대 한 열거형 값을 결합 하려면 부울 조건 연산자를 사용 합니다. 특정 열거형 값이 있는지 여부를 확인 하려면 비트 필드를 테스트 하려면 부울 논리 연산자를 사용 합니다. 저장 하 고 결합 된 열거형 값을 올바르게 검색 비트 필드에 대 한 열거형에 정의 된 각 값에는 2의 거듭제곱 이어야 합니다. 그렇지 않은, 부울 논리 연산자 필드에 저장 되는 각 열거형 값을 추출할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 추가 <xref:System.FlagsAttribute> 의 열거형입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

열거형 값의 조합을 허용 하지 않을 경우이 규칙에서 경고를 표시 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1027.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예에서 `DaysEnumNeedsFlags` 사용에 대 한 요구 사항을 충족 하는 열거형은 <xref:System.FlagsAttribute> 하지만 해당 필요는 없습니다. 합니다 `ColorEnumShouldNotHaveFlag` 열거형 값 2의 거듭제곱을 없지만 잘못 지정 <xref:System.FlagsAttribute>합니다. 이 규칙을 위반 [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)합니다.

[!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.FlagsAttribute?displayProperty=fullName>