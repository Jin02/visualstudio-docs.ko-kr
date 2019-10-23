---
title: 폭포수형 설정 | Microsoft IntelliTest 개발자 테스트 도구
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: ad5f03d7722fa2fb8452b6a1217c18996d6c978f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72653163"
---
# <a name="settings-waterfall"></a>폭포수형 설정

폭포수형 설정의 개념은 사용자가 **어셈블리**, **설비** 및 **탐색** 수준에서 설정을 지정할 수 있음을 의미합니다.

* 어셈블리 - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* 설비 - [PexClass](attribute-glossary.md#pexclass)
* 탐색 - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

**어셈블리** 수준에서 지정된 설정은 해당 어셈블리 아래 모든 설비 및 탐색에 영향을 줍니다. **설비** 수준에서 지정된 설정은 해당 설비 아래 모든 탐색에 영향을 줍니다. 자식 설정 우선&mdash;설정이 **어셈블리** 및 **설비** 수준에서 지정된 경우 **설비** 설정이 사용됩니다.

일부 설정은 **어셈블리** 수준 또는 **설비** 수준에만 관련됩니다.

**예제**

```csharp
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>피드백이 있으신가요?

아이디어와 기능 요청을 [개발자 커뮤니티](https://developercommunity.visualstudio.com/content/idea/post.html?space=8)에 게시하세요.