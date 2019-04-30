---
title: 'CA1060: P/Invoke를 NativeMethods 클래스로 이동하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a01c8ca81ab469d578d58e6195171c2e3b07704b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788676"
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060: P/Invoke를 NativeMethods 클래스로 이동

|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

메서드를 플랫폼 호출 서비스를 사용 하 여 관리 되지 않는 코드에 액세스 하 고 중 하나의 멤버인 합니다 **NativeMethods** 클래스입니다.

## <a name="rule-description"></a>규칙 설명

플랫폼 호출 메서드를 사용 하 여 표시 된 것과 같은 합니다 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성 또는 사용 하 여 정의 된 메서드를를 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 비관리 코드에 액세스 합니다. 이러한 메서드는 다음 클래스 중 하나 이어야 합니다.

- **NativeMethods** -이 클래스는 비관리 코드 권한에 대 한 스택 워크를 표시 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 하지 않아야 합니다.) 이 클래스는 스택 워크가 수행 않으므로 어디서 나 사용할 수 있는 방법입니다.

- **SafeNativeMethods** -이 클래스를 비관리 코드 권한에 대 한 스택 워크를 표시 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 됩니다.) 이 클래스는 누구 든 지 호출에 대 한 안전한 방법입니다. 이러한 메서드의 호출자는 메서드는 모든 호출자에 게는 치명적이 지 때문에 사용법은 보안 되도록 전체 보안 검토를 수행 필요가 없습니다.

- **UnsafeNativeMethods** -이 클래스를 비관리 코드 권한에 대 한 스택 워크를 표시 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 됩니다.) 이 클래스는 잠재적으로 위험한 메서드. 이러한 메서드의 호출자는 사용이 안전한 지 스택 워크도 없으므로 수행할지 되도록 전체 보안 검토를 수행 해야 합니다.

이러한 클래스를 선언 `internal` (`Friend`, Visual Basic의) 하 고 새 인스턴스가 생성 되지 않도록 하는 private 생성자를 선언 합니다. 이러한 클래스의 메서드 수 있어야 합니다 `static` 하 고 `internal` (`Shared` 및 `Friend` Visual basic에서).

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적절 한 메서드를 이동 **NativeMethods** 클래스입니다. 대부분의 응용 프로그램에 대 한 P/Invoke 라는 새 클래스를 이동 **NativeMethods** 충분 합니다.

 그러나 다른 응용 프로그램에서 사용 하기 위한 라이브러리를 개발 하는 경우 고려해 야 이라고 하는 다른 두 클래스를 정의 **SafeNativeMethods** 하 고 **UnsafeNativeMethods**합니다. 이러한 클래스와 유사 합니다 **NativeMethods** 클래스; 그러나 라는 특수 한 특성을 사용 하 여 표시 됩니다 **SuppressUnmanagedCodeSecurityAttribute**합니다. 런타임이이 특성을 적용 하는 경우 모든 호출자에 게 되도록 전체 스택 워크를 수행 하지는 **UnmanagedCode** 권한. 일반적으로 런타임은 시작이 사용 권한을 확인합니다. 확인이 수행 되지 않기 때문에 이러한 관리 되지 않는 메서드 호출에 대 한 성능을 크게 향상 시킬 수, 이러한 메서드를 호출할 수 있는 권한이 제한 된 코드에 있습니다.

 그러나를 기울여서는이 특성을 사용 해야 합니다. 올바르게 구현 되는 경우 심각한 보안 관련 문제가 있습니다...

 메서드를 구현 하는 방법에 대 한 자세한 내용은 참조 하세요.는 **NativeMethods** 예에서 **SafeNativeMethods** 예 및 **UnsafeNativeMethods** 예제입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 메서드를 선언 합니다. 규칙 위반을 수정 하는 **RemoveDirectory** P/Invoke만 P/Invoke를 보유 하도록 설계 하는 적절 한 클래스를 이동 해야 합니다.

 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]

## <a name="nativemethods-example"></a>NativeMethods 예제

### <a name="description"></a>설명
 때문에 합니다 **NativeMethods** 클래스를 사용 하 여 표시 하지 말아야 **SuppressUnmanagedCodeSecurityAttribute**에 P/Invoke에 둔 해야 **UnmanagedCode** 사용 권한입니다. 대부분의 응용 프로그램을 로컬 컴퓨터에서 실행 되므로 완전 신뢰와 함께 실행이 일반적으로 문제가 되지 않습니다. 그러나 재사용 가능한 라이브러리를 개발 하는 경우 고려해 야 정의 **SafeNativeMethods** 하거나 **UnsafeNativeMethods** 클래스입니다.

 에서는 다음 예제는 **Interaction.Beep** 래핑하는 메서드는 **MessageBeep** user32.dll의 함수입니다. 합니다 **MessageBeep** P/Invoke에 배치 되는 **NativeMethods** 클래스입니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
 [!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]

## <a name="safenativemethods-example"></a>SafeNativeMethods 예제

### <a name="description"></a>설명
 모든 응용 프로그램에 안전 하 게 노출할 수 있는 모든 파생 작업이 없는 P/Invoke 메서드 라는 클래스에 넣어야 **SafeNativeMethods**합니다. 권한을 요청할 필요가 및에서 호출 되는 위치에 특히 많은 주의 필요가 없습니다.

 에서는 다음 예제는 **Environment.TickCount** 래핑하는 속성을 **GetTickCount** kernel32.dll에서 함수.

### <a name="code"></a>코드
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]

## <a name="unsafenativemethods-example"></a>UnsafeNativeMethods 예제

### <a name="description"></a>설명
 P/Invoke 메서드를 호출할 수 없습니다. 안전 하 게 하 고 부작용을 일으킬 수 있는 명명 된 클래스에 넣어야 **UnsafeNativeMethods**합니다. 노출 되지 않습니다 사용자에 게 실수로 되도록 이러한 메서드를 엄격 하 게 확인 해야 합니다. 규칙 [CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) 이 도움이 될 수 있습니다. 또는 메서드 대신 요구 하는 다른 권한이 있어야 **UnmanagedCode** 사용 하는 경우.

 에서는 다음 예제는 **Cursor.Hide** 래핑하는 메서드는 **ShowCursor** user32.dll의 함수입니다.

### <a name="code"></a>코드
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]

## <a name="see-also"></a>참고자료

- [디자인 경고](../code-quality/design-warnings.md)