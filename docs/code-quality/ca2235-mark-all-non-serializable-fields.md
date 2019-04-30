---
title: 'CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 51bb7c0e38df92873da6c17b305334c2f6aac25b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806552"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.

## <a name="rule-description"></a>규칙 설명
 직렬화 가능 형식 것으로 표시 되는 <xref:System.SerializableAttribute?displayProperty=fullName> 특성입니다. 형식으로 serialize 될 때를 <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> 형식을 직렬화 할 수 없는 형식의 인스턴스 필드를 포함 하는 경우 예외가 throw 됩니다.

 이 예외는 유형을 통해 사용자 지정 serialization을 사용 하는 경우는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스입니다. 이 인터페이스를 구현 하는 형식 자체 직렬화 논리를 제공 하 고 따라서 CA2235 이러한 형식의 직렬화 인스턴스 필드에 대해 발생 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적용 된 <xref:System.NonSerializedAttribute?displayProperty=fullName> 특성을 직렬화 할 수 없는 필드입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 경우에이 규칙에서 경고를 표시는 <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> 형식이 serialize 및 deserialize 될 필드의 인스턴스를 허용 하는 선언 되었습니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 규칙을 충족 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 합니다.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: ISerializable을 올바르게 구현](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: 선택적 필드에 deserialization 메서드를 제공 합니다.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)
