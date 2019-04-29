---
title: 빌드 프로세스의 코드 생성
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- text templates, build tasks
- text templates, transforming by using msbuild
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 07f7c91c74961fa846abb70637f358de59d0eb94
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62424055"
---
# <a name="code-generation-in-a-build-process"></a>빌드 프로세스에서 코드 생성

[텍스트 변형](../modeling/code-generation-and-t4-text-templates.md) 의 일부로 호출할 수는 [빌드 프로세스](/azure/devops/pipelines/index) Visual Studio 솔루션. 이는 텍스트 변형에 대해 특수화된 빌드 작업입니다. T4 빌드 작업은 디자인 타임 텍스트 템플릿을 실행하고 전처리된 런타임 텍스트 템플릿을 컴파일합니다.

사용하는 빌드 엔진에 따라 빌드 작업에서 수행할 수 있는 몇 가지 작업이 다를 수 있습니다. 경우 텍스트 템플릿에서 Visual Studio API (EnvDTE)에 액세스할 수 있는지 Visual Studio에서 솔루션을 빌드할 때 합니다 [hostspecific = "true"](../modeling/t4-template-directive.md) 특성이 설정 되어 있습니다. 이것이 true 명령줄에서 솔루션을 빌드할 때 또는 Visual Studio를 통해 서버 빌드를 시작 합니다. 이러한 경우에는 MSBuild에서 빌드가 수행되고 다른 T4 호스트가 사용됩니다.

이 MSBuild에서 텍스트 템플릿을 빌드할 때 동일한 방식으로 프로젝트 파일 이름 등을 액세스할 수 없는지를 의미 합니다. 그러나 수 있습니다 [빌드 매개 변수를 사용 하 여 텍스트 템플릿 지시문 프로세서에 환경 정보를 전달할](#parameters)합니다.

## <a name="buildserver"></a> 컴퓨터 구성

개발 컴퓨터에서 빌드 작업을 사용 하려면 Visual Studio 용 모델링 SDK를 설치 합니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

하는 경우 [빌드 서버](/azure/devops/pipelines/agents/agents) 는 Visual Studio 설치 되지 않은 컴퓨터에서 실행 개발 컴퓨터에서 빌드 컴퓨터로 다음 파일을 복사 합니다. 대체에 대 한 가장 최근 버전 번호 ' *'.

- $(ProgramFiles)\MSBuild\Microsoft\VisualStudio\v*.0\TextTemplating

    - Microsoft.VisualStudio.TextTemplating.Sdk.Host.*.0.dll

    - Microsoft.TextTemplating.Build.Tasks.dll

    - Microsoft.TextTemplating.targets

- $(ProgramFiles)\Microsoft Visual Studio *.0\VSSDK\VisualStudioIntegration\Common\Assemblies\v4.0

    - Microsoft.VisualStudio.TextTemplating.*.0.dll

    - Microsoft.VisualStudio.TextTemplating.Interfaces.*.0.dll(여러 파일)

    - Microsoft.VisualStudio.TextTemplating.VSHost.*.0.dll

- $(ProgramFiles)\Microsoft Visual Studio *.0\Common7\IDE\PublicAssemblies\

    - Microsoft.VisualStudio.TextTemplating.Modeling.*.0.dll

## <a name="to-edit-the-project-file"></a>프로젝트 파일을 편집하려면

MSBuild의 기능 중 일부를 구성 하려면 프로젝트 파일을 편집 해야 합니다.

**솔루션 탐색기**, 선택 **언로드** 프로젝트의 마우스 오른쪽 단추로 클릭 합니다. 이렇게 하면 XML 편집기에서 .csproj 또는 .vbproj 파일을 편집할 수 있습니다.

편집을 마쳤으면 선택할 **다시 로드**합니다.

## <a name="import-the-text-transformation-targets"></a>텍스트 변형 대상 가져오기

.vbproj 또는 .csproj 파일에서 다음과 같은 줄을 찾습니다.

`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`

\- 또는 -

`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`

이 코드 뒤에 텍스트 템플릿 가져오기를 삽입합니다.

```xml
<!-- Optionally make the import portable across VS versions -->
  <PropertyGroup>
    <!-- Get the Visual Studio version: -->
    <VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">16.0</VisualStudioVersion>
    <!-- Keep the next element all on one line: -->
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>
  </PropertyGroup>

<!-- This is the important line: -->
  <Import Project="$(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets" />
```

## <a name="transform-templates-in-a-build"></a>빌드에서 템플릿 변형

변형 작업을 제어하기 위해 프로젝트 파일에 삽입할 수 있는 몇 가지 속성이 있습니다.

- 모든 빌드를 시작할 때 변환 작업을 실행합니다.

    ```xml
    <PropertyGroup>
        <TransformOnBuild>true</TransformOnBuild>
    </PropertyGroup>
    ```

- 예를 들어, 읽기 전용 파일은 체크 아웃되지 않기 때문에 파일을 덮어씁니다.

    ```xml
    <PropertyGroup>
        <OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>
    </PropertyGroup>
    ```

- 항상 모든 템플릿 변형:

    ```xml
    <PropertyGroup>
        <TransformOutOfDateOnly>false</TransformOutOfDateOnly>
    </PropertyGroup>
    ```

     기본적으로 T4 MSBuild 작업은 출력 파일이 명령 프로세서나 템플릿에 의해 이전에 읽혀진 파일이나 포함된 모든 파일 또는 해당 템플릿 파일보다 오래되었을 경우 출력 파일을 재생성합니다. 이는 템플릿과 출력 파일의 날짜만 비교하는 Visual Studio의 모든 템플릿 변형 명령을 사용하는 것보다 훨씬 더 강력한 종속성 테스트입니다.

프로젝트에서 텍스트 변형만 수행하려면 TransformAll 작업을 호출합니다.

`msbuild myProject.csproj /t:TransformAll`

특정한 텍스트 템플릿을 변형하려면 다음을 수행합니다.

`msbuild myProject.csproj /t:Transform /p:TransformFile="Template1.tt"`

변형 파일에서 와일드카드를 사용할 수 있습니다.

`msbuild dsl.csproj /t:Transform /p:TransformFile="GeneratedCode\**\*.tt"`

## <a name="source-control"></a>소스 제어

소스 제어 시스템과의 특정 기본 제공 통합은 없습니다. 그러나 예를 들어 생성된 파일을 체크 아웃하고 체크 인하기 위해 확장을 추가할 수 있습니다. 기본적으로 텍스트 변환 작업은 읽기 전용으로 표시된 파일을 덮어쓰지 않으며, 이러한 파일에 오류가 발생하면 해당 오류가 Visual Studio의 오류 목록에 로깅되고 작업은 실패합니다.

읽기 전용 파일을 덮어쓰도록 지정하려면 다음 속성을 삽입합니다.

`<OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>`

후처리 단계를 사용자 지정하지 않는 한 파일을 덮어쓸 때 경고가 오류 목록에 기록됩니다.

## <a name="customize-the-build-process"></a>빌드 프로세스를 사용자 지정

빌드 프로세스에서 다른 작업을 수행하기 전에 텍스트 변환이 수행됩니다. `$(BeforeTransform)` 및 `$(AfterTransform)` 속성을 설정하여 변환 전과 후에 호출되는 작업을 정의할 수 있습니다.

```xml
<PropertyGroup>
    <BeforeTransform>CustomPreTransform</BeforeTransform>
    <AfterTransform>CustomPostTransform</AfterTransform>
  </PropertyGroup>
  <Target Name="CustomPreTransform">
    <Message Text="In CustomPreTransform..." Importance="High" />
  </Target>
  <Target Name="CustomPostTransform">
    <Message Text="In CustomPostTransform..." Importance="High" />
  </Target>
```

`AfterTransform`에서 파일 목록을 참조할 수 있습니다.

- GeneratedFiles - 프로세스에서 쓴 파일의 목록입니다. 기존 읽기 전용 파일을 덮어쓴 파일의 경우 %(GeneratedFiles.ReadOnlyFileOverwritten)이 true입니다. 이러한 파일은 소스 제어에서 체크 아웃할 수 있습니다.

- NonGeneratedFiles - 덮어쓰지 않은 읽기 전용 파일의 목록입니다.

예를 들어, 생성된 파일을 체크 아웃하는 작업을 정의합니다.

## <a name="outputfilepath-and-outputfilename"></a>OutputFilePath 및 OutputFileName

MSBuild에서만 이러한 속성을 사용합니다. Visual Studio의 코드 생성에는 영향을 주지 않습니다. 이러한 속성은 생성된 출력 파일을 다른 폴더 또는 파일로 리디렉션합니다. 대상 폴더가 이미 있어야 합니다.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFilePath>MyFolder</OutputFilePath>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

리디렉션하기 유용한 폴더는 `$(IntermediateOutputPath).`입니다.

파일 이름을 지정하고 출력하는 경우 템플릿의 출력 지시문에 지정된 확장명보다 해당 이름이 우선적으로 적용됩니다.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFileName>MyOutputFileName.cs</OutputFileName>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

OutputFileName 이나 OutputFilePath를 지정 하는 단일 파일 생성기를 실행 하거나 모두 변형을 사용 하 여 VS에서 템플릿을 변형 하는 경우 권장 되지 않습니다. 변환을 실행하는 방법에 따라 서로 다른 파일 경로가 지정됩니다. 이는 매우 복잡할 수 있습니다.

## <a name="add-reference-and-include-paths"></a>참조를 추가 하 고 경로 포함 합니다.

템플릿에 참조된 어셈블리를 검색할 때 호스트에 기본 경로 집합이 있습니다. 이 집합에 추가하려면 다음을 수행합니다.

```xml
<ItemGroup>
    <T4ReferencePath Include="$(VsIdePath)PublicAssemblies\" />
    <!-- Add more T4ReferencePath items here -->
</ItemGroup>
```

포함 파일을 검색할 폴더를 설정하려면 세미콜론 구분 목록을 제공합니다. 일반적으로 기존 폴더 목록에 추가합니다.

```xml
<PropertyGroup>
    <IncludeFolders>
$(IncludeFolders);$(MSBuildProjectDirectory)\Include;AnotherFolder;And\Another</IncludeFolders>
</PropertyGroup>
```

## <a name="parameters"></a> 템플릿으로 빌드 컨텍스트 데이터 전달

프로젝트 파일에서 매개 변수 값을 설정할 수 있습니다. 예를 들어, 전달할 수 있습니다 [빌드합니다](../msbuild/msbuild-properties.md) 속성 및 [환경 변수](../msbuild/how-to-use-environment-variables-in-a-build.md):

```xml
<ItemGroup>
  <T4ParameterValues Include="ProjectFolder">
    <Value>$(ProjectDir)</Value>
    <Visible>false</Visible>
  </T4ParameterValues>
</ItemGroup>
```

텍스트 템플릿에서 `hostspecific`를 템플릿 지시문에 설정하십시오. 사용 된 [매개 변수](../modeling/t4-parameter-directive.md) 지시문 값을 가져오려면:

```
<#@template language="c#" hostspecific="true"#>
<#@ parameter type="System.String" name="ProjectFolder" #>
The project folder is: <#= ProjectFolder #>
```

지시문 프로세서에서 호출할 수 있습니다 [ITextTemplatingEngineHost.ResolveParameterValue](/previous-versions/visualstudio/visual-studio-2012/bb126369\(v\=vs.110\)):

```csharp
string value = Host.ResolveParameterValue("-", "-", "parameterName");
```

```vb
Dim value = Host.ResolveParameterValue("-", "-", "parameterName")
```

> [!NOTE]
> MSBuild를 사용하는 경우에만 `ResolveParameterValue`이 `T4ParameterValues`에서 데이터를 가져옵니다. Visual Studio를 사용하여 템플릿을 변형하는 경우 매개 변수에 기본값이 사용됩니다.

## <a name="msbuild"></a> 어셈블리의 프로젝트 속성을 사용 하 고 include 지시문

Visual Studio 매크로 같은 **$ (solutiondir)** MSBuild에서 작동 하지 않습니다. 대신 적절한 프로젝트 속성을 사용할 수 있습니다.

편집 하 *.csproj* 하거나 *.vbproj* 프로젝트 속성을 정의 하는 파일입니다. 이 예제에서는 라는 속성을 정의 **myLibFolder**:

```xml
<!-- Define a project property, myLibFolder: -->
<PropertyGroup>
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myLibFolder">
      <Value>$(myLibFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>
```

이제 assembly 및 Include 지시문에서 프로젝트 속성을 사용할 수 있습니다.

```
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>
<#@ include file="$(myLibFolder)\MyIncludeFile.t4" #>
```

이러한 지시문은 MSBuild와 Visual Studio 호스트에서 모두 T4parameterValues의 값을 가져옵니다.

## <a name="q--a"></a>Q&A

**빌드 서버에서 템플릿을 변형 해야 하는 이유 필자는 이미 내 코드를 체크 인하기 전에 Visual Studio에서 템플릿을 변환 합니다.**

포함된 파일을 또는 다른 파일 템플릿에서 읽기, 업데이트 하는 경우 Visual Studio 파일을 자동으로 변환 하지 않습니다. 빌드의 일부로 하면 템플릿을 변환 하는 모든 항목이 최신 상태입니다.

**다른 옵션은 무엇이 있습니다 텍스트 템플릿 변환에 대 한?**

- 합니다 [TextTransform 유틸리티](../modeling/generating-files-with-the-texttransform-utility.md) 명령 스크립트에서 사용할 수 있습니다. 대부분의 경우에서 MSBuild를 사용 하도록 쉽습니다.

- [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)

- [디자인 타임 텍스트 템플릿](../modeling/design-time-code-generation-by-using-t4-text-templates.md) Visual Studio에서 변환 됩니다.

- [런타임 텍스트 템플릿](../modeling/run-time-text-generation-with-t4-text-templates.md) 응용 프로그램에서 런타임에 변형 됩니다.

## <a name="see-also"></a>참고자료

::: moniker range="vs-2017"

- T4 MSbuild 템플릿이 훌륭한 지침 *%ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\msbuild\Microsoft\VisualStudio\v15.0\TextTemplating\Microsoft.TextTemplating.targets*

::: moniker-end

::: moniker range=">=vs-2019"

- T4 MSbuild 템플릿이 훌륭한 지침 *%ProgramFiles (x86) %\Microsoft Visual Studio\2019\Enterprise\msbuild\Microsoft\VisualStudio\v16.0\TextTemplating\Microsoft.TextTemplating.targets*

::: moniker-end

- [T4 텍스트 템플릿 작성](../modeling/writing-a-t4-text-template.md)
