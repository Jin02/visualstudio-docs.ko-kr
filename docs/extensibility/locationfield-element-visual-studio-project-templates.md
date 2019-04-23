---
title: LocationField 요소 (Visual Studio 프로젝트 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f55c67fbad80b05431ed13439584d3a94fa88c65
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60078306"
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField 요소 (Visual Studio 프로젝트 템플릿)
지정 여부는 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자 활성화, 비활성화 또는 프로젝트 템플릿에 대 한 숨겨진 합니다.

 \<VSTemplate > \<TemplateData > \<LocationField >

## <a name="syntax"></a>구문

```
<LocationField> Enabled/Disabled/Hidden </LocationField>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성
 없음

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고 표시 하는 방법을 정의 합니다 **새 프로젝트**합니다.|

## <a name="text-value"></a>텍스트 값
 텍스트 값은 필수입니다.

 유효한 텍스트 값은

- `Enabled`를 지정 하는 **위치** 상자를 **새 프로젝트** 대화 상자가 활성화 됩니다.

- `Disabled`를 지정 하는 합니다 **위치** 상자를 **새 프로젝트** 대화 상자는 비활성화 됩니다.

- `Hidden`를 지정 하는 합니다 **위치** 상자를 **새 프로젝트** 대화 상자가 숨겨집니다.

## <a name="remarks"></a>설명
 기본값은 `Enabled`입니다.

 합니다 **위치** 텍스트 상자에 **새 프로젝트** 대화 상자가 새 프로젝트 저장 되는 기본 디렉터리를 변경할 수 있습니다.

 지정 된 값은 `Location` 요소 기본 프로젝트 시스템에서 지 원하는 경우에 대화 상자에서 적용 됩니다.

## <a name="example"></a>예제
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 템플릿의 메타데이터를 보여 줍니다.

```
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <LocationField>Disabled</LocationField>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>참고자료
- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)