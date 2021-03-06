---
title: 'CA2141: 투명 한 메서드는 LinkDemands를 충족 하지 않아야 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bee810ed938d316e92095ad47062ed5ad9cd456f
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85546447"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 보안 투명 메서드가 (APTCA) 특성으로 표시 되지 않은 어셈블리의 메서드를 호출 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 하거나, 보안 투명 메서드가 <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` 형식 또는 메서드에 대 한를 충족 합니다.

## <a name="rule-description"></a>규칙 설명
 LinkDemand를 만족 하는 것은 보안에 중요 한 작업 이므로 의도 하지 않은 권한 상승이 발생할 수 있습니다. 보안 투명 코드는 보안에 중요 한 코드와 같은 보안 감사 요구 사항이 적용 되지 않으므로 LinkDemands를 충족 해서는 안 됩니다. 보안 규칙 집합 수준 1 어셈블리의 투명 한 메서드는 런타임에 만족 하는 모든 LinkDemands가 전체 요청으로 변환 되어 성능 문제가 발생할 수 있습니다. 보안 규칙 집합 수준 2 어셈블리에서는 LinkDemand를 충족 하려고 할 때 투명 메서드가 JIT (just-in-time) 컴파일러에서 컴파일되지 않습니다.

 Usee 수준 2 보안 어셈블리에서 보안 투명 메서드가 LinkDemand를 만족 시키거나 비 APTCA 어셈블리의 메서드를 호출 하려고 하면이 발생 합니다 <xref:System.MethodAccessException> . 수준 1 어셈블리에서는 LinkDemand가 전체 요청이 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 액세스 방법을 <xref:System.Security.SecurityCriticalAttribute> 또는 특성으로 표시 <xref:System.Security.SecuritySafeCriticalAttribute> 하거나 액세스 된 메서드에서 LinkDemand를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예제에서 투명 메서드는 LinkDemand가 있는 메서드를 호출 하려고 합니다. 이 규칙은이 코드에서 발생 합니다.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2141.transparentmethodsmustnotsatisfylinkdemands/cs/ca2141 - transparentmethodsmustnotsatisfylinkdemands.cs#1)]
