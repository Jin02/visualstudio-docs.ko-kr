---
title: 관리 코드에 대 한 정적 코드 분석
ms.date: 03/26/2018
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 38a2bce9e3343c4439eaf033ccfb8d6e58b01baa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540696"
---
# <a name="overview-of-static-code-analysis-for-managed-code-in-visual-studio"></a>Visual Studio에서 관리 되는 코드에 대 한 정적 코드 분석 개요

Visual Studio는 두 가지 방법으로 관리 되는 코드의 코드 분석을 수행할 수 있습니다: 사용 하 여 *FxCop* 자세한 최신와 관리 되는 어셈블리의 정적 분석 *Roslyn 분석기*합니다. 이 항목에서는 FxCop 정적 코드 분석을 설명 합니다. 코드 분석기를 사용 하 여 코드를 분석 하는 방법에 대 한 자세한 내용은 참조 하세요 [개요의 Roslyn 분석기](../code-quality/roslyn-analyzers-overview.md)합니다.

관리 코드에 대한 코드 분석에서는 관리되는 어셈블리를 분석하고, Microsoft .NET Framework 디자인 지침에 설정된 프로그래밍 및 디자인 규칙의 위반과 같은 어셈블리 관련 정보를 보고합니다.

분석 도구는 분석하는 동안 수행하는 검사를 경고 메시지로 나타냅니다. 경고 메시지는 관련 프로그래밍 및 디자인 문제를 식별하며 가능한 경우 문제 해결 방법에 대한 정보를 제공합니다.

> [!NOTE]
> Visual Studio에서.NET Core 및.NET Standard 프로젝트에 대 한 정적 코드 분석이 지원 되지 않습니다. Msbuild의 일부로.NET Core 또는.NET Standard 프로젝트에서 코드 분석을 실행 하는 경우 유사한 오류가 표시 됩니다 **오류: CA0055 : 에 대 한 플랫폼을 식별할 수 없습니다 \<your.dll >** 합니다. .NET Core 또는.NET Standard 프로젝트에서 코드를 분석 하려면 사용 하 여 [Roslyn 분석기](../code-quality/roslyn-analyzers-overview.md) 대신 합니다.

## <a name="ide-integrated-development-environment-integration"></a>IDE(통합 개발 환경) 통합

수동 또는 자동으로 프로젝트에서 코드 분석을 실행할 수 있습니다.

프로젝트를 빌드할 때마다 코드 분석을 실행 하려면 선택한 **빌드에 코드 분석 사용** 프로젝트의 속성 페이지. 자세한 내용은 [방법: 자동 코드 분석 사용 설정 및 해제](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)를 참조하세요.

프로젝트에 대해 수동으로 코드 분석을 실행, 메뉴 모음에서 선택 **분석** > **코드 분석 실행** > **에서 코드 분석 실행 \<프로젝트 >** 합니다.

## <a name="rule-sets"></a>규칙 집합

관리 코드에 대한 코드 분석 규칙은 [규칙 집합](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)으로 그룹화됩니다. Microsoft 표준 규칙 집합 중 하나를 사용 하거나 할 수 있습니다 [사용자 지정 규칙 집합 만들기](../code-quality/how-to-create-a-custom-rule-set.md) 를 특정 요구를 충족 합니다.

## <a name="suppress-warnings"></a>경고 표시 안 함

경고가 적용되지 않는 것으로 표시하면 유용한 경우가 많습니다. 이렇게 하면 경고를 조사한 다음 이를 표시하지 않거나 무시하도록 설정했다는 것을 개발자와 나중에 이 코드를 검토할 수 있는 다른 사람에게 알릴 수 있습니다.

경고 표시 안 함 소스 사용자 지정 특성을 통해 구현 됩니다. 경고를 표시하지 않으려면 다음 예제와 같이 소스 코드에 `SuppressMessage` 특성을 추가합니다.

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

자세한 내용은 [경고 표시 안 함](../code-quality/in-source-suppression-overview.md)합니다.

> [!NOTE]
> Visual Studio 2017 또는 Visual Studio 2019에 프로젝트를 마이그레이션하는 경우 많은 수의 코드 분석 경고를 사용 하 여 직면 갑자기 수 있습니다. 경고를 해결 하 고 생산성을 높이려는 바로 준비가 아닌 경우 *기준* 프로젝트의 분석 상태입니다. **분석** 메뉴에서 **코드 분석 실행 및 활성 문제를 표시 하지 않으려면**합니다.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 코드 분석 실행

조직에서 반드시 특정 정책에 따라 체크 인을 수행하려는 경우 특히 다음 정책을 따르는지 확인할 수 있습니다.

- 체크 인할 코드에 빌드 오류가 있습니다.

- 최신 빌드의 일부로 코드 분석을 실행 합니다.

체크 인 정책을 지정하여 위 사항을 확인할 수 있습니다. 자세한 내용은 [프로젝트 체크 인 정책 사용 하 여 코드 품질 향상](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)합니다.

## <a name="team-build-integration"></a>팀 빌드 통합

빌드 시스템의 통합된 기능을 사용하여 빌드 프로세스의 일부로 분석 도구를 실행할 수 있습니다. 자세한 내용은 [Azure 파이프라인](/azure/devops/pipelines/index?view=vsts)을 참조합니다.

## <a name="see-also"></a>참고자료

- [Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [방법: 자동 코드 분석 사용 설정 및 해제](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
