---
title: Touch 작업 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 873783196a3eebdaca9cc4278b091e084c1488b0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631655"
---
# <a name="touch-task"></a>Touch 작업

파일의 액세스 및 수정 시간을 설정합니다.

## <a name="parameters"></a>매개 변수

 다음 표에서는 `Touch` 작업의 매개 변수에 대해 설명합니다.

|매개 변수|Description|
|---------------|-----------------|
|`AlwaysCreate`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 아직 없는 모든 파일을 만듭니다.|
|`Files`|필수 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 터치할 파일 컬렉션을 지정합니다.|
|`ForceTouch`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 파일이 읽기 전용인 경우에도 파일 터치를 적용합니다.|
|`Time`|선택적 `String` 매개 변수입니다.<br /><br /> 현재 시간 이외의 시간을 지정합니다. 형식이 <xref:System.DateTime.Parse%2A> 메서드에 사용할 수 있는 형식이어야 합니다.|
|`TouchedFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 성공적으로 터치한 항목 컬렉션을 포함합니다.|

## <a name="remarks"></a>설명

 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension 기본 클래스](../msbuild/taskextension-base-class.md)를 참조하세요.

## <a name="example"></a>예제

 다음 예제에서는 `Touch` 작업을 사용하여 `Files` 항목 컬렉션에 지정된 파일의 액세스 및 수정 시간을 변경하고 성공적으로 터치한 파일을 `FilesTouched` 항목 컬렉션에 추가합니다.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

<ItemGroup>
    <Files Include="File1.cs;File2.cs;File3.cs" />
</ItemGroup>

    <Target Name="TouchFiles">
        <Touch
            Files="@(Files)">
            <Output
                TaskParameter="TouchedFiles"
                ItemName="FilesTouched"/>
    </Touch>
</Target>
</Project>
```

## <a name="see-also"></a>참고 항목

- [작업](../msbuild/msbuild-tasks.md)
- [작업 참조](../msbuild/msbuild-task-reference.md)
