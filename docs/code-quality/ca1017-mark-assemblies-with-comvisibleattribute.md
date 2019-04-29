---
title: 'CA1017: ComVisibleAttribute로 어셈블리를 표시하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 648c59e2660c0509edfcf65ac50bf8791bc5896e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779434"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: ComVisibleAttribute로 어셈블리를 표시하세요.

|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 어셈블리에 없는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 특성이 적용 합니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성 COM 클라이언트가 관리 되는 코드를 액세스 하는 방법을 결정 합니다. 어셈블리에서 COM에 노출할지 여부를 명시적으로 나타내는 것이 좋은 디자인입니다. COM 노출 여부 전체 어셈블리에 대해 설정 하 고 개별 형식 및 형식 멤버를 재정의할 수 있습니다. 특성이 없는 어셈블리의 내용을 COM 클라이언트에 표시 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 합니다. 어셈블리를 COM 클라이언트에 노출 하지 않으려면 특성을 적용 하 고 해당 값을 설정 `false`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 표시 되도록 어셈블리를 하려는 경우 특성을 적용 하 고 해당 값을 설정 `true`합니다.

## <a name="example"></a>예제
 다음 예제에서는 있는 어셈블리는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM 클라이언트에 표시 되지 않도록 방지 하기 위해 적용 된 특성입니다.

 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]

## <a name="see-also"></a>참고자료

- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)
- [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)