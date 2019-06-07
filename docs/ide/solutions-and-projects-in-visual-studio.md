---
title: 솔루션 및 프로젝트
ms.date: 10/05/2017
ms.topic: conceptual
f1_keywords:
- vs.addnewitem
- vs.addnewsolutionitem
- vs.openproject
- vs.addexistingitem
- vs.addexistingsolutionitem
- vs.environment.projects
- vs.environment.solutions
- VS.SolutionExplorer
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solutions [Visual Studio]
- projects [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 42a8dbc2fd9a6fc89b0be62271b048f8275a82b2
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432204"
---
# <a name="solutions-and-projects-in-visual-studio"></a>Visual Studio의 솔루션 및 프로젝트

이 문서에서는 Visual Studio의 *프로젝트* 및 *솔루션*의 개념에 대해 설명합니다. 새 프로젝트를 만드는 방법 및 **솔루션 탐색기** 도구 창에 대해서도 간략하게 설명합니다.

> [!NOTE]
> 이 토픽은 Windows의 Visual Studio에 적용됩니다. Mac용 Visual Studio는 [Mac용 Visual Studio의 프로젝트 및 솔루션](/visualstudio/mac/projects-and-solutions)을 참조하세요.

## <a name="projects"></a>프로젝트

Visual Studio에서 앱, 웹 사이트, 플러그인 등을 만들 때 *프로젝트*를 시작합니다. 논리적인 측면에서 프로젝트에는 실행 파일, 라이브러리 또는 웹 사이트로 컴파일되는 모든 소스 코드 파일, 아이콘, 이미지, 데이터 파일 등이 포함됩니다. 프로젝트에도 프로그램이 통신하는 여러 서비스 또는 구성 요소에 필요할 수 있는 컴파일러 설정 및 기타 구성 파일이 포함되어 있습니다.

> [!NOTE]
> Visual Studio에서 코드를 편집, 빌드 및 디버깅하기 위해 솔루션이나 프로젝트를 사용할 필요는 없습니다. Visual Studio에서 소스 파일이 들어 있는 폴더를 열고 편집을 시작하면 됩니다. 자세한 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)을 참조하세요.

프로젝트는 *.vbproj*, *.csproj* 또는 *.vcxproj*와 같은 확장명의 XML 파일로 정의됩니다. 이 파일에는 가상 폴더 계층과 프로젝트의 모든 항목에 대한 경로가 포함됩니다. 빌드 설정을 포함합니다.

> [!TIP]
> Visual Studio에서 프로젝트 파일의 콘텐츠를 보려면 먼저 **솔루션 탐색기**에서 프로젝트 이름을 선택하고 상황에 맞는 메뉴 또는 마우스 오른쪽 단추를 클릭하여 나타나는 메뉴에서 **언로드 프로젝트**를 선택하여 프로젝트를 언로드합니다. 그런 다음 상황에 맞는 메뉴를 다시 열고 **\<projectname\> 편집**을 선택합니다.

Visual Studio에서 프로젝트 파일은 **솔루션 탐색기**에서 프로젝트 내용 및 설정을 표시하는 데 사용됩니다. 프로젝트를 컴파일할 때 MSBuild 엔진은 프로젝트 파일을 사용하여 실행 파일을 만듭니다. 또한 다른 종류의 출력을 생성하는 프로젝트를 사용자 지정할 수 있습니다.

## <a name="solutions"></a>솔루션

프로젝트는 *솔루션*에 포함되어 있습니다. 이름과 달리 솔루션은 "답변"이 아닙니다. 이는 간단히 빌드 정보, Visual Studio 창 설정 및 특정 프로젝트와 관련이 없는 기타 파일과 함께 하나 이상의 관련된 프로젝트를 위한 컨테이너입니다. 솔루션은 고유한 형식을 가진 텍스트 파일( *.sln* 확장명)로 설명되고 직접 편집할 수 없습니다.

Visual Studio에서는 두 가지 파일 형식( *.sln* 및 *.suo*)을 사용하여 솔루션 관련 설정을 저장합니다.

|확장명|name|설명|
|---------------|----------|-----------------|
|.sln|Visual Studio 솔루션|솔루션에서 프로젝트, 프로젝트 항목 및 솔루션 항목을 구성합니다.|
|.suo|솔루션 사용자 옵션|중단점과 같은 사용자 수준 설정 및 사용자 지정을 저장합니다.|

## <a name="create-new-projects"></a>새 프로젝트 만들기

새 프로젝트를 만드는 가장 쉬운 방법은 특정 유형의 애플리케이션이나 웹 사이트에 대한 프로젝트 템플릿에서 시작하는 것입니다. 프로젝트 템플릿은 미리 생성된 코드 파일, 구성 파일, 자산 및 설정의 기본 집합으로 구성됩니다. 이러한 템플릿은 새 프로젝트(**파일** > **새로 만들기** > **프로젝트**)를 만드는 대화 상자에서 사용할 수 있습니다. 자세한 내용은 [Visual Studio에서 새 프로젝트 만들기](create-new-project.md) 및 [솔루션 및 프로젝트 만들기](../ide/creating-solutions-and-projects.md)를 참조하세요.

주로 특정 방식으로 프로젝트를 사용자 지정하는 경우에는 사용자 지정 프로젝트 템플릿을 만든 다음 새 프로젝트를 만드는 데 사용할 수 있습니다. 자세한 내용은 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)를 참조하세요.

새 프로젝트를 만들 때 기본적으로 *%USERPROFILE%\source\repos*에 저장됩니다. **도구** > **옵션** > **프로젝트 및 솔루션** > **위치** 아래의 **프로젝트 위치** 설정에서 이 위치를 변경할 수 있습니다. 자세한 내용은 [프로젝트 및 솔루션 페이지, 옵션 대화 상자](../ide/reference/projects-and-solutions-options-dialog-box.md)를 참조하세요.

## <a name="solution-explorer"></a>솔루션 탐색기

새 프로젝트를 만든 후에 **솔루션 탐색기** 를 사용하여 프로젝트와 솔루션 및 연결된 항목을 보고 관리할 수 있습니다. 다음 그림은 두 프로젝트가 포함되어 있으며, C# 솔루션을 사용하는 **솔루션 탐색기**를 보여 줍니다.

![솔루션 탐색기](../ide/media/vs2015_solution_explorer.png)

대부분의 메뉴 명령은 **솔루션 탐색기**에 있는 다양한 항목의 오른쪽 클릭 메뉴에서 사용할 수 있습니다. 이러한 명령에는 프로젝트 빌드, NuGet 패키지 관리, 참조 추가, 파일 이름 바꾸기, 테스트 실행 등이 포함됩니다. **솔루션 탐색기**의 위쪽에 있는 도구 모음에는 솔루션 보기를 폴더 보기로 전환하고 숨겨진 파일을 표시하고 모든 노드를 축소하는 등의 작업을 위한 단추가 있습니다.

ASP.NET Core 프로젝트의 경우에는 파일이 **솔루션 탐색기**에 중첩되는 방식을 사용자 지정할 수 있습니다. 자세한 내용은 [솔루션 탐색기에서 파일 중첩 사용자 지정](file-nesting-solution-explorer.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Visual Studio IDE](../get-started/visual-studio-ide.md)
- [프로젝트 및 솔루션(Mac용 Visual Studio)](/visualstudio/mac/projects-and-solutions)
- [프로젝트 항목 추가 및 제거(Mac 용 Visual Studio)](/visualstudio/mac/add-and-remove-project-items)
