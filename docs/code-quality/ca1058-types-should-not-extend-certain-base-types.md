---
title: 'CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa1ffbb393700647f12c455c8d1307a77548f2d1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235490"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|범주|Microsoft.Design|
|주요 변경 내용|주요 변경|

## <a name="cause"></a>원인

형식은 다음 기본 형식 중 하나를 확장 합니다.

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

예외는 <xref:System> 네임 스페이스 <xref:System.Exception?displayProperty=fullName> 의 서브 클래스 중 하나 또는에서 파생 되어야 합니다.

기본 개체 모델 또는 데이터 원본의 <xref:System.Xml.XmlDocument> XML 뷰를 만들려는 경우의 서브 클래스를 만들지 마십시오.

### <a name="non-generic-collections"></a>제네릭이 아닌 컬렉션

가능 하면 언제 든 지 및/또는 제네릭 컬렉션을 확장 하십시오. 이전에 제공 하지 않는 한 코드에서 제네릭이 아닌 컬렉션을 확장 하지 마십시오.

**잘못 된 사용 예**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**올바른 사용법의 예**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 다른 기본 형식 또는 제네릭 컬렉션에서 형식을 파생 시킵니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

위반에 대해이 규칙에서 경고를 표시 하지 마십시오 <xref:System.ApplicationException>. 위반에 대해이 규칙에서 경고를 표시 하지 않는 것이 <xref:System.Xml.XmlDocument>안전 합니다. 코드가 이전에 릴리스된 경우 제네릭이 아닌 컬렉션에 대 한 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1058.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.