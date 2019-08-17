---
title: 'CA2234: 문자열 대신 System.Uri 개체를 전달하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 74484c5f014c9a677c321a0d9fed649f016ea3c9
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546877"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: 문자열 대신 System.Uri 개체를 전달하세요.

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

이름에 "uri", "uri", "urn", "urn", "url" 또는 "url"이 포함 되 고 메서드의 선언 형식에는 <xref:System.Uri?displayProperty=fullName> 매개 변수가 있는 해당 메서드 오버 로드가 포함 된 문자열 매개 변수가 있는 메서드에 대 한 호출이 수행 됩니다.

기본적으로이 규칙은 외부에서 볼 수 있는 메서드 및 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

매개 변수 이름은 카멜식 대/소문자 규칙을 기반으로 하는 토큰으로 분할 된 다음 각 토큰을 검사 하 여 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"과 일치 하는지 여부를 확인 합니다. 일치 하는 항목이 있는 경우 매개 변수는 URI (uniform resource identifier)를 나타내는 것으로 간주 됩니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. 클래스 <xref:System.Uri> 는 안전 하 고 안전한 방식으로 이러한 서비스를 제공 합니다. URI 표시와 관련 하 여 다른 두 오버 로드 중에서 선택 하는 경우 사용자는 <xref:System.Uri> 인수를 사용 하는 오버 로드를 선택 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 <xref:System.Uri> 인수를 사용 하는 오버 로드를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

문자열 매개 변수가 URI를 나타내지 않는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca2234.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (사용량). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 `ErrorProne` <xref:System.Uri> 오버 로드를 올바르게 호출 하는 규칙 및 `SaferWay`메서드를 위반 하는 메서드를 보여 줍니다.

[!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
[!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
[!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1057: 문자열 URI 오버 로드는 System.uri 오버 로드를 호출 합니다.](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)
- [CA1056: URI 속성은 문자열이 면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1054: URI 매개 변수는 문자열이 면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
- [CA1055: URI 반환 값은 문자열이 면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)