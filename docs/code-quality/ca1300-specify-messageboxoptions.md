---
title: 'CA1300: MessageBoxOptions를 지정하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 746475e60bbe72c4ebfc51f13d0b2d4d0552ff62
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235189"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: MessageBoxOptions를 지정하세요.

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|범주|Microsoft.Globalization|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

메서드는 인수를 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> 사용 하지 않는 메서드의 오버 로드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명

오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 대 한 메시지 상자를 올바르게 표시 하려면 [messageboxoptions를 전달 합니다. rightalign](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>) 및 [messageboxoptions.](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>) <xref:System.Windows.Forms.MessageBox.Show%2A> 필드를 메서드로 읽습니다. 포함 하는 컨트롤의 속성을검사하여오른쪽에서왼쪽읽기순서를사용할지여부를결정합니다.<xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 <xref:System.Windows.Forms.MessageBox.Show%2A> <xref:System.Windows.Forms.MessageBoxOptions> 인수를 사용 하는 메서드의 오버 로드를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 대해 코드 라이브러리를 지역화 하지 않을 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제

다음 예제에서는 문화권의 읽기 순서에 적합 한 옵션이 있는 메시지 상자를 표시 하는 메서드를 보여 줍니다. 예제를 빌드하려면 리소스 파일 (표시 되지 않음)이 필요 합니다. 예제의 주석을 따라 리소스 파일 없이 예제를 빌드하고 오른쪽에서 왼쪽으로 기능을 테스트 합니다.

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>참고 항목

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [데스크톱 앱의 리소스(.NET Framework)](/dotnet/framework/resources/index)