---
title: '연습: XAML을 사용하여 단추 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646471"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="7b543-102">연습: XAML을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="7b543-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="7b543-103">이 연습의 목적은 WPF(Windows 프레젠테이션 재단) 응용 프로그램에서 사용할 애니메이션 단추를 만드는 방법을 알아보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="7b543-104">이 연습에서는 스타일과 템플릿을 사용하여 코드를 다시 사용하고 단추 선언에서 단추 논리를 분리할 수 있는 사용자 지정된 단추 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="7b543-105">이 연습은 전적으로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b543-106">이 연습에서는 Visual Studio에 입력하거나 복사하여 붙여넣기를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 통해 응용 프로그램을 만드는 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="7b543-107">디자이너를 사용하여 동일한 응용 프로그램을 만드는 방법을 알아보려면 [Microsoft 표현식 혼합을 사용하여 단추 만들기를](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="7b543-108">다음 그림은 완성된 단추를 보여 주며, 완료된 단추를 보여 주어 도표입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="7b543-109">![XAML을 사용하여 만든 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="7b543-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="7b543-110">기본 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="7b543-110">Create Basic Buttons</span></span>

<span data-ttu-id="7b543-111">먼저 새 프로젝트를 만들고 창에 몇 개의 단추를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="7b543-112">새 WPF 프로젝트를 만들고 창에 단추를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="7b543-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="7b543-113">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="7b543-114">**새 WPF 프로젝트 만들기:** **파일** 메뉴에서 **새로**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="7b543-115">Windows **응용 프로그램(WPF)** 템플릿을 찾아 프로젝트 이름을 "AnimatedButton"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="7b543-116">이렇게 하면 응용 프로그램에 대한 골격이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="7b543-117">**기본 기본 단추 추가:** 이 연습에 필요한 모든 파일은 템플릿에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="7b543-118">솔루션 탐색기에서 Window1.xaml 파일을 두 번 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="7b543-119">기본적으로 Window1.xaml에는 요소가 있습니다. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="7b543-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="7b543-120"><xref:System.Windows.Controls.Grid> 요소를 제거하고 다음 강조 표시된 코드를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 입력하거나 복사하여 다음 코드를 Window1.xaml에 붙여넣도록 페이지에 몇 개의 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="7b543-121">응용 프로그램을 실행하려면 F5를 누르십시오. 다음 그림과 같은 단추 집합이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="7b543-122">![세 개의 기본 단추](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="7b543-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="7b543-123">기본 단추를 만들었으니 Window1.xaml 파일에서 작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="7b543-124">이 연습의 나머지 부분에서는 app.xaml 파일에 초점을 맞추고 단추에 대한 스타일과 템플릿을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="7b543-125">기본 속성 설정</span><span class="sxs-lookup"><span data-stu-id="7b543-125">Set Basic Properties</span></span>

<span data-ttu-id="7b543-126">다음으로 이러한 단추의 일부 속성을 설정하여 단추 모양과 레이아웃을 제어해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="7b543-127">단추에 속성을 개별적으로 설정하는 대신 리소스를 사용하여 전체 응용 프로그램에 대한 단추 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="7b543-128">응용 프로그램 리소스는 웹 페이지의 외부 계단식 스타일 시트(CSS)와 개념적으로 유사합니다. 그러나 이 연습의 끝에서 볼 수 있듯이 리소스는 CSS(계단식 스타일 시트)보다 훨씬 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="7b543-129">리소스에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="7b543-130">스타일을 사용하여 단추의 기본 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7b543-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="7b543-131">**응용 프로그램 정의.리소스 블록:** app.xaml을 열고 아직 없는 경우 다음 강조 표시된 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="7b543-132">리소스 범위는 리소스를 정의하는 위치에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="7b543-133">app.xaml 파일에서 `Application.Resources` 리소스를 정의하면 응용 프로그램의 어느 곳에서나 리소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="7b543-134">리소스 범위 정의에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="7b543-135">**스타일을 만들고 스타일을 사용하여 기본 속성 값을 정의합니다.** 블록에 다음 태그를 `Application.Resources` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="7b543-136">이 태그는 <xref:System.Windows.Style> 응용 프로그램의 모든 단추에 적용되는 단추를 만들고 <xref:System.Windows.FrameworkElement.Width%2A> 단추를 90으로 설정하고 <xref:System.Windows.FrameworkElement.Margin%2A> 10으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="7b543-137">속성은 <xref:System.Windows.Style.TargetType%2A> 스타일형식의 모든 개체에 적용 <xref:System.Windows.Controls.Button>되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="7b543-138">각각은 <xref:System.Windows.Setter> 에 대해 다른 <xref:System.Windows.Style>속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="7b543-139">따라서 이 시점에서 응용 프로그램의 모든 단추의 너비는 90이고 여백은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="7b543-140">응용 프로그램을 실행하기 위해 F5를 누르면 다음 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="7b543-141">![너비 90, 여백 10의 단추](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="7b543-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="7b543-142">대상 개체를 미세 조정하는 다양한 방법, 복잡한 속성 값을 지정하는 방법, 다른 스타일에 대한 입력으로 스타일을 사용하는 등 스타일로 수행할 수 있는 방법이 훨씬 더 많습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="7b543-143">자세한 내용은 [스타일 지정 및 템플릿을](../../../desktop-wpf/fundamentals/styles-templates-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="7b543-144">**스타일 속성 값을 리소스에 설정합니다.** 리소스를 사용하면 일반적으로 정의된 개체와 값을 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="7b543-145">특히 리소스를 사용하여 복잡한 값을 정의하여 코드를 보다 모듈화하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="7b543-146">app.xaml에 다음 강조 표시된 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="7b543-147">`Application.Resources` 블록 바로 아래에서 "GrayBlueGradient브러시"라는 리소스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="7b543-148">이 리소스는 수평 그라데이션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="7b543-149">이 리소스는 <xref:System.Windows.Controls.Control.Background%2A> 속성에 대한 단추 스타일 setter 내부를 포함하여 응용 프로그램의 어느 곳에서나 속성 값으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="7b543-150">이제 모든 단추에 이 <xref:System.Windows.Controls.Control.Background%2A> 그라데이션의 속성 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="7b543-151">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-151">Press F5 to run the application.</span></span> <span data-ttu-id="7b543-152">다음과 같이 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-152">It should look like the following.</span></span>

     <span data-ttu-id="7b543-153">![그라데이션 배경이 있는 단추](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="7b543-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="7b543-154">단추모양을 정의하는 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="7b543-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="7b543-155">이 섹션에서는 단추의 모양(프레젠테이션)을 사용자 지정하는 템플릿을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="7b543-156">단추 프레젠테이션은 단추를 고유한 모양으로 지정하기 위해 사각형 및 기타 구성 요소를 비롯한 여러 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="7b543-157">지금까지 응용 프로그램에서 단추 모양의 제어는 단추의 속성을 변경하는 데 국한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="7b543-158">단추의 모양에 더 급진적인 변화를 원한다면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="7b543-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="7b543-159">템플릿을 사용하면 개체의 프레젠테이션을 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="7b543-160">템플릿은 스타일 내에서 사용할 수 있으므로 스타일이 적용되는 모든 개체에 템플릿을 적용할 수 있습니다(이 연습에서 단추).</span><span class="sxs-lookup"><span data-stu-id="7b543-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="7b543-161">템플릿을 사용하여 단추의 모양을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="7b543-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="7b543-162">**템플릿 설정:** 속성과 <xref:System.Windows.Controls.Button> 같은 <xref:System.Windows.Controls.Control.Template%2A> 컨트롤에는 <xref:System.Windows.Style> <xref:System.Windows.Setter>using에서 설정한 다른 속성 값과 마찬가지로 템플릿 속성 값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="7b543-163">단추 스타일에 다음 강조 표시된 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="7b543-164">**버튼 표시 변경:** 이 시점에서 템플릿을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="7b543-165">강조 표시된 태그는 다음과 같은 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-165">Add the following highlighted markup.</span></span> <span data-ttu-id="7b543-166">이 태그는 둥근 <xref:System.Windows.Shapes.Rectangle> 모서리가 있는 두 요소를 지정한 다음 <xref:System.Windows.Controls.DockPanel>을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="7b543-167">는 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.ContentPresenter> 단추를 호스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="7b543-168">A는 <xref:System.Windows.Controls.ContentPresenter> 단추의 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="7b543-169">이 연습에서 내용은 텍스트입니다("단추 1", "단추 2", "단추 3").</span><span class="sxs-lookup"><span data-stu-id="7b543-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="7b543-170">모든 템플릿 구성 요소(사각형 <xref:System.Windows.Controls.DockPanel>및)는 <xref:System.Windows.Controls.Grid>의 내부에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="7b543-171">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-171">Press F5 to run the application.</span></span> <span data-ttu-id="7b543-172">다음과 같이 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-172">It should look like the following.</span></span>

     ![버튼 3개](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="7b543-174">**템플릿에 유리 효과를 추가합니다.** 다음으로 유리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="7b543-175">먼저 유리 그라데이션 효과를 만드는 몇 가지 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="7b543-176">이러한 그라데이션 리소스를 `Application.Resources` 블록 내의 아무 곳에나 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="7b543-177">이러한 리소스는 단추 <xref:System.Windows.Shapes.Shape.Fill%2A> 템플릿에 삽입하는 <xref:System.Windows.Controls.Grid> 사각형의 리소스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="7b543-178">템플릿에 다음 강조 표시된 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="7b543-179"><xref:System.Windows.UIElement.Opacity%2A> "glassCube"의 `x:Name` 속성이 있는 사각형의 경우 0이므로 샘플을 실행할 때 위에 유리 사각형이 겹쳐져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="7b543-180">이는 나중에 사용자가 단추와 상호 작용할 때 템플릿에 트리거를 추가하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="7b543-181">그러나 값을 1로 변경하고 응용 프로그램을 실행하여 단추의 <xref:System.Windows.UIElement.Opacity%2A> 모양을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="7b543-182">다음 그림을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b543-182">See the following figure.</span></span> <span data-ttu-id="7b543-183">다음 단계로 진행하기 전에 <xref:System.Windows.UIElement.Opacity%2A> 뒤로 0으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="7b543-184">![XAML을 사용하여 만든 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="7b543-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="7b543-185">버튼 상호 작용 만들기</span><span class="sxs-lookup"><span data-stu-id="7b543-185">Create Button Interactivity</span></span>

<span data-ttu-id="7b543-186">이 섹션에서는 속성 값을 변경하고 단추 위로 마우스 포인터를 이동하고 클릭하는 등의 사용자 작업에 대한 응답으로 애니메이션을 실행하는 속성 트리거 및 이벤트 트리거를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="7b543-187">대화형 작업을 추가하는 쉬운 방법(마우스 오버, 마우스 리브, 클릭 등)은 템플릿 또는 스타일 내에서 트리거를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="7b543-188">을 <xref:System.Windows.Trigger>만들려면 다음과 같은 속성 "조건"을 <xref:System.Windows.UIElement.IsMouseOver%2A> 정의합니다. `true`</span><span class="sxs-lookup"><span data-stu-id="7b543-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="7b543-189">그런 다음 트리거 조건이 true일 때 수행되는 setter(작업)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="7b543-190">단추 상호 작용을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7b543-190">To create button interactivity</span></span>

1. <span data-ttu-id="7b543-191">**템플릿 트리거 추가:** 강조 표시된 태그를 템플릿에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="7b543-192">**속성 트리거 추가:** 강조 표시된 태그를 블록에 `ControlTemplate.Triggers` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="7b543-193">F5를 눌러 응용 프로그램을 실행하고 단추 위에 마우스 포인터를 실행할 때 효과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="7b543-194">**포커스 트리거 추가:** 다음으로 단추에 포커스가 있는 경우(예: 사용자가 클릭한 후)를 처리하기 위해 몇 가지 유사한 setter를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="7b543-195">응용 프로그램을 실행하고 버튼 중 하나를 클릭하려면 F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="7b543-196">단추는 여전히 포커스가 있기 때문에 단추를 클릭한 후에도 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="7b543-197">다른 단추를 클릭하면 새 버튼이 포커스를 얻고 마지막 단추는 포커스를 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="7b543-198">**Add animations for**<xref:System.Windows.UIElement.MouseEnter> **and** 및 <xref:System.Windows.UIElement.MouseLeave> **:** 다음에 트리거에 애니메이션을 추가합니다.  </span><span class="sxs-lookup"><span data-stu-id="7b543-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="7b543-199">블록 내부의 아무 곳에나 `ControlTemplate.Triggers` 다음 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="7b543-200">마우스 포인터가 단추 위로 이동하면 유리 사각형이 축소되고 포인터가 나오면 정상 크기로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="7b543-201">포인터가 단추를 넘을 때 트리거되는 두 가지<xref:System.Windows.UIElement.MouseEnter> 애니메이션이 있습니다(이벤트가 발생).</span><span class="sxs-lookup"><span data-stu-id="7b543-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="7b543-202">이러한 애니메이션은 X 축과 Y축을 따라 유리 사각형을 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="7b543-203">요소의 속성및 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>에 주목하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="7b543-204">애니메이션이 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 1초 이상 발생한다고 지정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 유리가 10% 축소되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="7b543-205">두 번째 이벤트<xref:System.Windows.UIElement.MouseLeave>트리거 () 단순히 첫 번째 를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="7b543-206"><xref:System.Windows.Media.Animation.Storyboard>을 중지하면 애니메이션된 모든 속성이 기본값으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="7b543-207">따라서 사용자가 단추에서 포인터를 이동하면 단추는 마우스 포인터가 단추 위로 이동하기 전의 방식으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="7b543-208">애니메이션에 대한 자세한 내용은 [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b543-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="7b543-209">**단추를 클릭할 때 애니메이션추가:** 마지막 단계는 사용자가 단추를 클릭할 때 트리거를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="7b543-210">블록 내부의 아무 곳에나 `ControlTemplate.Triggers` 다음 태그추가</span><span class="sxs-lookup"><span data-stu-id="7b543-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="7b543-211">응용 프로그램을 실행하려면 F5를 누르고 단추 중 하나를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="7b543-212">단추를 클릭하면 유리 사각형이 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="7b543-213">요약</span><span class="sxs-lookup"><span data-stu-id="7b543-213">Summary</span></span>
 <span data-ttu-id="7b543-214">이 연습에서는 다음 연습을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="7b543-215">대상 <xref:System.Windows.Style> a 개체 유형<xref:System.Windows.Controls.Button>().</span><span class="sxs-lookup"><span data-stu-id="7b543-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="7b543-216">을 사용하여 전체 응용 프로그램에서 단추의 <xref:System.Windows.Style>제어된 기본 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="7b543-217"><xref:System.Windows.Style> 세터의 속성 값에 사용할 그라데이션과 같은 리소스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="7b543-218">단추에 템플릿을 적용하여 전체 응용 프로그램에서 단추 모양을 사용자 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="7b543-219">애니메이션 효과를 포함하는 사용자 작업(예: <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> <xref:System.Windows.Controls.Primitives.ButtonBase.Click>및) 단추에 대한 사용자 지정 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="7b543-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b543-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b543-220">See also</span></span>

- [<span data-ttu-id="7b543-221">Microsoft Expression Blend를 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="7b543-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="7b543-222">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7b543-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7b543-223">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="7b543-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="7b543-224">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="7b543-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7b543-225">비트맵 효과 개요</span><span class="sxs-lookup"><span data-stu-id="7b543-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
