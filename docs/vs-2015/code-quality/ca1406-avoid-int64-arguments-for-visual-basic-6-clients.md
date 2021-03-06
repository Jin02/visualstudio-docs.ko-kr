---
title: 'CA1406: Visual Basic 6 클라이언트에 대해 Int64 인수를 사용 하지 않습니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: b6ab93c24cd97d498ae886c7a9184fd4a5f111f1
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85534916"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Visual Basic 6 클라이언트에서는 Int64 인수를 사용하지 마세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 COM (구성 요소 개체 모델)에 표시 되도록 특별히 표시 된 형식은 인수를 사용 하는 멤버를 선언 <xref:System.Int64?displayProperty=fullName> 합니다.

## <a name="rule-description"></a>규칙 설명
 Visual Basic 6 COM 클라이언트는 64 비트 정수를 액세스할 수 없습니다.

 기본적으로 다음은 COM에 표시 됩니다. 어셈블리, public 형식, public 형식의 공용 인스턴스 멤버 및 public 값 형식의 모든 멤버입니다. 그러나 가양성을 줄이기 위해이 규칙을 사용 하려면 형식에 대 한 COM 표시 여부를 명시적으로 명시 해야 합니다. 포함 하는 어셈블리는로 설정 된로 표시 되어야 하 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> `false` 고 형식은로 설정 된로 표시 되어야 합니다 <xref:System.Runtime.InteropServices.ComVisibleAttribute> `true` .

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 값이 항상 32 비트 정수 계열로 표현 될 수 있는 매개 변수에 대 한이 규칙 위반 문제를 해결 하려면 매개 변수 형식을로 변경 합니다 <xref:System.Int32?displayProperty=fullName> . 매개 변수 값이 32 비트 정수 계열로 표현할 수 있는 것 보다 클 수 있는 경우 매개 변수 형식을로 변경 합니다 <xref:System.Decimal?displayProperty=fullName> . 및는 모두 <xref:System.Single?displayProperty=fullName> <xref:System.Double?displayProperty=fullName> 데이터 형식의 상위 범위에서 전체 자릿수를 잃게 <xref:System.Int64> 됩니다. 멤버가 COM에 표시 되지 않는 경우를로 설정 하 여 표시 합니다 <xref:System.Runtime.InteropServices.ComVisibleAttribute> `false` .

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 Visual Basic 6 COM 클라이언트에서 형식에 액세스 하지 않는 것이 확실 한 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/cs/FxCop.Interoperability.LongArgument.cs#1)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/vb/FxCop.Interoperability.LongArgument.vb#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1413: COM 노출 값 형식에 public이 아닌 필드를 사용하지 마세요.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마세요.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: ComVisibleAttribute로 어셈블리를 표시하세요.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고 항목
 [비관리 코드의](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [Long 데이터 형식](https://msdn.microsoft.com/library/b4770c34-1804-4f8c-b512-c10b0893e516) 상호 운용
