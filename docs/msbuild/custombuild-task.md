---
title: CustomBuild 작업 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.custombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (C++), CustomBuild task
- CustomBuild task (MSBuild (C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 678068d1b6acc055fa65e6d0305b07152ed28695
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748108"
---
# <a name="custombuild-task"></a>CustomBuild 작업

Microsoft C++ 컴파일러 도구 cmd.exe를 래핑합니다. 이 클래스는 [TrackedVCToolTask](../msbuild/trackedvctooltask-base-class.md)에서 파생되나 파일 종속성 검색을 위해 파일 추적을 사용하지는 않습니다. 증분 빌드가 제대로 작동하려면 모든 종속성은AdditionalDependencies로 명시적으로 지정되어야 합니다.

## <a name="parameters"></a>매개 변수

다음 표에서는 **CustomBuild** 작업의 매개 변수에 대해 설명합니다.

|매개 변수|설명|
|---------------|-----------------|
|**BuildSuffix**|선택적 **string** 매개 변수입니다.|
|**Sources**|필수 **ITaskItem[]** 매개 변수입니다.|
|**TrackerLogDirectory**|선택적 **string** 매개 변수입니다.|

## <a name="see-also"></a>참고 항목

[작업 참조](../msbuild/msbuild-task-reference.md)
