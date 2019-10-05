---
title: 그래픽 진단 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: fa69c550-62a7-41b5-bb1f-7eb04af1a6e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cbc3edfabe041804a632b919eff4e565be9cc5e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848605"
---
# <a name="visual-studio-graphics-diagnostics"></a>Visual Studio 그래픽 진단
Visual Studio*그래픽 진단* 기록 하 고 다음 Direct3D 앱의 렌더링 및 성능 문제를 분석에 대 한 도구 집합이 있습니다. Windows PC에서 로컬로 실행 중이거나 Windows 디바이스 에뮬레이터 또는 원격 PC나 디바이스에서 실행 중인 앱에서 그래픽 진단을 사용할 수 있습니다.

 그래픽 진단 워크플로에서는 동작을 즉시 분석, 공유 또는 나중에 저장할 수 있도록 먼저 앱이 Direct3D를 사용하는 방법(라이브, 실행 시)에 대한 기록을 캡처합니다. 캡처 세션을 시작 하 고 Visual Studio 또는 명령줄 캡처 도구를 사용 하 여 수동으로 제어할 수 **dxcap.exe**합니다. 또한 캡처 세션을 시작한 고 그래픽 진단 캡처 Api를 사용 하 여 프로그래밍 방식으로 제어할 수 있습니다.

 캡처 세션이 기록된 후에 Visual Studio *Graphics Analyzer*에서 언제든지 해당 내용을 재생하고 앱이 사용한 것과 동일한 리소스 및 렌더링 명령을 사용하여 캡처된 프레임을 다시 만들 수 있습니다. 그런 다음 Graphics Analyzer 창에서 제공 하는 도구를 사용 하 여, 캡처된 프레임 중 하나에서 분석할 수 있습니다 세부 정보. 이러한 도구는 Direct3D API 호출, 리소스, 파이프라인 상태 개체, 파이프라인 단계 또는 캡처된 프레임의 픽셀에 대한 전체 기록을 검사하는 데 사용할 수 있습니다. 이러한 도구를 함께 사용하면 캡처된 프레임에 표시되는 방식부터 시작해서 앱 소스 코드, 셰이더 또는 그래픽 자산의 근본 원인으로 드릴다운하여 렌더링 문제를 직관적으로 탐색할 수 있습니다.

 성능 문제를 진단하려면 *프레임 분석* 도구를 사용하여 캡처된 프레임을 분석할 수 있습니다. 이 도구는 앱이 Direct3D를 사용하는 방식을 자동으로 변경하고 모든 변형을 벤치마킹하여 잠재적인 성능 최적화를 탐색합니다. 이전에는 단순히 차이를 만드는 변경을 찾기 위해 이러한 종류의 변경을 수동으로 수행하고 벤치마킹했을 수 있습니다. 프레임 분석을 사용하면 이미 효과를 알고 있는 변경을 수행하기만 하면 됩니다.

 그래픽 진단은 그래픽이 많은 Direct3D 앱의 모양과 실행을 최적화하는 데 도움이 됩니다.

 계속 해 서 [개요](overview-of-visual-studio-graphics-diagnostics.md) Visual Studio 그래픽 진단에서 제공 하는 기능에 대해 자세히 알아보려면 합니다.

## <a name="in-this-section"></a>섹션 내용
 [개요](overview-of-visual-studio-graphics-diagnostics.md) 그래픽 진단 워크플로 및 도구를 소개 합니다.

 [Getting Started](getting-started-with-visual-studio-graphics-diagnostics.md) 이 섹션에서는 배웁니다 Visual Studio 그래픽 진단을 설치 하는 방법 및 Direct3D 앱에서 그래픽 진단 사용을 시작 하는 방법입니다.

 [그래픽 정보 캡처](capturing-graphics-information.md) 그래픽 진단에 앱의 렌더링 문제를 검사 하는 데 사용 하려면 먼저 앱에서 DirectX를 사용 하는 방법에 대 한 내용은 기록 합니다. 기록 세션 중에는 정상적으로 앱이 실행될 때 관심 있는 프레임을 *캡처*, 즉 선택합니다. 캡처에는 프레임이 렌더링되는 방법에 대한 자세한 정보가 포함됩니다. 나중에 검사하거나 팀의 다른 멤버와 공유할 수 있도록 캡처한 정보를 그래픽 로그 문서로 저장할 수 있습니다.

 [GPU 사용량](gpu-usage.md) 그래픽 진단을 사용 하 여 앱을 프로 파일링, GPU 사용량 도구를 사용 합니다. GPU 사용량을 CPU 사용량 등의 기타 프로파일링 도구와 함께 사용하여 앱의 성능 문제에 영향을 줄 수 있는 CPU 및 GPU 작업을 상호 연결할 수 있습니다.

 [그래픽 로그 문서](graphics-log-document.md) 기록된 된 그래픽 로그 검사를 시작 하려면 사용할 그래픽 로그 문서 창 캡처된 프레임을 선택 하려면-특정 픽셀 또는-자세히 검사할 수 있도록 합니다 *이벤트* ( , DirectX API 호출)에 영향을 주는 합니다.

 [프레임 분석](graphics-frame-analysis.md) 점검 하 여 렌더링 성능 튜닝 그래픽 프레임 분석을 사용 하는 프레임을 선택한 후 합니다.

 [이벤트 목록](graphics-event-list.md) 프레임을 선택한 후 사용 합니다 **그래픽 이벤트 목록** 렌더링 문제에 관련 되어 있는지 여부를 확인 하려면 해당 이벤트를 검사 하 합니다.

 [상태](graphics-state.md) 창 상태를 사용 하면 현재 이벤트의 시간에 활성화 된 그래픽 상태를 이해 합니다.

 [파이프라인 단계](graphics-pipeline-stages.md) 에 **그래픽 파이프라인 단계** 창 위치를 식별할 수 있도록 현재 선택한 이벤트 그래픽 파이프라인의 각 단계에서 처리 하는 방법을 조사 하면 렌더링 문제 첫 번째 표시 됩니다. 잘못된 변형으로 인해 개체가 나타나지 않는 경우 또는 단계 중 하나에서 다음 단계에서 예상하는 것과 일치하지 않는 출력을 생성하는 경우 파이프라인 단계 검사가 특히 유용합니다.

 [이벤트 호출 스택](graphics-event-call-stack.md) 사용할 합니다 **그래픽 이벤트 호출 스택** 렌더링 문제와 관련이 있는 앱 코드로 이동할 수 있도록 현재 선택한 이벤트의 호출 스택을 검사 합니다.

 [픽셀 기록](graphics-pixel-history.md) 를 사용 하 여 합니다 **그래픽 픽셀 기록** 현재 선택된 된 픽셀을 영향을 받는 이벤트에 미치는 영향을 분석 하는 창 이벤트 또는 조합 하는 특정 이벤트를 식별할 수 있습니다 렌더링 문제의 종류입니다. 픽셀 셰이더 출력이 잘못되었거나 프레임 버퍼와 잘못 결합되어서 개체가 잘못 렌더링된 경우 또는 픽셀이 프레임 버퍼에 도달하기 전에 버려져 개체가 나타나지 못한 경우 픽셀 기록은 특히 유용합니다.

 [테이블 개체](graphics-object-table.md) 사용 합니다 **그래픽 개체 테이블** 속성과 특정 Direct3D 개체 및 현재 선택한 이벤트에 대 한 적용 되는 리소스의 내용을 검사할 합니다. 개체 테이블을 사용하면 이벤트 중 활성 상태인 그래픽 디바이스 컨텍스트를 확인하고 상수 버퍼, 꼭짓점 버퍼 및 질감과 같은 그래픽 리소스의 콘텐츠를 검사할 수 있습니다.

 [HLSL 디버거](hlsl-shader-debugger.md) 셰이더 코드는 현재 선택한 이벤트와 그래픽 파이프라인 단계에 대 한 동작 방식을 검사 하려면 사용 합니다 **HLSL 디버거** 코드를 단계별로 실행 하려면 변수 내용을 검사 하 고 다른 수행 일반적인 디버깅 작업입니다. 그래픽 파이프라인이 결과를 추가로 처리하는지 또는 앱에서 결과를 다시 읽는지와 상관없이 HLSL 디버거를 사용하여 컴퓨팅 셰이더 코드를 검사할 수 있습니다.

 [명령줄 캡처 도구](command-line-capture-tool.md) 명령줄 캡처 도구를 사용 하 여 신속 하 게 캡처하고 Visual Studio 또는 프로그래밍 방식 캡처를 사용 하지 않고 그래픽 정보 재생 합니다. 특히 자동화 수행 시 또는 테스트 환경에서 명령줄 캡처 도구를 사용할 수 있습니다.

 [예제](graphics-diagnostics-examples.md) 몇 가지 예에는 다른 종류의 렌더링 문제를 진단 하려면 그래픽 진단 도구를 함께 사용 하는 방법을 보여 줍니다.

## <a name="related-sections"></a>관련 단원

| 제목 | 설명 |
| - | - |
| [디버거 기능 둘러보기](/visualstudio/debugger/debugger-feature-tour) | [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 디버깅 기능에 대해 소개합니다. |
| [DirectX 그래픽 및 게임](http://go.microsoft.com/fwlink/?LinkId=256498) | DirectX 그래픽 기술에 대해 설명하는 문서를 제공합니다. |
