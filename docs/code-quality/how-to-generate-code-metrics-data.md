---
title: IDE 또는 명령줄에서 코드 메트릭 생성
ms.date: 11/02/2018
ms.topic: conceptual
helpviewer_keywords:
- code metrics data
- code metrics results
- code metrics [Visual Studio]
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37f208421079f77cadaf85556e00a8f8548c6182
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73188797"
---
# <a name="how-to-generate-code-metrics-data"></a>방법: 코드 메트릭 데이터 생성

다음 세 가지 방법으로 코드 메트릭 데이터를 생성할 수 있습니다.

- [FxCop 분석기](#fxcop-analyzers-code-metrics-rules) 를 설치 하 고 여기에 포함 된 4 개의 코드 메트릭 (유지 관리) 규칙을 사용 하도록 설정 합니다.

- Visual Studio 내에서 [ **분석**  > **코드 메트릭 계산** ](#calculate-code-metrics-menu-command) 메뉴 명령을 선택 합니다.

- C# 및 Visual Basic 프로젝트에 대한 [명령줄](#command-line-code-metrics)에서

## <a name="fxcop-analyzers-code-metrics-rules"></a>FxCop 분석기 코드 메트릭 규칙

[FxCopAnalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) 는 다음과 같은 몇 가지 코드 메트릭 [분석기](roslyn-analyzers-overview.md) 규칙을 포함 합니다.

- [CA1501](ca1501-avoid-excessive-inheritance.md)
- [CA1502](ca1502.md)
- [CA1505](ca1505-avoid-unmaintainable-code.md)
- [CA1506](ca1506-avoid-excessive-class-coupling.md)

이러한 규칙은 기본적으로 사용 하지 않도록 설정 되어 있지만 [**솔루션 탐색기**](use-roslyn-analyzers.md#set-rule-severity-from-solution-explorer) 또는 [규칙 집합](using-rule-sets-to-group-code-analysis-rules.md) 파일에서 사용 하도록 설정할 수 있습니다. 예를 들어 규칙 CA1502을 경고로 사용 하도록 설정 하려면. 규칙 집합 파일에 다음 항목이 포함 됩니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="Rules" Description="Rules" ToolsVersion="16.0">
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1502" Action="Warning" />
  </Rules>
</RuleSet>
```

### <a name="configuration"></a>Configuration

FxCop 분석기 패키지의 코드 메트릭 규칙에서 발생 하는 임계값을 구성할 수 있습니다.

1. 텍스트 파일을 만듭니다. 예를 들어 이름을 *CodeMetricsConfig*로 지정할 수 있습니다.

2. 다음 형식으로 텍스트 파일에 원하는 임계값을 추가 합니다.

   ```txt
   CA1502: 10
   ```

   이 예제에서 rule [CA1502](ca1502.md) 는 메서드의 순환 복잡성이 10 보다 클 때 발생 하도록 구성 됩니다.

3. Visual Studio의 **속성** 창 또는 프로젝트 파일에서 구성 파일의 빌드 작업을 [**additionalfiles**](../ide/build-actions.md#build-action-values)로 표시 합니다. 예를 들면,

   ```xml
   <ItemGroup>
     <AdditionalFiles Include="CodeMetricsConfig.txt" />
   </ItemGroup>
   ```

## <a name="calculate-code-metrics-menu-command"></a>코드 메트릭 계산 메뉴 명령

**분석**  > **코드 메트릭 계산** 메뉴를 사용 하 여 IDE에서 열려 있는 프로젝트 중 하나 또는 모두에 대해 코드 메트릭을 생성 합니다.

### <a name="generate-code-metrics-results-for-an-entire-solution"></a>전체 솔루션에 대 한 코드 메트릭 결과 생성

다음 방법 중 하나를 통해 전체 솔루션에 대 한 코드 메트릭 결과를 생성할 수 있습니다.

- 메뉴 모음에서 **분석  >  분석** 을 선택 하  > **솔루션에 대해** **코드 메트릭을 계산** 합니다.

- **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭 한 다음 **코드 메트릭 계산**을 선택 합니다.

- **코드 메트릭 결과** 창에서 **솔루션에 대 한 코드 메트릭 계산** 단추를 선택 합니다.

결과가 생성 되 고 **코드 메트릭 결과** 창이 표시 됩니다. 결과 세부 정보를 보려면 **계층** 열의 트리를 확장 합니다.

### <a name="generate-code-metrics-results-for-one-or-more-projects"></a>하나 이상의 프로젝트에 대 한 코드 메트릭 결과 생성

1. **솔루션 탐색기**에서 하나 이상의 프로젝트를 선택 합니다.

1. 메뉴 모음에서 **분석**  >   > **선택한 프로젝트에 대해** **코드 메트릭 계산** 을 선택 합니다.

결과가 생성 되 고 **코드 메트릭 결과** 창이 표시 됩니다. 결과 세부 정보를 보려면 **계층 구조**에서 트리를 확장 합니다.

::: moniker range="vs-2017"

> [!NOTE]
> **코드 메트릭 계산** 명령은 .net Core 및 .NET Standard 프로젝트에 대해 작동 하지 않습니다. .NET Core 또는 .NET Standard 프로젝트에 대 한 코드 메트릭을 계산 하려면 다음을 수행할 수 있습니다.
>
> - 대신 [명령줄](#command-line-code-metrics) 에서 코드 메트릭을 계산 합니다.
>
> - [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) 로 업그레이드

::: moniker-end

## <a name="command-line-code-metrics"></a>명령줄 코드 메트릭

명령줄에서 .NET Framework, .NET Core 및 .NET Standard 앱에 대 C# 한 Visual Basic 프로젝트에 대 한 코드 메트릭 데이터를 생성할 수 있습니다. 명령줄에서 코드 메트릭을 실행 하려면 [Microsoft CodeAnalysis. 메트릭 NuGet 패키지](#microsoftcodeanalysismetrics-nuget-package) 를 설치 하거나 직접 [메트릭과](#metricsexe) 실행 파일을 빌드합니다.

### <a name="microsoftcodeanalysismetrics-nuget-package"></a>Microsoft CodeAnalysis. 메트릭 NuGet 패키지

명령줄에서 코드 메트릭 데이터를 생성 하는 가장 쉬운 방법은 [Microsoft CodeAnalysis. 메트릭](https://www.nuget.org/packages/Microsoft.CodeAnalysis.Metrics/) NuGet 패키지를 설치 하는 것입니다. 패키지를 설치한 후 프로젝트 파일이 포함 된 디렉터리에서 `msbuild /t:Metrics`를 실행 합니다. 예를 들면,

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:29:57 PM.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics\Metrics.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:ClassLibrary3.Metrics.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'ClassLibrary3.Metrics.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

`/p:MetricsOutputFile=<filename>`를 지정 하 여 출력 파일 이름을 재정의할 수 있습니다. `/p:LEGACY_CODE_METRICS_MODE=true`를 지정 하 여 [레거시 스타일](#previous-versions) 코드 메트릭 데이터를 가져올 수도 있습니다. 예를 들면,

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics /p:LEGACY_CODE_METRICS_MODE=true /p:MetricsOutputFile="Legacy.xml"
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:31:00 PM.
The "MetricsOutputFile" property is a global property, and cannot be modified.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics.Legacy\Metrics.Legacy.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:Legacy.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'Legacy.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

### <a name="code-metrics-output"></a>코드 메트릭 출력

생성 된 XML 출력은 다음 형식을 사용 합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeMetricsReport Version="1.0">
  <Targets>
    <Target Name="ConsoleApp20.csproj">
      <Assembly Name="ConsoleApp20, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null">
        <Metrics>
          <Metric Name="MaintainabilityIndex" Value="100" />
          <Metric Name="CyclomaticComplexity" Value="1" />
          <Metric Name="ClassCoupling" Value="1" />
          <Metric Name="DepthOfInheritance" Value="1" />
          <Metric Name="LinesOfCode" Value="11" />
        </Metrics>
        <Namespaces>
          <Namespace Name="ConsoleApp20">
            <Metrics>
              <Metric Name="MaintainabilityIndex" Value="100" />
              <Metric Name="CyclomaticComplexity" Value="1" />
              <Metric Name="ClassCoupling" Value="1" />
              <Metric Name="DepthOfInheritance" Value="1" />
              <Metric Name="LinesOfCode" Value="11" />
            </Metrics>
            <Types>
              <NamedType Name="Program">
                <Metrics>
                  <Metric Name="MaintainabilityIndex" Value="100" />
                  <Metric Name="CyclomaticComplexity" Value="1" />
                  <Metric Name="ClassCoupling" Value="1" />
                  <Metric Name="DepthOfInheritance" Value="1" />
                  <Metric Name="LinesOfCode" Value="7" />
                </Metrics>
                <Members>
                  <Method Name="void Program.Main(string[] args)" File="C:\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
                    <Metrics>
                      <Metric Name="MaintainabilityIndex" Value="100" />
                      <Metric Name="CyclomaticComplexity" Value="1" />
                      <Metric Name="ClassCoupling" Value="1" />
                      <Metric Name="LinesOfCode" Value="4" />
                    </Metrics>
                  </Method>
                </Members>
              </NamedType>
            </Types>
          </Namespace>
        </Namespaces>
      </Assembly>
    </Target>
  </Targets>
</CodeMetricsReport>
```

### <a name="metricsexe"></a>메트릭과

NuGet 패키지를 설치 하지 않으려면 직접 *메트릭과* 실행 파일을 생성 하 고 사용할 수 있습니다. *메트릭 .exe* 실행 파일을 생성 하려면:

1. [Dotnet/roslyn](https://github.com/dotnet/roslyn-analyzers) 리포지토리를 복제 합니다.
2. 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 엽니다.
3. **Roslyn-분석기** 리포지토리의 루트에서 다음 명령을 실행 합니다. `Restore.cmd`
4. 디렉터리를 *src\Tools*로 변경 합니다.
5. 다음 명령을 실행 하 여 **메트릭의 .csproj** 프로젝트를 빌드합니다.

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   Ildasm.exe 라는 실행 파일은 리포지토리 루트 아래의 *artifacts\bin* 디렉터리에 생성 *됩니다.*

#### <a name="metricsexe-usage"></a>메트릭 .exe 사용

*Sc.exe*를 실행 하려면 프로젝트 또는 솔루션과 출력 XML 파일을 인수로 제공 합니다. 예를 들면,

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

#### <a name="legacy-mode"></a>레거시 모드

*레거시 모드*에서 *메트릭과* 빌드를 선택할 수 있습니다. 도구의 레거시 모드 버전은 [이전 버전의 도구에서 생성](#previous-versions)된 것과 더 가까운 메트릭 값을 생성 합니다. 또한 레거시 모드에서 *메트릭은* 이전 버전의 도구에서 코드 메트릭을 생성 한 것과 동일한 메서드 형식 집합에 대 한 코드 메트릭을 생성 합니다. 예를 들어 필드 및 속성 이니셜라이저의 코드 메트릭 데이터를 생성 하지 않습니다. 레거시 모드는 이전 버전과의 호환성을 위해 또는 코드 메트릭 번호를 기반으로 하는 코드 체크 인 게이트를 사용 하는 경우에 유용 합니다. 레거시 모드에서 *메트릭과* 를 빌드하는 명령은 다음과 같습니다.

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

자세한 내용은 [레거시 모드에서 코드 메트릭 생성 사용](https://github.com/dotnet/roslyn-analyzers/pull/1841)을 참조 하세요.

### <a name="previous-versions"></a>이전 버전

Visual Studio 2015에는 *wsdl.exe*라고도 하는 명령줄 코드 메트릭 도구가 포함 되어 있습니다. 이 이전 버전의 도구는 이진 분석 (즉, 어셈블리 기반 분석)을 수행 했습니다. 새 *메트릭과* 도구는 소스 코드를 대신 분석 합니다. 새 *메트릭과* 도구는 소스 코드 기반 이므로 명령줄 코드 메트릭 결과는 VISUAL Studio IDE 및 이전 버전의 *메트릭에*의해 생성 된 것과 다릅니다.

새 명령줄 코드 메트릭 도구는 솔루션과 프로젝트를 로드할 수 있는 한 소스 코드 오류가 있는 경우에도 메트릭을 계산 합니다.

#### <a name="metric-value-differences"></a>메트릭 값 차이

`LinesOfCode` 메트릭은 새로운 명령줄 코드 메트릭 도구에서 더 정확 하 고 안정적입니다. Codegen 차이가 없으며 도구 집합 또는 런타임이 변경 될 때 변경 되지 않습니다. 새 도구는 빈 줄 및 주석을 포함 하 여 실제 코드 줄 수를 계산 합니다.

`CyclomaticComplexity` 및 `MaintainabilityIndex`와 같은 다른 메트릭은 이전 버전의 *메트릭과*동일한 수식을 사용 하지만, 새 도구는 IL (중간 언어) 명령 대신 `IOperations` (논리적 원본 명령)의 수를 계산 합니다. 숫자는 Visual Studio IDE 및 이전 버전의 *메트릭에*의해 생성 된 것과 약간 다릅니다.

## <a name="see-also"></a>참조

- [코드 메트릭 결과 창 사용](../code-quality/working-with-code-metrics-data.md)
- [코드 메트릭 값](../code-quality/code-metrics-values.md)
