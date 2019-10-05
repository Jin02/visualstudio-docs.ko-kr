---
title: 'CA1401: P/Invoke는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d4a0a1c001407d947988497c422fdb8e88dd7c83
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234890"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: P/Invoke는 노출되지 않아야 합니다.

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|범주|Microsoft.Interoperability|
|주요 변경 내용|주요 변경|

## <a name="cause"></a>원인
공용 형식의 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 공용 또는 보호 된 메서드에는의 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]키워드에 의해 구현 되는 특성도 있습니다.

## <a name="rule-description"></a>규칙 설명
<xref:System.Runtime.InteropServices.DllImportAttribute> 특성으로 표시 된 메서드 (또는의 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]키워드를 `Declare` 사용 하 여 정의 된 메서드)는 플랫폼 호출 서비스를 사용 하 여 비관리 코드에 액세스 합니다. 이러한 메서드는 노출되지 않아야 합니다. 이러한 메서드를 private 또는 internal로 유지 하면 호출자가 다른 방법으로 호출할 수 없는 관리 되지 않는 Api에 대 한 액세스를 허용 하 여 보안을 위반 하는 데 라이브러리를 사용할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 메서드의 액세스 수준을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반 하는 메서드를 선언 합니다.

[!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]