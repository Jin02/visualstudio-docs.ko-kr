---
title: '워크플로 디자이너-방법: 워크플로 디자이너로 XAML 디버그'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: cdbf5fa21c8fcf9069db9a7348d4ed576fc342c5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065885"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>방법: 워크플로 디자이너로 XAML 디버그

워크플로는 XAML로 정의됩니다. 워크플로의 UI 표현은 해당 워크플로를 정의하는 XAML 트리의 맨 위에 빌드됩니다. 디버깅 환경은 Workflow Designer에서 워크플로 디버깅 하는 것과 비슷합니다. 예를 들어 XAML을 디버깅 하는 동안 로컬, 조사식 및 스레드 창은 동일한 방식으로 작동 합니다 디버깅 하는 워크플로 디자이너에서. 또한 XAML 디버깅 중의 호출 스택 보기는 워크플로에 대한 실행 흐름의 줄 기반 계층 보기입니다.

> [!NOTE]
> 워크플로의 XAML이 활동과 동일한 어셈블리에 있는 경우 클래스 이름의 어셈블리 부분이 포함되지 않습니다. 클래스 (활동) 이름의 이 부분이 없으면 XAML을 런타임에 로드할 수 없습니다. 기본 프로젝트와 같은 네임스페이스에 활동을 정의하지 않는 것이 좋습니다. 그렇지 않으면 XAML을 디자이너에서 편집한 후에 수작업으로 편집해야 합니다.

## <a name="to-debug-workflow-xaml"></a>워크플로 XAML을 디버깅하려면

1. Visual Studio에서 워크플로 또는 활동 프로젝트를 엽니다.

2. 에 설명 된 대로 디버깅할 활동을 활동에 중단점을 설정할 [방법: 워크플로에 중단점 설정](../workflow-designer/how-to-set-breakpoints-in-workflows.md)합니다.

3. 워크플로 정 및 선택 포함 된.xaml 파일을 마우스 오른쪽 단추로 클릭 **코드 보기**합니다. 디자인 뷰에서 중단점을 설정한 활동의 XAML 요소 선언과 같은 줄에 중단점이 표시됩니다.

4. 에 설명 된 대로 디버거를 호출 [워크플로 디버깅할](debugging-workflows-with-the-workflow-designer.md)합니다.

5. 코드 실행이 중단점 중 하나에 도달하면 해당 중단점과 연결된 XAML 요소가 강조 표시됩니다. 다음 중단점으로 이동 하려면 사용 합니다 **F10** 하거나 **F11** 키입니다.

## <a name="see-also"></a>참고자료

- [방법: 워크플로에 중단점 설정](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [워크플로 디버깅](debugging-workflows-with-the-workflow-designer.md)