---
title: 'CA1056: URI 속성은 문자열이면 안 됩니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2d9ff79bc7e276e4070a1df1760c0cfde7ed28b1
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547332"
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056: URI 속성은 문자열이면 안 됩니다.

|||
|-|-|
|TypeName|UriPropertiesShouldNotBeStrings|
|CheckId|CA1056|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식은 이름에 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"이 포함 되어 있는 문자열 속성을 선언 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

이 규칙은 파스칼식 대/소문자 규칙에 따라 속성 이름을 토큰으로 분할 하 고 각 토큰이 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"과 일치 하는지 확인 합니다. 일치 하는 항목이 있는 경우 규칙은 속성이 URI (uniform resource identifier)를 나타내는 것으로 가정 합니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. 클래스 <xref:System.Uri?displayProperty=fullName> 는 안전 하 고 안전한 방식으로 이러한 서비스를 제공 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 속성을 <xref:System.Uri> 형식으로 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

속성이 URI를 나타내지 않는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1056.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반 `ErrorProne`하는 형식 및 규칙을 충족 하는 `SaferWay`형식을 보여 줍니다.

[!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1056-uri-properties-should-not-be-strings_1.cs)]
[!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1056-uri-properties-should-not-be-strings_1.vb)]
[!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1056-uri-properties-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>관련 규칙

- [CA1054: URI 매개 변수는 문자열이 면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
- [CA1055: URI 반환 값은 문자열이 면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
- [CA2234: 문자열 대신 System.uri 개체를 전달 합니다.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)
- [CA1057: 문자열 URI 오버 로드는 System.uri 오버 로드를 호출 합니다.](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)