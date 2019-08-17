---
title: 'CA1721: 속성 이름은 Get 메서드와 달라야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 44028caf027191846fa653db06abbe4027fdde8d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547095"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: 속성 이름은 Get 메서드와 달라야 합니다.

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

멤버의 이름이 ' Get '으로 시작 하 고 그렇지 않은 경우 속성의 이름과 일치 합니다. 예를 들어 이름이 ' GetColor ' 인 메서드가 포함 된 형식과 ' Color '로 명명 된 속성은 규칙 위반을 발생 시킵니다.

기본적으로이 규칙은 외부에서 볼 수 있는 멤버 및 속성만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

"Get" 메서드와 속성은 서로가 분명히 구분되는 이름을 사용해야 합니다.

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이러한 일관성은 새 소프트웨어 라이브러리를 학습 하는 데 필요한 시간을 단축 하 고 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 것에 대 한 고객의 신뢰도를 높입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

' Get ' 접두사가 붙은 메서드의 이름과 일치 하지 않도록 이름을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다.

> [!NOTE]
> 가 iextenderprovider 인터페이스를 구현 하 여 "Get" 메서드가 발생 하면이 경고가 제외 될 수 있습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1721.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에는이 규칙을 위반 하는 메서드와 속성이 포함 되어 있습니다.

[!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
[!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>관련 규칙

- [CA1024: 적절 한 경우 속성 사용](../code-quality/ca1024-use-properties-where-appropriate.md)