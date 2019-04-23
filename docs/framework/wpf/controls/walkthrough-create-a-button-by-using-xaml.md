---
title: '연습: XAML을 사용하여 단추 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 908a38485c879e3f28399bb7dbc8303afd4505da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309500"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="ca8eb-102">연습: XAML을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="ca8eb-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="ca8eb-103">이 연습의 목적은 Windows Presentation Foundation (WPF) 응용 프로그램에서 사용 하기 위해 애니메이션된 단추를 만드는 방법에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="ca8eb-104">이 연습에서는 스타일 및 템플릿을 사용 하 여 코드의 재사용 및 단추 선언에서 단추 논리의 분리 허용 하는 사용자 지정된 단추 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="ca8eb-105">이 연습에 완전히 기록 됩니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca8eb-106">이 연습에서는 입력 하거나 복사 및 붙여넣기 하 여 응용 프로그램을 만드는 단계를 안내 합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Microsoft Visual Studio로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="ca8eb-107">디자인 도구 (Microsoft Expression Blend)를 사용 하 여 동일한 응용 프로그램 만들기를 참조 하는 방법을 알아보려면 선호 [Microsoft Expression Blend를 사용 하 여 단추 만들기](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="ca8eb-108">다음 그림은 완료 단추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="ca8eb-109">![XAML을 사용 하 여 생성 된 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="ca8eb-110">기본 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="ca8eb-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="ca8eb-111">새 프로젝트를 만들고 창에 단추 몇 개를 추가 하 여 시작 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="ca8eb-112">새 WPF 프로젝트를 만들고 창에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="ca8eb-112">To create a new WPF project and add buttons to the window</span></span>  
  
1. <span data-ttu-id="ca8eb-113">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-113">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="ca8eb-114">**새 WPF 프로젝트를 만듭니다.** **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="ca8eb-115">찾을 합니다 **Windows 응용 프로그램 (WPF)** 템플릿과 "AnimatedButton" 프로젝트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="ca8eb-116">이 응용 프로그램에 대 한 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-116">This will create the skeleton for the application.</span></span>  
  
3. <span data-ttu-id="ca8eb-117">**기본 단추를 추가 합니다.** 이 연습에 필요한 모든 파일은 템플릿에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="ca8eb-118">Window1.xaml 파일을 두 번 솔루션 탐색기에서 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="ca8eb-119">기본적으로는 <xref:System.Windows.Controls.Grid> 살펴볼 내용은 Window1.xaml에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="ca8eb-120">제거 합니다 <xref:System.Windows.Controls.Grid> 요소에 단추 몇 개를 추가 하 고는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 입력 하거나 복사 및 붙여넣기 Window1.xaml 다음 강조 표시 된 코드를 사용 하 여 페이지:</span><span class="sxs-lookup"><span data-stu-id="ca8eb-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-121">F5 키를 눌러 응용 프로그램을 실행 하려면 다음 그림 처럼 보이는 단추 집합이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="ca8eb-122">![세 개의 기본 단추](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="ca8eb-123">기본 단추를 만들었으므로 이제 Window1.xaml 파일의 작업 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="ca8eb-124">연습의 나머지 부분에 중점을 둡니다 app.xaml 파일 스타일 및 단추에 대 한 템플릿을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="ca8eb-125">기본 속성 설정</span><span class="sxs-lookup"><span data-stu-id="ca8eb-125">Set Basic Properties</span></span>  
 <span data-ttu-id="ca8eb-126">다음으로 단추 모양 및 레이아웃을 제어 하려면이 단추에 몇 가지 속성을 설정 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="ca8eb-127">단추의 속성을 개별적으로 설정 하는 대신 전체 응용 프로그램에 대 한 단추 속성을 정의 하려면 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="ca8eb-128">그러나 응용 프로그램 리소스는 외부와 개념적으로 유사 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] 웹 페이지, 리소스는 보다 훨씬 더 강력 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]처럼이 연습의 끝 부분에서 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="ca8eb-129">리소스에 대 한 자세한 내용은 참조 하세요 [XAML 리소스](../advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="ca8eb-130">스타일을 사용 하 여 단추에서 기본 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ca8eb-130">To use styles to set basic properties on the buttons</span></span>  
  
1. <span data-ttu-id="ca8eb-131">**사용 블록을 정의 합니다.** App.xaml 열고 아직 없는 경우 다음 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-132">리소스 범위는 리소스를 정의 하 여 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="ca8eb-133">리소스 정의 `Application.Resources` 는 app.xaml에서 파일을 통해 리소스를 응용 프로그램의 어디에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="ca8eb-134">리소스의 범위를 정의 하는 방법에 대 한 자세한 내용은 참조 하세요 [XAML 리소스](../advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>  
  
2. <span data-ttu-id="ca8eb-135">**스타일을 만들고이 사용 하 여 기본 속성 값을 정의 합니다.** 다음 태그를 추가 합니다 `Application.Resources` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="ca8eb-136">이 태그를 만듭니다는 <xref:System.Windows.Style> 응용 프로그램 설정에서 모든 단추에 적용 되는 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 90 단추 중 및 <xref:System.Windows.FrameworkElement.Margin%2A> 10:</span><span class="sxs-lookup"><span data-stu-id="ca8eb-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="ca8eb-137">합니다 <xref:System.Windows.Style.TargetType%2A> 속성의 스타일 유형의 모든 개체에 적용 되도록 지정 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="ca8eb-138">각 <xref:System.Windows.Setter> 서로 다른 속성 값을 설정 합니다 <xref:System.Windows.Style>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="ca8eb-139">따라서이 시점에서 응용 프로그램에서 모든 단추에는 너비 90, 여백 10의</span><span class="sxs-lookup"><span data-stu-id="ca8eb-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="ca8eb-140">F5 키를 눌러 응용 프로그램을 실행 하는 경우 다음과 같은 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="ca8eb-141">![너비 90, 여백 10의 단추](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="ca8eb-142">훨씬 더 다양 한 개체를 대상으로 미세 조정 하는 방법 포함 하 고 복잡 한 속성 값을 지정도 다른 스타일에 대 한 입력으로 스타일을 사용 하 스타일을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="ca8eb-143">자세한 내용은 [스타일 지정 및 템플릿](styling-and-templating.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-143">For more information, see [Styling and Templating](styling-and-templating.md).</span></span>  
  
3. <span data-ttu-id="ca8eb-144">**리소스에 스타일 속성 값을 설정 합니다.** 리소스는 일반적으로 정의 된 개체 및 값을 다시 사용 하는 간단한 방법을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="ca8eb-145">특히 리소스를 사용 하 여 코드를 더 모듈식 쉽게 복잡 한 값을 정의 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="ca8eb-146">App.xaml에 다음 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-146">Add the following highlighted markup to app.xaml.</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-147">바로 아래는 `Application.Resources` 블록 "GrayBlueGradientBrush" 라고 하는 리소스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="ca8eb-148">이 리소스에는 가로 그라데이션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="ca8eb-149">이 리소스는 어디에서 나 속성 값으로 사용할 수 있습니다 단추 스타일 setter 내에 포함 하 여 응용 프로그램에 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="ca8eb-150">이제 모든 단추가는 <xref:System.Windows.Controls.Control.Background%2A> 이 그라데이션의 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="ca8eb-151">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-151">Press F5 to run the application.</span></span> <span data-ttu-id="ca8eb-152">다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="ca8eb-153">![그라데이션 배경이 있는 단추](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="ca8eb-154">단추의 모양을 정의 하는 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="ca8eb-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="ca8eb-155">이 섹션에서는 단추의 모양을 (presentation) 사용자 지정 하는 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="ca8eb-156">단추 표시 단추에 고유한 모양을 제공 하려면 사각형 및 기타 구성 요소를 포함 하는 여러 개체의 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="ca8eb-157">지금 응용 프로그램에서 단추 모양을 제어 단추의 속성을 변경 하려면 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="ca8eb-158">단추의 모양 근본적으로 변경 하려면 어떻게 해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="ca8eb-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="ca8eb-159">템플릿을 개체의 표시를 보다 강력한 제어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="ca8eb-160">템플릿 스타일 내에서 사용할 수 있으므로 (이 연습에서는 단추)에 스타일 적용 되는 모든 개체에 템플릿을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="ca8eb-161">템플릿을 사용 하 여 단추의 모양을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="ca8eb-161">To use the template to define the look of the button</span></span>  
  
1. <span data-ttu-id="ca8eb-162">**서식 파일을 설정 합니다.** 컨트롤 때문 <xref:System.Windows.Controls.Button> 가 <xref:System.Windows.Controls.Control.Template%2A> 속성을 다른 속성 값에서 설정한 것 처럼 템플릿 속성 값을 정의할 수 있습니다를 <xref:System.Windows.Style> 사용 하 여를 <xref:System.Windows.Setter>입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="ca8eb-163">단추 스타일을 다음 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-163">Add the following highlighted markup to your button style.</span></span>  
  
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
  
2. <span data-ttu-id="ca8eb-164">**단추 표시를 변경 합니다.** 이 시점에서 템플릿을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="ca8eb-165">다음 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-165">Add the following highlighted markup.</span></span> <span data-ttu-id="ca8eb-166">이 태그 지정 두 <xref:System.Windows.Shapes.Rectangle> 뒤에 둥근 가장자리와 요소를 <xref:System.Windows.Controls.DockPanel>입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="ca8eb-167"><xref:System.Windows.Controls.DockPanel> 는 호스트에는 <xref:System.Windows.Controls.ContentPresenter> 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="ca8eb-168"><xref:System.Windows.Controls.ContentPresenter> 단추의 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="ca8eb-169">이 연습에서는 콘텐츠는 텍스트 ("단추 1", "단추 2", "단추 3").</span><span class="sxs-lookup"><span data-stu-id="ca8eb-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="ca8eb-170">모든 템플릿 구성 요소 (사각형 및 <xref:System.Windows.Controls.DockPanel>) 내에 배치 되는 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-171">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-171">Press F5 to run the application.</span></span> <span data-ttu-id="ca8eb-172">다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="ca8eb-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3. <span data-ttu-id="ca8eb-174">**서식 파일을 템플릿에 추가 합니다.** 다음은 투명 효과 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="ca8eb-175">먼저 투명 그라데이션 효과 만드는 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="ca8eb-176">이러한 그라데이션 리소스 내에서 추가 된 `Application.Resources` 블록:</span><span class="sxs-lookup"><span data-stu-id="ca8eb-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-177">으로 이러한 리소스를 사용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 에 삽입 하는 사각형에 대 한는 <xref:System.Windows.Controls.Grid> 단추 템플릿.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="ca8eb-178">템플릿에 다음 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-178">Add the following highlighted markup to the template.</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-179">있음을 합니다 <xref:System.Windows.UIElement.Opacity%2A> 사용 하 여 사각형의는 `x:Name` "glassCube"의 속성은 0으로, 샘플을 실행 하는 경우 표시 되지 않으면 위쪽에 오버레이된 투명 효과 사각형을 하므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="ca8eb-180">나중에 트리거를 추가 하기 위한 템플릿이 단추와 상호 작용할 때 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="ca8eb-181">단추 모양을 지금 변경 하 여 볼 수는 있지만 <xref:System.Windows.UIElement.Opacity%2A> 값 1 및 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="ca8eb-182">다음 그림을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-182">See the following figure.</span></span> <span data-ttu-id="ca8eb-183">다음 단계를 계속 하기 전에 변경 된 <xref:System.Windows.UIElement.Opacity%2A> 다시 0으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="ca8eb-184">![XAML을 사용 하 여 생성 된 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="ca8eb-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="ca8eb-185">단추 대화형 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="ca8eb-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="ca8eb-186">이 섹션에서는 속성 트리거 및 이벤트 트리거 속성 값을 변경 하 고 애니메이션 단추 위로 마우스 포인터를 이동 하 고 클릭과 같은 사용자 작업에 대 한 응답을 실행를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="ca8eb-187">대화형 작업 (위로 마우스를 가져가면, 밖으로 마우스, 클릭, 및 등)을 추가 하는 간편한 방법은 자신의 템플릿 또는 스타일 내에서 트리거를 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="ca8eb-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="ca8eb-188">만들려는 <xref:System.Windows.Trigger>와 같은 "condition" 속성을 정의 합니다. 단추 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성 값이 같지 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="ca8eb-189">그런 다음 트리거 조건이 true 일 때 발생 하는 setter (작업)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="ca8eb-190">단추 대화형 작업을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca8eb-190">To create button interactivity</span></span>  
  
1. <span data-ttu-id="ca8eb-191">**템플릿 트리거를 추가 합니다.** 서식 파일에 강조 표시 된 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
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
  
2. <span data-ttu-id="ca8eb-192">**속성 트리거를 추가 합니다.** 강조 표시 된 태그를 추가 합니다 `ControlTemplate.Triggers` 블록:</span><span class="sxs-lookup"><span data-stu-id="ca8eb-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```xaml
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="ca8eb-193">F5 키를 눌러 응용 프로그램을 실행 하 고 단추 위에 마우스 포인터를 실행 하는 대로 효과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3. <span data-ttu-id="ca8eb-194">**포커스 트리거를 추가 합니다.** 다음으로, 몇 가지 유사한 setter 단추에 (예: 사용자가 클릭 한 후) 포커스가 있을 때 경우를 처리 하도록 추가 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-195">F5 키를 눌러 응용 프로그램을 실행 하 여 단추 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="ca8eb-196">포커스를 여전히 있기 때문에 클릭 한 후 단추를 강조 표시에 유지 된다는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="ca8eb-197">또 다른 단추를 클릭 하면 마지막 손실 하는 동안 새 단추 포커스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4. <span data-ttu-id="ca8eb-198">**추가 대 한 애니메이션** <xref:System.Windows.UIElement.MouseEnter> **하 고** <xref:System.Windows.UIElement.MouseLeave> **:** 다음 몇 가지 애니메이션 트리거를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="ca8eb-199">내에 다음 태그를 추가 합니다 `ControlTemplate.Triggers` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-200">투명 효과 사각형을 마우스 포인터를 단추 위로 이동 하 고 포인터를 벗어날 때 원래 크기로 다시 반환 하는 경우 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="ca8eb-201">포인터를 단추 위로 이동할 때 트리거되는 두 개의 애니메이션이 (<xref:System.Windows.UIElement.MouseEnter> 이벤트 발생).</span><span class="sxs-lookup"><span data-stu-id="ca8eb-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="ca8eb-202">이러한 애니메이션 X 및 Y 축에 투명 효과 사각형을 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="ca8eb-203">속성을 확인 합니다 <xref:System.Windows.Media.Animation.DoubleAnimation> 요소 — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="ca8eb-204">합니다 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션 0.5 초 동안에 발생 하도록 지정 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 투명 10% 씩 축소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="ca8eb-205">두 번째 이벤트 트리거 (<xref:System.Windows.UIElement.MouseLeave>) 첫 번째 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="ca8eb-206">중지 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, 기본값으로 애니메이션된 속성을 모두 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="ca8eb-207">따라서 사용자를 단추 밖 포인터를 움직이면 단추가 돌아갑니다를 단추 위로 마우스 포인터를 이동 하기 전의 방식.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="ca8eb-208">애니메이션에 대 한 자세한 내용은 참조 하세요. [애니메이션 개요](../graphics-multimedia/animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>  
  
5. <span data-ttu-id="ca8eb-209">**단추를 클릭 하는 경우에 대 한 애니메이션을 추가 합니다.** 마지막 단계는 사용자가 단추를 클릭에 대 한 트리거를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="ca8eb-210">내에 다음 태그를 추가 합니다 `ControlTemplate.Triggers` 블록:</span><span class="sxs-lookup"><span data-stu-id="ca8eb-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
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
  
     <span data-ttu-id="ca8eb-211">F5 키를 눌러 응용 프로그램을 실행 하 고 단추 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="ca8eb-212">단추를 클릭 하면 투명 효과 사각형을 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ca8eb-213">요약</span><span class="sxs-lookup"><span data-stu-id="ca8eb-213">Summary</span></span>  
 <span data-ttu-id="ca8eb-214">이 연습에서는 다음 연습을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="ca8eb-215">대상으로 한 <xref:System.Windows.Style> 개체 유형 (<xref:System.Windows.Controls.Button>).</span><span class="sxs-lookup"><span data-stu-id="ca8eb-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="ca8eb-216">기본 단추의 속성을 사용 하 여 전체 응용 프로그램 제어는 <xref:System.Windows.Style>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="ca8eb-217">속성 값에 사용할 그라데이션 같은 리소스를 생성 합니다 <xref:System.Windows.Style> setter.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="ca8eb-218">단추에 템플릿을 적용 하 여 전체 응용 프로그램의 단추 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="ca8eb-219">사용자 작업에 대 한 응답에 있는 단추에 대 한 동작을 사용자 지정 (같은 <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, 및 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) 애니메이션 효과 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8eb-220">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca8eb-220">See also</span></span>

- [<span data-ttu-id="ca8eb-221">Microsoft Expression Blend를 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="ca8eb-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="ca8eb-222">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ca8eb-222">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="ca8eb-223">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ca8eb-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="ca8eb-224">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="ca8eb-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="ca8eb-225">비트맵 효과 개요</span><span class="sxs-lookup"><span data-stu-id="ca8eb-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
