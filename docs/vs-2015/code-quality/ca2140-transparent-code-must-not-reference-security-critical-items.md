---
title: 'CA2140: 투명 코드는 보안에 중요 한 항목을 참조 해서는 안 됩니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6f11125f43fd06b0442d1c40cbd4da41e346fd1d
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85546460"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 투명 한 메서드:

- 보안에 중요 보안 예외 유형을 처리 합니다.

- 보안에 중요 형식으로 표시 된 매개 변수가 있습니다.

- 보안에 중요 제약 조건이 있는 제네릭 매개 변수가 있습니다.

- 보안에 중요 형식의 지역 변수가 있습니다.

- 보안 위험으로 표시 된 형식을 참조 합니다.

- 보안에 중요로 표시 된 메서드를 호출 합니다.

- 보안 위험으로 표시 된 필드를 참조 합니다.

- 보안 위험으로 표시 된 형식을 반환 합니다.

## <a name="rule-description"></a>규칙 설명
 특성으로 표시 된 코드 요소는 <xref:System.Security.SecurityCriticalAttribute> 보안에 중요 합니다. 투명 메서드는 보안에 중요한 요소를 사용할 수 없습니다. 투명 형식이 보안에 중요 한 형식을 사용 하려고 시도 하는 경우, <xref:System.TypeAccessException> <xref:System.MethodAccessException> 또는 <xref:System.FieldAccessException> 이 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 다음 중 하나를 수행 합니다.

- 보안에 중요 한 코드를 사용 하는 코드 요소를 특성으로 표시 합니다. <xref:System.Security.SecurityCriticalAttribute>

     \- 또는 -

- 보안에 <xref:System.Security.SecurityCriticalAttribute> 중요로 표시 된 코드 요소에서 특성을 제거 하 고 대신 또는 특성으로 표시 <xref:System.Security.SecuritySafeCriticalAttribute> 합니다 <xref:System.Security.SecurityTransparentAttribute> .

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서 투명 메서드는 보안에 중요 한 제네릭 컬렉션, 보안에 중요 한 필드 및 보안에 중요 한 메서드를 참조 하려고 합니다.

 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2140.transparentmethodsmustnotreferencecriticalcode/cs/ca2140 - transparentmethodsmustnotreferencecriticalcode.cs#1)]

## <a name="see-also"></a>참고 항목
 <xref:System.Security.SecurityTransparentAttribute> <xref:System.Security.SecurityCriticalAttribute>
 <xref:System.Security.SecurityTransparentAttribute>
 <xref:System.Security.SecurityTreatAsSafeAttribute>
 <xref:System.Security?displayProperty=fullName>
