---
title: 'How to: Troubleshoot Unsuccessful Project Upgrades | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: troubleshooting
f1_keywords:
- VisualStudio.SourceControl.CannotOpenFromSourceControlDSW
- vs.UpgradeProjectSolution.8.0
helpviewer_keywords:
- upgrading applications, Visual Studio
- upgrading projects [Visual Studio]
- projects [Visual Studio], upgrading
- Visual Studio Conversion Wizard
- Conversion wizard
ms.assetid: 842fe448-c044-4343-8eae-d81711cf48ba
caps.latest.revision: 31
author: kraigb
ms.author: kraigb
manager: jillfra
ms.openlocfilehash: 16232a72cd37f8d1d68760f032b6050e0bdf74c5
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300359"
---
# <a name="how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades"></a>방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

때때로 Visual Studio는 이전 버전의 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 프로젝트를 완전히 전환할 수 없습니다. If the tips in the following sections do not resolve your specific problem, you might be able to find more information on the TechNet [Wiki: Development Portal](https://go.microsoft.com/fwlink/?LinkId=254808).

## <a name="the-project-does-not-run-because-files-are-not-found"></a>The Project Does Not Run Because Files Are Not Found
 프로젝트 파일에는 F5를 누를 때 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]가 프로젝트를 실행하기 위해 사용하는 하드 코드된 파일이 포함되어 있습니다. These paths may include the location of devenv.exe and other required files. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]의 업그레이드 버전에서 이러한 파일의 경로는 변경이 가능할 수 있습니다.

#### <a name="to-resolve-incorrect-file-paths"></a>To resolve incorrect file paths

1. Open your project file in a text editor.

2. 올바르지 않을 수 있는 파일 경로의 탐색, 특히 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 버전 번호를 포함하는 경로입니다.

3. Modify incorrect file paths so that they point to the new targets.

## <a name="the-project-does-not-build-because-references-are-not-valid"></a>The Project Does Not Build Because References Are Not Valid
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]를 업그레이드 하는 경우 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]버전을 업그레이드할 수도 있습니다. 프로젝트에 최신 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전에서 중지된 참조가 포함되어 있는 경우 올바르게 해결할 수 없을 수 있습니다. This is especially likely for references that include version numbers, for example, `Microsoft.VisualStudio.Shell.Interop.8.0`.

 코드에 잘못된 참조가 많이 있는 경우 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]의 멀티 타기팅 기능을 사용하여 이전 버전의 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]를 대상하는 하는 것이 가장 쉬운 해결 방법일 수 있습니다.

#### <a name="to-resolve-incorrect-references"></a>잘못된 참조를 해결하려면

1. Open your project file in a text editor.

2. 프로젝트 속성을 엽니다.

3. 올바른 **대상 프레임워크** 값을 선택합니다. 또는 프로젝트 파일에서 `<TargetFrameworkVersion>` 요소의 값을 직접 수정할 수 있습니다.

   프로젝트를 업그레이드된 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전에서 실행하려면 프로젝트에 대한 참조를 업데이트하고 참조를 호출하는 `Imports` 또는 `Using` 문도 업데이트해야 합니다. IDE에서 프로젝트가 로드되는 경우 **솔루션 탐색기** 또는 **참조 관리자** 대화 상자를 사용하여 참조를 업데이트할 수 있습니다.

## <a name="see-also"></a>관련 항목:
 [/Upgrade (devenv.exe)](../ide/reference/upgrade-devenv-exe.md) [Converting to ASP.NET 4](https://msdn.microsoft.com/library/790147c6-36c1-41b5-a52d-30b9ccd2bd10)
