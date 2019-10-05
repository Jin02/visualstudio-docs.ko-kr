---
title: 'CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8e4e5c4ed258bcc88fedbb6d015fed576d326a0f
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234965"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|범주|Microsoft.Interoperability|
|주요 변경 내용|DependsOnFix|

## <a name="cause"></a>원인
Com (구성 요소 개체 모델) 표시 형식이 COM에 표시 되지 않는 형식에서 파생 됩니다.

## <a name="rule-description"></a>규칙 설명
COM 노출 형식이 새 버전에 멤버를 추가 하는 경우 현재 버전에 바인딩하는 COM 클라이언트의 중단을 방지 하기 위해 엄격한 지침을 따라야 합니다. COM에 표시 되지 않는 형식은 새 멤버를 추가할 때 이러한 COM 버전 관리 규칙을 따르지 않을 것으로 가정 합니다. 그러나 com 노출 형식이 com에 표시 되지 않는 형식에서 파생 되 고 또는 <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> <xref:System.Runtime.InteropServices.ClassInterfaceType> (기본값)의 클래스 인터페이스를 노출 하는 경우 기본 형식의 모든 public 멤버 (특별히 COM 숨김으로 표시 되지 않은 경우 중복 됨) COM에 노출 됩니다. 기본 형식에서 후속 버전에 새 멤버를 추가 하는 경우 파생 형식의 클래스 인터페이스에 바인딩하는 모든 COM 클라이언트는 중단 될 수 있습니다. Com 노출 형식은 com 클라이언트의 손상 가능성을 줄이기 위해 com 노출 형식 에서만 파생 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 기본 형식 COM을 표시 하거나 파생 형식 COM을 숨깁니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)