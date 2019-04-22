---
title: -Project(devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bbb215efc6ddeabda860b3f0cc218f388f8eaeee
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59652451"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

빌드, 정리, 다시 빌드 또는 배포하도록 솔루션 구성 내에서 단일 프로젝트를 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName   
[/project ProjName] [/projectconfig ProjConfigName]   
```  
  
## <a name="arguments"></a>인수  
 /build  
 `/project` `ProjName`로 지정한 프로젝트를 빌드합니다.  
  
 /clean  
 빌드 중에 만든 모든 중간 파일 및 출력 디렉터리를 정리합니다.  
  
 /rebuild  
 `/project` `ProjName`로 지정한 프로젝트를 정리한 후 빌드합니다.  
  
 /deploy  
 빌드 또는 다시 빌드 후 배포할 프로젝트를 지정합니다.  
  
 `SolnConfigName`  
 필수 요소. `SolutionName`으로 명명된 솔루션에 적용할 솔루션 구성의 이름입니다.  
  
 `SolutionName`  
 필수 요소. 솔루션 파일의 전체 경로 및 이름입니다.  
  
 /project `ProjName`  
 선택 사항입니다. 솔루션 내에 있는 프로젝트 파일의 경로와 이름입니다. `SolutionName` 폴더에서 프로젝트 파일, 프로젝트의 표시 이름 또는 프로젝트 파일의 전체 경로와 이름까지의 상대 경로를 입력할 수 있습니다.  
  
 /projectconfig `ProjConfigName`  
 선택 사항입니다. `/project`에 적용할 프로젝트 빌드 구성 이름입니다.  
  
## <a name="remarks"></a>주의  
  
-   `devenv /build`, /`clean`, `/rebuild` 또는 `/deploy` 명령의 일부로 사용해야 합니다.  
  
-   공백을 포함하는 문자열은 큰따옴표로 묶습니다.  
  
-   오류를 포함한 빌드에 대한 요약 정보는 **명령** 창 또는 `/out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `MySolution`의 `Debug` 솔루션 구성 내에 있는 `Debug` 프로젝트 빌드 구성을 사용하여 `CSharpConsoleApp` 프로젝트를 빌드합니다.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [/ProjectConfig(devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)   
 [/Build(devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Clean(devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Rebuild(devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Deploy(devenv.exe)](../../ide/reference/deploy-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
