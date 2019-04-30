---
title: 'CA2200: 스택 정보를 유지하도록 다시 throw하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 55c58f098616a5c3c2d6ad72f56e8eda51f689be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796847"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: 스택 정보를 유지하도록 다시 throw하십시오.

|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

예외가 다시 throw 하 고 예외를 명시적으로 지정 된 `throw` 문입니다.

## <a name="rule-description"></a>규칙 설명

예외가 throw 된 전달 정보 부분은 스택 추적입니다. 스택 추적에는 예외를 throw 하 고 예외를 catch 하는 메서드를 사용 하 여 종료 하는 메서드를 사용 하 여 시작 하는 메서드 호출 계층의 목록입니다. 예외를 지정 하 여 예외가 예외가 다시 throw 하는 경우는 `throw` 문, 스택 추적을 현재 메서드를 다시 시작 되 고 예외를 발생 시킨 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실 됩니다. 예외를 사용 하 여 원래 스택 추적 정보, 사용를 `throw` 예외를 지정 하지 않고 문입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 예외를 명시적으로 지정 하지 않고 예외를 다시 throw 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 메서드를 보여 줍니다 `CatchAndRethrowExplicitly`에서 규칙을 위반 하는 메서드는 `CatchAndRethrowImplicitly`, 규칙을 충족 하는 합니다.

[!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
[!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]