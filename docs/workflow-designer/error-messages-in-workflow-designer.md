---
title: Workflow Designer의 오류 메시지
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab2cb4562f816b254b658cfdc152dc38033fbe03
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949700"
---
# <a name="error-messages-in-workflow-designer"></a>Workflow Designer의 오류 메시지

이 항목에서는 워크플로 디자이너를 사용 하 여 작업할 때 발생할 수 있는 오류 메시지 유형을 설명 합니다.

## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>워크플로 디자이너에서 오류가 발생하는 경우

워크플로 디자이너의 오류는 다음과 같은 상황에서 발생합니다.

1. 식에 오류가 있습니다.

2. 활동의 유효성 검사 제약 조건이 충족되지 않았습니다.

3. XAML 파일에 오류가 있어서 활동을 로드할 수 없습니다.

4. XAML 파일에 오류가 있어서 워크플로를 로드할 수 없습니다.

잘못된 식과 충족되지 않은 유효성 검사 제약 조건으로도 워크플로가 작성됩니다. 워크플로는 작성되지만 런타임 시 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다. XAML 파일에 오류가 있으면 빌드가 수행되지 않습니다.

Visual Studio 내에서 워크플로가 로드 될 때 해당에 오류가 표시 됩니다는 **오류 목록**합니다. 오류의 소스인 작업으로 이동 하려면에서 오류를 두 번 클릭 합니다 **오류 목록**합니다.

### <a name="expression-errors"></a>식 오류
 잘못된 식에는 식 앞에 빨간색 원과 흰색 느낌표가 표시됩니다. 하지만 이 아이콘 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다. Visual Studio 내에서 오류 원인을 밑줄을 표시 하는 줄을 보려면 클릭 합니다. 밑줄이 그어진 텍스트 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다.

### <a name="activity-validation-errors"></a>활동 유효성 검사 오류
 활동의 유효성 검사 제약 조건이 충족되지 않은 경우 빨간색 원과 흰색 느낌표가 활동의 오른쪽 위 모서리에 나타납니다. 하지만 이 아이콘 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다.

### <a name="xaml-load-errors"></a>XAML 로드 오류
 로드 작업에 실패 하면 텍스트를 사용 하 여 "활동 들일 수 없습니다는 XAML에 오류가 있어서" 빨간색 상자가 표시 됩니다. 이 문제는 일반적으로 활동 형식을 확인할 수 없는 경우 발생 합니다. 빨간색 상자를 선택한 후 삭제하여 디자이너에서 잘못된 활동을 삭제할 수 있습니다.

### <a name="workflow-load-errors"></a>워크플로 로드 오류
 워크플로 로드 하지 못하는 경우 "문서를 사용 하 여 발생 하는 워크플로 디자이너 문제를" 워크플로 로드 실패를 발생 시킨 예외 정보와 함께 디자이너 화면에 표시 됩니다. 일반적으로 이 오류는 XAML 파일의 구문을 분석할 수 없는 경우에 발생합니다.