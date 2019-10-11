---
title: EditorConfig와 분석기 비교
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12e6681490c6c933369d3fef064ec88f240e3a99
ms.sourcegitcommit: b23d73c86ec7720c4cd9a58050860bc559623a3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72172767"
---
# <a name="code-analysis-faq"></a>코드 분석 FAQ

이 페이지에는 Visual Studio의 .NET Compiler Platform 기반 코드 분석에 대 한 몇 가지 질문과 대답을 포함 합니다.

## <a name="code-analysis-versus-editorconfig"></a>코드 분석 및 EditorConfig

**Q**: 코드 스타일을 확인 하는 데 코드 분석 또는 EditorConfig를 사용 해야 하나요?

**A**: 코드 분석 및 EditorConfig 파일은 직접 작동 합니다. [EditorConfig 파일](../ide/editorconfig-code-style-settings-reference.md) 또는 [텍스트 편집기 옵션](../ide/code-styles-and-code-cleanup.md) 페이지에서 코드 스타일을 정의 하는 경우 실제로는 Visual Studio에 기본 제공 되는 코드 분석기를 구성 하는 것입니다. EditorConfig 파일은 분석기 규칙을 사용 하거나 사용 하지 않도록 설정 하는 데 사용할 수 있으며 [FxCop](configure-fxcop-analyzers.md)분석기와 같은 일부 NuGet analyzer 패키지를 구성 하는 데에도 사용할 수 있습니다.

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig와 규칙 집합 비교

**Q**: 규칙 집합이 나 EditorConfig 파일을 사용 하 여 분석기를 구성 해야 하나요?

**A**: 규칙 집합 및 EditorConfig 파일은 공존할 수 있으며 분석기를 구성 하는 데 사용할 수 있습니다. EditorConfig 파일 및 규칙 집합을 사용 하 여 규칙을 사용 하거나 사용 하지 않도록 설정 하 고 심각도를 설정할 수 있습니다.

그러나 EditorConfig 파일은 규칙을 구성 하는 또 다른 방법을 제공 합니다.

- FxCop 분석기의 경우 EditorConfig 파일을 사용 하 [여 분석할 코드 형식을 정의할](fxcop-analyzer-options.md)수 있습니다.
- Visual Studio에 기본 제공 되는 코드 스타일 분석기의 경우 EditorConfig 파일을 사용 하 여 코드 베이스에 대해 [기본 설정 된 코드 스타일을 정의할](../ide/editorconfig-code-style-settings-reference.md) 수 있습니다.

규칙 집합 및 EditorConfig 파일 외에도 일부 분석기는 C# 및 VB 컴파일러에 대 한 [추가 파일로](../ide/build-actions.md#build-action-values) 표시 된 텍스트 파일을 사용 하 여 구성 됩니다.

> [!NOTE]
> - EditorConfig 파일은 Visual Studio 2019 버전 16.3 이상에서 규칙을 사용 하도록 설정 하 고 심각도를 설정 하는 데만 사용할 수 있습니다.
> - EditorConfig 파일은 레거시 분석을 구성 하는 데 사용할 수 없지만 규칙 집합은 사용할 수 있습니다.

## <a name="code-analysis-in-ci-builds"></a>CI 빌드에서 코드 분석

**Q**: CI (연속 통합) 빌드에서 .NET Compiler Platform 기반 코드 분석이 작동 하나요?

**A**: 예. NuGet 패키지에서 설치 된 분석기의 경우 이러한 규칙은 CI 빌드 중을 포함 하 여 [빌드 시에 적용](roslyn-analyzers-overview.md#build-errors)됩니다. CI 빌드에서 사용 되는 분석기는 규칙 집합과 EditorConfig 파일의 규칙 구성을 모두 고려 합니다. 현재 Visual Studio에 기본 제공 되는 코드 분석기는 NuGet 패키지로 사용할 수 없으므로 이러한 규칙은 CI 빌드에서 시행 되지 않습니다.

## <a name="ide-analyzers-versus-stylecop"></a>IDE 분석기와 StyleCop 비교

**Q**: Visual Studio IDE 코드 분석기와 StyleCop 분석기 간의 차이점은 무엇 인가요?

**A**: Visual Studio IDE에는 코드 스타일 및 품질 문제를 모두 검색 하는 기본 제공 분석기가 포함 되어 있습니다. 이러한 규칙은 도입 된 새로운 언어 기능을 사용 하 고 코드의 유지 관리 효율성을 향상 시키는 데 도움이 됩니다. IDE 분석기는 Visual Studio 릴리스 마다 지속적으로 업데이트 됩니다.

[StyleCop 분석기](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) 는 코드에서 스타일 일관성을 검사 하는 NuGet 패키지로 설치 된 타사 분석기입니다. 일반적으로 StyleCop 규칙을 사용 하 여 코드 베이스에 대 한 특정 스타일을 권장 하지 않고 개인 기본 설정을 지정할 수 있습니다.

## <a name="code-analyzers-versus-legacy-analysis"></a>코드 분석기와 레거시 분석 비교

**Q**: 레거시 분석과 .NET Compiler Platform 기반 코드 분석의 차이점은 무엇 인가요?

**A**: .NET Compiler Platform 기반 코드 분석은 컴파일 중에 소스 코드를 실시간으로 분석 하는 반면 레거시 분석은 빌드가 완료 된 후 이진 파일을 분석 합니다. 자세한 내용은 [.NET Compiler Platform 기반 분석 및 레거시 분석](roslyn-analyzers-overview.md#source-code-analysis-versus-legacy-analysis) 및 [FxCop 분석기 FAQ](fxcop-analyzers-faq.md)를 참조 하세요.

## <a name="treat-warnings-as-errors"></a>경고를 오류로 처리

**Q**: 내 프로젝트는 빌드 옵션을 사용 하 여 경고를 오류로 처리 합니다. 레거시 분석에서 원본 코드 분석으로 마이그레이션한 후 모든 코드 분석 경고가 이제 오류로 표시 됩니다. 이를 방지 하려면 어떻게 해야 하나요?

**A**: 코드 분석 경고가 오류로 처리 되지 않도록 하려면 다음 단계를 수행 합니다.

  1. 다음 콘텐츠를 사용 하 여 props 파일을 만듭니다.

     ```xml
     <Project>
        <PropertyGroup>
           <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
        </PropertyGroup>
     </Project>
     ```

  2. .Csproj 또는 .vbproj 프로젝트 파일에 줄을 추가 하 여 이전 단계에서 만든 props 파일을 가져옵니다. 이 줄은 FxCop 분석기. props 파일을 가져오는 모든 줄 앞에 배치 해야 합니다. 예를 들어, props 파일 이름이 codeanalysis. props 인 경우:

     ```xml
     ...
     <Import Project="..\..\codeanalysis.props" Condition="Exists('..\..\codeanalysis.props')" />
     <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.5\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.5\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
     ...
     ```

## <a name="see-also"></a>참조

- [분석기 개요](roslyn-analyzers-overview.md)
- [EditorConfig에 대한 .NET 코딩 규칙 설정](../ide/editorconfig-code-style-settings-reference.md)
