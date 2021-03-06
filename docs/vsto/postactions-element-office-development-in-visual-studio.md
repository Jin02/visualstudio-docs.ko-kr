---
title: '&lt;postActions &gt; 요소 (Visual Studio에서 Office 개발)'
ms.date: 02/02/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postActions> element
- postActions element
- <postActions> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bfe9ae171f0f6fac1c2b5add5340de1c11f3da0f
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85544419"
---
# <a name="ltpostactionsgt-element-office-development-in-visual-studio"></a>&lt;postActions &gt; 요소 (Visual Studio에서 Office 개발)
  `postActions` 네임스페이스의 `vstav3` 요소에는 배포 후 작업을 설명하는 모든 `postAction` 요소가 포함되며 Office 솔루션 설치 후 실행됩니다.

## <a name="syntax"></a>구문

```xml
<postActions>
  <postAction>
    <entryPoint>
    </entryPoint>
    <postActionData>
    </postActionData>
  </postAction>
</postActions>
```

## <a name="elements-and-attributes"></a>요소 및 특성
 `postActions` 요소는 선택적이며 `vstav3` 네임스페이스에 있습니다. 하나의 애플리케이션 매니페스트에서는 하나의 `postActions` 요소만 정의할 수 있습니다.

 `postActions` 요소에는 특성이 없습니다.

 `postActions` 에는 다음 요소가 있습니다.

### <a name="postaction"></a>postAction
 선택 사항입니다. `postAction`네임 스페이스에 있는 요소의 역할은 `vstav3` [Visual Studio&#41;에서 Office 개발 &#40;&#60;postaction&#62; 요소 ](../vsto/postaction-element-office-development-in-visual-studio.md)에 정의 되어 있습니다.

## <a name="post-deployment-action-example"></a>배포 후 작업 예제

### <a name="description"></a>설명
 다음 코드 예제에서는 `postActions` 을 사용하여 배포된 Office 솔루션에 대한 애플리케이션 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는 [Office 솔루션의 응용 프로그램 매니페스트에](../vsto/application-manifests-for-office-solutions.md)제공 된 더 큰 예제의 일부입니다.

### <a name="code"></a>코드

```xml
<vstav3:postActions>
  <vstav3:postAction>
    <vstav3:entryPoint
      class="PostDeploymentAction.PostDeploymentActionSample">
      <assemblyIdentity
        name="PostDeploymentAction"
        version="1.0.0.0"
        language="neutral"
        processorArchitecture="msil" />
    </vstav3:entryPoint>
    <vstav3:postActionData>
    </vstav3:postActionData>
  </vstav3:postAction>
</vstav3:postActions>
```

## <a name="see-also"></a>참고 항목

- [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)
- [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)
