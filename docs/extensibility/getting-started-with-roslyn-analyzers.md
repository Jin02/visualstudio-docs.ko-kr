---
title: Roslyn 분석기 시작 | Microsoft Docs
ms.date: 04/02/2018
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb224d1c84f9216ed303c919118af4997be2405c
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66835903"
---
# <a name="get-started-with-roslyn-analyzers"></a>Roslyn 분석기 시작

Visual Studio에서 프로젝트 기반 라이브 코드 분석기를 사용 하 여 API 작성자는 NuGet 패키지의 일부로 도메인 관련 코드 분석을 제공할 수 있습니다. 이러한 분석기는.NET 컴파일러 플랫폼 (코드 이름된 "Roslyn")에서 구동 되, 때문에 (빌드 문제를 검색 하는 코드를 더 이상 대기) 줄을 마친 전이라를 입력할 때 코드에서 경고를 생성할 수 있으므로 합니다. 분석기는 자동 코드 수정 사항을 즉시 코드 정리 수 Visual Studio 전구 프롬프트를 통해 발생할 수도 수 있습니다.

## <a name="get-started"></a>시작

[Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)

[자습서: 첫 번째 분석기 및 코드 수정 사항을 작성 합니다.](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)

[코드 수정 연습을 추가 합니다. 분석기 문제에 대 한 사용자 수정 사항 제공](https://msdn.microsoft.com/magazine/dn904670.aspx)

[실제 Roslyn 분석기](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) 로 볼 수 있는 한 [통신](https://channel9.msdn.com/events/Build/2015/3-725)

[세 가지 유형의 분석기를 그룹화 하는 GitHub에서 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)


## <a name="see-also"></a>참고자료

- [.NET 컴파일러 플랫폼 패키지 버전 참조](roslyn-version-support.md)
- [GitHub OSS 사이트에서 더 많은 문서](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Roslyn 분석기를 사용 하 여 구현 하는 FxCop 규칙](http://roslynanalyzersstatus.azurewebsites.net/)
