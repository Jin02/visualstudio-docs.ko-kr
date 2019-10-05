---
title: 'CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e5af6b7872f0fa05183334e6acd2bc4922f84990
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231168"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다.

|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|범주|Microsoft.Usage|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

을 재정의 <xref:System.Object.Finalize%2A?displayProperty=fullName> 하는 형식은 기본 클래스의 <xref:System.Object.Finalize%2A> 메서드를 호출 하지 않습니다.

## <a name="rule-description"></a>규칙 설명

종료는 상속 계층을 통해 전파되어야 합니다. 이를 위해 형식은 자체 <xref:System.Object.Finalize%2A> <xref:System.Object.Finalize%2A> 메서드 내에서 기본 클래스 메서드를 호출 해야 합니다. C# 컴파일러가 기본 클래스 종료자에 대 한 호출을 자동으로 추가 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 <xref:System.Object.Finalize%2A> <xref:System.Object.Finalize%2A> 메서드에서 기본 형식의 메서드를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 공용 언어 런타임을 대상으로 하는 일부 컴파일러는 기본 형식의 종료자에 대 한 호출을 MSIL (Microsoft 중간 언어)에 삽입 합니다. 이 규칙의 경고를 보고 하는 경우 컴파일러는 호출을 삽입 하지 않으므로 코드에 추가 해야 합니다.

## <a name="example"></a>예제

다음 Visual Basic 예제에서는 기본 클래스에서 `TypeB` 메서드를 <xref:System.Object.Finalize%2A> 올바르게 호출 하는 형식을 보여 줍니다.

[!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]

## <a name="see-also"></a>참고 항목

- [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)