---
title: 컴파일 빌드
ms.date: 07/14/2017
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 38d583553c0382598681ab3aa52ca3a41a27ed2c
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75585498"
---
# <a name="compile-and-build-in-visual-studio"></a>Visual Studio에서 컴파일 및 빌드

소스 코드를 빌드할 때 빌드 엔진에서 어셈블리 및 실행 가능한 애플리케이션을 만듭니다. 일반적으로 빌드 프로세스는 Windows, ASP.NET, 모바일 앱 등 여러 다양한 프로젝트 형식에서 매우 유사합니다. 빌드 프로세스는 C#, Visual Basic, C++ 및 F# 같은 프로그래밍 언어에서도 유사합니다.

코드를 자주 빌드하면 잘못된 구문, 맞춤법 오류가 있는 키워드 및 형식 불일치와 같은 컴파일 시간 오류를 빠르게 식별할 수 있습니다. 디버그 버전의 코드를 빌드하고 실행하면 논리 오류 및 의미 오류와 같은 런타임 오류도 찾아 해결할 수 있습니다.

성공적인 빌드를 위해서는 애플리케이션의 소스 코드에 올바른 구문이 포함돼 있어야 하고 라이브러리, 어셈블리 및 기타 구성 요소에 대한 모든 정적 참조를 확인해야 합니다. 애플리케이션 실행 파일이 생성되면 [디버깅 환경](../debugger/index.yml)과 다양한 수동/자동 테스트 환경 모두에서 해당 파일이 제대로 작동하는지 테스트하여 [코드 품질의 유효성을 검사](../test/improve-code-quality.md)할 수 있습니다. 애플리케이션이 완전히 테스트되면 고객에게 배포할 릴리스 버전을 컴파일할 수 있습니다. 이 프로세스에 대한 개요는 [연습: 애플리케이션 빌드](../ide/walkthrough-building-an-application.md)를 참조하세요.

Visual Studio IDE, MSBuild 명령줄 도구 및 Azure Pipelines와 같은 방법 중 하나를 사용하여 애플리케이션을 빌드할 수 있습니다.

| 빌드 방법 | 이점 |
| --- |--- | --- |
| IDE |- 즉시 빌드를 만들고 디버거에서 테스트할 수 있습니다.<br />- C++ 및 C# 프로젝트에 대해 다중 프로세서 빌드를 실행할 수 있습니다.<br />-   빌드 시스템의 다양한 측면을 사용자 지정할 수 있습니다. |
| MSBuild 명령줄| - Visual Studio를 설치하지 않고도 프로젝트를 빌드할 수 있습니다.<br />- 모든 프로젝트 형식에 대해 다중 프로세서 빌드를 실행할 수 있습니다.<br />-   빌드 시스템의 영역 대부분을 사용자 지정할 수 있습니다.|
| Azure Pipelines | - 지속적인 통합/지속적인 업데이트 파이프라인의 일부로 빌드 프로세스를 자동화할 수 있습니다.<br />- 모든 빌드에서 자동화된 테스트를 적용할 수 있습니다.<br />- 빌드 프로세스에 사실상 제한 없는 클라우드 기반 리소스를 사용할 수 있습니다.<br />- 빌드 워크플로를 수정하고 빌드 작업을 만들어 사용자 지정 수준이 높은 작업을 수행할 수 있습니다.|

이 섹션의 문서에는 IDE 기반 빌드 프로세스에 대한 자세한 내용이 나와 있습니다. 다른 방법에 대한 자세한 내용은 [MSBuild](../msbuild/msbuild.md) 및 [Azure Pipelines](/azure/devops/pipelines/index?view=vsts)를 각각 참조하세요.

> [!NOTE]
> 이 토픽은 Windows용 Visual Studio에만 적용됩니다. Mac용 Visual Studio는 [Mac용 Visual Studio에서 컴파일 및 빌드](/visualstudio/mac/compiling-and-building)를 참조하세요.

## <a name="overview-of-building-from-the-ide"></a>IDE에서 빌드하는 방법에 대한 개요

사용자가 프로젝트를 만드는 경우 Visual Studio에서 해당 프로젝트와 프로젝트가 포함된 솔루션에 대해 기본 빌드 구성을 만듭니다.  이러한 구성은 솔루션 및 프로젝트를 빌드하고 배포하는 방법을 정의합니다. 특히 프로젝트 구성은 대상 플랫폼(예: Windows 또는 Linux) 및 빌드 형식(예: 디버그 또는 릴리스)에 대해 고유합니다. 사용자는 원하는 방식으로 이러한 구성을 편집할 수도 있고, 필요에 따라 고유한 구성을 만들 수도 있습니다.

IDE 내에서 빌드하는 방법에 대한 가장 기본적인 개요는 [연습: 애플리케이션 빌드](walkthrough-building-an-application.md)를 참조하세요.

그런 다음 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](building-and-cleaning-projects-and-solutions-in-visual-studio.md)를 참조하여 프로세스에 대해 수행할 수 있는 다양한 측면의 사용자 지정 작업에 대해 알아보세요. 사용자 지정 작업으로는 [출력 디렉터리 변경](how-to-change-the-build-output-directory.md), [사용자 지정 빌드 이벤트 지정](specifying-custom-build-events-in-visual-studio.md), [프로젝트 종속성 관리](how-to-create-and-remove-project-dependencies.md), [빌드 로그 파일 관리](how-to-view-save-and-configure-build-log-files.md) 및 [컴파일러 경고 표시 안 함](how-to-suppress-compiler-warnings.md)이 있습니다.

다음과 같은 다른 다양한 작업도 알아볼 수 있습니다.
- [빌드 구성 이해](understanding-build-configurations.md)
- [빌드 플랫폼 이해](understanding-build-platforms.md)
- [프로젝트 및 솔루션 속성 관리](managing-project-and-solution-properties.md)
- [C#](how-to-specify-build-events-csharp.md) 및 [Visual Basic](how-to-specify-build-events-visual-basic.md)에서 빌드 이벤트 지정
- [빌드 옵션 설정](reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [병렬로 여러 프로젝트 빌드](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)

## <a name="see-also"></a>참조

- [웹 사이트 프로젝트 빌드(컴파일)](https://msdn.microsoft.com/Library/a9cbb88c-8fff-4c67-848b-98fbfd823193)
- [컴파일 및 빌드(Mac용 Visual Studio)](/visualstudio/mac/compiling-and-building)
