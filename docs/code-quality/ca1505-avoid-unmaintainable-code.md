---
title: 'CA1505: 유지 관리할 수 없는 코드를 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 740ef26af6f1f84d23ef27de5176df1b3de98b34
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797323"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: 유지 관리할 수 없는 코드를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|범주|Microsoft.Maintainability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식 또는 메서드에 낮은 유지 관리 인덱스 값이 있습니다.

## <a name="rule-description"></a>규칙 설명

유지 관리 인덱스는 다음 메트릭을 사용 하 여 계산 됩니다: 줄의 코드, 프로그램 볼륨 및 순환 복잡성입니다. 프로그램 볼륨은 형식 또는 코드의 연산자 및 피연산자의 수를 기반으로 하는 방법에 대 한 이해 하기 어려운 이유는 측정값입니다. 순환 복잡성은 구조적 형식 또는 메서드의 복잡성을 측정 합니다. 코드 메트릭에 대 한 자세히 알아볼 수 있습니다 [복잡성과 관리 되는 코드의 관리 용이성 측정](../code-quality/code-metrics-values.md)합니다.

낮은 유지 관리 인덱스를 나타내고 형식 또는 메서드를 유지 관리 하기 어렵고 다시 디자인 좋은 후보가 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 위반을 해결 하려면 형식 또는 메서드를 다시 디자인 하 고 작고 더욱 중점을 둔 형식이 나 메서드의로 분할 하려고 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

형식 또는 메서드를 분할할 수 없는 또는 큰 크기로 불구 하 고 관리 하기 쉬운 것으로 간주 됩니다 때이 경고를 무시할 수 있습니다.

## <a name="see-also"></a>참고자료

- [유지 관리 경고](../code-quality/maintainability-warnings.md)
- [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/code-metrics-values.md)