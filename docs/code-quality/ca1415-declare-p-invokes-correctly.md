---
title: 'CA1415: P/Invoke를 올바르게 선언하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99274abee2c05a1bd33e34c9eb02cc928c1b54b0
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234619"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: P/Invoke를 올바르게 선언하십시오.

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|범주|Microsoft.Interoperability|
|주요 변경 내용|분리 안 됨-매개 변수를 선언 하는 P/Invoke를 어셈블리 외부에서 볼 수 없는 경우 중단-매개 변수를 선언 하는 P/Invoke를 어셈블리 외부에서 볼 수 있는 경우.|

## <a name="cause"></a>원인
플랫폼 호출 메서드가 잘못 선언 되었습니다.

## <a name="rule-description"></a>규칙 설명
플랫폼 호출 메서드는 비관리 코드에 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 액세스 하 고 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>의 키워드를 사용 하 여 정의 됩니다. 현재이 규칙은 겹친 구조체 매개 변수에 대 한 포인터를 포함 하는 Win32 함수를 대상으로 하는 플랫폼 호출 메서드 선언을 검색 하 고 해당 관리 되는 매개 <xref:System.Threading.NativeOverlapped?displayProperty=fullName> 변수는 구조체에 대 한 포인터가 아닙니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 플랫폼 호출 메서드를 올바르게 선언 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하 고 규칙을 충족 하는 플랫폼 호출 메서드를 보여 줍니다.

[!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>참고 항목
[비관리 코드와의 상호 운용](/dotnet/framework/interop/index)