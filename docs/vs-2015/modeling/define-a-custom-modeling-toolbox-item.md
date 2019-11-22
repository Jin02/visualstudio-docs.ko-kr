---
title: Define a custom modeling toolbox item | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML - extending, customizing the toolbox
ms.assetid: a2463606-1100-40ac-97f3-5ba22ca47b7c
caps.latest.revision: 33
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ac299f18e544ef4f3215707abbdc3d9e8d266de6
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74299294"
---
# <a name="define-a-custom-modeling-toolbox-item"></a>사용자 지정 모델링 도구 상자 항목 정의
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

자주 사용하는 패턴에 따라 요소 또는 요소 그룹을 쉽게 만들 수 있도록 Visual Studio의 모델링 다이어그램 도구 상자에 새로운 도구를 추가할 수 있습니다. 다른 Visual Studio 사용자에게 이러한 도구 상자 항목을 배포할 수 있습니다.

 이 기능을 지원하는 Visual Studio 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)을 참조하세요.

 사용자 지정 도구는 다이어그램에서 하나 이상의 새 요소를 만듭니다. 예를 들어 다음과 같은 요소를 만드는 사용자 지정 도구를 만들 수 있습니다.

- .NET 프로필 및 .NET 스테레오타입을 가진 클래스에 연결된 패키지

- 관찰자 패턴을 나타내기 위해 연결에 의해 연결된 클래스 쌍

> [!NOTE]
> 이 방법을 사용하여 요소 도구를 만들 수 있습니다. 즉, 도구 상자에서 다이어그램으로 끌어오는 도구를 만들 수 있습니다. 연결선 도구는 만들 수 없습니다.

## <a name="DefineTool"></a> Defining a Custom Modeling Tool

#### <a name="to-define-a-custom-modeling-tool"></a>사용자 지정 모델링 도구를 정의하려면

1. 요소 또는 요소 그룹을 포함하는 UML 다이어그램을 만듭니다.

    - 이러한 요소는 요소 간에 관계가 있을 수 있으며 포트, 특성, 작업 또는 핀과 같은 보조 요소를 포함할 수 있습니다.

2. 새 도구에 지정하려는 이름을 사용하여 다이어그램을 저장합니다. On the **File** menu, use **Save…As**.

3. Windows 탐색기를 사용하여 다음 폴더나 하위 폴더에 두 개의 다이어그램 파일을 복사합니다.

     *YourDocuments* **\Visual Studio\Architecture Tools\Custom Toolbox Items**

    - 이 폴더가 없는 경우 새로 만듭니다. You might have to create both **Architecture Tools** and **Custom Toolbox Items**.

    - Copy both diagram files, one with a name that ends "…**diagram**" and the other with a name that ends "…**diagram.layout**"

    - 사용자 지정 도구를 원하는 개수만큼 만들 수 있습니다. 각 도구에 대해 하나의 다이어그램을 사용합니다.

4. (Optional) Create a **.tbxinfo** file as described in [How to Define the Properties of Custom Tools](#tbxinfo), and add it to the same directory. 이렇게 하면 도구 상자 아이콘, 도구 설명 등을 정의할 수 있습니다.

    - A single **.tbxinfo** file can be used to define several tools. 하위 폴더에 있는 다이어그램 파일을 참조할 수 있습니다.

5. Visual Studio를 다시 시작합니다. 해당 다이어그램 형식의 도구 상자에 추가 도구가 나타납니다.

### <a name="what-the-custom-tool-will-replicate"></a>사용자 지정 도구에 의해 복제되는 항목
 사용자 지정 도구는 소스 다이어그램의 기능을 대부분 복제합니다.

- 이름. 도구 상자에서 항목을 만들 때 동일한 네임스페이스에서 중복된 이름을 방지하기 위해 필요한 경우 이름의 끝에 번호가 추가됩니다.

- 색, 크기 및 모양

- 스테레오타입 및 패키지 프로필

- 추상과 같은 속성 값

- 연결된 작업 항목

- 복합성 및 관계의 기타 속성

- 모양의 상대 위치

  다음 기능은 사용자 지정 도구에서 유지되지 않습니다.

- 단순 도형. 모델 요소와 관련이 없으며 일부 종류의 다이어그램에서 그릴 수 있는 모양입니다.

- 연결선 경로 지정. 연결선 경로를 수동으로 지정하는 경우 도구를 사용할 때 경로 지정이 유지되지 않습니다. 포트와 같은 일부 중첩된 모양의 위치는 소유자를 기준으로 유지되지 않습니다.

## <a name="tbxinfo"></a> How to Define the Properties of Custom Tools
 A toolbox information ( **.tbxinfo**) file allows you to specify a toolbox name, icon, tooltip, tab, and help keyword for one or more custom tools. Give it any name, such as **MyTools.tbxinfo**.

 일반적인 파일 형식은 다음과 같습니다.

```
<?xml version="1.0" encoding="utf-8" ?>
<customToolboxItems xmlns="http://schemas.microsoft.com/visualstudio/[version]/ArchitectureTools/CustomToolboxItems">
  <customToolboxItem fileName="MyObserverTool.classdiagram">
    <displayName>
       <value>Observer Pattern</value>
    </displayName>
    <tabName>
       <value>UML Class Diagram</value>
    </tabName>
    <image><bmp fileName="ObserverPatternIcon.bmp"/></image>
    <f1Keyword>
      <value>ObserverPatternHelp</value>
    </f1Keyword>
    <tooltip>
       <value>Create a pair of classes</value>
    </tooltip>
  </customToolboxItem>
</customToolboxItems>
```

 각 항목의 값은 다음 중 하나일 수 있습니다.

- 예제와 같이 도구 상자 아이콘은 `<bmp fileName="…"/>`이고, 다른 항목은 `<value>string</value>`입니다.

  \- 또는 -

- `<resource fileName="Resources.dll"`

   `baseName="Observer.resources" id="Observer.tabname" />`

   이 경우 문자열 값이 리소스로 컴파일된, 컴파일된 어셈블리를 제공합니다.

  정의할 각 도구 상자 항목에 대한 `<customToolboxItem>` 노드를 추가합니다.

  The nodes in the **.tbxinfo** file are as follows. 각 노드에 대한 기본값이 있습니다.

|노드 이름|정의|
|---------------|-------------|
|displayName|도구 상자 항목의 이름입니다.|
|tabName|항목이 표시되어야 하는 도구 상자 탭입니다. 이 다이어그램 형식에 대한 일반 탭의 이름이나 별도 이름을 지정할 수 있습니다.|
|이미지|The location of the bitmap ( **.bmp**) file, which must have height and width of 16, and a color depth of 24 bits.|
|f1Keyword|도움말 항목을 찾는 키워드입니다.|
|도구 설명|이 도구에 대한 도구 설명입니다.|

 Visual Studio에서 비트맵 파일을 편집하고 속성 창에서 해당 높이와 너비를 16으로 설정할 수 있습니다.

> [!NOTE]
> 자체적으로 다이어그램 파일을 사용하여 실험한 후 .tbxinfo 파일 사용을 시작하는 경우 도구 상자에 기존 및 새 버전의 도구 상자 항목이 모두 포함될 수도 있습니다. 이 문제는 .tbxinfo 파일에 다이어그램 파일의 이름을 잘못 입력한 경우에도 발생할 수 있습니다. If this occurs, on the shortcut menu of the toolbox choose **Reset Toolbox**. 사용자 지정 도구 상자 항목이 사라집니다. Visual Studio를 다시 시작하면 올바른 사용자 지정 항목이 나타납니다.

## <a name="Extension"></a> How to Distribute Toolbox Items in a Visual Studio Extension
 You can distribute toolbox items to other [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] users by packaging them into a Visual Studio Extension (VSIX). 동일한 VSIX 파일에 명령, 프로필 및 기타 확장을 패키징할 수 있습니다. For more information, see [Deploying Visual Studio Extensions](https://go.microsoft.com/fwlink/?LinkId=160780).

 Visual Studio 확장을 빌드하는 일반적인 방법은 VSIX 프로젝트 템플릿을 사용하는 것입니다. 이렇게 하려면 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]가 설치되어 있어야 합니다.

#### <a name="to-add-a-toolbox-item-to-a-visual-studio-extension"></a>Visual Studio 확장에 도구 상자 항목을 추가하려면

1. [Create and test one or more custom tools](#DefineTool).

2. [Create a .tbxinfo file](#tbxinfo) that references the tools.

3. 기존 Visual Studio 확장 프로젝트를 엽니다.

     \- 또는 -

     새 Visual Studio 확장 프로젝트를 정의합니다.

    1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

    2. In the **New Project** dialog box, under **Installed Templates**, choose **Visual C#** , **Extensibility**, **VSIX project**.

4. 프로젝트에 도구 상자 정의를 추가합니다. Include the **.tbxinfo** file, the diagram files, bitmap files, and any resource files, and make sure that they are included in the VSIX.

    - In Solution Explorer, on the shortcut menu of the VSIX project, choose **Add**, **Existing Item**. In the dialog box, set **Objects of Type: All Files**. Locate the files, select them all, and then choose **Add**.

        > [!NOTE]
        > 이 프로젝트에서는 모델 편집기에서 다이어그램 파일을 열 수 없습니다.

5. 방금 추가한 모든 파일의 다음 속성을 설정합니다. 솔루션 탐색기에서 모두 선택하여 동시에 해당 속성을 설정할 수 있습니다. 프로젝트에 있는 다른 파일의 속성을 변경하지 않도록 주의하세요.

     **Copy to Output Directory** = **Copy Always**

     **Build Action** = **Content**

     **Include in VSIX** = **true**

6. **source.extension.vsixmanifest**를 엽니다. 확장 매니페스트 편집기에서 열립니다.

7. Under **Metadata**, add a description for the custom tools.

     Under **Assets**, choose **New** and then set the fields in the dialog as follows:

    - **Type** = **Custom Extension Type**

    - 형식 = `Microsoft.VisualStudio.ArchitectureTools.CustomToolboxItems`

        > [!NOTE]
        > 이는 드롭다운 목록의 옵션 중 하나가 아닙니다. 키보드를 사용하여 입력해야 합니다.

    - **Source** = **File on filesystem**.

    - **Path** = your **.tbxinfo** file, for example **MyTools.tbxinfo**

8. 프로젝트를 빌드합니다.

9. **To verify that the extension works**, press F5. Visual Studio의 실험적 인스턴스가 시작됩니다.

     실험적 인스턴스에서 관련 형식의 UML 다이어그램을 만들거나 엽니다. 도구 상자에 새 도구가 나타나고 요소를 제대로 만드는지 확인합니다.

10. **To obtain a VSIX file for deployment:** In Windows Explorer, open the folder **.\bin\Debug** or **.\bin\Release** to find the **.vsix** file. 이 파일은 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] 확장 파일입니다. 사용자 컴퓨터에 설치할 수 있으며 다른 Visual Studio 사용자에게 전송할 수도 있습니다.

#### <a name="to-install-custom-tools-from-a-visual-studio-extension"></a>Visual Studio 확장에서 사용자 지정 도구를 설치하려면

1. Windows 탐색기 또는 Visual Studio에서 `.vsix` 파일을 엽니다.

2. Choose **Install** in the dialog box that appears.

3. To uninstall or temporarily disable the extension, open **Extensions and Updates** from the **Tools** menu.

## <a name="localization"></a>지역화
 다른 컴퓨터에 설치될 때 대상 컴퓨터의 언어로 도구 이름 및 도구 설명을 표시하는 확장을 만들 수 있습니다.

#### <a name="to-provide-versions-of-the-tool-in-more-than-one-language"></a>두 개 이상의 언어로 도구 버전을 제공하려면

1. 사용자 지정 도구를 하나 이상 포함하는 Visual Studio 확장 프로젝트를 만듭니다.

    In the **.tbxinfo** file, use the resource file method to define the tool's `displayName`, toolbox `tabName`, and the tooltip. 이러한 문자열이 정의된 리소스 파일을 만들고 어셈블리로 컴파일한 다음 tbxinfo 파일에서 참조합니다.

2. 다른 언어의 문자열이 있는 리소스 파일을 포함하는 추가 어셈블리를 만듭니다.

3. 이름이 언어의 문화권 코드인 폴더에 각 추가 어셈블리를 배치합니다. For example, place a French version of the assembly inside a folder that is named **fr**.

4. `fr-CA`와 같은 특정 문화권이 아니라 일반적으로 두 문자로 이루어진 중립 문화권 코드를 사용해야 합니다. For more information about culture codes, see [CultureInfo.GetCultures method](https://go.microsoft.com/fwlink/?LinkId=160782), which provides a complete list of culture codes.

5. Visual Studio 확장을 빌드하고 배포합니다.

6. 다른 컴퓨터에 확장을 설치하면 사용자의 로컬 문화권에 대한 리소스 파일 버전이 자동으로 로드됩니다. 사용자 문화권에 대한 버전을 제공하지 않은 경우 기본 리소스가 사용됩니다.

   이 방법을 사용하여 여러 버전의 프로토타입 다이어그램을 설치할 수 없습니다. 요소 및 연결선의 이름이 모든 설치에서 동일합니다.

## <a name="other-toolbox-operations"></a>기타 도구 상자 작업
 일반적으로 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]에서 도구 이름을 바꾸고, 다른 도구 상자 탭으로 이동하고, 삭제하여 도구 상자를 개인 설정할 수 있습니다. 그러나 이 항목에서 설명한 절차에 따라 만든 사용자 지정 모델링 도구에 대해서는 이러한 변경 내용이 유지되지 않습니다. [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]를 다시 시작하면 사용자 지정 도구가 정의된 이름 및 도구 상자 위치로 다시 나타납니다.

 Furthermore, your custom tools will disappear if you perform the **Reset Toolbox** command. 그러나 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]를 다시 시작하면 다시 나타납니다.

## <a name="see-also"></a>관련 항목:
 [Extend UML models and diagrams](../modeling/extend-uml-models-and-diagrams.md) [Define a profile to extend UML](../modeling/define-a-profile-to-extend-uml.md) [Define a menu command on a modeling diagram](../modeling/define-a-menu-command-on-a-modeling-diagram.md) [Define validation constraints for UML models](../modeling/define-validation-constraints-for-uml-models.md)
