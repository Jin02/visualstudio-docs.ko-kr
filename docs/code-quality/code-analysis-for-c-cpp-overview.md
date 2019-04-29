---
title: C/C++용 코드 분석 개요
ms.date: 04/28/2018
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 07ba2c64be0af987b82c870b89d3451b5d48d28f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540829"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++용 코드 분석 개요

C/C++ 코드 분석 도구는 C 및 C++로 작성된 소스 코드에서 발생할 수 있는 결함에 대한 정보를 제공합니다. 이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 있습니다. [C++ Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)에 입각한 코드를 작성했는지 여부에 대한 검사도 가능합니다.

## <a name="ide-integrated-development-environment-integration"></a>IDE(통합 개발 환경) 통합

코드 분석 도구는 Visual Studio IDE와 완전히 통합되어 있어 사용하기에 편리합니다.

빌드 진행 과정에서 생성된 소스 코드에 대한 모든 경고가 오류 목록에 표시됩니다. 경고를 발생시킨 소스 코드로 쉽게 이동할 수 있으며 해당 원인 및 문제 해결에 도움이 되는 추가 정보를 볼 수 있습니다.

## <a name="command-line-support"></a>명령줄 지원

다음과 같이 명령줄에서 분석 도구를 실행할 수도 있습니다.

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 15.7 이상의 버전**이 필요하며 CMake를 포함한 모든 빌드 시스템에서 명령줄 도구를 실행할 수 있습니다.

## <a name="pragma-support"></a>#pragma 지원

`#pragma` 지시문을 사용해 경고를 오류로 간주하거나 경고의 활성화 및 비활성화, 코드 라인별 경고 표시를 생략할 수 있습니다. 자세한 내용은 [방법: C/C++ 프로젝트에 대 한 코드 분석 속성 설정](how-to-set-code-analysis-properties-for-c-cpp-projects.md)합니다.

## <a name="annotation-support"></a>주석 지원

주석을 통해 코드 분석의 정확성을 개선 할 수 있습니다. 주석을 이용해 함수 매개변수나 반환 형식의 사전, 사후 조건에 대한 추가 정보를 제공할 수 있습니다. 자세한 내용은 [방법: __analysis_assume를 사용한 추가 코드 정보 지정](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)을 참조하세요.

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 분석 도구 실행

모든 소스 코드 체크인이 특정 정책을 충족하도록 요구할 수 있습니다. 특히, 최신 로컬 빌드 과정에서 분석이 실행되도록 할 수 있습니다. 코드 분석 체크인 정책을 사용하도록 설정하는 방법에 대한 자세한 내용은 [코드 분석 체크인 정책 만들고 사용하기](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)를 참조하세요.

## <a name="team-build-integration"></a>팀 빌드 통합

빌드 시스템의 통합 기능을 사용하여 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 빌드 절차에 코드 분석 도구 실행 단계를 추가할 수 있습니다. 자세한 내용은 [Azure 파이프라인](/azure/devops/pipelines/index?view=vsts)을 참조합니다.

## <a name="see-also"></a>참고자료

- [빠른 시작: C/C++ 용 코드 분석](quick-start-code-analysis-for-c-cpp.md)
- [연습: 오류에 대 한 C/C++ 코드 분석](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++용 코드 분석 경고](code-analysis-for-c-cpp-warnings.md)
- [C++ Core 지침 검사기 사용](using-the-cpp-core-guidelines-checkers.md)
- [C++핵심 지침 검사기 참조](code-analysis-for-cpp-corecheck.md)
- [규칙 집합을 사용하여 실행할 C++ 규칙 지정](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [코드 분석 도구를 사용한 드라이버 품질 분석](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [드라이버 경고에 대한 코드 분석](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
