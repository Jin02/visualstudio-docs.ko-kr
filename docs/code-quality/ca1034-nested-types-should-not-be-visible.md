---
title: 'CA1034: 중첩 형식은 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a086ad80bd13fb18f866769db34d72cae3e67496
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922872"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: 중첩 형식은 노출되면 안 됩니다.

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

외부에 노출 되는 형식에는 외부에서 볼 때 표시 되는 형식 선언이 포함 됩니다. 중첩 열거형 및 protected 형식은이 규칙에서 제외 됩니다.

## <a name="rule-description"></a>규칙 설명
중첩 형식은 다른 형식의 범위 내에 선언 된 형식입니다. 중첩 형식은 포함 하는 형식의 개인 구현 세부 정보를 캡슐화 하는 데 유용 합니다. 이 용도로 사용할 경우 중첩 형식은 외부에 노출되면 안 됩니다.

논리적 그룹화에 대해 외부에서 볼 수 있는 중첩 유형을 사용 하거나 이름 충돌을 방지 하려면 대신 네임 스페이스를 사용 합니다.

중첩 형식에는 멤버 액세스 가능성 이라는 개념이 포함 되며 일부 프로그래머는 명확 하 게 이해할 수 없습니다.

보호 된 형식은 미리 사용자 지정 시나리오에서 서브 클래스 및 중첩 형식에 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
중첩 형식을 외부에서 볼 수 있도록 하려는 경우 형식의 액세스 가능성을 변경 합니다. 그렇지 않으면 부모에서 중첩 형식을 제거 합니다. 중첩의 목적이 중첩 된 형식을 범주화 하려면 네임 스페이스를 사용 하 여 계층을 만듭니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
[!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
[!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]