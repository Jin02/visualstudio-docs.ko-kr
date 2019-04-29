---
title: 'CA2135: 수준 2 어셈블리는 LinkDemands를 포함할 수 없습니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fcd9032d550e79a47941540408dc6e98a15e33f7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796720"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: 수준 2 어셈블리는 LinkDemands를 포함할 수 없습니다.

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 클래스 또는 클래스 멤버를 사용 하는 <xref:System.Security.Permissions.SecurityAction> 수준 2 보안을 사용 하는 응용 프로그램에서 합니다.

## <a name="rule-description"></a>규칙 설명
 LinkDemands는 수준 2 보안 규칙 집합에서 사용되지 않습니다. LinkDemands를 사용 하 여 적시에 (JIT) 컴파일 시 보안을 강화할 수, 하는 대신 메서드, 형식 및 필드를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 제거 합니다 <xref:System.Security.Permissions.SecurityAction> 형식 또는 멤버를 표시 하 고는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 <xref:System.Security.Permissions.SecurityAction> 제거 해야 하 고 사용 하 여 표시 된 메서드는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]