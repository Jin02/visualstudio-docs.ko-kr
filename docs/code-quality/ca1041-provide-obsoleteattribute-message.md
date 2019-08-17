---
title: 'CA1041: ObsoleteAttribute 메시지를 제공하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a0545503b80e2f256593012e06cdf7ccd8b3b5b1
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547635"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute 메시지를 제공하세요.

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

형식 또는 멤버가 해당 <xref:System.ObsoleteAttribute?displayProperty=fullName> <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> 속성이 지정 되지 않은 특성을 사용 하 여 표시 됩니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식 및 멤버만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

<xref:System.ObsoleteAttribute>는 사용 되지 않는 라이브러리 형식 및 멤버를 표시 하는 데 사용 됩니다. 라이브러리 소비자는 사용 되지 않는 것으로 표시 된 형식이 나 멤버를 사용 하지 않도록 해야 합니다. 이는 지원 되지 않으며 나중 버전의 라이브러리에서 제거 될 수 있기 때문입니다. 를 사용 하 <xref:System.ObsoleteAttribute> 여 표시 된 형식 또는 멤버를 컴파일하면 <xref:System.ObsoleteAttribute.Message%2A> 특성의 속성이 표시 됩니다. 사용되지 않는 형식 또는 멤버에 대한 정보가 사용자에게 제공됩니다. 이 정보에는 일반적으로 사용 되지 않는 형식 또는 멤버가 라이브러리 디자이너에서 지원 되는 기간 및 사용 하려는 기본 설정 대체가 포함 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 `message` 매개 변수를 <xref:System.ObsoleteAttribute> 생성자에 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

속성이 사용 되지 않는 형식 또는 멤버에 대 한 <xref:System.ObsoleteAttribute.Message%2A> 중요 한 정보를 제공 하기 때문에이 규칙에서 경고를 표시 하지 마십시오.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1041.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는가 올바르게 선언 <xref:System.ObsoleteAttribute>된 사용 되지 않는 멤버를 보여 줍니다.

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>참고자료

- <xref:System.ObsoleteAttribute?displayProperty=fullName>