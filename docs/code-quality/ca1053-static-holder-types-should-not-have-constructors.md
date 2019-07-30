---
title: 'CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fec59e1d683c7867eb1cad9ae4e796a0815200d4
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68604777"
---
# <a name="ca1053-static-holder-types-should-not-have-default-constructors"></a>CA1053: 정적 소유자 형식에는 기본 생성자를 사용할 수 없습니다.

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

> [!NOTE]
> Rule CA1053는 CA1052로 [결합 됩니다. 정적 소유자 형식은 [FxCop 분석기](fxcop-analyzers.yml)에서](ca1052-static-holder-types-should-be-sealed.md) sealed 여야 합니다.

## <a name="cause"></a>원인

Public 또는 nested public 형식은 정적 멤버만 선언 하 고 기본 생성자를 포함 합니다.

## <a name="rule-description"></a>규칙 설명

정적 멤버를 호출 하려면 형식의 인스턴스가 필요 하지 않으므로 기본 생성자는 필요 하지 않습니다. 또한 형식이 비정적 멤버를 포함 하지 않기 때문에 인스턴스를 만들 때 형식의 멤버에 대 한 액세스 권한은 제공 되지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 기본 생성자를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 기본 생성자가 있으면 형식이 정적 형식이 아닌 것으로 제안 됩니다.