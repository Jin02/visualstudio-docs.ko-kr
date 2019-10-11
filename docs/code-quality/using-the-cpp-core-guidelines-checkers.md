---
title: C++ Core Guidelines를 이용한 코드검사 사용
ms.date: 08/14/2018
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: markl
dev_langs:
- CPP
ms.openlocfilehash: 57c8d6daf75987bfb5c6a6642b89f198693a5dce
ms.sourcegitcommit: 535ef05b1e553f0fc66082cd2e0998817eb2a56a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72018412"
---
# <a name="use-the-c-core-guidelines-checkers"></a>C++ Core Guidelines 검사기 사용

C++ Core Guidelines는 이식 가능한 집합 지침, 규칙 및 C++ 전문가가 및 디자이너에서 생성 하는 C++에서 코딩 하는 방법에 대 한 모범 사례입니다. Visual Studio는 현재 C++용 코드 분석 도구의 일부로 이러한 규칙의 하위 집합을 지원합니다. 핵심 지침 체커는 visual Studio 2017 및 Visual Studio 2019에 기본적으로 설치 되며, [Visual studio 2015 용 NuGet 패키지로 제공](#vs2015_corecheck)됩니다.

## <a name="the-c-core-guidelines-project"></a>C++ Core Guidelines 프로젝트

C++ Core Guidelines를 안전 하 게 하 고 효과적으로 최신 C++를 사용 하는 데는 Bjarne Stroustrup 등에서 생성 합니다. 지침은 정적 형식 안전성 및 리소스 안전성을 강조 합니다. 이는 언어에서 가장 오류가 발생 하기 쉬운 부분을 제거 하거나 최소화 하는 방법을 파악 하 고 안정적인 방식으로 코드를 더 간단 하 고 더 효율적으로 만드는 방법을 제안 합니다. 이러한 지침 표준 C++ Foundation에서 유지 됩니다. 자세한 내용은 설명서를 참조 [C++ Core Guidelines](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines), C++ Core Guidelines 설명서 프로젝트 파일에 액세스 하고 [GitHub](https://github.com/isocpp/CppCoreGuidelines)합니다.

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>코드 분석에서 C++ Core Check 지침을 사용 하도록 설정
프로젝트에 대 한 **속성 페이지** 대화 상자의 **코드 분석** 섹션에서 **빌드 시 코드 분석 사용** 확인란을 선택 하 여 프로젝트에 대해 코드 분석을 사용 하도록 설정할 수 있습니다.

![코드 분석 일반 설정에 대한 속성 페이지](media/cppcorecheck_codeanalysis_general.png)

C++ Core Check 규칙의 하위 집합 코드 분석 사용 하도록 설정 하는 경우 기본적으로 실행 되는 Microsoft 네이티브 권장 규칙 집합에 포함 됩니다. 추가 핵심 검사 규칙을 사용 하도록 설정 하려면 드롭다운을 클릭 하 고 포함 하려는 규칙 집합을 선택 합니다.

![추가 C++ Core Check 규칙 집합에 대 한 드롭다운](media/cppcorecheck_codeanalysis_extensions.png)

## <a name="examples"></a>예제
C++ Core Check 규칙을 찾을 수 있는 문제 중 일부는 다음과 같습니다.

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

이 예제에서는 C++ Core Check 규칙을 찾을 수 있는 경고의 일부를 보여 줍니다.

- C26494은 규칙 유형입니다. 5: 항상 개체를 초기화 합니다.

- C26485는 규칙 범위입니다. 3: 배열-포인터 감소를 하지 않습니다.

- C26481는 규칙 범위입니다. 1: 포인터 산술 연산을 사용 하지 마세요. 대신 `span`를 사용하세요.

C++ Core Check 코드 분석 규칙 집합은를 설치 하 고이 코드를 컴파일할 때 사용 하도록 설정 하는 경우 처음 두 개의 경고를 출력 하지만 세 번째 표시 되지 않습니다. 예제 코드의 빌드 출력은 다음과 같습니다.

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Core Guidelines 향상하고 안전한 코드를 작성할 수 있도록 하는 것입니다. 그러나 규칙이 나 프로필을 적용 하지 않아야 하는 인스턴스가 있는 경우 코드에서 직접 표시 하지 않는 것이 쉽습니다. 사용할 수는 `gsl::suppress` 특성을 검색 하 고 다음 코드 블록에서 규칙의 위반을 보고에서 C++ Core Check를 유지 합니다. 개별 문을 표시 하 여 특정 규칙을 표시 하지 않을 수 있습니다. 작성하여 전체 범위 프로필도 억제할 수 있습니다 `[[gsl::suppress(bounds)]]` 특정 규칙 수를 포함 하지 않고 있습니다.

## <a name="supported-rule-sets"></a>지원 되는 규칙 집합
새 규칙은 C++ 핵심 지침 검사기에 추가 되 면 기존 코드에 대 한 생성 되는 경고 수가 늘어날 수 있습니다. 미리 정의 된 규칙 집합을 사용 하 여 사용할 규칙의 종류를 필터링 할 수 있습니다.
대부분의 규칙에 대 한 참조 항목은 [Visual Studio C++ Core 확인 참조](code-analysis-for-cpp-corecheck.md)합니다.

Visual Studio 2017 버전 15.3에서 지원 되는 규칙 집합은 다음과 같습니다.
- **소유자 포인터 규칙** [ C++ 은 핵심 지침에서 Owner @ no__t-2t > 관련 된 리소스 관리 검사를](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)적용 합니다.

- **Const 규칙** 적용 [C++ Core Guidelines의 const 관련 검사](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)합니다.

- **원시 포인터 규칙** 적용 [리소스 관리 검사 C++ Core Guidelines에서 원시 관련이 포인터](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)합니다.

- **고유 포인터 규칙** 적용 [C++ Core Guidelines에서 고유 포인터 의미 체계를 사용 하는 형식 관련 리소스 관리 검사](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)합니다.

- **범위 규칙** 적용 된 [프로필은 C++ Core Guidelines의 범위](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)합니다.

- **형식 규칙** 적용 된 [프로필은 C++ Core Guidelines의 입력](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)합니다.

**Visual Studio 2017 버전 15.5**:

- **클래스 규칙** 특수 멤버 함수 및 가상 사양의 적절 한 사용에 초점을 맞춘 몇 가지 규칙입니다. [클래스 및 클래스 계층 구조](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)에 권장 되는 검사의 하위 집합입니다.
- **동시성 규칙** 잘못 선언 된 가드 개체를 catch 하는 단일 규칙 자세한 내용은 [concurrency와 관련 된 지침](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)을 참조 하세요.
- **선언 규칙** [인터페이스 지침](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) 의 몇 가지 규칙은 전역 변수를 선언 하는 방법에 중점을 둡니다.
- **함수 규칙** @No__t-1 지정자를 도입 하는 데 도움이 되는 두 가지 검사입니다. 이는 [clear 함수 디자인 및 구현](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)에 대 한 지침의 일부입니다.
- **공유 포인터 규칙** [리소스 관리](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) 지침 적용의 일부로 공유 포인터가 함수로 전달 되거나 로컬로 사용 되는 방법과 관련 된 몇 가지 규칙을 추가 했습니다.
- **스타일 규칙** 차단을 [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)를 사용 하는 것은 간단 하지만 중요한 검사입니다. 이 코딩 스타일 및 식과 C++에서 문을 사용 하 여 개선 하는 데 첫 번째 단계입니다.

**Visual Studio 2017 버전 15.6**:

- **산술 규칙** 산술 [오버플로](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [부호 없는 서명 된 작업](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned) 및 [비트 조작을](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)검색 하는 규칙입니다.

경고를 하나 또는 몇 개의 그룹 으로만 제한 하도록 선택할 수 있습니다. **네이티브 최소** 하 고 **네이티브 권장** 집합 기타 PREfast 검사 하는 것 외에도 C++ Core Check 규칙을 포함 하는 규칙입니다. 사용 가능한 규칙 집합을 보려면 프로젝트 속성 대화 상자를 열고 **코드 Analysis\General**를 선택한 다음 **규칙 집합** 콤보 상자에서 드롭다운을 열고 **여러 규칙 집합 선택**을 선택 합니다. Visual Studio에서 규칙 집합을 사용 하는 방법에 대 한 자세한 내용은 [규칙 집합을 사용 하 여 코드 분석 규칙 그룹화](using-rule-sets-to-group-code-analysis-rules.md)를 참조 하세요.

## <a name="macros"></a>매크로

C++ 핵심 지침 검사기 전체 범주의 코드에서 경고를 표시 하지 않으려면 쉽게 해 주는 매크로 정의 하는 헤더 파일에 포함 되어 있습니다.

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

이러한 매크로는 규칙 집합에 해당 하며 공백으로 구분 된 경고 번호 목록으로 확장 됩니다. 적절 한 pragma 구문을 사용 하 여 프로젝트 또는 코드 섹션에 대 한 유용한 규칙 집합을 구성할 수 있습니다. 다음 예제에서 코드 분석은 누락 된 상수 한정자에 대해서만 경고를 표시 합니다.

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>특성

Microsoft Visual C++ 컴파일러는 특성을 표시 하지 않으려면는 GSL 지원을 제한 합니다. 식 및 함수 내에서 블록 문에 대한 경고를 표시 하지 않으려면 사용할 수 있습니다.

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppress-analysis-by-using-command-line-options"></a>명령줄 옵션을 사용 하 여 분석 표시 안 함

#Pragmas 대신 파일의 속성 페이지에서 명령줄 옵션을 사용 하 여 프로젝트 또는 단일 파일에 대 한 경고를 표시 하지 않을 수 있습니다. 예를 들어 파일에 대해 26400 경고를 사용 하지 않도록 설정 하려면 다음을 수행 합니다.

1. 에서 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**

2. 선택 **속성 | C/C++ | 명령줄**

3. **추가 옵션** 창에서 `/wd26400`을 추가 합니다.

명령줄 옵션을 사용하여 일시적으로 파일에 대한 모든 코드 분석을 사용 하지 않도록 지정하여 `/analyze-`입니다. 이렇게 하면 ' */analyze '를 '/analyze-'로 재정의*하는 경고 D9025 생성 되며 나중에 코드 분석을 다시 사용 하도록 설정 하는 것을 알려 줍니다.

## <a name="corecheck_per_file"></a>특정 프로젝트 C++ 파일에서 핵심 지침 검사기 사용

때로는 포커스가 있는 코드 분석을 수행 하 고 여전히 Visual Studio IDE를 사용 하는 것이 유용할 수 있습니다. 다음 샘플 시나리오를 사용 하 여 빌드 시간을 절약 하 고 결과를 보다 쉽게 필터링 할 수 있습니다.

1. 명령 셸에서 `esp.extension` 및 `esp.annotationbuildlevel` 환경 변수를 설정 합니다.
2. 이러한 변수를 상속 하려면 명령 셸에서 Visual Studio를 엽니다.
3. 프로젝트를 로드 하 고 해당 속성을 엽니다.
4. 코드 분석을 사용 하도록 설정 하 고, 적절 한 규칙 집합을 선택 하지만 코드 분석 확장을 사용 하지 않습니다.
5. C++ 핵심 지침 검사기를 사용 하 여 분석 하 고 해당 속성을 열고 파일이 있는 위치로 이동 합니다.
6. **C/C++\ 명령줄 옵션** 을 선택 하 고 `/analyze:plugin EspXEngine.dll`를 추가 합니다.
7. 미리 컴파일된 헤더 (**C/C++\ 미리 컴파일된 헤더**)를 사용 하지 않도록 설정 합니다. 확장 엔진이 미리 컴파일된 헤더 (PCH)에서 내부 정보를 읽으려고 할 수 있으므로이 작업이 필요 합니다. PCH가 기본 프로젝트 옵션으로 컴파일된 경우에는 호환 되지 않습니다.
8. 프로젝트를 다시 빌드합니다. 모든 파일에서 일반적인 PREFast 검사를 실행 해야 합니다. 기본적으로 C++ 핵심 지침 검사기를 사용할 수 없으므로 사용 하도록 구성 된 파일에만 실행 해야 합니다.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Visual Studio 외부에서 C++ 핵심 지침 검사기를 사용 하는 방법

자동화 된 빌드에 C++ Core Guidelines 검사를 사용할 수 있습니다.

### <a name="msbuild"></a>MSBuild
네이티브 코드 분석 검사기 (PREfast)는 사용자 지정 대상 파일을 통해 MSBuild 환경에 통합 됩니다. 프로젝트 속성을 사용하여 사용 하도록 설정 하 고 (PREfast 기반)는 C++ 핵심 지침 검사기를 추가할 수 있습니다.

```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```

Microsoft .Cpp .targets 파일을 가져오기 전에 이러한 속성을 추가 해야 합니다. 특정 규칙 집합을 선택 하거나 사용자 지정 규칙 집합을 만들거나 다른 PREfast 검사를 포함 하는 기본 규칙 집합을 사용할 수 있습니다.

와 동일한 방식으로 사용하여 C++ Core Checker 지정 된 파일에 대해서만 실행할 수 있습니다 [앞에서 설명한](#corecheck_per_file), 하지만 MSBuild 파일을 사용 합니다. @No__t-0 항목을 사용 하 여 환경 변수를 설정할 수 있습니다.

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

프로젝트 파일을 수정 하지 않으려는 경우 명령줄에서 속성을 전달할 수 있습니다.

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>비 MSBuild 프로젝트

MSBuild를 사용 하지 않는 빌드 시스템을 사용 하는 경우 검사기를 계속 실행할 수 있지만 코드 분석 엔진 구성의 내부에 대해 잘 알고 있어야 합니다. 이러한 내부는 나중에 지원 되지 않을 수도 있습니다.

몇 가지 환경 변수를 설정하고 컴파일러에 대 한 적절 한 명령줄 옵션을 사용해야 합니다. 컴파일러에 대한 특정 경로 대한 검색, 디렉터리 등을 포함할 필요가 없습니다 있도록 "네이티브 도구 명령 프롬프트" 환경에서 작동 하는 것이 좋습니다.

1. **환경 변수**
   - `set esp.extensions=cppcorecheck.dll` 이 C++ Core Guidelines 모듈을 로드 하도록 엔진에 지시 합니다.
   - `set esp.annotationbuildlevel=ignore`은 SAL 주석을 처리 하는 논리를 사용 하지 않도록 설정 합니다. 주석에서 C++ 핵심 지침 검사기, 코드 분석에 영향을 주지 아직 처리 시간이 (경우에 따라 긴 시간). 이 설정은 선택 사항 이지만 매우 권장 됩니다.
   - `set caexcludepath=%include%` 표준 헤더에서 발생 하는 경고를 사용 하지 않도록 설정 하는 것이 좋습니다. 여기에 경로를 더 추가할 수 있습니다. 예를 들어 프로젝트의 공용 헤더에 대 한 경로를 추가할 수 있습니다.
2. **명령줄 옵션**
   - `/analyze`은 코드 분석을 사용 하도록 설정 합니다 (/analyze: only 및/analyze: quiet를 사용 하는 경우에도 사용).
   - `/analyze:plugin EspXEngine.dll`이 옵션은 코드 분석 확장 엔진을 PREfast 로드 합니다. 이 엔진을 C++ 핵심 지침 검사기를 차례로 로드합니다.

## <a name="use-the-guideline-support-library"></a>지침 지원 라이브러리 사용
지침 지원 라이브러리는 핵심 지침을 따르는 데 도움이 되도록 설계 되었습니다. GSL에는 오류가 발생 하기 쉬운 구문을 보다 안전한 대체 항목으로 바꿀 수 있는 정의가 포함 되어 있습니다. 예를 들어 매개 변수 `T*, length` 쌍을 `span<T>` 형식으로 바꿀 수 있습니다. GSL은 [http://www.nuget.org/packages/Microsoft.Gsl](http://www.nuget.org/packages/Microsoft.Gsl)에서 사용할 수 있습니다. 라이브러리는 오픈 소스 이므로 소스를 보거나 의견을 올리거나 참가할 수 있습니다. [@No__t-1](https://github.com/Microsoft/GSL)에서 프로젝트를 찾을 수 있습니다.

## <a name="vs2015_corecheck"></a>Visual Studio C++ 2015 프로젝트의 핵심 검사 지침 사용

Visual Studio 2015를 사용 하는 경우 C++ Core Check 코드 분석 규칙 집합 기본적으로 설치 되지 않습니다. Visual Studio 2015의 C++ Core Check 코드 분석 도구를 사용 하려면 먼저 몇 가지 추가 단계를 수행 해야 합니다. Microsoft에서는 Nuget 패키지를 사용 하 여 Visual Studio 2015 프로젝트에 대 한 지원을 제공 합니다. 패키지 이름은 CppCoreCheck입니다 .이 패키지는 [http://www.nuget.org/packages/Microsoft.CppCoreCheck](http://www.nuget.org/packages/Microsoft.CppCoreCheck)에서 사용할 수 있습니다. 이 패키지에는 Visual Studio 2015 이상 업데이트 1이 설치 되어 있어야 합니다.

또한 패키지는 다른 패키지를 종속성으로 설치 합니다 .이는 헤더 전용의 GSL (지침 지원 라이브러리)입니다. GSL는 [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL)의 GitHub 에서도 사용할 수 있습니다.

코드 분석 규칙 로드 되는 방식으로 인해 Visual Studio 2015 내에서 확인 하려는 각 C++ 프로젝트로 Microsoft.CppCoreCheck NuGet 패키지를 설치 해야 합니다.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015에서 프로젝트에 CppCoreCheck 패키지를 추가 하려면

1. **솔루션 탐색기**에서 패키지를 추가 하려는 솔루션의 프로젝트에 대 한 상황에 맞는 메뉴를 마우스 오른쪽 단추로 클릭 하 여 엽니다. Nuget 패키지 **관리** 를 선택 하 여 **nuget 패키지 관리자**를 엽니다.

2. **NuGet 패키지 관리자** 창에서 CppCoreCheck를 검색 합니다.

    ![Nuget 패키지 관리자 창에 CppCoreCheck 패키지 표시](../code-quality/media/cppcorecheck_nuget_window.png)

3. CppCoreCheck 패키지를 선택한 후 **설치** 단추를 선택 하 여 프로젝트에 규칙을 추가 합니다.

   NuGet 패키지는 프로젝트에 대해 코드 분석을 사용 하도록 설정할 때 호출 되는 프로젝트에 다른 Msbuild.exe *.targets* 파일을 추가 합니다. 이렇게 *.targets* 파일 추가 확장으로 Visual Studio 코드 분석 도구에는 C++ Core Check 규칙을 추가 합니다. 패키지를 설치할 때에 출시되고 실험적 규칙을 사용할지 여부를 속성 페이지 대화 상자를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio C++ Core Check 참조](code-analysis-for-cpp-corecheck.md)