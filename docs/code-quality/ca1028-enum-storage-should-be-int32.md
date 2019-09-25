---
title: 'CA1028: 열거형 스토리지는 Int32여야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 47a934a6e35296927eea64465ff8e7007219bec5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236091"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: 열거형 스토리지는 Int32여야 합니다.

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|범주|Microsoft.Design|
|주요 변경 내용|주요 변경|

## <a name="cause"></a>원인

열거형의 내부 형식이가 아닌 <xref:System.Int32?displayProperty=fullName>경우

기본적으로이 규칙은 공용 열거만을 찾지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 기본적 <xref:System.Int32?displayProperty=fullName> 으로 데이터 형식은 상수 값을 저장 하는 데 사용 됩니다. 이 기본 형식을 변경할 수 있지만 대부분의 시나리오에서는 필요 하지 않거나 권장 되지 않습니다. 보다 <xref:System.Int32>작은 데이터 형식을 사용 하 여 성능이 크게 향상 되는 것은 아닙니다. 기본 데이터 형식을 사용할 수 없는 경우 CLS (공용 언어 시스템 <xref:System.Byte>) 규격 정수 형식 <xref:System.Int16> <xref:System.Int32>,, 또는 <xref:System.Int64> 중 하나를 사용 하 여 열거형의 모든 값을에 표시할 수 있는지 확인 해야 합니다. CLS 규격 프로그래밍 언어

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

크기 또는 호환성 문제가 있는 경우를 제외 하 고이 규칙 위반 문제를 해결 <xref:System.Int32>하려면를 사용 합니다. <xref:System.Int32> 가 값을 저장할 수 있을 정도로 크지 않은 경우를 사용 <xref:System.Int64>합니다. 이전 버전과의 호환성을 위해 더 작은 데이터 형식이 <xref:System.Byte> 필요한 <xref:System.Int16>경우 또는를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이전 버전과의 호환성 문제를 필요로 하는 경우에만이 규칙에서 경고를 표시 하지 않습니다. 응용 프로그램에서이 규칙을 준수 하지 않으면 일반적으로 문제가 발생 하지 않습니다. 언어 상호 운용성이 필요한 라이브러리에서이 규칙을 준수 하지 않으면 사용자에 게 부정적인 영향을 줄 수 있습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1028.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example-of-a-violation"></a>위반 예

다음 예에서는 권장 되는 기본 데이터 형식을 사용 하지 않는 두 개의 열거형을 보여 줍니다.

[!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
[!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]

## <a name="example-of-how-to-fix"></a>해결 방법의 예

다음 예에서는 기본 데이터 형식을로 <xref:System.Int32>변경 하 여 이전 위반을 수정 합니다.

[!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
[!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]

## <a name="related-rules"></a>관련 규칙

- [CA1008: 열거형에는 0 값이 있어야 합니다.](../code-quality/ca1008-enums-should-have-zero-value.md)
- [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: 열거형을 FlagsAttribute로 표시 하지 않습니다.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: 열거형 값의 이름을 ' Reserved '로 하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: 열거형 값에 형식 이름을 접두사로 사용 하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>참고 항목

- <xref:System.Byte?displayProperty=fullName>
- <xref:System.Int16?displayProperty=fullName>
- <xref:System.Int32?displayProperty=fullName>
- <xref:System.Int64?displayProperty=fullName>