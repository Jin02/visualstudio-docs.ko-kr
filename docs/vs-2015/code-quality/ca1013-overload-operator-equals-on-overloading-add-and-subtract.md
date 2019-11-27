---
title: 'CA1013: 오버 로드 연산자는 add 및 뺄셈을 오버 로드 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: dd1c144f04150e3965e2c0264b80147cbd9b8f19
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663207"
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 public 또는 protected 형식이 같음 연산자를 구현하지 않고 더하기 또는 빼기 연산자를 구현합니다.

## <a name="rule-description"></a>규칙 설명
 더하기 및 빼기와 같은 작업을 사용 하 여 형식의 인스턴스를 결합할 수 있는 경우에는 거의 항상 같음을 정의 하 여 동일한 구성 값을 가진 두 인스턴스의 `true`을 반환 해야 합니다.

 같음 연산자의 오버 로드 된 구현에서는 기본 같음 연산자를 사용할 수 없습니다. 이렇게 하면 스택 오버플로가 발생 합니다. 같음 연산자를 구현 하려면 구현에서 개체. Equals 메서드를 사용 합니다. 다음 예제를 참조하세요.

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 더하기 및 빼기 연산자와 수학적으로 일치 하도록 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 같음 연산자의 기본 구현이 형식에 올바른 동작을 제공 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식 (`BadAddableType`)을 정의 합니다. 이 형식은 같음 연산자를 구현 하 여 동일한 필드 값이 있는 두 인스턴스가 같은지를 `true` 합니다. `GoodAddableType` 형식에는 수정 된 구현이 표시 됩니다. 또한이 형식은 같지 않음 연산자를 구현 하 고 다른 규칙을 충족 하기 위해 <xref:System.Object.Equals%2A>를 재정의 합니다. 전체 구현에서는 <xref:System.Object.GetHashCode%2A>도 구현 합니다.

 [!code-csharp[FxCop.Design.AddAndSubtract#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AddAndSubtract/cs/FxCop.Design.AddAndSubtract.cs#1)]

## <a name="example"></a>예제
 다음 예제에서는이 항목에서 이전에 정의한 형식의 인스턴스를 사용 하 여 같은지 여부를 테스트 하 여 같음 연산자에 대 한 기본 동작 및 올바른 동작을 보여 줍니다.

 [!code-csharp[FxCop.Design.TestAddAndSubtract#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestAddAndSubtract/cs/FxCop.Design.TestAddAndSubtract.cs#1)]

 이 예제의 결과는 다음과 같습니다.

 **잘못 된 형식: {2,2} {2,2} 같습니다. **
**올바른 형식이 아닙니다. {3,3} {3,3}는 동일 합니까? 예**
**좋은 유형: {3,3} {3,3} = =?   예**
**잘못 된 유형: {2,2} {9,9} 같습니다. **
**올바른 형식이 아닙니다. {3,3} {9,9} = =?   아니요**
## <a name="see-also"></a>참고 항목
 [같음 연산자](https://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)
