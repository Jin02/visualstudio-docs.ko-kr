---
title: -DoNotLoadProjects(devenv.exe)
ms.date: 03/11/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de757e7022339b11f6d7c04ea7315abf685da24c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428049"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects(devenv.exe)

프로젝트를 로드하지 않고 지정된 솔루션을 엽니다. 자세한 내용은 [Visual Studio의 필터링된 솔루션](../filtered-solutions.md)을 참조하세요.

## <a name="syntax"></a>구문

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>인수

*SolutionName*

필수 요소. 열려는 솔루션의 전체 경로 및 이름입니다.

## <a name="example"></a>예제

예제에서는 프로젝트를 로드하지 않고 MySln.sln 솔루션을 엽니다.

```shell
devenv /donotloadprojects MySln.sln
```

## <a name="see-also"></a>참고 항목

- [Visual Studio의 필터링된 솔루션](../filtered-solutions.md)
- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
