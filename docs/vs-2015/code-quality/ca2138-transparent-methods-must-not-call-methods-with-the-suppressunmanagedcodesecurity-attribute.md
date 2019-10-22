---
title: 'CA2138: 투명 한 메서드는 SuppressUnmanagedCodeSecurity 특성을 사용 하 여 메서드를 호출 하면 안 됩니다. Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 65e00d319bff3bbfd3c441c6b60ed8a703e69251
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654807"
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: 투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|
|CheckId|CA2138|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 보안 투명 메서드는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시 된 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 P/Invoke (플랫폼 호출) 호출을 통해를 사용 하는 등의 방법으로 네이티브 코드를 직접 호출 하는 모든 투명 메서드에 대해 발생 합니다. P/Invoke 및 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시 된 COM interop 메서드는 호출 하는 메서드에 대해 LinkDemand를 수행 합니다. 보안 투명 코드는 LinkDemands를 충족 시킬 수 없기 때문에 코드에서 SuppressUnmanagedCodeSecurity 특성으로 표시 된 메서드나 SuppressUnmanagedCodeSecurity 특성으로 표시 된 클래스의 메서드를 호출할 수 없습니다. 메서드가 실패 하거나 요청이 전체 수요로 변환 됩니다.

 이 규칙이 위반 되 면 수준 2 보안 투명도 모델의 <xref:System.MethodAccessException>이 되 고 수준 1 투명도 모델의 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>에 대 한 전체 수요를 초래 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성을 제거 하 고 메서드를 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2138.transparentmethodsmustnotcallsuppressunmanagedcodesecuritymethods/cs/ca2138.cs#1)]
