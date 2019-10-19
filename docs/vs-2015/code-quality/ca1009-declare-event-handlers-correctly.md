---
title: 'CA1009: 이벤트 처리기를 올바르게 선언 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 261013ed844b6c5ba37c544c7745a77378c0c722
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668916"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: 이벤트 처리기를 제대로 선언하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|CheckId|CA1009|
|범주|Microsoft 디자인|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 이벤트를 처리 하는 대리자에 올바른 시그니처, 반환 형식 또는 매개 변수 이름이 없습니다.

## <a name="rule-description"></a>규칙 설명
 이벤트 처리기 메서드는 두 개의 매개 변수를 사용합니다. 첫 번째는 <xref:System.Object?displayProperty=fullName> 형식이 고 이름이 ' m e t e r '로 지정 됩니다. 이 매개 변수는 이벤트를 발생시킨 개체입니다. 두 번째 매개 변수는 <xref:System.EventArgs?displayProperty=fullName> 형식이 고 이름이 ' e '입니다. 이 매개 변수는 이벤트와 관련된 데이터입니다. 예를 들어, 파일을 열 때마다 이벤트가 발생 하는 경우 이벤트 데이터에는 일반적으로 파일 이름이 포함 됩니다.

 이벤트 처리기 메서드는 값을 반환 하면 안 됩니다. C# 프로그래밍 언어에서이는 `void` 반환 형식으로 표시 됩니다. 이벤트 처리기는 여러 개체의 여러 메서드를 호출할 수 있습니다. 메서드가 값을 반환할 수 있는 경우 각 이벤트에 대해 여러 개의 반환 값이 발생 하 고, 호출 된 마지막 메서드 값만 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 대리자의 시그니처, 반환 형식 또는 매개 변수 이름을 수정 합니다. 자세한 내용은 다음 예제를 참조 하세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 이벤트를 처리 하는 데 적합 한 대리자를 보여 줍니다. 이 이벤트 처리기에 의해 호출 될 수 있는 메서드는 디자인 지침에 지정 된 서명을 준수 합니다. `AlarmEventHandler`은 대리자의 형식 이름입니다. `AlarmEventArgs`는 이벤트 데이터에 대 한 기본 클래스에서 파생 되 고, <xref:System.EventArgs> 하 고, 경보 이벤트 데이터를 보유 합니다.

 [!code-cpp[FxCop.Design.EventsTwoParams#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cpp/FxCop.Design.EventsTwoParams.cpp#1)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cs/FxCop.Design.EventsTwoParams.cs#1)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/vb/FxCop.Design.EventsTwoParams.vb#1)]

## <a name="related-rules"></a>관련 규칙
 [CA2109: 표시되는 이벤트 처리기를 검토하십시오.](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>관련 항목:
 <xref:System.EventArgs?displayProperty=fullName> <xref:System.Object?displayProperty=fullName>
 [NIB: 이벤트 및 대리자](https://msdn.microsoft.com/d98fd58b-fa4f-4598-8378-addf4355a115)
