---
title: 'CA2143: 투명 메서드는 보안 요청을 사용할 수 없습니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 532a10740b0617f32e4f970da8dc2a7e2807f792
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920478"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: 투명 메서드는 보안 요청을 사용할 수 없습니다.

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
전 부모 형식 또는 메서드는 <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` 요청으로 선언적으로 표시 <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> 되거나 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명
보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다. 보안 투명 코드는 보안에 중요한 결정을 내리는 데 전체 요청을 사용해야 하며 안전에 중요한 코드는 전체 요청을 위해 투명 코드를 사용해서는 안 됩니다. 보안 요구와 같은 보안 검사를 수행 하는 모든 코드가 안전 하 게 중요 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
일반적으로이 규칙 위반 문제를 해결 하려면 메서드를 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 합니다. 또한 수요를 제거할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
투명 메서드는 선언적 보안 요구를 수행 하기 때문에 다음 코드의 규칙 파일은 다음과 같습니다.

[!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>참고자료
[CA2142: 투명 코드는 LinkDemands로 보호할 수 없습니다.](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)