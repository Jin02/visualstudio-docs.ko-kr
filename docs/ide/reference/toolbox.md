---
title: 도구 상자 창
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- vs.toolbox.general
- vs.toolbox
helpviewer_keywords:
- Toolbox [Visual Studio]
- custom controls [Visual Studio]
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5311c9a910c3140d5a5053a42befe7ed7f5b1278
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651120"
---
# <a name="toolbox"></a>도구 상자

**도구 상자** 창에는 Visual Studio 프로젝트에 추가할 수 있는 컨트롤이 표시됩니다. **도구 상자**를 열려면 **보기** 메뉴에서 도구 상자를 선택합니다.

![도구 상자 창](media/toolbox.png)

여러 컨트롤을 사용 중인 디자이너 화면에 끌어 놓은 다음 해당 컨트롤의 크기를 조정하고 배치할 수 있습니다.

도구 상자는 XAML 파일의 디자이너 보기와 같은 디자이너 보기와 함께 나타납니다. 현재 디자이너에서 사용할 수 있는 컨트롤만 **도구 상자**에 표시됩니다. **도구 상자** 내에서 검색하여 표시되는 항목을 추가로 필터링할 수 있습니다.

> [!NOTE]
> 일부 프로젝트 유형의 경우 **도구 상자**에 항목이 표시되지 않을 수 있습니다.

프로젝트가 대상으로 하는 .NET 버전도 도구 상자에 표시되는 컨트롤 집합에 영향을 줍니다. 필요한 경우 프로젝트의 속성 페이지에서 대상 프레임워크 버전을 변경할 수 있습니다. **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음, 메뉴 모음에서 **프로젝트** > **프로젝트 이름 속성**을 선택합니다. **애플리케이션** 탭에서 **대상 프레임워크** 드롭다운을 사용합니다.

## <a name="manage-the-toolbox-window-and-its-controls"></a>도구 상자 창 및 해당 컨트롤 관리

기본적으로 **도구 상자**는 Visual Studio IDE 왼쪽에 축소되어 있으며 커서를 위로 이동하면 표시됩니다. 도구 모음의 **핀** 아이콘을 클릭하여 **도구 상자**를 고정하면 커서를 이동해도 도구 상자가 열린 상태로 유지됩니다. **도구 상자** 창의 도킹을 해제하고 화면의 원하는 위치로 끌어 올 수도 있습니다. 도구 모음을 마우스 오른쪽 단추로 클릭하고 옵션 중 하나를 선택하여 **도구 상자**를 도킹 및 도킹 해제하고 숨길 수 있습니다.

오른쪽 클릭 메뉴에서 다음 명령을 사용하여 **도구 상자** 탭의 항목을 다시 정렬하거나 사용자 지정 탭과 항목을 추가할 수 있습니다.

- **항목 이름 바꾸기** - 선택한 항목의 이름을 바꿉니다.

- **모두 표시** - 현재 디자이너에 적용된 컨트롤뿐 아니라 사용 가능한 모든 컨트롤을 표시합니다.

- **목록 보기** - 세로 목록에 컨트롤을 표시합니다. 선택을 취소하면 컨트롤이 가로로 표시됩니다.

- **항목 선택** - **도구 상자**에 표시되는 항목을 지정할 수 있도록 **도구 상자 항목 선택** 대화 상자를 엽니다. 확인란을 선택하거나 선택을 취소하여 항목을 표시하거나 숨길 수 있습니다.

- **항목 사전순 정렬** - 이름을 기준으로 항목을 정렬합니다.

- **도구 모음 다시 설정** - 기본 **도구 상자** 설정 및 항목을 복원합니다.

- **탭 추가** - 새 **도구 상자** 탭을 추가합니다.

- **위로 이동** - 선택한 항목을 위로 이동합니다.

- **아래로 이동** - 선택한 항목을 아래로 이동합니다.

## <a name="create-and-distribute-custom-toolbox-controls"></a>사용자 지정 도구 상자 컨트롤 만들기 및 배포

[Windows Presentation Foundation](../../extensibility/creating-a-wpf-toolbox-control.md) 또는 [Windows Forms](../../extensibility/creating-a-windows-forms-toolbox-control.md)를 기반으로 하는 프로젝트 템플릿으로 시작하는 사용자 지정 **도구 상자** 컨트롤을 만들 수 있습니다. 그런 후에 [도구 상자 컨트롤 설치 관리자](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx)를 사용하여 사용자 지정 컨트롤을 팀원에게 배포하거나 웹에 게시할 수 있습니다.

## <a name="help-on-toolbox-tabs"></a>도구 상자 탭에 대한 도움말

다음 항목에서는 일부 사용 가능한 **도구 상자** 탭을 자세히 설명합니다.

- [도구 상자, 데이터 탭](../../ide/reference/toolbox-data-tab.md)
- [도구 상자, 구성 요소 탭](../../ide/reference/toolbox-components-tab.md)
- [도구 상자, HTML 탭](../../ide/reference/toolbox-html-tab.md)

## <a name="see-also"></a>참고 항목

- [도구 상자 항목 선택, WPF 구성 요소](choose-toolbox-items-wpf-components.md)