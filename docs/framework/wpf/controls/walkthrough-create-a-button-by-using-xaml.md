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
# <a name="walkthrough-create-a-button-by-using-xaml"></a>연습: XAML을 사용하여 단추 만들기

이 연습의 목적은 WPF(Windows 프레젠테이션 재단) 응용 프로그램에서 사용할 애니메이션 단추를 만드는 방법을 알아보는 것입니다. 이 연습에서는 스타일과 템플릿을 사용하여 코드를 다시 사용하고 단추 선언에서 단추 논리를 분리할 수 있는 사용자 지정된 단추 리소스를 만듭니다. 이 연습은 전적으로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 기록됩니다.

> [!IMPORTANT]
> 이 연습에서는 Visual Studio에 입력하거나 복사하여 붙여넣기를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 통해 응용 프로그램을 만드는 단계를 안내합니다. 디자이너를 사용하여 동일한 응용 프로그램을 만드는 방법을 알아보려면 [Microsoft 표현식 혼합을 사용하여 단추 만들기를](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)참조하십시오.

다음 그림은 완성된 단추를 보여 주며, 완료된 단추를 보여 주어 도표입니다.

![XAML을 사용하여 만든 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>기본 단추 만들기

먼저 새 프로젝트를 만들고 창에 몇 개의 단추를 추가해 보겠습니다.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>새 WPF 프로젝트를 만들고 창에 단추를 추가하려면

1. Visual Studio를 시작합니다.

2. **새 WPF 프로젝트 만들기:** **파일** 메뉴에서 **새로**를 가리킨 다음 **프로젝트**를 클릭합니다. Windows **응용 프로그램(WPF)** 템플릿을 찾아 프로젝트 이름을 "AnimatedButton"로 지정합니다. 이렇게 하면 응용 프로그램에 대한 골격이 생성됩니다.

3. **기본 기본 단추 추가:** 이 연습에 필요한 모든 파일은 템플릿에서 제공합니다. 솔루션 탐색기에서 Window1.xaml 파일을 두 번 클릭하여 엽니다. 기본적으로 Window1.xaml에는 요소가 있습니다. <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Grid> 요소를 제거하고 다음 강조 표시된 코드를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 입력하거나 복사하여 다음 코드를 Window1.xaml에 붙여넣도록 페이지에 몇 개의 단추를 추가합니다.

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

     응용 프로그램을 실행하려면 F5를 누르십시오. 다음 그림과 같은 단추 집합이 표시됩니다.

     ![세 개의 기본 단추](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     기본 단추를 만들었으니 Window1.xaml 파일에서 작업이 완료되었습니다. 이 연습의 나머지 부분에서는 app.xaml 파일에 초점을 맞추고 단추에 대한 스타일과 템플릿을 정의합니다.

## <a name="set-basic-properties"></a>기본 속성 설정

다음으로 이러한 단추의 일부 속성을 설정하여 단추 모양과 레이아웃을 제어해 보겠습니다. 단추에 속성을 개별적으로 설정하는 대신 리소스를 사용하여 전체 응용 프로그램에 대한 단추 속성을 정의합니다. 응용 프로그램 리소스는 웹 페이지의 외부 계단식 스타일 시트(CSS)와 개념적으로 유사합니다. 그러나 이 연습의 끝에서 볼 수 있듯이 리소스는 CSS(계단식 스타일 시트)보다 훨씬 강력합니다. 리소스에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>스타일을 사용하여 단추의 기본 속성을 설정하려면

1. **응용 프로그램 정의.리소스 블록:** app.xaml을 열고 아직 없는 경우 다음 강조 표시된 태그를 추가합니다.

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

     리소스 범위는 리소스를 정의하는 위치에 따라 결정됩니다. app.xaml 파일에서 `Application.Resources` 리소스를 정의하면 응용 프로그램의 어느 곳에서나 리소스를 사용할 수 있습니다. 리소스 범위 정의에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.

2. **스타일을 만들고 스타일을 사용하여 기본 속성 값을 정의합니다.** 블록에 다음 태그를 `Application.Resources` 추가합니다. 이 태그는 <xref:System.Windows.Style> 응용 프로그램의 모든 단추에 적용되는 단추를 만들고 <xref:System.Windows.FrameworkElement.Width%2A> 단추를 90으로 설정하고 <xref:System.Windows.FrameworkElement.Margin%2A> 10으로 설정합니다.

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     속성은 <xref:System.Windows.Style.TargetType%2A> 스타일형식의 모든 개체에 적용 <xref:System.Windows.Controls.Button>되도록 지정 합니다. 각각은 <xref:System.Windows.Setter> 에 대해 다른 <xref:System.Windows.Style>속성 값을 설정합니다. 따라서 이 시점에서 응용 프로그램의 모든 단추의 너비는 90이고 여백은 10입니다.  응용 프로그램을 실행하기 위해 F5를 누르면 다음 창이 표시됩니다.

     ![너비 90, 여백 10의 단추](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     대상 개체를 미세 조정하는 다양한 방법, 복잡한 속성 값을 지정하는 방법, 다른 스타일에 대한 입력으로 스타일을 사용하는 등 스타일로 수행할 수 있는 방법이 훨씬 더 많습니다. 자세한 내용은 [스타일 지정 및 템플릿을](../../../desktop-wpf/fundamentals/styles-templates-overview.md)참조하십시오.

3. **스타일 속성 값을 리소스에 설정합니다.** 리소스를 사용하면 일반적으로 정의된 개체와 값을 재사용할 수 있습니다. 특히 리소스를 사용하여 복잡한 값을 정의하여 코드를 보다 모듈화하는 것이 유용합니다. app.xaml에 다음 강조 표시된 태그를 추가합니다.

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

     `Application.Resources` 블록 바로 아래에서 "GrayBlueGradient브러시"라는 리소스를 만들었습니다. 이 리소스는 수평 그라데이션을 정의합니다. 이 리소스는 <xref:System.Windows.Controls.Control.Background%2A> 속성에 대한 단추 스타일 setter 내부를 포함하여 응용 프로그램의 어느 곳에서나 속성 값으로 사용할 수 있습니다. 이제 모든 단추에 이 <xref:System.Windows.Controls.Control.Background%2A> 그라데이션의 속성 값이 있습니다.

     F5 키를 눌러 애플리케이션을 실행합니다. 다음과 같이 보일 것입니다.

     ![그라데이션 배경이 있는 단추](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>단추모양을 정의하는 템플릿 만들기

이 섹션에서는 단추의 모양(프레젠테이션)을 사용자 지정하는 템플릿을 만듭니다. 단추 프레젠테이션은 단추를 고유한 모양으로 지정하기 위해 사각형 및 기타 구성 요소를 비롯한 여러 개체로 구성됩니다.

지금까지 응용 프로그램에서 단추 모양의 제어는 단추의 속성을 변경하는 데 국한되었습니다. 단추의 모양에 더 급진적인 변화를 원한다면 어떻게 해야 합니까? 템플릿을 사용하면 개체의 프레젠테이션을 강력하게 제어할 수 있습니다. 템플릿은 스타일 내에서 사용할 수 있으므로 스타일이 적용되는 모든 개체에 템플릿을 적용할 수 있습니다(이 연습에서 단추).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>템플릿을 사용하여 단추의 모양을 정의하려면

1. **템플릿 설정:** 속성과 <xref:System.Windows.Controls.Button> 같은 <xref:System.Windows.Controls.Control.Template%2A> 컨트롤에는 <xref:System.Windows.Style> <xref:System.Windows.Setter>using에서 설정한 다른 속성 값과 마찬가지로 템플릿 속성 값을 정의할 수 있습니다. 단추 스타일에 다음 강조 표시된 태그를 추가합니다.

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

2. **버튼 표시 변경:** 이 시점에서 템플릿을 정의해야 합니다. 강조 표시된 태그는 다음과 같은 태그를 추가합니다. 이 태그는 둥근 <xref:System.Windows.Shapes.Rectangle> 모서리가 있는 두 요소를 지정한 다음 <xref:System.Windows.Controls.DockPanel>을 지정합니다. 는 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.ContentPresenter> 단추를 호스트하는 데 사용됩니다. A는 <xref:System.Windows.Controls.ContentPresenter> 단추의 내용을 표시합니다. 이 연습에서 내용은 텍스트입니다("단추 1", "단추 2", "단추 3"). 모든 템플릿 구성 요소(사각형 <xref:System.Windows.Controls.DockPanel>및)는 <xref:System.Windows.Controls.Grid>의 내부에 배치됩니다.

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

     F5 키를 눌러 애플리케이션을 실행합니다. 다음과 같이 보일 것입니다.

     ![버튼 3개](./media/custom-button-animatedbutton-4.gif)

3. **템플릿에 유리 효과를 추가합니다.** 다음으로 유리를 추가합니다. 먼저 유리 그라데이션 효과를 만드는 몇 가지 리소스를 만듭니다. 이러한 그라데이션 리소스를 `Application.Resources` 블록 내의 아무 곳에나 추가합니다.

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

     이러한 리소스는 단추 <xref:System.Windows.Shapes.Shape.Fill%2A> 템플릿에 삽입하는 <xref:System.Windows.Controls.Grid> 사각형의 리소스로 사용됩니다. 템플릿에 다음 강조 표시된 태그를 추가합니다.

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

     <xref:System.Windows.UIElement.Opacity%2A> "glassCube"의 `x:Name` 속성이 있는 사각형의 경우 0이므로 샘플을 실행할 때 위에 유리 사각형이 겹쳐져 있지 않습니다. 이는 나중에 사용자가 단추와 상호 작용할 때 템플릿에 트리거를 추가하기 때문입니다. 그러나 값을 1로 변경하고 응용 프로그램을 실행하여 단추의 <xref:System.Windows.UIElement.Opacity%2A> 모양을 볼 수 있습니다. 다음 그림을 참조하세요. 다음 단계로 진행하기 전에 <xref:System.Windows.UIElement.Opacity%2A> 뒤로 0으로 변경합니다.

     ![XAML을 사용하여 만든 사용자 지정 단추](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>버튼 상호 작용 만들기

이 섹션에서는 속성 값을 변경하고 단추 위로 마우스 포인터를 이동하고 클릭하는 등의 사용자 작업에 대한 응답으로 애니메이션을 실행하는 속성 트리거 및 이벤트 트리거를 만듭니다.

대화형 작업을 추가하는 쉬운 방법(마우스 오버, 마우스 리브, 클릭 등)은 템플릿 또는 스타일 내에서 트리거를 정의하는 것입니다. 을 <xref:System.Windows.Trigger>만들려면 다음과 같은 속성 "조건"을 <xref:System.Windows.UIElement.IsMouseOver%2A> 정의합니다. `true` 그런 다음 트리거 조건이 true일 때 수행되는 setter(작업)를 정의합니다.

### <a name="to-create-button-interactivity"></a>단추 상호 작용을 만들려면

1. **템플릿 트리거 추가:** 강조 표시된 태그를 템플릿에 추가합니다.

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

2. **속성 트리거 추가:** 강조 표시된 태그를 블록에 `ControlTemplate.Triggers` 추가합니다.

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     F5를 눌러 응용 프로그램을 실행하고 단추 위에 마우스 포인터를 실행할 때 효과를 확인합니다.

3. **포커스 트리거 추가:** 다음으로 단추에 포커스가 있는 경우(예: 사용자가 클릭한 후)를 처리하기 위해 몇 가지 유사한 setter를 추가합니다.

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

     응용 프로그램을 실행하고 버튼 중 하나를 클릭하려면 F5를 누릅니다. 단추는 여전히 포커스가 있기 때문에 단추를 클릭한 후에도 강조 표시됩니다. 다른 단추를 클릭하면 새 버튼이 포커스를 얻고 마지막 단추는 포커스를 잃게 됩니다.

4. **Add animations for**<xref:System.Windows.UIElement.MouseEnter> **and** 및 <xref:System.Windows.UIElement.MouseLeave> **:** 다음에 트리거에 애니메이션을 추가합니다.   블록 내부의 아무 곳에나 `ControlTemplate.Triggers` 다음 태그를 추가합니다.

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

     마우스 포인터가 단추 위로 이동하면 유리 사각형이 축소되고 포인터가 나오면 정상 크기로 돌아갑니다.

     포인터가 단추를 넘을 때 트리거되는 두 가지<xref:System.Windows.UIElement.MouseEnter> 애니메이션이 있습니다(이벤트가 발생). 이러한 애니메이션은 X 축과 Y축을 따라 유리 사각형을 축소합니다. 요소의 속성및 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>에 주목하십시오. 애니메이션이 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 1초 이상 발생한다고 지정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 유리가 10% 축소되도록 지정합니다.

     두 번째 이벤트<xref:System.Windows.UIElement.MouseLeave>트리거 () 단순히 첫 번째 를 중지합니다. <xref:System.Windows.Media.Animation.Storyboard>을 중지하면 애니메이션된 모든 속성이 기본값으로 돌아갑니다. 따라서 사용자가 단추에서 포인터를 이동하면 단추는 마우스 포인터가 단추 위로 이동하기 전의 방식으로 돌아갑니다. 애니메이션에 대한 자세한 내용은 [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.

5. **단추를 클릭할 때 애니메이션추가:** 마지막 단계는 사용자가 단추를 클릭할 때 트리거를 추가하는 것입니다. 블록 내부의 아무 곳에나 `ControlTemplate.Triggers` 다음 태그추가

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

     응용 프로그램을 실행하려면 F5를 누르고 단추 중 하나를 클릭합니다. 단추를 클릭하면 유리 사각형이 회전합니다.

## <a name="summary"></a>요약
 이 연습에서는 다음 연습을 수행했습니다.

- 대상 <xref:System.Windows.Style> a 개체 유형<xref:System.Windows.Controls.Button>().

- 을 사용하여 전체 응용 프로그램에서 단추의 <xref:System.Windows.Style>제어된 기본 속성입니다.

- <xref:System.Windows.Style> 세터의 속성 값에 사용할 그라데이션과 같은 리소스를 만들었습니다.

- 단추에 템플릿을 적용하여 전체 응용 프로그램에서 단추 모양을 사용자 지정했습니다.

- 애니메이션 효과를 포함하는 사용자 작업(예: <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> <xref:System.Windows.Controls.Primitives.ButtonBase.Click>및) 단추에 대한 사용자 지정 동작입니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Expression Blend를 사용하여 단추 만들기](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [애니메이션 개요](../graphics-multimedia/animation-overview.md)
- [단색 및 그라데이션을 사용한 그리기 개요](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [비트맵 효과 개요](../graphics-multimedia/bitmap-effects-overview.md)
