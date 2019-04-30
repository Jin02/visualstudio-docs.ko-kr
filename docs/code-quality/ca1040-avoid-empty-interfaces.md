---
title: 'CA1040: 빈 인터페이스를 사용하지 마세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 726953de0a92c0237ecaf7b724d9586a5d0f4c16
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778761"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: 빈 인터페이스를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

인터페이스 멤버를 선언 하지 않거나 두 개 이상의 다른 인터페이스를 구현 합니다.

기본적으로이 규칙만 살펴봅니다 인터페이스 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

인터페이스에서는 동작이나 사용 계약을 제공하는 멤버를 정의합니다. 인터페이스에 의해 설명되는 기능은 상속 계층 구조에서 형식이 나타나는 위치에 관계없이 모든 형식에서 사용할 수 있습니다. 형식에서는 인터페이스의 멤버에 대한 구현을 제공하여 인터페이스를 구현합니다. 빈 인터페이스 멤버를 정의 하지 않습니다. 따라서 구현 될 수 있는 계약을 정의 하지 않습니다.

빈 디자인 포함가 인터페이스를 구현 해야 하는 경우 아마도 인터페이스를 사용 하 여 표식 또는 형식 그룹을 식별 하는 방법으로는 합니다. 이 식별 런타임 시 발생 하는 경우이 작업을 수행 하는 올바른 방법은 사용자 지정 특성을 사용 하는 것입니다. 대상 형식을 식별 하기 위해 존재 여부 또는 특성의 부재 나 특성의 속성을 사용 합니다. 빈 인터페이스를 사용 하는 것이 적합 한 다음 식별 컴파일 타임에 발생 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

인터페이스를 제거 하거나 멤버를 추가 합니다. 빈 인터페이스 형식 집합이 레이블을 사용 중인 경우 사용자 지정 특성을 사용 하 여 인터페이스를 대체 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

컴파일 타임에 형식의 집합을 식별 하기 위해 인터페이스를 사용 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1040.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 빈 인터페이스를 보여 줍니다.

[!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
[!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
[!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]