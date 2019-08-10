---
title: 'CA1407: COM 노출 형식에 정적 멤버를 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 631be1a93318cd24af4251fefbc710294fa52bf7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922005"
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: COM 노출 형식에 정적 멤버를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidStaticMembersInComVisibleTypes|
|CheckId|CA1407|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
COM (구성 요소 개체 모델)에 표시 되도록 특별히 표시 된 형식에 `public``static` 메서드가 포함 되어 있습니다.

## <a name="rule-description"></a>규칙 설명
COM은 메서드를 `static` 지원 하지 않습니다.

이 규칙은 속성 및 이벤트 접근자, 연산자 오버 로드 메서드 또는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 또는 특성을 사용 하 여 표시 된 메서드를 무시 합니다.

기본적으로 다음은 COM에 표시 됩니다. 어셈블리, public 형식, public 형식의 공용 인스턴스 멤버 및 public 값 형식의 모든 멤버입니다.

이 규칙이 발생 하려면 다음 코드에 표시 된 것 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 처럼 어셈블리 수준을 `false` 로 설정 하 고 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 클래스를로 `true`설정 해야 합니다.

```csharp
using System;
using System.Runtime.InteropServices;

[assembly: ComVisible(false)]
namespace Samples
{
    [ComVisible(true)]
    public class MyClass
    {
        public static void DoSomething()
        {
        }
    }
}
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 `static` 메서드와 동일한 기능을 제공 하는 인스턴스 메서드를 사용 하도록 디자인을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
COM 클라이언트가 `static` 메서드에서 제공 하는 기능에 액세스할 필요가 없는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example-violation"></a>위반 예

### <a name="description"></a>Description
다음 예제에서는이 규칙 `static` 을 위반 하는 메서드를 보여 줍니다.

### <a name="code"></a>코드
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]

### <a name="comments"></a>주석
이 예제에서는 COM에서 **Book. FromPages** 메서드를 호출할 수 없습니다.

## <a name="example-fix"></a>예제 수정

### <a name="description"></a>Description
이전 예제에서 위반 문제를 해결 하기 위해 메서드를 인스턴스 메서드로 변경할 수 있지만이 경우이 인스턴스에서는 의미가 없습니다. 다른 개발자가 메서드를 COM에서 `ComVisible(false)` 볼 수 없다는 것을 명확 하 게 하기 위해 메서드에 명시적으로 적용 하는 것이 더 나은 방법입니다.

다음 예제는 메서드에 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 적용 됩니다.

### <a name="code"></a>코드
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]

## <a name="related-rules"></a>관련 규칙
[CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

[CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용 하지 않습니다.](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)

[CA1413: COM 노출 값 형식에 public이 아닌 필드를 사용 하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

## <a name="see-also"></a>참고자료
[비관리 코드와의 상호 운용](/dotnet/framework/interop/index)