---
title: "Visual Studio의 데이터 과학 및 분석 응용 프로그램 워크로드 | Microsoft Docs"
ms.custom: 
ms.date: 9/5/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
- devlang-python
- devlang-fsharp
ms.tgt_pltfrm: 
ms.topic: landing-page
ms.assetid: 018069f3-6d1a-4143-a851-d86d2ff5fbfc
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 976bd73c7740e474e4fa7ea3e4cf89f880c7900c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="data-science-and-analytical-applications-workload"></a>데이터 과학 및 분석 응용 프로그램 워크로드

Visual Studio의 데이터 과학 및 분석 응용 프로그램 워크로드는 세 언어 및 해당 런타임 분포와 함께 나타납니다.

- [R 및 Microsoft R Client](../rtvs/index.md)
- [Python 및 Anaconda](../python/python-in-visual-studio.md)
- [.NET 프레임워크로 F#](https://docs.microsoft.com/dotnet/fsharp/)

![Visual Studio 설치 관리자의 데이터 과학 및 분석 응용 프로그램 워크로드](media/data-science-workload.png)

R 및 Python은 데이터 과학에 사용되는 두 가지 기본 스크립팅 언어입니다. 두 언어는 배우기 쉬우며 풍부한 패키지의 에코시스템에서 지원됩니다. 이러한 패키지는 데이터 취득, 정리, 모델 학습, 배포 및 그리기와 같은 다양한 범위의 시나리오를 해결합니다. F#은 다양한 데이터 처리 작업에 적합한 강력한 기능 우선 .NET 언어입니다.

<!--Note link on the image because this one is large -->
[![R, Python 및 F#을 사용한 Visual Studio의 스크린샷](media/data-science-workload-screens.png)](media/data-science-workload-screens.png)

## <a name="workload-options"></a>워크로드 옵션

기본적으로 워크로드는 Visual Studio 설치 관리자의 작업에 대한 요약 섹션에서 수정할 수 있는 다음 옵션을 설치합니다.

- F# 언어 지원
- Python:
    - Python 언어 지원
    - Python 웹 지원
    - [Anaconda3 64비트](https://www.continuum.io)(광범위한 데이터 과학 라이브러리 및 Python 인터프리터를 포함하는 Python 배포판)
    - Cookiecutter 템플릿 지원
- R:
    - R 언어 지원    
    - [Microsoft R Client](https://msdn.microsoft.com/microsoft-r/r-client-get-started)(단일 노드 또는 클러스터에서 더 빠른 계산을 위해 ScaleR 라이브러리를 사용하는 Microsoft의 완전히 호환되는, 커뮤니티 지원 R 인터프리터입니다. [CRAN](https://cran.r-project.org/)에서 R을 사용할 수도 있습니다.)
    - R 개발 도구에 대한 런타임 지원

> [!Note]
> F#이 다양한 다른 작업에 포함되어 있고 Python에 고유한 워크로드가 있더라도 데이터 과학 및 분석 응용 프로그램은 워크로드에 독립적인 R을 포함하는 현재 유일한 워크로드이며 세 가지 R 구성 요소는 설치 관리자의 **개별 구성 요소** 탭에서 선택 가능합니다. 옵션 **개발 작업 > R 언어 지원**, **개발 작업 > Microsoft R Client** 및 **컴파일러, 빌드 도구 및 런타임 > R 개발 도구에 대한 런타임 지원**을 선택합니다.

## <a name="sql-server-integration"></a>SQL Server 통합

SQL Server는 SQL Server 내에서 직접 고급 분석을 수행하도록 R 및 Python 사용을 지원합니다. R 지원은 Server 2016 이상과 함께 제공됩니다. Python 지원은 SQL Server 2017 CTP 2.0 이상에서 사용할 수 있습니다.

데이터가 이미 있는 코드를 실행하여 여러 장점을 이용할 수 있습니다:

- **데이터 이동의 제거**: 데이터베이스에서 응용 프로그램 또는 모델로 데이터를 이동하는 대신 데이터베이스에서 R 및 Python 응용 프로그램을 빌드할 수 있습니다. 이 기능은 보안의 장벽, 규정 준수, 거버넌스, 무결성 및 방대한 양의 데이터 이동과 관련된 호스트의 비슷한 문제를 제거합니다. 또한 클라이언트 컴퓨터의 메모리에 맞출 수 없는 데이터 집합을 사용할 수 있습니다.

- **간편한 배포**: R 또는 Python 모델의 준비가 완료되면 프로덕션에 이를 배포하는 것은 단순히 T-SQL 스크립트에 포함하는 것을 의미합니다. 어떠한 언어로 작성된 모든 SQL 클라이언트 응용 프로그램은 저장된 프로시저 호출을 통해 모델 및 인텔리전스를 활용할 수 있습니다. 특정 R 또는 Python 통합이 필요하지 않습니다.

- **엔터프라이즈급 성능 및 확장성**: RevoScaleR 및 RevoScalePy 패키지의 고성능 확장 가능한 API를 사용하여 메모리 내 테이블 및 열 저장소 인덱스와 같은 SQL Server의 고급 기능을 사용할 수 있습니다. 데이터 이동의 제거는 데이터가 확대되거나 응용 프로그램의 성능을 향상시키기 원하므로 클라이언트 메모리 제약 조건을 방지하는 것을 의미하기도 합니다.

- **풍부한 확장성**: SQL Server에서 최신 오픈 소스 R 또는 Python 패키지를 설치하고 실행하여 SQL Server에서 엄청난 양의 데이터에 대한 딥 러닝 및 AI 응용 프로그램을 빌드할 수 있습니다. SQL Server에 패키지를 설치하는 것은 로컬 컴퓨터에 패키지를 설치하는 것만큼 간단합니다.

- **추가 비용 없는 광범위한 가용성**: R 및 Python 통합은 Express 버전을 포함하여 SQL Server 2017 이상의 모든 버전에서 사용할 수 있습니다. (R 지원은 SQL Server 2016 이상에서 사용할 수 있습니다.)

SQL Server 통합을 모두 활용하려면 **SQL Server Data Tools** 옵션으로 **데이터 저장소 및 처리** 워크로드도 설치해야 합니다. 이 옵션은 SQL IntelliSense, 구문 강조 표시 및 배포를 활성화합니다.

![데이터 저장소 및 처리 워크로드](media/data-storage-workload.png) &nbsp;&nbsp; &nbsp;&nbsp; ![데이터 저장소 및 처리 워크로드 옵션](media/data-storage-workload-options.png)


추가 정보

- [SQL Server 및 R 사용](../rtvs/sql-server.md)
- [SQL Server 2016에서 R을 사용하여 데이터베이스 내 고급 분석](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)
- [SQL Server 2017의 Python: 향상된 데이터베이스 내 기계 학습](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="additional-services-and-sdks"></a>추가 서비스 및 SDK

데이터 과학 및 분석 응용 프로그램 워크로드에 있는 것 외에도 Azure Notebooks 서비스 및 Python용 Azure SDK도 데이터 과학에 유용합니다.

Python용 Azure SDK를 사용하면 Windows, Mac OSX 및 Linux에서 실행되는 응용 프로그램에서 Microsoft Azure 서비스를 쉽게 사용하고 관리할 수 있습니다. 자세한 내용은 [Python용 Azure SDK](../python/azure-sdk-for-python.md)를 참조하세요.

Azure Notebooks(현재 미리 보기 상태)는 Microsoft Azure의 클라우드에서 실행되는 Jupyter 노트북에 대한 무료 온라인 액세스를 제공합니다. 서비스는 시작하기 위해 Python, R 및 F#에서 샘플 전자 필기장을 포함합니다. [notebooks.azure.com](https://notebooks.azure.com/)을 방문하세요.

<!--Note link on the image because this one is large -->
[![R 샘플에 대한 소개가 있는 Azure Notebooks의 스크린샷](media/data-science-workload-notebooks.png)](media/data-science-workload-notebooks.png)