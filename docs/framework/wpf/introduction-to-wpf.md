---
title: WPF 소개
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: d8ea49bbe400c5ec478a94ad7c1adb759af28abb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454201"
---
# <a name="wpf-overview"></a><span data-ttu-id="089fe-102">WPF 개요</span><span class="sxs-lookup"><span data-stu-id="089fe-102">WPF overview</span></span>

<span data-ttu-id="089fe-103">WPF(Windows Presentation Foundation)를 사용하면 시각적으로 뛰어난 사용자 환경을 통해 Windows용 데스크톱 클라이언트 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-103">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Contoso Healthcare UI 샘플](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="089fe-105">WPF의 핵심은 최신 그래픽 하드웨어를 활용하도록 작성된 해상도 독립적인 벡터 기반 렌더링 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-105">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="089fe-106">WPF는 XAML(Extensible Application Markup Language), 컨트롤, 데이터 바인딩, 레이아웃, 2D 및 3D 그래픽, 애니메이션, 스타일, 템플릿, 문서, 미디어, 텍스트 및 입력 체계를 포함하는 포괄적인 애플리케이션 개발 기능을 사용하여 핵심을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-106">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="089fe-107">WPF는 .NET의 일부이므로, .NET API의 다른 요소를 통합하는 애플리케이션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-107">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="089fe-108">이 개요는 초보자를 위한 것이며 WPF의 주요 기능 및 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-108">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="089fe-109">WPF로 프로그램</span><span class="sxs-lookup"><span data-stu-id="089fe-109">Program with WPF</span></span>

<span data-ttu-id="089fe-110">WPF는 대부분 <xref:System.Windows> 네임스페이스에 있는 .NET 형식의 하위 집합으로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-110">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="089fe-111">이전에 ASP.NET 및 Windows Forms와 같은 관리되는 기술을 사용하여 .NET으로 애플리케이션을 빌드한 적이 있는 경우 기본적인 WPF 프로그래밍 환경이 친숙할 것입니다. C# 또는 Visual Basic과 같은 원하는 .NET 프로그래밍 언어를 사용하여 클래스를 인스턴스화하고, 속성을 설정하고, 메서드를 호출하고, 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-111">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="089fe-112">WPF에는 속성 및 이벤트를 향상시키는 [종속성 속성](advanced/dependency-properties-overview.md) 및 [라우트된 이벤트](advanced/routed-events-overview.md)와 같은 추가 프로그래밍 구문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-112">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="089fe-113">태그 및 코드 숨김</span><span class="sxs-lookup"><span data-stu-id="089fe-113">Markup and code-behind</span></span>

<span data-ttu-id="089fe-114">WPF를 사용하면 ASP.NET 개발자에게 익숙한 환경인 *태그* 및 *코드 숨김* 둘 다를 통해 애플리케이션을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-114">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="089fe-115">일반적으로 XAML 태그를 사용하여 애플리케이션의 모양을 구현하고 관리되는 프로그래밍 언어(코드 숨김)를 사용하여 해당 동작을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-115">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="089fe-116">모양 및 동작의 이러한 분리는 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-116">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="089fe-117">모양 관련 태그가 동작 관련 코드와 밀접하게 결합되지 않으므로 개발 및 유지 관리 비용이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-117">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="089fe-118">디자이너가 애플리케이션의 동작을 구현하는 개발자와 동시에 애플리케이션의 모양을 구현할 수 있으므로 개발이 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-118">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="089fe-119">WPF 애플리케이션에 대한[전역화 및 지역화](advanced/wpf-globalization-and-localization-overview.md) 가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-119">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="089fe-120">태그</span><span class="sxs-lookup"><span data-stu-id="089fe-120">Markup</span></span>

<span data-ttu-id="089fe-121">XAML은 선언적으로 애플리케이션의 모양을 구현하는 XML 기반 태그 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-121">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="089fe-122">일반적으로 창, 대화 상자, 페이지 및 사용자 정의 컨트롤을 만들고 컨트롤, 도형 및 그래픽으로 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-122">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="089fe-123">다음 예제에서는 XAML을 사용 하 여 단일 단추가 포함 된 창의 모양을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-123">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="089fe-124">특히, 이 XAML은 각각 `Window` 및 `Button` 요소를 사용하여 창과 단추를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-124">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="089fe-125">각 요소는 창의 제목 표시줄 텍스트를 지정하는 `Window` 요소의 `Title` 특성과 같은 특성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-125">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="089fe-126">런타임에 WPF는 태그에 정의된 요소와 특성을 WPF 클래스 인스턴스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-126">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="089fe-127">예를 들어 `Window` 요소는 <xref:System.Windows.Window.Title%2A> 속성이 `Title` 특성의 값인 <xref:System.Windows.Window> 클래스 인스턴스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-127">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="089fe-128">다음 그림은 이전 예제에서 XAML로 정의 된 UI (사용자 인터페이스)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-128">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![단추가 있는 창](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="089fe-130">XAML은 XML 기반이기 때문에 XAML로 작성한 UI는 [요소 트리](advanced/trees-in-wpf.md)라고 하는 중첩된 요소 계층 구조로 어셈블됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-130">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="089fe-131">요소 트리는 UI를 만들고 관리하는 논리적이고 직관적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-131">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="089fe-132">코드 숨김</span><span class="sxs-lookup"><span data-stu-id="089fe-132">Code-behind</span></span>

<span data-ttu-id="089fe-133">애플리케이션의 주요 작업은 이벤트 (예: 메뉴, 도구 모음, 단추 클릭) 처리, 비즈니스 논리 작업 및 데이터 엑세스 응답과 같은 사용자 조작에 맞는 기능을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-133">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="089fe-134">WPF에서 이 동작은 태그와 연결된 코드에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-134">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="089fe-135">이러한 종류의 코드를 코드 숨김이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-135">This type of code is known as code-behind.</span></span> <span data-ttu-id="089fe-136">다음 예제에서는 이전 예제와 코드 숨김으로 업데이트 된 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-136">The following example shows the updated markup from the previous example and the code-behind:</span></span>

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
            // Show message box when button is clicked.
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

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub 

    End Class 

End Namespace
```

<span data-ttu-id="089fe-137">이 예제에서 코드 숨김은 <xref:System.Windows.Window> 클래스에서 파생된 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-137">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="089fe-138">`x:Class` 특성은 태그를 코드 숨김 클래스와 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-138">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="089fe-139">`InitializeComponent`는 코드 숨김 클래스를 사용하여 태그에서 정의된 UI를 병합하기 위해 코드 숨김 클래스의 생성자에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-139">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="089fe-140">응용 프로그램을 빌드할 때 `InitializeComponent` 생성 됩니다. 즉, 수동으로 구현 하지 않아도 됩니다. `x:Class`와 `InitializeComponent`의 조합은 구현이 만들어질 때마다 올바르게 초기화 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-140">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="089fe-141">코드 숨김 클래스는 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 이벤트 처리기도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-141">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="089fe-142">단추를 클릭하면 이벤트 처리기가 <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> 메서드를 호출하여 메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-142">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="089fe-143">다음 그림은 단추를 클릭할 때의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-143">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="089fe-145">컨트롤</span><span class="sxs-lookup"><span data-stu-id="089fe-145">Controls</span></span>

<span data-ttu-id="089fe-146">애플리케이션 모델에서 제공하는 사용자 환경은 생성된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-146">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="089fe-147">WPF에서 *컨트롤*은 창이나 페이지에서 호스트되고 사용자 인터페이스가 있으며 일부 동작을 구현하는 WPF 클래스의 한 범주에 적용되는 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-147">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="089fe-148">자세한 내용은 [컨트롤](controls/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-148">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="089fe-149">기능별 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="089fe-149">WPF controls by function</span></span>

<span data-ttu-id="089fe-150">기본 제공 WPF 컨트롤은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-150">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="089fe-151">**단추**: <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Primitives.RepeatButton></span><span class="sxs-lookup"><span data-stu-id="089fe-151">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="089fe-152">**데이터 표시**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>및 <xref:System.Windows.Controls.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-152">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="089fe-153">**날짜 표시 및 선택**: <xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker></span><span class="sxs-lookup"><span data-stu-id="089fe-153">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="089fe-154">**대화 상자**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>및 <xref:Microsoft.Win32.SaveFileDialog></span><span class="sxs-lookup"><span data-stu-id="089fe-154">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="089fe-155">**디지털 잉크**: <xref:System.Windows.Controls.InkCanvas> 및 <xref:System.Windows.Controls.InkPresenter></span><span class="sxs-lookup"><span data-stu-id="089fe-155">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="089fe-156">**문서**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>및 <xref:System.Windows.Controls.StickyNoteControl></span><span class="sxs-lookup"><span data-stu-id="089fe-156">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="089fe-157">**입력**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>및 <xref:System.Windows.Controls.PasswordBox></span><span class="sxs-lookup"><span data-stu-id="089fe-157">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="089fe-158">**레이아웃**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>및 <xref:System.Windows.Controls.WrapPanel></span><span class="sxs-lookup"><span data-stu-id="089fe-158">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="089fe-159">**미디어**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>및 <xref:System.Windows.Controls.SoundPlayerAction></span><span class="sxs-lookup"><span data-stu-id="089fe-159">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="089fe-160">**메뉴**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>및 <xref:System.Windows.Controls.ToolBar></span><span class="sxs-lookup"><span data-stu-id="089fe-160">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="089fe-161">**탐색**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>및 <xref:System.Windows.Controls.TabControl></span><span class="sxs-lookup"><span data-stu-id="089fe-161">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="089fe-162">**선택**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>및 <xref:System.Windows.Controls.Slider></span><span class="sxs-lookup"><span data-stu-id="089fe-162">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="089fe-163">**사용자 정보**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>및 <xref:System.Windows.Controls.ToolTip></span><span class="sxs-lookup"><span data-stu-id="089fe-163">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="089fe-164">입력 및 명령</span><span class="sxs-lookup"><span data-stu-id="089fe-164">Input and commands</span></span>

<span data-ttu-id="089fe-165">컨트롤은 대체로 사용자 입력을 감지하고 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-165">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="089fe-166">[WPF 입력 시스템](advanced/input-overview.md) 은 직접 및 라우트된 이벤트를 사용하여 텍스트 입력, 포커스 관리 및 마우스 위치 지정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-166">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="089fe-167">애플리케이션에 복잡한 입력 요구 사항이 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-167">Applications often have complex input requirements.</span></span> <span data-ttu-id="089fe-168">WPF는 사용자 입력 작업을 이러한 작업에 응답하는 코드에서 분리하는 [명령 시스템](advanced/commanding-overview.md)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-168">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="089fe-169">레이아웃</span><span class="sxs-lookup"><span data-stu-id="089fe-169">Layout</span></span>

<span data-ttu-id="089fe-170">사용자 인터페이스를 만들 때 위치 및 크기별로 컨트롤을 정렬하여 레이아웃을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-170">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="089fe-171">모든 레이아웃의 주요 요구 사항은 창 크기와 표시 설정의 변경 내용에 맞게 조정되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-171">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="089fe-172">이러한 상황에서 레이아웃을 조정하는 코드를 작성하도록 요구하는 대신 WPF는 확장 가능한 뛰어난 레이아웃 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-172">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="089fe-173">이 레이아웃 시스템의 토대는 상대 위치 지정으로, 변화하는 창과 표시 조건에 맞게 조정하는 기능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-173">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="089fe-174">또한 이 레이아웃 시스템은 레이아웃을 결정하기 위한 컨트롤 간의 협상을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-174">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="089fe-175">협상은 2단계 프로세스입니다. 첫 번째로, 컨트롤이 필요한 위치 및 크기를 부모에게 알립니다. 두 번째로, 부모가 사용할 수 있는 공간을 컨트롤에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-175">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="089fe-176">이 레이아웃 시스템은 기본 WPF 클래스를 통해 자식 컨트롤에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-176">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="089fe-177">그리드, 스택 및 도킹과 같은 일반적인 레이아웃을 위해 WPF는 여러 레이아웃 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-177">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="089fe-178"><xref:System.Windows.Controls.Canvas>: 자식 컨트롤이 자체 레이아웃을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-178"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="089fe-179"><xref:System.Windows.Controls.DockPanel>: 자식 컨트롤이 패널 가장자리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-179"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="089fe-180"><xref:System.Windows.Controls.Grid>: 자식 컨트롤이 행 및 열별로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-180"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="089fe-181"><xref:System.Windows.Controls.StackPanel>: 자식 컨트롤이 가로 또는 세로로 포개집니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-181"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="089fe-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: 자식 컨트롤이 가상화되고 가로 또는 세로 방향인 한 줄에 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="089fe-183"><xref:System.Windows.Controls.WrapPanel>: 자식 컨트롤이 왼쪽에서 오른쪽 순서로 배치되고 공간에 허용되는 것보다 더 많은 컨트롤이 현재 줄에 있는 경우 다음 줄로 줄 바꿈됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-183"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="089fe-184">다음 예제에서는 <xref:System.Windows.Controls.DockPanel>를 사용 하 여 여러 <xref:System.Windows.Controls.TextBox> 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-184">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="089fe-185"><xref:System.Windows.Controls.DockPanel>을 사용하면 자식 <xref:System.Windows.Controls.TextBox> 컨트롤이 정렬 방법을 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-185">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="089fe-186">이렇게 하려면 <xref:System.Windows.Controls.DockPanel>은 각각 도킹 스타일을 지정할 수 있도록 자식 컨트롤에 노출되는 `Dock` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-186">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="089fe-187">자식 컨트롤에서 사용할 수 있도록 부모 컨트롤이 구현하는 속성은 [연결된 속성](advanced/attached-properties-overview.md)이라는 WPF 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-187">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="089fe-188">다음 그림에서는 이전 예제의 XAML 태그 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-188">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![DockPanel 페이지](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="089fe-190">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="089fe-190">Data binding</span></span>

<span data-ttu-id="089fe-191">대부분의 애플리케이션은 데이터를 보고 편집할 수 있는 수단을 사용자에게 제공하기 위해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-191">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="089fe-192">WPF 애플리케이션의 경우 데이터를 저장 및 액세스하는 작업이 SQL Server 및 ADO .NET과 같은 기술에 의해 이미 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-192">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="089fe-193">데이터에 액세스하고 애플리케이션의 관리되는 개체에 로드한 후 WPF 애플리케이션에 대한 힘든 작업이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-193">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="089fe-194">기본적으로 다음 두 가지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-194">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="089fe-195">관리되는 개체에서 데이터를 표시 및 편집할 수 있는 컨트롤로 데이터 복사</span><span class="sxs-lookup"><span data-stu-id="089fe-195">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="089fe-196">컨트롤을 사용한 데이터 변경 내용이 관리되는 개체에 다시 복사되는지 확인</span><span class="sxs-lookup"><span data-stu-id="089fe-196">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="089fe-197">애플리케이션 개발을 간소화하기 위해 WPF는 이러한 단계를 자동으로 수행하는 데이터 바인딩 엔진을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-197">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="089fe-198">데이터 바인딩 엔진의 핵심 단위는 <xref:System.Windows.Data.Binding> 클래스로, 컨트롤(바인딩 대상)을 데이터 개체(바인딩 소스)에 바인딩하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-198">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="089fe-199">이 관계는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-199">This relationship is illustrated by the following figure:</span></span>

![기본 데이터 바인딩 다이어그램](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="089fe-201">다음 예제에서는 <xref:System.Windows.Controls.TextBox>를 사용자 지정 `Person` 개체의 인스턴스에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-201">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="089fe-202">`Person` 구현은 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-202">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="089fe-203">다음 태그는 <xref:System.Windows.Controls.TextBox> 사용자 지정 `Person` 개체의 인스턴스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-203">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_6.cs)]

<span data-ttu-id="089fe-204">이 예제에서 `Person` 클래스는 코드 숨김에서 인스턴스화되고 `DataBindingWindow`에 대한 데이터 컨텍스트로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-204">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="089fe-205">태그에서 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 "`{Binding ... }`" XAML 구문을 사용하는 `Person.Name` 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-205">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="089fe-206">이 XAML은 WPF가 <xref:System.Windows.Controls.TextBox> 컨트롤을 해당 창의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 저장된 `Person` 개체에 바인딩되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-206">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="089fe-207">WPF 데이터 바인딩 엔진은 유효성 검사, 정렬, 필터링 및 그룹화를 포함하는 추가 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-207">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="089fe-208">또한 데이터 바인딩은 표준 WPF 컨트롤에 의해 표시되는 사용자 인터페이스가 적절하지 않은 경우 데이터 템플릿을 사용하여 바인딩된 데이터에 대한 사용자 지정 사용자 인터페이스를 만들 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-208">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="089fe-209">자세한 내용은 [데이터 바인딩 개요](../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-209">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="089fe-210">그래픽</span><span class="sxs-lookup"><span data-stu-id="089fe-210">Graphics</span></span>

<span data-ttu-id="089fe-211">WPF는 다음과 같은 이점이 있는 광범위하고 확장 가능하며 유연한 그래픽 집합을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-211">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="089fe-212">**해상도 및 디바이스 독립적인 그래픽**.</span><span class="sxs-lookup"><span data-stu-id="089fe-212">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="089fe-213">WPF 그래픽 시스템의 기본 측정 단위는 실제 화면 해상도에 관계없이 1/96인치인 디바이스 독립적 픽셀이며, 해상도 및 디바이스 독립적인 렌더링을 위한 토대를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-213">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="089fe-214">각 디바이스 독립적 픽셀은 렌더링되는 시스템의 dpi(인치당 도트 수) 설정에 맞게 자동으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-214">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="089fe-215">**향상된 정밀도**.</span><span class="sxs-lookup"><span data-stu-id="089fe-215">**Improved precision**.</span></span> <span data-ttu-id="089fe-216">WPF 좌표계는 단정밀도 대신 배정밀도 부동 소수점 숫자로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-216">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="089fe-217">변환 및 불투명도 값도 배정밀도로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-217">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="089fe-218">또한 WPF는 광범위한 색 영역(scRGB)을 지원하며 여러 색 공간의 입력을 관리하기 위한 통합 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-218">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="089fe-219">**고급 그래픽 및 애니메이션 지원**.</span><span class="sxs-lookup"><span data-stu-id="089fe-219">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="089fe-220">WPF는 애니메이션 장면을 관리하여 그래픽 프로그래밍을 간소화합니다. 장면 처리, 렌더링 루프 및 쌍선형 보간에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-220">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="089fe-221">또한 WPF는 적중 테스트 및 전체 알파 합치기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-221">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="089fe-222">**하드웨어 가속**.</span><span class="sxs-lookup"><span data-stu-id="089fe-222">**Hardware acceleration**.</span></span> <span data-ttu-id="089fe-223">WPF 그래픽 시스템은 그래픽 하드웨어를 활용하여 CPU 사용량을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-223">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="089fe-224">2D 도형</span><span class="sxs-lookup"><span data-stu-id="089fe-224">2D shapes</span></span>

<span data-ttu-id="089fe-225">WPF는 다음 그림에 표시된 사각형 및 타원과 같은 일반적인 벡터 기반의 2D 도형 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-225">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![타원 및 사각형](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="089fe-227">도형의 흥미로운 기능은 표시에 사용되는 것뿐 아니라 키보드 및 마우스 입력을 비롯하여 컨트롤에서 기대하는 기능을 대부분 구현한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-227">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="089fe-228">다음 예에서는 처리 중인 <xref:System.Windows.Shapes.Ellipse>의 <xref:System.Windows.UIElement.MouseUp> 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-228">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="089fe-229">다음 그림은 위의 코드에서 생성 되는 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-229">The following figure shows what is produced by the preceding code:</span></span>

!["you clicked the ellipse!" 텍스트가 있는 창](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="089fe-231">자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-231">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="089fe-232">2D 기하 도형</span><span class="sxs-lookup"><span data-stu-id="089fe-232">2D geometries</span></span>

<span data-ttu-id="089fe-233">WPF에서 제공하는 2D 도형은 기본 도형의 표준 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-233">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="089fe-234">그러나 사용자 지정 사용자 인터페이스의 디자인이 용이하도록 사용자 지정 도형을 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-234">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="089fe-235">이 용도로 WPF는 기하 도형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-235">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="089fe-236">다음 그림은 기하 도형을 사용하여 직접 그리거나, 브러시로 사용하거나, 다른 도형 및 컨트롤을 자르는 데 사용할 수 있는 사용자 지정 도형을 만드는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-236">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="089fe-237"><xref:System.Windows.Shapes.Path> 개체는 닫혔거나 열린 도형, 여러 도형 및 곡선 도형을 그리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-237"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="089fe-238"><xref:System.Windows.Media.Geometry> 개체는 자르기, 적중 테스트 및 2D 그래픽 데이터 렌더링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-238"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![Path의 다양한 용도](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="089fe-240">자세한 내용은 [기하 도형 개요](graphics-multimedia/geometry-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-240">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="089fe-241">2D 효과</span><span class="sxs-lookup"><span data-stu-id="089fe-241">2D effects</span></span>

<span data-ttu-id="089fe-242">WPF 2D 기능의 하위 집합에는 그라데이션, 비트맵, 그리기, 비디오로 그리기, 회전, 크기 조정 및 기울이기와 같은 시각 효과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-242">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="089fe-243">이러한 모두 브러시를 사용 하 여 달성 됩니다. 다음 그림에서는 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-243">These are all achieved with brushes; the following figure shows some examples:</span></span>

![여러 브러시의 설명](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="089fe-245">자세한 내용은 [WPF 브러시 개요](graphics-multimedia/wpf-brushes-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-245">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="089fe-246">3D 렌더링</span><span class="sxs-lookup"><span data-stu-id="089fe-246">3D rendering</span></span>

<span data-ttu-id="089fe-247">WPF에는 더 흥미로운 사용자 인터페이스를 만들 수 있도록 2D 그래픽을 통합하는 3D 렌더링 기능도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-247">WPF also includes 3D rendering capabilities that integrate with 2-d graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="089fe-248">예를 들어 다음 그림은 3D 도형에 렌더링 된 2D 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-248">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Visual3D 샘플 스크린 샷](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="089fe-250">자세한 내용은 [3D 그래픽 개요](graphics-multimedia/3-d-graphics-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-250">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="089fe-251">애니메이션</span><span class="sxs-lookup"><span data-stu-id="089fe-251">Animation</span></span>

<span data-ttu-id="089fe-252">WPF 애니메이션 지원을 사용하면 컨트롤이 커지거나, 흔들리거나, 회전하거나, 사라지도록 하여 흥미로운 페이지 전환 등을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-252">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="089fe-253">사용자 지정 클래스를 비롯한 대부분의 WPF 클래스에 애니메이션 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-253">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="089fe-254">다음 그림에서는 간단한 애니메이션의 작동을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-254">The following figure shows a simple animation in action:</span></span>

![애니메이션 효과가 적용된 큐브의 이미지](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="089fe-256">자세한 내용은 [애니메이션 개요](graphics-multimedia/animation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-256">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="089fe-257">미디어</span><span class="sxs-lookup"><span data-stu-id="089fe-257">Media</span></span>

<span data-ttu-id="089fe-258">풍부한 콘텐츠를 전달하는 한 가지 방법은 시청각 미디어를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-258">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="089fe-259">WPF는 이미지, 비디오 및 오디오에 대한 특별한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-259">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="089fe-260">이미지</span><span class="sxs-lookup"><span data-stu-id="089fe-260">Images</span></span>

<span data-ttu-id="089fe-261">이미지는 대부분의 애플리케이션에서 공통적으로 사용되며 WPF는 이미지를 사용하는 여러 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-261">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="089fe-262">다음 그림에서는 미리 보기 이미지를 포함하는 목록 상자가 있는 사용자 인터페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-262">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="089fe-263">미리 보기를 선택하면 이미지가 전체 크기로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-263">When a thumbnail is selected, the image is shown full-size.</span></span>

![축소판 이미지 및 전체 크기 이미지](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="089fe-265">자세한 내용은 [이미징 개요](graphics-multimedia/imaging-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-265">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="089fe-266">비디오 및 오디오</span><span class="sxs-lookup"><span data-stu-id="089fe-266">Video and audio</span></span>

<span data-ttu-id="089fe-267"><xref:System.Windows.Controls.MediaElement> 컨트롤은 비디오와 오디오를 둘 다 재생할 수 있으며 사용자 지정 미디어 플레이어의 토대가 될 수 있을 정도로 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-267">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="089fe-268">다음 XAML 태그는 미디어 플레이어를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-268">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="089fe-269">다음 그림의 창에서는 실행 중인 <xref:System.Windows.Controls.MediaElement> 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-269">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![오디오와 비디오가 있는 MediaElement 컨트롤](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="089fe-271">자세한 내용은 [그래픽 및 멀티미디어](graphics-multimedia/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-271">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="089fe-272">텍스트 및 입력 체계</span><span class="sxs-lookup"><span data-stu-id="089fe-272">Text and typography</span></span>

<span data-ttu-id="089fe-273">고품질 텍스트 렌더링이 용이하도록 WPF는 다음 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-273">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="089fe-274">OpenType 글꼴 지원</span><span class="sxs-lookup"><span data-stu-id="089fe-274">OpenType font support.</span></span>

- <span data-ttu-id="089fe-275">ClearType 향상</span><span class="sxs-lookup"><span data-stu-id="089fe-275">ClearType enhancements.</span></span>

- <span data-ttu-id="089fe-276">하드웨어 가속을 활용하는 고성능</span><span class="sxs-lookup"><span data-stu-id="089fe-276">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="089fe-277">미디어, 그래픽 및 애니메이션과 텍스트 통합</span><span class="sxs-lookup"><span data-stu-id="089fe-277">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="089fe-278">국가별 글꼴 지원 및 대체(fallback) 메커니즘</span><span class="sxs-lookup"><span data-stu-id="089fe-278">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="089fe-279">그래픽과 텍스트 통합의 데모로, 다음 그림에서는 텍스트 장식의 적용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-279">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![다양한 텍스트 장식이 적용된 텍스트](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="089fe-281">자세한 내용은 [Windows Presentation Foundation의 입력 체계](advanced/typography-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-281">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="089fe-282">WPF 앱 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="089fe-282">Customize WPF apps</span></span>

<span data-ttu-id="089fe-283">지금까지 애플리케이션을 개발하기 위한 핵심 WPF 구성 요소를 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-283">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="089fe-284">애플리케이션 모델을 사용하여 주로 컨트롤로 구성된 애플리케이션 콘텐츠를 호스트 및 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-284">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="089fe-285">사용자 인터페이스에서 컨트롤 정렬을 간소화하고 창 크기 및 디스플레이 설정이 변경되어도 정렬이 유지되도록 하기 위해 WPF 레이아웃 시스템을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-285">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="089fe-286">대부분의 애플리케이션은 사용자의 데이터 조작을 허용하므로 데이터 바인딩을 사용하여 사용자 인터페이스와 데이터 통합 작업을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-286">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="089fe-287">애플리케이션의 시각적 모양을 개선하려면 WPF에서 제공하는 광범위한 그래픽, 애니메이션 및 미디어 지원을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-287">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="089fe-288">하지만 기본 사항이 고유하고 시각적으로 멋진 사용자 환경을 만들고 관리하는 데 충분하지 않은 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-288">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="089fe-289">표준 WPF 컨트롤이 원하는 애플리케이션 모양과 통합되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-289">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="089fe-290">데이터가 가장 효율적인 방식으로 표시되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-290">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="089fe-291">애플리케이션의 전반적인 사용자 환경이 Windows 테마의 기본 모양과 느낌에 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-291">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="089fe-292">여러 측면에서 프레젠테이션 기술은 다른 형식의 확장성만큼 시각적 확장성을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-292">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="089fe-293">이런 이유로 WPF는 컨트롤, 트리거, 컨트롤 및 데이터 템플릿, 스타일, 사용자 인터페이스 리소스, 테마 및 스킨에 대한 풍부한 콘텐츠 모델을 포함하여 고유한 사용자 환경을 만들기 위한 다양한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-293">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="089fe-294">콘텐츠 모델</span><span class="sxs-lookup"><span data-stu-id="089fe-294">Content model</span></span>

<span data-ttu-id="089fe-295">대부분의 WPF 컨트롤은 주로 콘텐츠를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-295">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="089fe-296">WPF에서 컨트롤의 콘텐츠를 구성할 수 있는 항목의 유형과 개수를 컨트롤의 *콘텐츠 모델*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-296">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="089fe-297">일부 컨트롤은 단일 항목 및 유형의 콘텐츠를 포함할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.TextBox> 의 콘텐츠는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성에 할당되는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-297">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="089fe-298">다음 예에서는 <xref:System.Windows.Controls.TextBox>의 내용을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-298">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="089fe-299">다음 그림에서는 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-299">The following figure shows the result:</span></span>

![텍스트가 포함된 TextBox 컨트롤](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="089fe-301">그러나 다른 컨트롤은 다양한 콘텐츠 형식의 여러 항목을 포함할 수 있습니다. <xref:System.Windows.Controls.ContentControl.Content%2A> 속성으로 지정된 <xref:System.Windows.Controls.Button>의 콘텐츠에는 레이아웃 컨트롤, 텍스트, 이미지 및 도형을 포함하여 다양한 항목이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-301">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="089fe-302">다음 예에서는 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Border>및 <xref:System.Windows.Controls.MediaElement>를 포함 하는 콘텐츠가 포함 된 <xref:System.Windows.Controls.Button>를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-302">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

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

<span data-ttu-id="089fe-303">다음 그림에서는이 단추의 콘텐츠를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-303">The following figure shows the content of this button:</span></span>

![여러 형식의 콘텐츠가 포함된 단추](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="089fe-305">다양한 컨트롤에서 지원하는 콘텐츠 종류에 대한 자세한 내용은 [WPF 콘텐츠 모델](controls/wpf-content-model.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-305">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="089fe-306">트리거</span><span class="sxs-lookup"><span data-stu-id="089fe-306">Triggers</span></span>

<span data-ttu-id="089fe-307">XAML 태그의 주요 용도는 애플리케이션의 모양을 구현하는 것이지만 XAML을 사용하여 애플리케이션 동작의 일부 측면을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-307">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="089fe-308">한 가지 예는 트리거를 사용하여 사용자 조작에 따라 애플리케이션의 모양을 변경하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-308">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="089fe-309">자세한 내용은 [스타일 및 템플릿](../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-309">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="089fe-310">컨트롤 템플릿</span><span class="sxs-lookup"><span data-stu-id="089fe-310">Control templates</span></span>

<span data-ttu-id="089fe-311">WPF 컨트롤의 기본 사용자 인터페이스는 일반적으로 다른 컨트롤 및 도형에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-311">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="089fe-312">예를 들어 <xref:System.Windows.Controls.Button> 은 <xref:Microsoft.Windows.Themes.ButtonChrome> 및 <xref:System.Windows.Controls.ContentPresenter> 컨트롤 둘 다로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-312">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="089fe-313"><xref:Microsoft.Windows.Themes.ButtonChrome> 은 표준 단추 모양을 제공하는 반면, <xref:System.Windows.Controls.ContentPresenter> 는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 지정된 대로 단추의 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-313">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="089fe-314">컨트롤의 기본 모양이 애플리케이션의 전반적인 모양에 맞지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-314">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="089fe-315">이 경우 <xref:System.Windows.Controls.ControlTemplate> 을 사용하여 해당 콘텐츠 및 동작을 변경하지 않고 컨트롤의 사용자 인터페이스 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-315">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="089fe-316">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate>를 사용 하 여 <xref:System.Windows.Controls.Button> 모양을 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-316">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="089fe-317">이 예제에서는 기본 단추 사용자 인터페이스가 진한 파란색 테두리가 있는 <xref:System.Windows.Shapes.Ellipse>로 대체되고 <xref:System.Windows.Media.RadialGradientBrush>를 사용하여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-317">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="089fe-318"><xref:System.Windows.Controls.ContentPresenter> 컨트롤은 <xref:System.Windows.Controls.Button>의 콘텐츠인 "Click Me!"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-318">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="089fe-319"><xref:System.Windows.Controls.Button> 을 클릭하면 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 <xref:System.Windows.Controls.Button> 컨트롤의 기본 동작의 일부로 여전히 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-319">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="089fe-320">결과는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-320">The result is shown in the following figure:</span></span>

![타원형 단추 및 두 번째 창](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="089fe-322">데이터 템플릿</span><span class="sxs-lookup"><span data-stu-id="089fe-322">Data templates</span></span>

<span data-ttu-id="089fe-323">컨트롤 템플릿을 사용하면 컨트롤의 모양을 지정할 수 있는 반면 데이터 템플릿을 사용하면 컨트롤 콘텐츠의 모양을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-323">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="089fe-324">데이터 템플릿은 바인딩된 데이터가 표시되는 방식을 개선하는 데 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-324">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="089fe-325">다음 그림에서는 각 작업에 이름, 설명 및 우선 순위가 있는 `Task` 개체의 컬렉션에 바인딩되는 <xref:System.Windows.Controls.ListBox>의 기본 모양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-325">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![기본 모양의 목록 상자](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="089fe-327">기본 모양은 <xref:System.Windows.Controls.ListBox>에서 예상되는 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-327">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="089fe-328">그러나 각 작업의 기본 모양은 작업 이름만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-328">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="089fe-329">작업 이름, 설명 및 우선 순위를 표시하려면 <xref:System.Windows.DataTemplate>을 사용하여 <xref:System.Windows.Controls.ListBox> 컨트롤의 바인딩된 목록 항목에 대한 기본 모양을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-329">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="089fe-330">다음 XAML은 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 특성을 사용 하 여 각 작업에 적용 되는 <xref:System.Windows.DataTemplate>을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-330">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

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

<span data-ttu-id="089fe-331">다음 그림에서는이 코드의 효과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-331">The following figure shows the effect of this code:</span></span>

![데이터 템플릿을 사용하는 목록 상자](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="089fe-333"><xref:System.Windows.Controls.ListBox>의 동작과 전반적인 모양은 유지되고 목록 상자에 표시되는 콘텐츠의 모양만 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-333">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="089fe-334">자세한 내용은 [데이터 템플릿 개요](data/data-templating-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-334">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="089fe-335">스타일</span><span class="sxs-lookup"><span data-stu-id="089fe-335">Styles</span></span>

<span data-ttu-id="089fe-336">스타일을 사용하면 개발자와 디자이너가 해당 제품에 대해 특정 모양을 표준화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-336">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="089fe-337">WPF는 <xref:System.Windows.Style> 요소를 기반으로 하는 강력한 스타일 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-337">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="089fe-338">다음 예에서는 창의 모든 <xref:System.Windows.Controls.Button>에 대 한 배경색을 `Orange`로 설정 하는 스타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-338">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

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

<span data-ttu-id="089fe-339">이 스타일은 모든 <xref:System.Windows.Controls.Button> 컨트롤을 대상으로 하기 때문에 다음 그림과 같이 창에 있는 모든 단추에 스타일이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-339">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![두 개의 주황색 단추](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="089fe-341">자세한 내용은 [스타일 및 템플릿](../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-341">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="089fe-342">자료</span><span class="sxs-lookup"><span data-stu-id="089fe-342">Resources</span></span>

<span data-ttu-id="089fe-343">애플리케이션의 컨트롤은 글꼴 및 배경색부터 컨트롤 템플릿, 데이터 템플릿 및 스타일까지 모든 항목을 포함할 수 있는 동일한 모양을 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-343">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="089fe-344">사용자 인터페이스 리소스에 대한 WPF 지원을 사용하여 재사용을 위해 이러한 리소스를 단일 위치에 캡슐화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-344">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="089fe-345">다음 예제에서는 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Label>에서 공유 하는 공통 배경색을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-345">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

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

<span data-ttu-id="089fe-346">이 예제에서는 `Window.Resources` 속성 요소를 사용하여 배경색 리소스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-346">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="089fe-347">이 리소스는 <xref:System.Windows.Window>의 모든 자식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-347">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="089fe-348">다음을 포함하여 다양한 리소스 범위가 있습니다(확인되는 순서대로 나열됨).</span><span class="sxs-lookup"><span data-stu-id="089fe-348">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="089fe-349">개별 컨트롤(상속된 <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> 속성 사용)</span><span class="sxs-lookup"><span data-stu-id="089fe-349">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="089fe-350"><xref:System.Windows.Window> 또는 <xref:System.Windows.Controls.Page> (또한 상속된 <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> 속성 사용)</span><span class="sxs-lookup"><span data-stu-id="089fe-350">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="089fe-351"><xref:System.Windows.Application> ( <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> 속성 사용)</span><span class="sxs-lookup"><span data-stu-id="089fe-351">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="089fe-352">다양한 범위는 리소스를 정의 및 공유하는 방법과 관련해서 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-352">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="089fe-353">리소스를 특정 범위에 직접 연결하는 대신, 애플리케이션의 다른 부분에서 참조할 수 있는 별도 <xref:System.Windows.ResourceDictionary> 를 사용하여 하나 이상의 리소스를 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-353">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="089fe-354">예를 들어 다음 예제에서는 리소스 사전의 기본 배경색을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-354">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="089fe-355">다음 예제에서는 응용 프로그램 간에 공유 되도록 이전 예제에서 정의 된 리소스 사전을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-355">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

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

<span data-ttu-id="089fe-356">리소스 및 리소스 사전은 테마 및 스킨에 대한 WPF 지원의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-356">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="089fe-357">자세한 내용은 [리소스](../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-357">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="089fe-358">사용자 지정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="089fe-358">Custom controls</span></span>

<span data-ttu-id="089fe-359">WPF는 다양한 사용자 지정 지원을 제공하지만 기존 WPF 컨트롤이 애플리케이션 또는 해당 사용자의 요구를 충족하지 않는 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-359">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="089fe-360">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-360">This can occur when:</span></span>

- <span data-ttu-id="089fe-361">사용자가 요구하는 사용자 인터페이스가 기존 WPF 가 구현하는 모양이나 느낌으로 만들 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="089fe-361">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="089fe-362">필요한 동작이 기존 WPF 구현에서 지원되지 않는 경우(또는 쉽게 지원되지 않는 경우)</span><span class="sxs-lookup"><span data-stu-id="089fe-362">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="089fe-363">그러나 이제 세 가지 WPF 모델 중 하나를 활용하여 새 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-363">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="089fe-364">각 모델은 특정 시나리오를 대상으로 하며, 특정 WPF 기본 클래스에서 사용자 지정 컨트롤을 파생시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-364">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="089fe-365">세 가지 모델은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-365">The three models are listed here:</span></span>

- <span data-ttu-id="089fe-366">**사용자 정의 컨트롤 모델**.</span><span class="sxs-lookup"><span data-stu-id="089fe-366">**User Control Model**.</span></span> <span data-ttu-id="089fe-367">사용자 지정 컨트롤은 <xref:System.Windows.Controls.UserControl> 에서 파생되며 하나 이상의 다른 컨트롤로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-367">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="089fe-368">**컨트롤 모델**.</span><span class="sxs-lookup"><span data-stu-id="089fe-368">**Control Model**.</span></span> <span data-ttu-id="089fe-369">사용자 지정 컨트롤은 <xref:System.Windows.Controls.Control> 에서 파생되며 대부분의 WPF 컨트롤과 마찬가지로 템플릿을 사용하여 모양과 동작을 구분하는 구현을 작성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-369">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="089fe-370"><xref:System.Windows.Controls.Control> 에서 파생시키는 경우 사용자 정의 컨트롤보다 더 자유롭게 사용자 지정 사용자 인터페이스를 만들 수 있지만 더 많은 노력이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-370">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="089fe-371">**프레임워크 요소 모델**.</span><span class="sxs-lookup"><span data-stu-id="089fe-371">**Framework Element Model**.</span></span> <span data-ttu-id="089fe-372">사용자 지정 컨트롤은 모양이 사용자 지정 렌더링 논리(템플릿 아님)에 의해 정의되는 경우 <xref:System.Windows.FrameworkElement> 에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-372">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="089fe-373">다음 예제에서는 <xref:System.Windows.Controls.UserControl>에서 파생 되는 사용자 지정 숫자 위로/아래로 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-373">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="089fe-374">다음 예제에서는 사용자 정의 컨트롤을 <xref:System.Windows.Window>에 통합 하는 데 필요한 XAML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-374">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="089fe-375">다음 그림에서는 <xref:System.Windows.Window>에서 호스팅되는 `NumericUpDown` 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-375">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![사용자 지정 UserControl](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="089fe-377">사용자 지정 컨트롤에 대한 자세한 내용은 [컨트롤 제작 개요](controls/control-authoring-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="089fe-377">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="089fe-378">WPF 모범 사례</span><span class="sxs-lookup"><span data-stu-id="089fe-378">WPF best practices</span></span>

<span data-ttu-id="089fe-379">모든 개발 플랫폼과 마찬가지로 WPF를 다양한 방법으로 사용하여 원하는 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-379">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="089fe-380">WPF 애플리케이션이 필요한 사용자 환경을 제공하고 일반적인 사용자 요구를 충족하도록 하는 한 가지 방법으로 접근성, 전역화 및 지역화, 성능에 대한 권장 모범 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-380">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="089fe-381">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="089fe-381">For more information, see:</span></span>

- [<span data-ttu-id="089fe-382">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="089fe-382">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="089fe-383">WPF 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="089fe-383">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="089fe-384">WPF 앱 성능</span><span class="sxs-lookup"><span data-stu-id="089fe-384">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="089fe-385">WPF 보안</span><span class="sxs-lookup"><span data-stu-id="089fe-385">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="089fe-386">다음 단계</span><span class="sxs-lookup"><span data-stu-id="089fe-386">Next steps</span></span>

<span data-ttu-id="089fe-387">WPF의 주요 기능을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-387">We've looked at the key features of WPF.</span></span> <span data-ttu-id="089fe-388">이제 첫 번째 WPF 앱을 만들 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="089fe-388">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="089fe-389">연습: 내 첫 번째 WPF 데스크톱 앱</span><span class="sxs-lookup"><span data-stu-id="089fe-389">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="089fe-390">참조</span><span class="sxs-lookup"><span data-stu-id="089fe-390">See also</span></span>

- [<span data-ttu-id="089fe-391">WPF 시작</span><span class="sxs-lookup"><span data-stu-id="089fe-391">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="089fe-392">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="089fe-392">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="089fe-393">WPF 커뮤니티 리소스</span><span class="sxs-lookup"><span data-stu-id="089fe-393">WPF community resources</span></span>](getting-started/community-feedback.md)
