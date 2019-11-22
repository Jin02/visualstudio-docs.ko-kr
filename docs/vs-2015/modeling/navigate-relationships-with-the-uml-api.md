---
title: Navigate relationships with the UML API | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML API
ms.assetid: a4d11d45-b8c0-40f9-a597-363f07659610
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f19208e886eb499c825b119ad4ade7e8b52ab88f
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300236"
---
# <a name="navigate-relationships-with-the-uml-api"></a>UML API를 사용하여 관계 탐색
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

모델은 여러 종류의 관계에 의해 서로 연결된 요소로 구성됩니다. 이 항목에서는 프로그램 코드에서 모델을 탐색하는 방법을 설명합니다.

## <a name="traversing-relationships"></a>관계 트래버스

### <a name="any-relationship"></a>임의 관계
 `GetRelatedElements<T>()`를 사용하여 특정 요소에 연결된 모든 요소를 찾습니다. `T`를 `IRelationship`으로 설정하여 모든 종류의 관계를 트래버스하거나, `IAssociation`과 같은 보다 구체적인 형식을 사용하여 해당 형식만 트래버스합니다.

```
IElement anElement;
// Select all elements related to anElement.
Context.CurrentDiagram.SelectShapes (
   anElement.GetRelatedElements<IRelationship>()
    .SelectMany(e=>e.Shapes()).ToArray());

```

 `GetRelatedLinks<T>()`를 사용하여 요소에 연결된 모든 관계를 찾습니다.

```
// Process all relationships connected to an element.
foreach (IRelationship relationship in
   anElement.GetRelatedLinks<IRelationship>())
{
  Debug.Assert(relationship.SourceElement == anElement
      || relationship.TargetElement == anElement);
}

```

### <a name="association"></a>연결
 연결은 각각 분류자에 속해 있는 두 속성 간의 관계입니다.

```
IClassifier classifier; // class, interface, component, actor, ...
// Get all the associations sourced from this classifier
foreach (IProperty p in classifier.GetOutgoingAssociationEnds())
{
  // p represents the end further end of an association.
  IType oppositeElement = p.Type;
    // The type to which this association connects classifier

  IProperty oppositeProperty = p.Opposite;
    // The nearer end of the association.
  Debug.Assert(oppositeProperty.Type == classifier);
  IAssociation association = p.Association;
  Debug.Assert(association.MemberEnds.Contains(p)
     && association.MemberEnds.Contains(oppositeProperty));
}
```

### <a name="generalization-and-realization"></a>일반화 및 인식
 일반화의 반대쪽 끝에 액세스합니다.

```
foreach (IClassifier supertype in classifier.Generals) {…}
foreach (IClassifier subtype in classifier.GetSpecifics()) {…}
Access the relationship itself:
foreach (IGeneralization gen in classifier.Generalizations)
{ Debug.Assert(classifier == gen.Specific); }
```

```

/// InterfaceRealization:
IEnumerable<IInterface> GetRealizedInterfaces
    (this IBehavioredClassifier classifier);
IEnumerable<IBehavioredClassifier> GetRealizingClassifiers
    (this IInterface interface);

```

### <a name="dependency"></a>종속성

```
/// Returns the elements depending on this element
IEnumerable<INamedElement> GetDependencyClients(this INamedElement element);
/// Returns the elements this element depends on
IEnumerable<INamedElement> INamedElement GetDependencySuppliers(this INamedElement element);

```

### <a name="activity-edge"></a>작업 가장자리

```
/// Returns the nodes targeted by edges outgoing from this one
IEnumerable<IActivityNode> GetActivityEdgeTargets(this IActivityNode node);
/// Returns the nodes sourcing edges incoming to this one
IEnumerable<IActivityNode> GetActivityEdgeSources(this IActivityNode node);

```

### <a name="connector-assembly-and-delegation"></a>연결선(어셈블리 및 위임)

```
/// Returns the elements connected via assembly
/// or delegation to this one
IEnumerable<IConnectableElement> GetConnectedElements(this IConnectableElement element);

```

### <a name="messages-and-lifelines"></a>메시지 및 수명선

```
IEnumerable<IMessage> GetAllOutgoingMessages(this ILifeline  lifeline);
// both from lifeline and execution occurrences
IEnumerable<IMessage> GetAllIncomingMessages(this ILifeline  lifeline);
ILifeline GetSourceLifeline(this IMessage message);
    // may return null for found messages
ILifeline GetTargetLifeline(this IMessage message);
    // may return null for lost messages

```

### <a name="package-import"></a>패키지 가져오기

```
IEnumerable<IPackage>GetImportedPackages(this INamespace namespace);
IEnumerable<INamespace> GetImportingNamespaces(this IPackage package);

```

### <a name="use-case-extend-and-include"></a>사용 사례 확장 및 포함

```
IEnumerable<IUseCase>GetExtendedCases(this IUseCase usecase);
IEnumerable<IUseCase>GetExtendingCases(this IUseCase usecase);
IEnumerable<IUseCase>GetIncludedCases(this IUseCase usecase);
IEnumerable<IUseCase>GetIncludingCases(this IUseCase usecase);
```

## <a name="enumerating-relationships"></a>관계 열거
 All properties of the UML model that return multiple values conform to the IEnumerable<> interface. This means that you can use [Linq Query Expressions](https://go.microsoft.com/fwlink/?LinkId=168834) and the extension methods defined in the **System.Linq** namespace.

 예를 들어 다음과 같은 가치를 제공해야 합니다.

```
from shape in     Context.CurrentDiagram.GetSelectedShapes<IClassifier>()
where shape.Color == System.Drawing.Color.Red
select shape.Element

```

## <a name="see-also"></a>관련 항목:
 [Extend UML models and diagrams](../modeling/extend-uml-models-and-diagrams.md) [Navigate the UML model](../modeling/navigate-the-uml-model.md)
