---
title: 'CA2137: 투명 한 메서드는 안정형 IL만 포함 해야 합니다 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 77ff02a0db733c3151f4faccd00e07518d61e600
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591185"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: 투명한 메서드는 안정형 IL만 포함해야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2137: 투명 한 메서드는 안정형 IL만 포함 해야](https://docs.microsoft.com/visualstudio/code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il)합니다.

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 메서드가 확인할 수 없는 코드를 포함하거나 형식을 참조로 반환합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 보안 투명 코드에서 확인할 수 없는 MSIL(Microsoft Intermediate Language)을 실행하려고 할 때 적용됩니다. 그러나 이 규칙은 완전한 IL 검증 도구를 포함하지 않으며 대신 추론을 사용하여 MSIL 확인 시 대부분의 위반을 catch합니다.

 실행 코드에만 확인할 수 있는 MSIL 일 [Peverify.exe (PEVerify 도구)](http://msdn.microsoft.com/library/f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa) 어셈블리에 있습니다. PEVerify 사용 하 여 실행 합니다 **투명 한 /** 투명 메서드로만 오류가 유발 하는 출력을 제한 하는 옵션입니다. 경우는 투명 한 옵션이 사용 되지 않는 /, PEVerify도 확인할 수 없는 코드를 포함할 수 있는 중요 한 메서드를 확인 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 사용 하 여 메서드를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 또는 비안정형 코드를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예제에서 확인할 수 없는 코드를 사용 하 여 메서드와으로 표시 되어야 합니다는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2137.transparentmethodsmustbeverifiable/cs/ca2137 - transparentmethodsmustbeverifiable.cs#1)]


