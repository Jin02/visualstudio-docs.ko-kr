---
title: 'CA1901: P/Invoke 선언은 이식 가능해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a45b7061ae9d183ec7ee02a3b733ee9340b3689
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921311"
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: P/Invoke 선언은 이식 가능해야 합니다.

|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|범주|Microsoft 이식성|
|변경 수준|중단-P/Invoke가 어셈블리 외부에 표시 되는 경우입니다. 분리 안 함-P/Invoke가 어셈블리 외부에 표시 되지 않는 경우|

## <a name="cause"></a>원인
이 규칙은 각 매개 변수의 크기와 P/Invoke의 반환 값을 평가 하 고 32 비트 및 64 비트 플랫폼에서 비관리 코드로 마샬링될 때 크기가 올바른지 확인 합니다. 이 규칙의 가장 일반적인 위반은 플랫폼에 종속적인 포인터 크기의 변수가 필요한 고정 크기의 정수를 전달 하는 것입니다.

## <a name="rule-description"></a>규칙 설명
이 규칙을 위반 하는 다음 시나리오 중 하나가 발생 합니다.

- 반환 값 또는 매개 변수는로 `IntPtr`형식화 되어야 하는 경우 고정 크기 정수로 형식화 됩니다.

- 반환 값 또는 매개 변수는 고정 크기 정수로 `IntPtr` 형식화 되어야 하는 경우로 형식화 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
또는 대신 `IntPtr` 핸들`Int32` `UIntPtr` 을`UInt32`나타내기 위해 또는를 사용 하 여이 위반 문제를 해결할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 경고는 표시 하지 않아야 합니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반 하는 방법을 보여 줍니다.

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

이 예제에서 매개 변수 `nIconIndex` 는 32 비트 플랫폼의 `IntPtr`경우 4 바이트이 고 64 비트 플랫폼에서는 8 바이트 너비의로 선언 됩니다. 다음에 나오는 관리 되지 않는 선언에서 `nIconIndex` 가 모든 플랫폼에서 4 바이트 부호 없는 정수를 확인할 수 있습니다.

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>예제
위반 문제를 해결 하려면 선언을 다음과 같이 변경 합니다.

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>참고자료
[Portability Warnings](../code-quality/portability-warnings.md)