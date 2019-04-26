---
title: WPF 소개
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- csharp
- vb
ms.workload:
- multiple
ms.openlocfilehash: d15f0e8e5c5cbdac5a130804977adf90385adfe1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62893925"
---
# <a name="wpf-overview"></a>WPF 개요

WPF(Windows Presentation Foundation)를 사용하면 시각적으로 뛰어난 사용자 환경을 통해 Windows용 데스크톱 클라이언트 애플리케이션을 만들 수 있습니다.

![Contoso Healthcare UI 샘플](../designers/media/wpfintrofigure24.png)

WPF의 핵심은 최신 그래픽 하드웨어를 활용하도록 작성된 해상도 독립적인 벡터 기반 렌더링 엔진입니다. WPF는 XAML(Extensible Application Markup Language), 컨트롤, 데이터 바인딩, 레이아웃, 2D 및 3D 그래픽, 애니메이션, 스타일, 템플릿, 문서, 미디어, 텍스트 및 입력 체계를 포함하는 포괄적인 애플리케이션 개발 기능을 사용하여 핵심을 확장합니다. WPF는 .NET Framework에 포함되어 있으므로 .NET Framework 클래스 라이브러리의 다른 요소를 통합하는 애플리케이션을 빌드할 수 있습니다.

이 개요는 초보자를 위한 것이며 WPF의 주요 기능 및 개념에 대해 설명합니다.

## <a name="program-with-wpf"></a>WPF로 프로그램

WPF는 대부분 <xref:System.Windows> 네임스페이스에 있는 .NET Framework 형식의 하위 집합으로 존재합니다. 이전에 ASP.NET 및 Windows Forms와 같은 관리되는 기술을 사용하여 .NET Framework로 애플리케이션을 빌드한 적이 있는 경우 기본적인 WPF 프로그래밍 환경이 친숙할 것입니다. 모두 C# 또는 Visual Basic과 같은 원하는 .NET 프로그래밍 언어를 사용하여 클래스를 인스턴스화하고, 속성을 설정하고, 메서드를 호출하고, 이벤트를 처리합니다.

WPF에는 속성 및 이벤트를 향상시키는 [종속성 속성](/dotnet/framework/wpf/advanced/dependency-properties-overview) 및 [라우트된 이벤트](/dotnet/framework/wpf/advanced/routed-events-overview)와 같은 추가 프로그래밍 구문이 포함되어 있습니다.

## <a name="markup-and-code-behind"></a>태그 및 코드 숨김

WPF를 사용하면 ASP.NET 개발자에게 익숙한 환경인 *태그* 및 *코드 숨김* 둘 다를 통해 애플리케이션을 개발할 수 있습니다. 일반적으로 XAML 태그를 사용하여 애플리케이션의 모양을 구현하고 관리되는 프로그래밍 언어(코드 숨김)를 사용하여 해당 동작을 구현합니다. 모양 및 동작의 이러한 분리는 다음과 같은 이점이 있습니다.

- 모양 관련 태그가 동작 관련 코드와 밀접하게 결합되지 않으므로 개발 및 유지 관리 비용이 줄어듭니다.

- 디자이너가 애플리케이션의 동작을 구현하는 개발자와 동시에 애플리케이션의 모양을 구현할 수 있으므로 개발이 보다 효율적입니다.

- WPF 애플리케이션에 대한[전역화 및 지역화](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview) 가 간소화됩니다.

### <a name="markup"></a>태그

XAML은 선언적으로 애플리케이션의 모양을 구현하는 XML 기반 태그 언어입니다. 일반적으로 창, 대화 상자, 페이지 및 사용자 정의 컨트롤을 만들고 컨트롤, 도형 및 그래픽으로 채우는 데 사용됩니다.

다음 예제에서는 XAML을 사용하여 단일 단추가 포함된 창의 모양을 구현합니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

특히, 이 XAML은 각각 `Window` 및 `Button` 요소를 사용하여 창과 단추를 정의합니다. 각 요소는 창의 제목 표시줄 텍스트를 지정하는 `Window` 요소의 `Title` 특성과 같은 특성으로 구성됩니다. 런타임에 WPF는 태그에 정의된 요소와 특성을 WPF 클래스 인스턴스로 변환합니다. 예를 들어 `Window` 요소는 <xref:System.Windows.Window.Title%2A> 속성이 `Title` 특성의 값인 <xref:System.Windows.Window> 클래스 인스턴스로 변환됩니다.  

다음 그림은 이전 예제에서 XAML로 정의된 UI(사용자 인터페이스)를 보여 줍니다.

![단추가 있는 창](../designers/media/wpfintrofigure10.png)

XAML은 XML 기반이기 때문에 XAML로 작성한 UI는 [요소 트리](/dotnet/framework/wpf/advanced/trees-in-wpf)라고 하는 중첩된 요소 계층 구조로 어셈블됩니다. 요소 트리는 UI를 만들고 관리하는 논리적이고 직관적인 방법을 제공합니다.

### <a name="code-behind"></a>코드 숨김

애플리케이션의 주요 작업은 이벤트 (예: 메뉴, 도구 모음, 단추 클릭) 처리, 비즈니스 논리 작업 및 데이터 엑세스 응답과 같은 사용자 조작에 맞는 기능을 실행하는 것입니다.  WPF에서 이 동작은 태그와 연결된 코드에서 구현됩니다. 이러한 종류의 코드를 코드 숨김이라고 합니다. 다음 예제에서는 이전 예제의 업데이트된 태그 및 코드 숨김을 보여 줍니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

```csharp
using System.Windows; // Window, RoutedEventArgs, MessageBox 

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI 
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI 
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub 

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub 

    End Class 

End Namespace
```

이 예제에서 코드 숨김은 <xref:System.Windows.Window> 클래스에서 파생된 클래스를 구현합니다. `x:Class` 특성은 태그를 코드 숨김 클래스와 연결하는 데 사용됩니다. `InitializeComponent`는 코드 숨김 클래스를 사용하여 태그에서 정의된 UI를 병합하기 위해 코드 숨김 클래스의 생성자에서 호출됩니다. `InitializeComponent`는 애플리케이션을 빌드할 때 자동으로 생성되므로 직접 구현할 필요가 없습니다. `x:Class` 및 `InitializeComponent`를 조합하면 구현을 만들 때마다 올바르게 초기화됩니다. 코드 숨김 클래스는 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 이벤트 처리기도 구현합니다. 단추를 클릭하면 이벤트 처리기가 <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> 메서드를 호출하여 메시지 상자를 표시합니다.

다음 그림은 단추를 클릭할 때의 결과를 보여 줍니다.

![MessageBox](../designers/media/wpfintrofigure25.png)

## <a name="controls"></a>컨트롤

애플리케이션 모델에서 제공하는 사용자 환경은 생성된 컨트롤입니다. WPF에서 *컨트롤*은 창이나 페이지에서 호스트되고 사용자 인터페이스가 있으며 일부 동작을 구현하는 WPF 클래스의 한 범주에 적용되는 포괄적인 용어입니다.

자세한 내용은 [컨트롤](/dotnet/framework/wpf/controls/index)을 참조하세요.

### <a name="wpf-controls-by-function"></a>기능별 WPF 컨트롤

기본 제공 WPF 컨트롤은 다음과 같습니다.

- **단추**: <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Primitives.RepeatButton>

- **데이터 표시**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>및 <xref:System.Windows.Controls.TreeView>

- **날짜 표시 및 선택**: <xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker>

- **대화 상자**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>및 <xref:Microsoft.Win32.SaveFileDialog>

- **디지털 잉크**: <xref:System.Windows.Controls.InkCanvas> 및 <xref:System.Windows.Controls.InkPresenter>

- **문서**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>및 <xref:System.Windows.Controls.StickyNoteControl>

- **입력**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>및 <xref:System.Windows.Controls.PasswordBox>

- **레이아웃**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>및 <xref:System.Windows.Controls.WrapPanel>

- **미디어**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>및 <xref:System.Windows.Controls.SoundPlayerAction>

- **메뉴**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>및 <xref:System.Windows.Controls.ToolBar>

- **탐색**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>및 <xref:System.Windows.Controls.TabControl>

- **선택**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>및 <xref:System.Windows.Controls.Slider>

- **사용자 정보**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>및 <xref:System.Windows.Controls.ToolTip>

## <a name="input-and-commands"></a>입력 및 명령

컨트롤은 대체로 사용자 입력을 감지하고 응답합니다. [WPF 입력 시스템](/dotnet/framework/wpf/advanced/input-overview) 은 직접 및 라우트된 이벤트를 사용하여 텍스트 입력, 포커스 관리 및 마우스 위치 지정을 지원합니다.

애플리케이션에 복잡한 입력 요구 사항이 있는 경우가 많습니다. WPF는 사용자 입력 작업을 이러한 작업에 응답하는 코드에서 분리하는 [명령 시스템](/dotnet/framework/wpf/advanced/commanding-overview)을 제공합니다.

## <a name="layout"></a>레이아웃

사용자 인터페이스를 만들 때 위치 및 크기별로 컨트롤을 정렬하여 레이아웃을 구성합니다. 모든 레이아웃의 주요 요구 사항은 창 크기와 표시 설정의 변경 내용에 맞게 조정되는 것입니다. 이러한 상황에서 레이아웃을 조정하는 코드를 작성하도록 요구하는 대신 WPF는 확장 가능한 뛰어난 레이아웃 시스템을 제공합니다.

이 레이아웃 시스템의 토대는 상대 위치 지정으로, 변화하는 창과 표시 조건에 맞게 조정하는 기능을 향상시킵니다. 또한 이 레이아웃 시스템은 레이아웃을 결정하기 위한 컨트롤 간의 협상을 관리합니다. 협상은 2단계 프로세스입니다. 첫 번째로, 컨트롤이 필요한 위치 및 크기를 부모에게 알립니다. 두 번째로, 부모가 사용할 수 있는 공간을 컨트롤에 알립니다.

이 레이아웃 시스템은 기본 WPF 클래스를 통해 자식 컨트롤에 노출됩니다. 그리드, 스택 및 도킹과 같은 일반적인 레이아웃을 위해 WPF는 여러 레이아웃 컨트롤을 포함합니다.

- <xref:System.Windows.Controls.Canvas>: 자식 컨트롤이 고유한 레이아웃을 제공합니다.

- <xref:System.Windows.Controls.DockPanel>: 자식 컨트롤이 패널 가장자리에 맞춰집니다.

- <xref:System.Windows.Controls.Grid>: 자식 컨트롤이 행 및 열별로 배치됩니다.

- <xref:System.Windows.Controls.StackPanel>: 자식 컨트롤이 가로 또는 세로로 포개집니다.

- <xref:System.Windows.Controls.VirtualizingStackPanel>: 자식 컨트롤이 가상화되고 가로 또는 세로 방향인 한 줄에 정렬됩니다.

- <xref:System.Windows.Controls.WrapPanel>: 자식 컨트롤이 왼쪽에서 오른쪽 순서로 배치되고 공간에 허용되는 것보다 더 많은 컨트롤이 현재 줄에 있는 경우 다음 줄로 줄 바꿈됩니다.

다음 예제에서는 <xref:System.Windows.Controls.DockPanel> 하나를 사용하여 여러 <xref:System.Windows.Controls.TextBox> 컨트롤을 레이아웃합니다.

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_1.xaml)]

<xref:System.Windows.Controls.DockPanel>을 사용하면 자식 <xref:System.Windows.Controls.TextBox> 컨트롤이 정렬 방법을 알려줄 수 있습니다. 이렇게 하려면 <xref:System.Windows.Controls.DockPanel>은 각각 도킹 스타일을 지정할 수 있도록 자식 컨트롤에 노출되는 `Dock` 속성을 구현합니다.

> [!NOTE]
> 자식 컨트롤에서 사용할 수 있도록 부모 컨트롤이 구현하는 속성은 [연결된 속성](/dotnet/framework/wpf/advanced/attached-properties-overview)이라는 WPF 구문입니다.

다음 그림에서는 이전 예제의 XAML 태그 결과를 보여 줍니다.

![DockPanel 페이지](../designers/media/wpfintrofigure11.png)

## <a name="data-binding"></a>데이터 바인딩

대부분의 애플리케이션은 데이터를 보고 편집할 수 있는 수단을 사용자에게 제공하기 위해 생성됩니다. WPF 애플리케이션의 경우 데이터를 저장 및 액세스하는 작업이 SQL Server 및 ADO .NET과 같은 기술에 의해 이미 제공됩니다. 데이터에 액세스하고 애플리케이션의 관리되는 개체에 로드한 후 WPF 애플리케이션에 대한 힘든 작업이 시작됩니다. 기본적으로 다음 두 가지가 포함됩니다.

1. 관리되는 개체에서 데이터를 표시 및 편집할 수 있는 컨트롤로 데이터 복사

2. 컨트롤을 사용한 데이터 변경 내용이 관리되는 개체에 다시 복사되는지 확인

애플리케이션 개발을 간소화하기 위해 WPF는 이러한 단계를 자동으로 수행하는 데이터 바인딩 엔진을 제공합니다. 데이터 바인딩 엔진의 핵심 단위는 <xref:System.Windows.Data.Binding> 클래스로, 컨트롤(바인딩 대상)을 데이터 개체(바인딩 소스)에 바인딩하는 작업을 수행합니다. 이 관계는 다음 그림에 나와 있습니다.

![기본 데이터 바인딩 다이어그램](../designers/media/databindingmostbasic.png)

다음 예제에서는 <xref:System.Windows.Controls.TextBox>를 사용자 지정 `Person` 개체의 인스턴스에 바인딩하는 방법을 보여 줍니다. `Person` 구현은 다음 코드에 나와 있습니다.

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/VisualBasic/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/CSharp/introduction-to-wpf_2.cs)]

다음 태그는 <xref:System.Windows.Controls.TextBox>를 사용자 지정 `Person` 개체의 인스턴스에 바인딩합니다.

 ```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
 ```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_6.cs)]

이 예제에서 `Person` 클래스는 코드 숨김에서 인스턴스화되고 `DataBindingWindow`에 대한 데이터 컨텍스트로 설정됩니다. 태그에서 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 "`{Binding ... }`" XAML 구문을 사용하는 `Person.Name` 속성에 바인딩됩니다. 이 XAML은 WPF가 <xref:System.Windows.Controls.TextBox> 컨트롤을 해당 창의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 저장된 `Person` 개체에 바인딩되도록 합니다.

WPF 데이터 바인딩 엔진은 유효성 검사, 정렬, 필터링 및 그룹화를 포함하는 추가 지원을 제공합니다. 또한 데이터 바인딩은 표준 WPF 컨트롤에 의해 표시되는 사용자 인터페이스가 적절하지 않은 경우 데이터 템플릿을 사용하여 바인딩된 데이터에 대한 사용자 지정 사용자 인터페이스를 만들 수 있도록 지원합니다.

자세한 내용은 [데이터 바인딩 개요](/dotnet/framework/wpf/data/data-binding-overview)를 참조하세요.

## <a name="graphics"></a>그래픽

WPF는 다음과 같은 이점이 있는 광범위하고 확장 가능하며 유연한 그래픽 집합을 도입합니다.

- **해상도 및 디바이스 독립적인 그래픽**. WPF 그래픽 시스템의 기본 측정 단위는 실제 화면 해상도에 관계없이 1/96인치인 디바이스 독립적 픽셀이며, 해상도 및 디바이스 독립적인 렌더링을 위한 토대를 제공합니다. 각 디바이스 독립적 픽셀은 렌더링되는 시스템의 dpi(인치당 도트 수) 설정에 맞게 자동으로 확장됩니다.

- **향상된 정밀도**. WPF 좌표계는 단정밀도 대신 배정밀도 부동 소수점 숫자로 측정됩니다. 변환 및 불투명도 값도 배정밀도로 표현됩니다. 또한 WPF는 광범위한 색 영역(scRGB)을 지원하며 여러 색 공간의 입력을 관리하기 위한 통합 지원을 제공합니다.

- **고급 그래픽 및 애니메이션 지원**. WPF는 애니메이션 장면을 관리하여 그래픽 프로그래밍을 간소화합니다. 장면 처리, 렌더링 루프 및 쌍선형 보간에 대해 걱정할 필요가 없습니다. 또한 WPF는 적중 테스트 및 전체 알파 합치기를 지원합니다.

- **하드웨어 가속**. WPF 그래픽 시스템은 그래픽 하드웨어를 활용하여 CPU 사용량을 최소화합니다.

### <a name="2d-shapes"></a>2D 도형

WPF는 다음 그림에 표시된 사각형 및 타원과 같은 일반적인 벡터 기반의 2D 도형 라이브러리를 제공합니다.

![타원 및 사각형](../designers/media/wpfintrofigure4.PNG)

도형의 흥미로운 기능은 표시에 사용되는 것뿐 아니라 키보드 및 마우스 입력을 비롯하여 컨트롤에서 기대하는 기능을 대부분 구현한다는 것입니다. 다음 예제에서는 <xref:System.Windows.UIElement.MouseUp> 의 <xref:System.Windows.Shapes.Ellipse> 이벤트가 처리되는 과정을 보여 줍니다.

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_8.cs)]

다음 그림은 위의 코드에서 생성되는 내용을 보여 줍니다.

!["you clicked the ellipse!" 텍스트가 있는 창](../designers/media/wpfintrofigure12.png)

자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](/dotnet/framework/wpf/data/data-binding-overview)를 참조하세요.

### <a name="2d-geometries"></a>2D 기하 도형

WPF에서 제공하는 2D 도형은 기본 도형의 표준 집합을 포함합니다. 그러나 사용자 지정 사용자 인터페이스의 디자인이 용이하도록 사용자 지정 도형을 만들어야 할 수도 있습니다. 이 용도로 WPF는 기하 도형을 제공합니다. 다음 그림은 기하 도형을 사용하여 직접 그리거나, 브러시로 사용하거나, 다른 도형 및 컨트롤을 자르는 데 사용할 수 있는 사용자 지정 도형을 만드는 과정을 보여 줍니다.

<xref:System.Windows.Shapes.Path> 개체는 닫혔거나 열린 도형, 여러 도형 및 곡선 도형을 그리는 데 사용할 수 있습니다.

<xref:System.Windows.Media.Geometry> 개체는 자르기, 적중 테스트 및 2D 그래픽 데이터 렌더링에 사용할 수 있습니다.

![Path의 다양한 용도](../designers/media/wpfintrofigure5.png)

자세한 내용은 [기하 도형 개요](/dotnet/framework/wpf/graphics-multimedia/geometry-overview)를 참조하세요.

### <a name="2d-effects"></a>2D 효과

WPF 2D 기능의 하위 집합에는 그라데이션, 비트맵, 그리기, 비디오로 그리기, 회전, 크기 조정 및 기울이기와 같은 시각 효과가 포함됩니다. 브러시를 통해 이러한 모든 효과를 얻을 수 있습니다. 다음 그림에서는 몇 가지 예를 보여 줍니다.

![여러 브러시의 설명](../designers/media/wpfintrofigure6.png)

자세한 내용은 [WPF 브러시 개요](/dotnet/framework/wpf/graphics-multimedia/wpf-brushes-overview)를 참조하세요.

### <a name="3d-rendering"></a>3D 렌더링

WPF에는 더 흥미로운 사용자 인터페이스를 만들 수 있도록 2D 그래픽을 통합하는 3D 렌더링 기능도 포함되어 있습니다. 예를 들어 다음 그림에서는 3D 도형에 렌더링된 2D 이미지를 보여줍니다.

![Visual3D 샘플 스크린 샷](../designers/media/wpfintrofigure13.png)

자세한 내용은 [3D 그래픽 개요](/dotnet/framework/wpf/graphics-multimedia/3-d-graphics-overview)를 참조하세요.

## <a name="animation"></a>애니메이션

WPF 애니메이션 지원을 사용하면 컨트롤이 커지거나, 흔들리거나, 회전하거나, 사라지도록 하여 흥미로운 페이지 전환 등을 만들 수 있습니다. 사용자 지정 클래스를 비롯한 대부분의 WPF 클래스에 애니메이션 효과를 줄 수 있습니다. 다음 그림에서는 간단한 애니메이션의 작동을 보여 줍니다.

![애니메이션 효과가 적용된 큐브의 이미지](../designers/media/wpfintrofigure7.png)

자세한 내용은 [애니메이션 개요](/dotnet/framework/wpf/graphics-multimedia/animation-overview)를 참조하세요.

## <a name="media"></a>미디어

풍부한 콘텐츠를 전달하는 한 가지 방법은 시청각 미디어를 사용하는 것입니다. WPF는 이미지, 비디오 및 오디오에 대한 특별한 지원을 제공합니다.

### <a name="images"></a>이미지

이미지는 대부분의 애플리케이션에서 공통적으로 사용되며 WPF는 이미지를 사용하는 여러 방법을 제공합니다. 다음 그림에서는 미리 보기 이미지를 포함하는 목록 상자가 있는 사용자 인터페이스를 보여 줍니다. 미리 보기를 선택하면 이미지가 전체 크기로 표시됩니다.

![축소판 이미지 및 전체 크기 이미지](../designers/media/wpfintrofigure8.png)

자세한 내용은 [이미징 개요](/dotnet/framework/wpf/graphics-multimedia/imaging-overview)를 참조하세요.

### <a name="video-and-audio"></a>비디오 및 오디오

<xref:System.Windows.Controls.MediaElement> 컨트롤은 비디오와 오디오를 둘 다 재생할 수 있으며 사용자 지정 미디어 플레이어의 토대가 될 수 있을 정도로 유연합니다. 다음 XAML 태그는 미디어 플레이어를 구현합니다.

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_9.xaml)]

다음 그림의 창에서는 <xref:System.Windows.Controls.MediaElement> 컨트롤의 작동을 보여 줍니다.

![오디오와 비디오가 있는 MediaElement 컨트롤](../designers/media/wpfintrofigure1.png)

자세한 내용은 [그래픽 및 멀티미디어](/dotnet/framework/wpf/graphics-multimedia)를 참조하세요.

## <a name="text-and-typography"></a>텍스트 및 입력 체계

고품질 텍스트 렌더링이 용이하도록 WPF는 다음 기능을 제공합니다.

- OpenType 글꼴 지원

- ClearType 향상

- 하드웨어 가속을 활용하는 고성능

- 미디어, 그래픽 및 애니메이션과 텍스트 통합

- 국가별 글꼴 지원 및 대체(fallback) 메커니즘

텍스트와 그래픽 통합의 데모로, 다음 그림에서는 텍스트 장식의 응용을 보여 줍니다.

![다양한 텍스트 장식이 적용된 텍스트](../designers/media/wpfintrofigure23.png)

자세한 내용은 [Windows Presentation Foundation의 입력 체계](/dotnet/framework/wpf/advanced/typography-in-wpf)를 참조하세요.

## <a name="customize-wpf-apps"></a>WPF 앱 사용자 지정

지금까지 애플리케이션을 개발하기 위한 핵심 WPF 구성 요소를 살펴봤습니다. 애플리케이션 모델을 사용하여 주로 컨트롤로 구성된 애플리케이션 콘텐츠를 호스트 및 제공합니다. 사용자 인터페이스에서 컨트롤 정렬을 간소화하고 창 크기 및 디스플레이 설정이 변경되어도 정렬이 유지되도록 하기 위해 WPF 레이아웃 시스템을 사용합니다. 대부분의 애플리케이션은 사용자의 데이터 조작을 허용하므로 데이터 바인딩을 사용하여 사용자 인터페이스와 데이터 통합 작업을 줄입니다. 애플리케이션의 시각적 모양을 개선하려면 WPF에서 제공하는 광범위한 그래픽, 애니메이션 및 미디어 지원을 사용합니다.

하지만 기본 사항이 고유하고 시각적으로 멋진 사용자 환경을 만들고 관리하는 데 충분하지 않은 경우도 많습니다. 표준 WPF 컨트롤이 원하는 애플리케이션 모양과 통합되지 않을 수 있습니다. 데이터가 가장 효율적인 방식으로 표시되지 않을 수도 있습니다. 애플리케이션의 전반적인 사용자 환경이 Windows 테마의 기본 모양과 느낌에 적합하지 않을 수 있습니다. 여러 측면에서 프레젠테이션 기술은 다른 형식의 확장성만큼 시각적 확장성을 필요로 합니다.

이런 이유로 WPF는 컨트롤, 트리거, 컨트롤 및 데이터 템플릿, 스타일, 사용자 인터페이스 리소스, 테마 및 스킨에 대한 풍부한 콘텐츠 모델을 포함하여 고유한 사용자 환경을 만들기 위한 다양한 메커니즘을 제공합니다.

### <a name="content-model"></a>콘텐츠 모델

대부분의 WPF 컨트롤은 주로 콘텐츠를 표시하는 데 사용됩니다. WPF에서 컨트롤의 콘텐츠를 구성할 수 있는 항목의 유형과 개수를 컨트롤의 *콘텐츠 모델*이라고 합니다. 일부 컨트롤은 단일 항목 및 유형의 콘텐츠를 포함할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.TextBox> 의 콘텐츠는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성에 할당되는 문자열 값입니다. 다음 예제에서는 <xref:System.Windows.Controls.TextBox>의 콘텐츠를 설정합니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

다음 그림에서는 결과를 보여 줍니다.

![텍스트가 포함된 TextBox 컨트롤](../designers/media/wpfintrofigure21.png)

그러나 다른 컨트롤은 다양한 콘텐츠 형식의 여러 항목을 포함할 수 있습니다. <xref:System.Windows.Controls.ContentControl.Content%2A> 속성으로 지정된 <xref:System.Windows.Controls.Button>의 콘텐츠에는 레이아웃 컨트롤, 텍스트, 이미지 및 도형을 포함하여 다양한 항목이 포함될 수 있습니다. 다음 예제에서는 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Border>및 <xref:System.Windows.Controls.MediaElement>를 포함하는 콘텐츠가 있는 <xref:System.Windows.Controls.Button>을 보여 줍니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2"
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>
</Window>
```

다음 그림에서는 이 단추의 콘텐츠를 보여 줍니다.

![여러 형식의 콘텐츠가 포함된 단추](../designers/media/wpfintrofigure22.png)

다양한 컨트롤에서 지원하는 콘텐츠 종류에 대한 자세한 내용은 [WPF 콘텐츠 모델](/dotnet/framework/wpf/controls/wpf-content-model)을 참조하세요.

### <a name="triggers"></a>트리거

XAML 태그의 주요 용도는 애플리케이션의 모양을 구현하는 것이지만 XAML을 사용하여 애플리케이션 동작의 일부 측면을 구현할 수도 있습니다. 한 가지 예는 트리거를 사용하여 사용자 조작에 따라 애플리케이션의 모양을 변경하는 것입니다. 자세한 내용은 [스타일 지정 및 템플릿](/dotnet/framework/wpf/controls/styling-and-templating)을 참조하세요.

### <a name="control-templates"></a>컨트롤 템플릿

WPF 컨트롤의 기본 사용자 인터페이스는 일반적으로 다른 컨트롤 및 도형에서 구성됩니다. 예를 들어 <xref:System.Windows.Controls.Button> 은 <xref:Microsoft.Windows.Themes.ButtonChrome> 및 <xref:System.Windows.Controls.ContentPresenter> 컨트롤 둘 다로 구성됩니다. <xref:Microsoft.Windows.Themes.ButtonChrome> 은 표준 단추 모양을 제공하는 반면, <xref:System.Windows.Controls.ContentPresenter> 는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 지정된 대로 단추의 콘텐츠를 표시합니다.

컨트롤의 기본 모양이 애플리케이션의 전반적인 모양에 맞지 않을 수도 있습니다. 이 경우 <xref:System.Windows.Controls.ControlTemplate> 을 사용하여 해당 콘텐츠 및 동작을 변경하지 않고 컨트롤의 사용자 인터페이스 모양을 변경할 수 있습니다.

예를 들어 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 <xref:System.Windows.Controls.Button>의 모양을 변경하는 방법을 보여 줍니다.

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_17.vb)]

이 예제에서는 기본 단추 사용자 인터페이스가 진한 파란색 테두리가 있는 <xref:System.Windows.Shapes.Ellipse> 로 대체되고 <xref:System.Windows.Media.RadialGradientBrush>를 사용하여 채워집니다. <xref:System.Windows.Controls.ContentPresenter> 컨트롤은 <xref:System.Windows.Controls.Button>의 콘텐츠인 "Click Me!"를 표시합니다. <xref:System.Windows.Controls.Button> 을 클릭하면 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 <xref:System.Windows.Controls.Button> 컨트롤의 기본 동작의 일부로 여전히 발생합니다. 결과는 다음 그림에 나와 있습니다.

![타원형 단추 및 두 번째 창](../designers/media/wpfintrofigure2.png)

### <a name="data-templates"></a>데이터 템플릿

컨트롤 템플릿을 사용하면 컨트롤의 모양을 지정할 수 있는 반면 데이터 템플릿을 사용하면 컨트롤 콘텐츠의 모양을 지정할 수 있습니다. 데이터 템플릿은 바인딩된 데이터가 표시되는 방식을 개선하는 데 자주 사용됩니다. 다음 그림은 각 작업에 이름, 설명 및 우선 순위가 있는 `Task` 개체의 컬렉션에 바인딩된 <xref:System.Windows.Controls.ListBox>의 기본 모양을 보여 줍니다.

![기본 모양의 목록 상자](../designers/media/wpfintrofigure18.png)

기본 모양은 <xref:System.Windows.Controls.ListBox>에서 예상되는 모양입니다. 그러나 각 작업의 기본 모양은 작업 이름만 포함합니다. 작업 이름, 설명 및 우선 순위를 표시하려면 <xref:System.Windows.DataTemplate>을 사용하여 <xref:System.Windows.Controls.ListBox> 컨트롤의 바인딩된 목록 항목에 대한 기본 모양을 변경해야 합니다. 다음 XAML은 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>특성을 사용하여 각 작업에 적용되는 이러한 <xref:System.Windows.DataTemplate>  을 정의합니다.

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2"
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>

    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox
      ItemsSource="{Binding}"
      ItemTemplate="{StaticResource myTaskTemplate}"
      HorizontalContentAlignment="Stretch"
      IsSynchronizedWithCurrentItem="True"
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```

다음 그림에서는 이 코드의 영향을 보여 줍니다.

![데이터 템플릿을 사용하는 목록 상자](../designers/media/wpfintrofigure19.png)

<xref:System.Windows.Controls.ListBox>의 동작과 전반적인 모양은 유지되고 목록 상자에 표시되는 콘텐츠의 모양만 변경되었습니다.

자세한 내용은 [데이터 템플릿 개요](/dotnet/framework/wpf/data/data-templating-overview)를 참조하세요.

### <a name="styles"></a>스타일

스타일을 사용하면 개발자와 디자이너가 해당 제품에 대해 특정 모양을 표준화할 수 있습니다. WPF는 <xref:System.Windows.Style> 요소를 기반으로 하는 강력한 스타일 모델을 제공합니다. 다음 예제에서는 창에 있는 모든 <xref:System.Windows.Controls.Button>의 배경색을 `Orange`로 설정하는 스타일을 만듭니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>
</Window>
```

이 스타일은 모든 <xref:System.Windows.Controls.Button> 컨트롤을 대상으로 하기 때문에 다음 그림과 같이 창에 있는 모든 단추에 스타일이 자동으로 적용됩니다.

![두 개의 주황색 단추](../designers/media/wpfintrofigure20.png)

자세한 내용은 [스타일 지정 및 템플릿](/dotnet/framework/wpf/controls/styling-and-templating)을 참조하세요.

### <a name="resources"></a>자료

애플리케이션의 컨트롤은 글꼴 및 배경색부터 컨트롤 템플릿, 데이터 템플릿 및 스타일까지 모든 항목을 포함할 수 있는 동일한 모양을 공유해야 합니다. 사용자 인터페이스 리소스에 대한 WPF 지원을 사용하여 재사용을 위해 이러한 리소스를 단일 위치에 캡슐화할 수 있습니다.

다음 예제에서는 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Label>에서 공유하는 공통 배경색을 정의합니다.

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

이 예제에서는 `Window.Resources` 속성 요소를 사용하여 배경색 리소스를 구현합니다. 이 리소스는 <xref:System.Windows.Window>의 모든 자식에서 사용할 수 있습니다. 다음을 포함하여 다양한 리소스 범위가 있습니다(확인되는 순서대로 나열됨).

1. 개별 컨트롤(상속된 <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> 속성 사용)

2. <xref:System.Windows.Window> 또는 <xref:System.Windows.Controls.Page> (또한 상속된 <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> 속성 사용)

3. <xref:System.Windows.Application> ( <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> 속성 사용)

다양한 범위는 리소스를 정의 및 공유하는 방법과 관련해서 유연성을 제공합니다.

리소스를 특정 범위에 직접 연결하는 대신, 애플리케이션의 다른 부분에서 참조할 수 있는 별도 <xref:System.Windows.ResourceDictionary> 를 사용하여 하나 이상의 리소스를 패키지할 수 있습니다. 예를 들어 다음 예제에서는 리소스 사전의 기본 배경색을 정의합니다.

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

 다음 예제에서는 애플리케이션 간에 공유되도록 이전 예제에서 정의된 리소스 사전을 참조합니다.

```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">

  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

리소스 및 리소스 사전은 테마 및 스킨에 대한 WPF 지원의 기반이 됩니다.

자세한 내용은 [리소스](/dotnet/framework/wpf/advanced/xaml-resources)를 참조하세요.

### <a name="custom-controls"></a>사용자 지정 컨트롤

WPF는 다양한 사용자 지정 지원을 제공하지만 기존 WPF 컨트롤이 애플리케이션 또는 해당 사용자의 요구를 충족하지 않는 경우가 발생할 수 있습니다. 이 오류는 다음과 같은 경우에 발생할 수 있습니다.

- 사용자가 요구하는 사용자 인터페이스가 기존 WPF 가 구현하는 모양이나 느낌으로 만들 수 없는 경우

- 필요한 동작이 기존 WPF 구현에서 지원되지 않는 경우(또는 쉽게 지원되지 않는 경우)

그러나 이제 세 가지 WPF 모델 중 하나를 활용하여 새 컨트롤을 만들 수 있습니다. 각 모델은 특정 시나리오를 대상으로 하며, 특정 WPF 기본 클래스에서 사용자 지정 컨트롤을 파생시켜야 합니다. 세 가지 모델은 다음과 같습니다.

- **사용자 정의 컨트롤 모델**. 사용자 지정 컨트롤은 <xref:System.Windows.Controls.UserControl> 에서 파생되며 하나 이상의 다른 컨트롤로 구성됩니다.

- **컨트롤 모델**. 사용자 지정 컨트롤은 <xref:System.Windows.Controls.Control> 에서 파생되며 대부분의 WPF 컨트롤과 마찬가지로 템플릿을 사용하여 모양과 동작을 구분하는 구현을 작성하는 데 사용됩니다. <xref:System.Windows.Controls.Control> 에서 파생시키는 경우 사용자 정의 컨트롤보다 더 자유롭게 사용자 지정 사용자 인터페이스를 만들 수 있지만 더 많은 노력이 필요할 수 있습니다.

- **프레임워크 요소 모델**. 사용자 지정 컨트롤은 모양이 사용자 지정 렌더링 논리(템플릿 아님)에 의해 정의되는 경우 <xref:System.Windows.FrameworkElement> 에서 파생됩니다.

다음 예제에서는 <xref:System.Windows.Controls.UserControl>에서 파생되는 사용자 지정 숫자 위로/아래로 컨트롤을 보여 줍니다.

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/CSharp/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/VisualBasic/introduction-to-wpf_34.vb)]

다음 예제에서는 사용자 정의 컨트롤을 <xref:System.Windows.Window>에 통합하는 데 필요한 XAML을 보여 줍니다.

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](../designers/codesnippet/Xaml/introduction-to-wpf_37.xaml)]

다음 그림에서는 <xref:System.Windows.Window>에 호스트된 `NumericUpDown` 컨트롤을 보여 줍니다.

![사용자 지정 UserControl](../designers/media/wpfintrofigure3.png)

사용자 지정 컨트롤에 대한 자세한 내용은 [컨트롤 제작 개요](/dotnet/framework/wpf/controls/control-authoring-overview)를 참조하세요.

## <a name="wpf-best-practices"></a>WPF 모범 사례

모든 개발 플랫폼과 마찬가지로 WPF를 다양한 방법으로 사용하여 원하는 결과를 얻을 수 있습니다. WPF 애플리케이션이 필요한 사용자 환경을 제공하고 일반적인 사용자 요구를 충족하도록 하는 한 가지 방법으로 접근성, 전역화 및 지역화, 성능에 대한 권장 모범 사례가 있습니다. 자세한 내용은 다음을 참조하세요.

- [액세스 가능성](/dotnet/framework/ui-automation/accessibility-best-practices)
- [WPF 전역화 및 지역화](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview)
- [WPF 앱 성능](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)
- [WPF 보안](/dotnet/framework/wpf/security-wpf)

## <a name="next-steps"></a>다음 단계

WPF의 주요 기능을 살펴보았습니다. 이제 첫 번째 WPF 앱을 만들 순서입니다.

> [!div class="nextstepaction"]
> [연습: 내 첫 WPF 데스크톱 앱](/dotnet/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application)

## <a name="see-also"></a>참고 항목

- [WPF 시작](../designers/getting-started-with-wpf.md)
- [Windows Presentation Foundation](/dotnet/framework/wpf/index)
- [WPF 커뮤니티 리소스](/dotnet/framework/wpf/getting-started/community-feedback)