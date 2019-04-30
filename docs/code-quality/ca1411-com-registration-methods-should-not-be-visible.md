---
title: 'CA1411: COM 등록 메서드는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bd721edab080de7708ac395e2a7d7e486c504fba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546377"
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: COM 등록 메서드는 노출되면 안 됩니다.

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldNotBeVisible|
|CheckId|CA1411|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

로 표시 된 메서드를 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성은 외부에서 볼 수 있습니다.

## <a name="rule-description"></a>규칙 설명
 어셈블리 구성 요소 개체 모델 (COM)를 사용 하 여 등록 되 면 어셈블리에 각 COM 노출 형식에 대 한 레지스트리 항목이 추가 됩니다. 로 표시 되는 메서드를 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 및 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 특성 이라고 등록 및 등록 취소 프로세스 중 각각 이러한 형식의 등록 또는 등록 취소에 관련 된 사용자 코드를 실행 합니다. 이 코드를 이러한 프로세스가 외부 호출 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드의 접근성을 변경 `private` 나 `internal` (`Friend` 에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 두 가지 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1410: COM 등록 메서드는 일치 해야 합니다.](../code-quality/ca1410-com-registration-methods-should-be-matched.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [COM에 어셈블리 등록](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe(어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)