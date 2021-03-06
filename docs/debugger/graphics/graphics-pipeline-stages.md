---
title: 그래픽 파이프라인 단계 | Microsoft Docs
ms.date: 02/09/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.pipeline
ms.assetid: 2bf5c12e-2a00-401c-8163-4e373d08ad3f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1d697313289bbf00234764cc04603b7bc256f174
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72735475"
---
# <a name="graphics-pipeline-stages"></a>그래픽 파이프라인 단계
그래픽 파이프라인 단계 창에서는 개별 그리기 호출이 Direct3D 그래픽 파이프라인의 각 단계에서 변환되는 방식을 이해할 수 있습니다.

 다음은 파이프라인 단계 창입니다.

 ![3D 개체가 파이프라인 단계를 거칩니다.](media/gfx_diag_demo_pipeline_stages_orientation.png)

## <a name="understanding-the-graphics-pipeline-stages-window"></a>그래픽 파이프라인 단계 창 이해
 파이프라인 단계 창에서는 각 그리기 호출에 대해 각 그래픽 파이프라인 단계의 결과를 별도로 시각화합니다. 일반적으로 파이프라인 중간 단계의 결과는 숨겨져 있어 렌더링 문제가 시작된 위치를 파악하기가 어렵습니다. 각 단계를 별도로 시각화하면 파이프라인 단계 창에서 문제가 시작되는 위치를 쉽게 확인할 수 있습니다. 예를 들어 꼭짓점 셰이더 단계에서 예기치 않게 개체를 화면 밖에 그리는 경우를 쉽게 확인할 수 있습니다.

 문제가 발생하는 단계를 파악한 후에는 다른 Graphics Analyzer 도구를 사용하여 데이터가 해석되거나 변환된 방법을 검사할 수 있습니다. 파이프라인 단계에서 발생하는 렌더링 문제는 잘못된 꼭짓점 형식 설명자, 셰이더 프로그램의 버그 또는 잘못 구성된 상태와 관련되는 경우가 많습니다.

### <a name="links-to-related-graphics-objects"></a>관련 그래픽 개체에 대한 링크
 경우에 따라 그리기 호출이 특정 방식으로 그래픽 파이프라인과 상호 작용하는 이유를 확인하려면 추가 컨텍스트가 필요합니다. 이 추가 컨텍스트를 쉽게 찾을 수 있도록 그래픽 파이프라인 단계 창은 그래픽 파이프라인에서 발생하는 상황과 관련된 추가 컨텍스트를 제공하는 하나 이상의 개체에 연결됩니다.

- Direct3D 12에서 이 개체는 일반적으로 명령 목록입니다.

- Direct3D 11에서 이 개체는 일반적으로 그래픽 디바이스 컨텍스트입니다.

  이러한 링크는 그래픽 파이프라인 단계 창의 왼쪽 위 모서리에 있는 현재 그래픽 이벤트 서명의 일부입니다. 개체에 대한 추가 정보를 검토하려면 다음 링크를 클릭하세요.

### <a name="viewing-and-debugging-shader-code"></a>셰이더 코드 보기 및 디버그
 파이프라인 단계 창에서 각 단계 아래쪽에 있는 컨트롤을 사용하여 꼭짓점, 헐, 도메인, 기하 도형 및 픽셀 셰이더에 대한 코드를 검사하고 디버그할 수 있습니다.

#### <a name="to-view-a-shaders-source-code"></a>셰이더의 소스 코드를 보려면

- **그래픽 파이프라인 단계** 창에서 검사하려는 셰이더에 해당하는 셰이더 단계를 찾습니다. 그런 다음, 미리 보기 이미지 아래에서 셰이더 단계 제목 링크를 클릭합니다. 예를 들어 꼭짓점 셰이더 소스 코드를 보려면 **꼭짓점 셰이더 obj:30** 링크를 클릭합니다.

    > [!TIP]
    > 개체 번호 **obj:30**은 개체 테이블 및 픽셀 기록 창에서처럼 Graphics Analyzer 인터페이스 전체에서 이 셰이더를 식별합니다.

#### <a name="to-debug-a-shader"></a>셰이더를 디버그하려면

- **그래픽 파이프라인 단계** 창에서 디버그하려는 셰이더에 해당하는 셰이더 단계를 찾습니다. 그런 다음, 미리 보기 이미지 아래에서 **디버깅 시작**을 선택합니다. HLSL 디버거의 이 진입점은 해당 단계에 대한 셰이더의 첫 번째 호출 즉, 이 그리기 호출 중 셰이더에서 처리되는 첫 번째 픽셀, 꼭짓점 또는 기본 형식으로 기본 설정됩니다. 특정 픽셀 또는 꼭짓점에 대한 이 셰이더의 호출은 **그래픽 픽셀 기록**을 통해 액세스할 수 있습니다.

### <a name="the-pipeline-stages"></a>파이프라인 단계
 파이프라인 단계 창은 그리기 호출 중 활성화된 파이프라인의 단계만 시각화합니다. 그래픽 파이프라인의 각 단계는 이전 단계의 입력을 변형하여 그 결과를 다음 단계에 전달합니다. 첫 번째 단계인 입력 어셈블러는 앱의 인덱스 및 꼭짓점 데이터를 입력으로 사용하고 마지막 단계인 출력 병합기는 프레임 버퍼나 렌더링 대상의 현재 콘텐츠와 함께 새로 렌더링된 픽셀을 출력으로 결합하여 화면에 표시되는 최종 이미지를 생성합니다.

> [!NOTE]
> 컴퓨팅 셰이더는 **그래픽 파이프라인 단계** 창에서 지원되지 않습니다.

 **입력 어셈블러** - 입력 어셈블러는 앱에서 지정한 인덱스 및 꼭짓점 데이터를 읽어 그래픽 하드웨어용으로 어셈블합니다.

 파이프라인 단계 창에서 입력 어셈블러 출력은 와이어프레임 모델로 시각화됩니다. 결과를 좀 더 자세히 살펴보려면 **그래픽 파이프라인 단계** 창에서 **입력 어셈블러**를 선택하여 어셈블된 꼭짓점을 모델 편집기에서 완전한 3D로 표시합니다.

> [!NOTE]
> `POSITION` 의미 체계가 입력 어셈블러 출력에 없으면 **입력 어셈블러** 단계에서는 아무 정보도 표시되지 않습니다.

 **꼭짓점 셰이더** - 꼭짓점 셰이더 단계에서는 일반적으로 변형, 스킨 적용, 조명 등의 작업을 수행하여 꼭짓점을 처리합니다. 꼭짓점 셰이더는 입력으로 사용하는 것과 동일한 수의 꼭짓점을 생성합니다.

 파이프라인 단계 창에서 꼭짓점 셰이더 출력은 와이어프레임 래스터 이미지로 시각화됩니다. 결과를 좀 더 자세히 살펴보려면 **그래픽 파이프라인 단계** 창에서 **꼭짓점 셰이더**를 선택하여 처리된 꼭짓점을 이미지 편집기에 표시합니다.

> [!NOTE]
> `POSITION` 또는 `SV_POSITION` 의미 체계가 꼭짓점 셰이더 출력에 없으면 **꼭짓점 셰이더** 단계에서는 아무 정보도 표시되지 않습니다.

 **헐 셰이더**(Direct3D 11 및 Direct3D 12만 해당) - 헐 셰이더 단계는 선, 삼각형, 사각형 등 하위 표면을 정의하는 제어점을 처리합니다. 출력으로 고정 함수 공간 분할(tessellation) 단계에 전달되는 상위 기하 도형 패치 및 패치 상수를 생성합니다.

 헐 셰이더 단계는 파이프라인 단계 창에서 시각화되지 않습니다.

 **Tessellator 단계**(Direct3D 11 및 Direct3D 12만 해당) - Tessellator 단계는 헐 셰이더의 출력으로 표시되는 도메인을 전처리하는 고정 함수(프로그래밍할 수 없음) 하드웨어 단위입니다. 출력으로 도메인의 샘플링 패턴과 이러한 샘플을 연결하는 점, 선, 삼각형 등의 더 작은 기본 형식 집합을 만듭니다.

 Tessellator 단계는 파이프라인 단계 창에서 시각화되지 않습니다.

 **도메인 셰이더**(Direct3D 11 및 Direct3D 12만 해당) - 도메인 셰이더 단계는 공간 분할(tessellation) 단계의 공간 분할(tessellation) 요소와 함께 헐 셰이더의 상위 기하 도형 패치를 처리합니다. 공간 분할(tessellation) 요소에는 출력 요소뿐만 아니라 tessellator 입력 요소가 포함될 수 있습니다. 출력으로 tessellator 요소에 따라 출력 패치에 있는 점의 꼭짓점 위치를 계산합니다.

 도메인 셰이더 단계는 파이프라인 단계 창에서 시각화되지 않습니다.

 **기하 도형 셰이더** - 기하 도형 셰이더 단계는 가장자리 인접 기본 형식의 선택적 꼭짓점 데이터와 함께 점, 선, 삼각형 등의 전체 기본 형식을 처리합니다. 꼭짓점 셰이더와 달리 기하 도형 셰이더는 입력으로 사용하는 것보다 더 많거나 더 적은 기본 형식을 생성할 수 있습니다.

 파이프라인 단계 창에서 기하 도형 셰이더 출력은 와이어프레임 래스터 이미지로 시각화됩니다. 결과를 좀 더 자세히 살펴보려면 **그래픽 파이프라인 단계** 창에서 **기하 도형 셰이더**를 선택하여 처리된 기본 형식을 이미지 편집기에 표시합니다.

 **스트림 출력 단계** - 스트림 출력 단계는 래스터화 전에 변형된 기본 형식을 가로채 메모리에 쓸 수 있습니다. 여기에서 데이터는 이전 그래픽 파이프라인 단계의 입력으로 재순환되거나 CPU에서 다시 읽을 수 있습니다.

 스트림 출력 단계는 파이프라인 단계 창에서 시각화되지 않습니다.

 **래스터라이저 단계** - 래스터라이저 단계는 스캔 라인 변환을 수행하여 점, 선, 삼각형 등의 벡터 기본 형식을 래스터 이미지로 변환하는 고정 함수(프로그래밍할 수 없음) 하드웨어 단위입니다. 래스터화 중 꼭짓점은 형식이 같은 클립 공간으로 변환되고 잘립니다. 출력으로 픽셀 셰이더가 매핑되고 꼭짓점별 특성이 기본 형식 전체에서 보간되어 픽셀 셰이더용으로 준비됩니다.

 래스터라이저 단계는 파이프라인 단계 창에서 시각화되지 않습니다.

 **픽셀 셰이더** - 픽셀 셰이더 단계는 보간된 꼭짓점 데이터와 함께 래스터화된 기본 형식을 처리하여 색 및 깊이와 같은 픽셀당 값을 생성합니다.

 파이프라인 단계 창에서 픽셀 셰이더 출력은 완전 컬러의 래스터 이미지로 시각화됩니다. 결과를 좀 더 자세히 살펴보려면 **그래픽 파이프라인 단계** 창에서 **픽셀 셰이더**를 선택하여 처리된 기본 형식을 이미지 편집기에 표시됩니다.

 **출력 병합기** - 출력 병합기 단계는 색, 깊이, 스텐실 등 해당 버퍼의 기존 콘텐츠와 함께 새로 렌더링된 픽셀의 효과를 결합하여 이러한 버퍼에 새 값을 생성합니다.

 파이프라인 단계 창에서 출력 병합기 출력은 완전 컬러의 래스터 이미지로 시각화됩니다. 결과를 좀 더 자세히 살펴보려면 **그래픽 파이프라인 단계** 창에서 **출력 병합기**를 선택하여 병합된 프레임 버퍼를 표시합니다.

### <a name="vertex-and-geometry-shader-preview"></a>꼭짓점 및 기하 도형 셰이더 미리 보기
 **파이프라인 단계** 창에서 꼭짓점 또는 기하 도형 셰이더 단계를 선택하면 아래 패널에서 셰이더의 입력 및 출력을 볼 수 있습니다.  여기서는 입력 어셈블러 단계에서 어셈블된 후 셰이더에 제공되는 꼭짓점 목록에 관한 정보를 찾을 수 있습니다.

 ![꼭짓점 셰이더 단계 입력 버퍼 뷰어](media/gfx_diag_vertex_shader_inbuffers.png)

 꼭짓점 셰이더 단계의 결과를 보려면 꼭짓점 셰이더 단계 미리 보기를 선택하여 꼭짓점 셰이더에서 변형된 후 메시의 래스터화된 전체 크기 와이어프레임을 표시합니다.

 ![꼭짓점 셰이더 단계 결과 미리 보기](media/gfx_diag_vertex_shader_preview.png)

## <a name="see-also"></a>참조
- [연습: 꼭짓점 음영으로 인해 누락된 개체](walkthrough-missing-objects-due-to-vertex-shading.md)
- [연습: 음영으로 인한 렌더링 오류 디버그](walkthrough-debugging-rendering-errors-due-to-shading.md)