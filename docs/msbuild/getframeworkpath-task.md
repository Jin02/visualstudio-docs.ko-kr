---
title: GetFrameworkPath 작업 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b836a0fef26f34e83f7238ebe4f6c64731b84257
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977671"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath 작업
[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리에 대한 경로를 검색합니다.

## <a name="task-parameters"></a>작업 매개 변수
다음 표에서는 `GetFrameworkPath` 작업의 매개 변수에 대해 설명합니다.

|매개 변수|설명|
|---------------|-----------------|
|`FrameworkVersion11Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 1.1 어셈블리에 대한 경로가 있는 경우 포함됩니다. 그렇지 않으면 `null`를 반환합니다.|
|`FrameworkVersion20Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 2.0 어셈블리에 대한 경로가 있는 경우 포함됩니다. 그렇지 않으면 `null`를 반환합니다.|
|`FrameworkVersion30Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 3.0 어셈블리에 대한 경로가 있는 경우 포함됩니다. 그렇지 않으면 `null`를 반환합니다.|
|`FrameworkVersion35Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 3.5 어셈블리에 대한 경로가 있는 경우 포함됩니다. 그렇지 않으면 `null`를 반환합니다.|
|`FrameworkVersion40Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 4.0 어셈블리에 대한 경로가 있는 경우 포함됩니다. 그렇지 않으면 `null`를 반환합니다.|
|`Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 사용 가능한 경우 최신 프레임워크 어셈블리에 대한 경로를 포함합니다. 그렇지 않으면 `null`를 반환합니다.|

## <a name="remarks"></a>주의
여러 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 설치한 경우 이 작업은 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 실행하도록 설계한 버전을 반환합니다.

이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension 기본 클래스](../msbuild/taskextension-base-class.md)를 참조하세요.

## <a name="example"></a>예제
다음 예제에서는 `GetFrameworkPath` 작업을 사용하여 `FrameworkPath` 속성에서 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 대한 경로를 저장합니다.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="GetPath">
        <GetFrameworkPath>
            <Output
                TaskParameter="Path"
                PropertyName="FrameworkPath" />
        </GetFrameworkPath>
    </Target>
</Project>
```

## <a name="see-also"></a>참고 항목
- [작업](../msbuild/msbuild-tasks.md)
- [작업 참조](../msbuild/msbuild-task-reference.md)
