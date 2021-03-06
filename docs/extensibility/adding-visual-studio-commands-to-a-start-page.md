---
title: 시작 페이지에 시각적 스튜디오 명령 추가 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- start page commands
- vs:VSCommands
ms.assetid: a8e2765c-cfb5-47b5-a414-6e48b434e0c2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: 13dd40006039209b06cc6a71760fdbaa240db4fe
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80740120"
---
# <a name="add-visual-studio-commands-to-a-start-page"></a>시작 페이지에 시각적 스튜디오 명령 추가

사용자 지정 시작 페이지를 만들 때 Visual Studio 명령을 추가할 수 있습니다. 이 문서에서는 시작 페이지에서 Visual Studio 명령을 XAML 개체에 바인딩하는 다양한 방법에 대해 설명합니다.

XAML의 명령에 대한 자세한 내용은 [명령 개요를](/dotnet/framework/wpf/advanced/commanding-overview) 참조하십시오.

## <a name="add-commands-from-the-command-well"></a>명령에서 명령을 잘 추가합니다.

사용자 지정 시작 페이지 [만들기에서](../extensibility/creating-a-custom-start-page.md) 만든 <xref:Microsoft.VisualStudio.PlatformUI?displayProperty=fullName> <xref:Microsoft.VisualStudio.Shell?displayProperty=fullName> 시작 페이지는 다음과 같이 및 네임스페이스를 추가했습니다.

```xml
xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"
xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"
```

어셈블리 Microsoft.VisualStudio.Shell에서 Microsoft.VisualStudio.Shell에 대한 다른 네임스페이스를 *추가합니다.11.0.dll*. (프로젝트에서 이 어셈블리에 대한 참조를 추가해야 할 수 있습니다.)

```xml
xmlns:vscom="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"
```

별칭을 `vscom:` 사용하여 컨트롤의 <xref:System.Windows.Controls.Primitives.ButtonBase.Command%2A> 속성을 로 설정하여 페이지의 XAML 컨트롤에 Visual Studio `vscom:VSCommands.ExecuteCommand`명령을 바인딩할 수 있습니다. 그런 다음 예제와 같이 <xref:System.Windows.Controls.Primitives.ButtonBase.CommandParameter%2A> 속성을 실행할 명령이름으로 설정할 수 있습니다.

```xml
<Button Name="btnNewProj" Content="New Project"
    Command="{x:Static vscom:VSCommands.ExecuteCommand}"
    CommandParameter="File.NewProject" >
</Button>
```

> [!NOTE]
> XAML 스키마를 참조하는 `x:` 별칭은 모든 명령의 시작 부분에 필요합니다.

 명령 창에서 액세스할 `Command` 수 있는 모든 명령으로 속성 **Command** 값을 설정할 수 있습니다. 사용 가능한 명령 목록은 [Visual Studio 명령 별칭을](../ide/reference/visual-studio-command-aliases.md)참조하십시오.

 추가할 명령에 추가 매개 변수가 필요한 경우 `CommandParameter` 속성 값에 추가할 수 있습니다. 다음 예제와 같이 공백을 사용하여 명령에서 매개 변수를 분리합니다.

```xml
<Button Content="Web Search"
        Command="{x:Static vscom:VSCommands.ExecuteCommand}"
        CommandParameter="View.WebBrowser www.bing.com" />
```

### <a name="call-extensions-from-the-command-well"></a>명령에서 확장을 호출합니다.
 다른 Visual Studio 명령을 호출하는 데 사용되는 구문을 사용하여 등록된 VSPackage의 명령을 호출할 수 있습니다. 예를 들어 설치된 VSPackage가 **보기** 메뉴에 **홈 페이지** 명령을 추가하는 경우 `CommandParameter` 을 `View.HomePage`클릭하여 해당 명령을 호출할 수 있습니다.

> [!NOTE]
> VSPackage와 연결된 명령을 호출하는 경우 명령을 호출할 때 패키지를 로드해야 합니다.

## <a name="add-commands-from-assemblies"></a>어셈블리에서 명령 추가
 어셈블리에서 명령을 호출하거나 메뉴 명령과 연결되지 않은 VSPackage의 코드에 액세스하려면 어셈블리에 대한 별칭을 만든 다음 별칭을 호출해야 합니다.

### <a name="to-call-a-command-from-an-assembly"></a>어셈블리에서 명령을 호출하려면

1. 솔루션에서 어셈블리에 대한 참조를 추가합니다.

2. *StartPage.xaml* 파일 의 맨 위에 다음 예제와 같이 어셈블리에 대한 네임스페이스 지시문을 추가합니다.

    ```xml
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"
    ```

3. 다음 예제와 같이 XAML 개체의 `Command` 속성을 설정하여 명령을 호출합니다.

     Xaml

    ```
    <vs:Button Text="Hide me" Command="{x:Static vsc:HideControl}" .../>
    ```

> [!NOTE]
> 어셈블리를 복사한 다음 *..에 붙여넣아야 합니다. \\{Visual Studio 설치\* 폴더}\Common7\IDE\Private어셈블리를 호출하기 전에 로드되었는지 확인합니다.

## <a name="add-commands-with-the-dte-object"></a>DTE 개체로 명령 추가
 태그와 코드 모두에서 시작 페이지에서 DTE 개체에 액세스할 수 있습니다.

 태그에서 [바인딩 태그 확장](/dotnet/framework/wpf/advanced/binding-markup-extension) 구문을 사용 하 여 <xref:EnvDTE.DTE> 개체를 호출 하 여 액세스할 수 있습니다. 이 방법을 사용하여 컬렉션을 반환하는 속성과 같은 간단한 속성에 바인딩할 수 있지만 메서드 또는 서비스에 바인딩할 수는 없습니다. 다음 예제에서는 <xref:System.Windows.Controls.TextBlock> <xref:EnvDTE._DTE.Name%2A> 속성에 바인딩하는 <xref:System.Windows.Controls.ListBox> 컨트롤과 속성에서 반환되는 컬렉션의 <xref:EnvDTE.Window.Caption%2A> 속성을 여과하는 컨트롤을 <xref:EnvDTE._DTE.Windows%2A> 보여 주었습니다.

```xml
<TextBlock Text="{Binding Path=DTE.Name}" FontSize="12" HorizontalAlignment="Center"/>
<ListBox ItemsSource="{Binding Path=DTE.Windows}">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Path=Caption}"/>
        </DataTemplate>
    </ListBox.ItemTemplate>
</ListBox
```

 예를 들어 [연습: 시작 페이지에서 사용자 설정 저장을](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)참조하십시오.

## <a name="see-also"></a>참조

- [시작 페이지에 사용자 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)
