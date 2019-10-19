---
title: 'CA1822: 멤버를 static으로 표시 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a571be6b713cd59ca290906e9398b78c8c021ba8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661163"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: 멤버를 static으로 표시하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio에 대 한 최신 설명서는 [CA1822: 멤버를 static으로 표시](https://docs.microsoft.com/visualstudio/code-quality/ca1822-mark-members-as-static)를 참조 하세요.

|||
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|범주|Microsoft 성능|
|변경 수준|중단-변경 내용에 관계 없이 멤버가 어셈블리 외부에 표시 되지 않는 경우입니다.<br /><br /> @No__t_0 키워드를 사용 하 여 멤버를 인스턴스 멤버로 변경 하는 경우에는 안 됩니다.<br /><br /> 중단-멤버를 인스턴스 멤버에서 정적 멤버로 변경 하 고 어셈블리 외부에서 볼 수 있는 경우.|

## <a name="cause"></a>원인
 인스턴스 데이터에 액세스 하지 않는 멤버는 static으로 표시 되지 않습니다 ([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]에서 공유).

## <a name="rule-description"></a>규칙 설명
 인스턴스 데이터에 액세스하지 않거나 인스턴스 메서드를 호출하지 않는 멤버는 static([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]의 경우 Shared)으로 표시할 수 있습니다. 메서드를 static으로 표시하면 컴파일러는 이러한 멤버에 대한 비가상 호출 사이트를 내보냅니다. 비가상 호출 사이트를 내보내면 현재 개체 포인터가 null이 아닌지 확인 하는 각 호출에 대해 런타임에 검사를 수행 하지 못합니다. 이렇게 하면 성능이 중요 한 코드의 성능을 향상 시킬 수 있습니다. 경우에 따라 현재 개체 인스턴스에 액세스 하지 못하는 경우 정확성 문제가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 멤버를 static으로 표시 하거나 ([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]에서 공유) 메서드 본문에서 ' this '/' Me '를 사용 합니다 (해당 하는 경우).

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이전에 제공 된 코드에 대 한 경고를 수정 하 여 주요 변경 내용을 적용할 수 있는 것은 안전 합니다.

## <a name="related-rules"></a>관련 규칙
 [CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)
