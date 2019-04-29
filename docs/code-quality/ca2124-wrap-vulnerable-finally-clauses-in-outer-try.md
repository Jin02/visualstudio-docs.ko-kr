---
title: 'CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c35a15e9ce1468edd2882396192a27a3fcc2c86
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796801"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 버전 1.0 및 1.1의.NET Framework에서는 public 또는 protected 메서드가 포함 된 `try` / `catch` / `finally` 블록입니다. `finally` 보안 상태를 되돌리려면 나타나고 되지 않은 블록을 `finally` 블록입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙을 찾습니다 `try` / `finally` 호출 스택에 있는 악성 예외 필터에 취약할 수 있는.NET Framework의 버전 1.0 및 1.1을 대상으로 하는 코드에서 차단 합니다. 필터 전에 실행할 수 있습니다 가장 등의 중요 한 작업 try 블록에서 발생 하 고 예외가 throw 되는 `finally` 블록입니다. 가장 예를 들어 필터 가장된 된 사용자로 실행 될 수는이 의미 합니다. 필터는 현재 Visual Basic에서 구현할 수 있습니다.

> [!NOTE]
> .NET framework 2.0 이상 버전에서는 런타임에서 자동으로 보호 된 `try` / `catch` /  `finally` 재설정 메서드 내에서 직접 발생 하는 경우 악의적인 예외 필터에서 차단 하는 예외 블록을 포함합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 배치는 래핑되지 않은 `try` / `finally` 외부 try 블록에 있습니다. 뒤에 오는 두 번째 예제를 참조 하세요. 이렇게 하면는 `finally` 필터 코드 보다 먼저 실행 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="pseudo-code-example"></a>의사 (pseudo) 코드 예제

### <a name="description"></a>설명

다음 의사 코드에서는 이 규칙에 의해 검색되는 패턴을 보여 줍니다.

```csharp
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

다음 의사 코드는 코드를 보호 하 고이 규칙을 충족 하는 데 사용할 수 있는 패턴을 보여 줍니다.

```csharp
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```