---
title: 'CA1404: P 호출 후 즉시 GetLastError를 호출 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 54ac9a4d56136d9e981ae038a0b219aa4cb4774e
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85544497"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: P/Invoke 다음에 바로 GetLastError를 호출하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName>메서드나 이와 동등한 Win32 함수를 호출 하 `GetLastError` 고 바로 앞에 오는 호출은 플랫폼 호출 메서드에 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 플랫폼 호출 메서드는 비관리 코드에 액세스 하 고 또는 특성의 키워드를 사용 하 여 정의 됩니다 `Declare` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> . 일반적으로 오류가 발생 하면 관리 되지 않는 함수는 Win32 함수를 호출 하 여 오류 `SetLastError` 와 연결 된 오류 코드를 설정 합니다. 실패 한 함수의 호출자는 Win32 함수를 호출 `GetLastError` 하 여 오류 코드를 검색 하 고 오류의 원인을 확인 합니다. 오류 코드는 스레드별 기준으로 유지 관리 되며,에 대 한 다음 호출로 덮어쓰여집니다 `SetLastError` . 실패 한 플랫폼 호출 메서드를 호출한 후에는 관리 코드에서 메서드를 호출 하 여 오류 코드를 검색할 수 있습니다 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> . 다른 관리 되는 클래스 라이브러리 메서드의 내부 호출로 오류 코드를 덮어쓸 수 있기 때문에 `GetLastError` <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 플랫폼 호출 메서드를 호출한 직후 또는 메서드를 호출 해야 합니다.

 규칙은 플랫폼 호출 메서드 호출과 호출 사이에 발생 하는 경우 다음 관리 되는 멤버에 대 한 호출을 무시 합니다 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> . 이러한 멤버는 오류 코드를 변경 하지 않으며 일부 플랫폼 호출 메서드 호출의 성공 여부를 확인 하는 데 유용 합니다.

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 플랫폼 호출 메서드에 대 한 호출 바로 뒤에 오는 호출을로 이동 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 플랫폼 호출 메서드 호출과 메서드 호출 사이의 코드에서 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 명시적으로 또는 암시적으로 오류 코드를 변경 하지 못할 경우에는이 규칙에서 경고를 표시 하지 않아도 됩니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 메서드와 규칙을 충족 하는 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/cs/FxCop.Interoperability.LastErrorPInvoke.cs#1)]
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/vb/FxCop.Interoperability.LastErrorPInvoke.vb#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1060: P/Invoke를 NativeMethods 클래스로 이동 합니다.](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400: P/Invoke 진입점이 있어야 합니다.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [CA1401: P/Invoke는 노출 되지 않아야 합니다.](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

 [CA2205: Win32 API의 동일한 관리형 기능을 사용하세요.](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)
