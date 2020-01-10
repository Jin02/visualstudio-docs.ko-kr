---
title: 잠금 정책을 정의 하 여 읽기 전용 세그먼트 만들기 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: fa549c71-2bf6-4b08-b7b2-7756dd6f1dc8
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0d9887e3c7cf283bff453e458502400a7ade1a41
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75849563"
---
# <a name="defining-a-locking-policy-to-create-read-only-segments"></a>잠금 정책을 정의하여 읽기 전용 세그먼트 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 시각화 및 모델링 SDK의 불변성 API를 사용 하면 프로그램에서 DSL (도메인 특정 언어) 모델의 일부 또는 전부를 잠그고 변경할 수 있습니다. 예를 들어이 읽기 전용 옵션을 사용 하면 사용자가 동료에 게 DSL 모델에 주석을 달고 검토할 수 있지만 원래는 변경 하지 못하게 할 수 있습니다.

 또한 DSL의 작성자는 *잠금 정책을* 정의할 수 있습니다. 잠금 정책은 허용 되거나 허용 되지 않는 잠금이나 필수를 정의 합니다. 예를 들어 DSL을 게시 하는 경우 타사 개발자가 새 명령으로 확장할 수 있습니다. 하지만 잠금 정책을 사용 하 여 모델의 지정 된 파트에 대 한 읽기 전용 상태를 변경 하지 못하게 할 수도 있습니다.

> [!NOTE]
> 리플렉션을 사용 하 여 잠금 정책을 우회할 수 있습니다. 타사 개발자를 위한 명확한 경계를 제공 하지만 강력한 보안을 제공 하지는 않습니다.

 추가 정보 및 샘플은 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] [시각화 및 모델링 SDK](https://docs.microsoft.com/samples/browse/?redirectedfrom=MSDN-samples) 웹 사이트에서 사용할 수 있습니다.

## <a name="setting-and-getting-locks"></a>잠금 설정 및 가져오기
 저장소, 파티션 또는 개별 요소에 대해 잠금을 설정할 수 있습니다. 예를 들어 다음 문은 모델 요소가 삭제 되는 것을 방지 하 고 해당 속성이 변경 되지 않도록 합니다.

```
using Microsoft.VisualStudio.Modeling.Immutability; ...
element.SetLocks(Locks.Delete | Locks.Property);
```

 다른 잠금 값을 사용 하 여 관계 변경, 요소 생성, 파티션 간 이동 및 역할의 링크 순서 변경을 방지할 수 있습니다.

 잠금은 사용자 작업 및 프로그램 코드에 모두 적용 됩니다. 프로그램 코드에서 변경을 시도 하면 `InvalidOperationException` throw 됩니다. 실행 취소 또는 다시 실행 작업에서 잠금이 무시 됩니다.

 `IsLocked(Locks)`를 사용 하 여 요소에 지정 된 집합의 잠금이 있는지 여부를 검색 하 고 `GetLocks()`를 사용 하 여 요소에 대 한 현재 잠금 집합을 가져올 수 있습니다.

 트랜잭션을 사용 하지 않고 잠금을 설정할 수 있습니다. 잠금 데이터베이스가 저장소의 일부가 아닙니다. 저장소에서 값의 변경에 대 한 응답으로 잠금을 설정 하는 경우 (예: OnValueChanged) 실행 취소 작업의 일부인 변경 작업을 허용 해야 합니다.

 이러한 메서드는 <xref:Microsoft.VisualStudio.Modeling.Immutability> 네임 스페이스에 정의 된 확장 메서드입니다.

### <a name="locks-on-partitions-and-stores"></a>파티션 및 저장소에 대 한 잠금
 잠금은 파티션과 저장소에도 적용할 수 있습니다. 파티션에 설정 된 잠금은 파티션의 모든 요소에 적용 됩니다. 따라서 예를 들어 다음 문은 자체 잠금의 상태와 관계 없이 파티션의 모든 요소가 삭제 되는 것을 방지 합니다. 그럼에도 불구 하 고 `Locks.Property` 같은 다른 잠금은 개별 요소에 대해 설정할 수 있습니다.

```
partition.SetLocks(Locks.Delete);
```

 저장소에 설정 된 잠금은 파티션 및 요소에 대 한 해당 잠금의 설정에 관계 없이 모든 해당 요소에 적용 됩니다.

### <a name="using-locks"></a>잠금 사용
 잠금을 사용 하 여 다음 예제와 같은 체계를 구현할 수 있습니다.

- 주석을 나타내는 모든 요소 및 관계를 제외 하 고 모든 요소 및 관계의 변경을 허용 하지 않습니다. 이렇게 하면 사용자가 모델을 변경 하지 않고 주석을 추가할 수 있습니다.

- 기본 파티션의 변경은 허용 하지 않지만 다이어그램 파티션은 변경할 수 있습니다. 사용자가 다이어그램을 다시 정렬할 수 있지만 기본 모델을 변경할 수는 없습니다.

- 별도의 데이터베이스에 등록 된 사용자 그룹을 제외 하 고 저장소에 대 한 변경 내용을 허용 하지 않습니다. 다른 사용자의 경우 다이어그램과 모델은 읽기 전용입니다.

- 다이어그램의 부울 속성이 true로 설정 된 경우 모델에 대 한 변경 내용을 허용 하지 않습니다. 해당 속성을 변경 하는 메뉴 명령을 제공 합니다. 이렇게 하면 사용자가 실수로 변경 하지 않는 사용자에 게이를 방지할 수 있습니다.

- 특정 클래스의 요소 및 관계를 추가 및 삭제 하는 것을 허용 하지 않지만 속성을 변경할 수 있습니다. 그러면 사용자가 속성을 채울 수 있는 고정 된 양식이 제공 됩니다.

## <a name="lock-values"></a>잠금 값
 잠금은 저장소, 파티션 또는 개별 ModelElement 설정할 수 있습니다. 잠금은 `Flags` 열거형입니다. '&#124;'를 사용 하 여 해당 값을 조합할 수 있습니다.

- ModelElement의 잠금은 항상 해당 파티션의 잠금을 포함 합니다.

- 파티션 잠금에는 항상 저장소 잠금이 포함 됩니다.

  파티션 또는 저장소에 대해 잠금을 설정할 수 없으며 동시에 개별 요소에 대해 잠금을 사용 하지 않도록 설정할 수 없습니다.

|값|`IsLocked(Value)` true 이면 의미|
|-----------|------------------------------------------|
|None|제한이 없습니다.|
|속성|요소의 도메인 속성을 변경할 수 없습니다. 관계에서 도메인 클래스의 역할에 의해 생성 된 속성에는 적용 되지 않습니다.|
|Add|파티션 또는 저장소에 새 요소 및 링크를 만들 수 없습니다.<br /><br /> `ModelElement`에 적용할 수 없습니다.|
|이동|`element.IsLocked(Move)` true 이면 파티션 간에 요소를 이동할 수 없습니다. `targetPartition.IsLocked(Move)` true 이면입니다.|
|삭제|요소 자체에 대해이 잠금이 설정 된 경우 요소를 삭제할 수 없습니다. 포함 된 요소 및 모양과 같이 삭제가 전파 되는 요소에 대해이 잠금이 설정 된 경우에는 요소를 삭제할 수 없습니다.<br /><br /> `element.CanDelete()`를 사용 하 여 요소를 삭제할 수 있는지 여부를 검색할 수 있습니다.|
|다시 정렬|Roleplayer에서 링크 순서를 변경할 수 없습니다.|
|RolePlayer|이 요소에서 소스인 링크 집합은 변경할 수 없습니다. 예를 들어 새 요소는이 요소에 포함 될 수 없습니다. 이 요소가 대상인 링크에는 영향을 주지 않습니다.<br /><br /> 이 요소가 링크 이면 해당 소스와 대상이 영향을 받지 않습니다.|
|모든|다른 값의 비트 OR입니다.|

## <a name="locking-policies"></a>잠금 정책
 DSL의 작성자는 *잠금 정책을*정의할 수 있습니다. 잠금 정책은 SetLocks ()의 작업을 작업이 특정 잠금이 설정 되지 않도록 하거나 특정 잠금을 설정 해야 하도록 지정할 수 있습니다. 일반적으로 `private`변수를 선언할 수 있는 것과 동일한 방식으로 사용자 또는 개발자가 의도 하지 않은 DSL 사용을 contravening 수 없도록 잠금 정책을 사용 합니다.

 잠금 정책을 사용 하 여 요소의 형식에 종속 된 모든 요소에 대 한 잠금을 설정할 수도 있습니다. 이는 요소를 처음으로 만들거나 파일에서 deserialize 할 때 `SetLocks(Locks.None)` 항상 호출 되기 때문입니다.

 그러나 수명 동안에는 요소에 대 한 잠금을 변경 하는 정책을 사용할 수 없습니다. 이러한 효과를 얻으려면 호출을 사용 하 여 `SetLocks()`해야 합니다.

 잠금 정책을 정의 하려면 다음을 수행 해야 합니다.

- <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>를 구현하는 클래스를 만듭니다.

- DSL의 DocData를 통해 사용할 수 있는 서비스에이 클래스를 추가 합니다.

### <a name="to-define-a-locking-policy"></a>잠금 정책을 정의 하려면
 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy> 정의는 다음과 같습니다.

```
public interface ILockingPolicy
{
  Locks RefineLocks(ModelElement element, Locks proposedLocks);
  Locks RefineLocks(Partition partition, Locks proposedLocks);
  Locks RefineLocks(Store store, Locks proposedLocks);
}
```

 이러한 메서드는 저장소, 파티션 또는 ModelElement에서 `SetLocks()`를 호출 하는 경우 호출 됩니다. 각 메서드에서 제안 된 잠금 집합이 제공 됩니다. 제안 된 집합을 반환 하거나, 잠금을 추가 하거나 뺄 수 있습니다.

 예를 들면 다음과 같습니다.:

```
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Immutability;
namespace Company.YourDsl.DslPackage // Change
{
  public class MyLockingPolicy : ILockingPolicy
  {
    /// <summary>
    /// Moderate SetLocks(this ModelElement target, Locks locks)
    /// </summary>
    /// <param name="element">target</param>
    /// <param name="proposedLocks">locks</param>
    /// <returns></returns>
    public Locks RefineLocks(ModelElement element, Locks proposedLocks)
    {
      // In my policy, users can never delete an element,
      // and other developers cannot easily change that:
      return proposedLocks | Locks.Delete);
    }
    public Locks RefineLocks(Store store, Locks proposedLocks)
    {
      // Only one user can change this model:
      return Environment.UserName == "aUser"
           ? proposedLocks : Locks.All;
    }

```

 다른 코드가를 호출 하는 경우에도 사용자가 항상 요소를 삭제할 수 있도록 하려면 `SetLocks(Lock.Delete):`

 `return proposedLocks & (Locks.All ^ Locks.Delete);`

 MyClass의 모든 요소에 대 한 모든 속성의 변경을 허용 하지 않으려면 다음을 수행 합니다.

 `return element is MyClass ? (proposedLocks | Locks.Property) : proposedLocks;`

### <a name="to-make-your-policy-available-as-a-service"></a>정책을 서비스로 사용할 수 있도록 설정 하려면
 `DslPackage` 프로젝트에서 다음 예제와 비슷한 코드를 포함 하는 새 파일을 추가 합니다.

```
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Immutability;
namespace Company.YourDsl.DslPackage // Change
{
  // Override the DocData GetService() for this DSL.
  internal partial class YourDslDocData // Change
  {
    /// <summary>
    /// Custom locking policy cache.
    /// </summary>
    private ILockingPolicy myLockingPolicy = null;

    /// <summary>
    /// Called when a service is requested.
    /// </summary>
    /// <param name="serviceType">Service requested</param>
    /// <returns>Service implementation</returns>
    public override object GetService(System.Type serviceType)
    {
      if (serviceType == typeof(SLockingPolicy)
       || serviceType == typeof(ILockingPolicy))
      {
        if (myLockingPolicy == null)
        {
          myLockingPolicy = new MyLockingPolicy();
        }
        return myLockingPolicy;
      }
      // Request is for some other service.
      return base.GetService(serviceType);
    }
}
```
