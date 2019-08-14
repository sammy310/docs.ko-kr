---
title: '연습: WPF 콘텐츠 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 32ca9658ddf4ab6e8690f29797b7ac7b09df2ca7
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012953"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="6e3a4-102">연습: WPF 콘텐츠 스타일</span><span class="sxs-lookup"><span data-stu-id="6e3a4-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="6e3a4-103">이 연습에서는 Windows Forms에 호스트되는 WPF(Windows Presentation Foundation) 컨트롤에 스타일을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="6e3a4-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="6e3a4-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-105">Create the project.</span></span>

- <span data-ttu-id="6e3a4-106">WPF 컨트롤 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-106">Create the WPF control type.</span></span>

- <span data-ttu-id="6e3a4-107">WPF 컨트롤에 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-107">Apply a style to the WPF control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e3a4-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6e3a4-108">Prerequisites</span></span>

<span data-ttu-id="6e3a4-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="6e3a4-110">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-110">Create the project</span></span>

<span data-ttu-id="6e3a4-111">Visual Studio를 열고 Visual Basic 또는 시각적 개체 C# `StylingWpfContent`에 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-111">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="6e3a4-112">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-112">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="6e3a4-113">WPF 컨트롤 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="6e3a4-113">Create the WPF control types</span></span>

<span data-ttu-id="6e3a4-114">프로젝트에 WPF 컨트롤 형식을 추가한 후 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-114">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="6e3a4-115">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-115">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="6e3a4-116">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-116">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="6e3a4-117">자세한 내용은 [연습: 디자인 타임](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)에 WINDOWS FORMS에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="6e3a4-117">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="6e3a4-118">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-118">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="6e3a4-119">자세한 내용은 [방법: Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))에서 요소를 선택 하 고 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-119">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="6e3a4-120">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성의 값을로 `200`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="6e3a4-121">에 컨트롤 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 을 추가 하 <xref:System.Windows.Controls.ContentControl.Content%2A>고 속성의 값을 Cancel로 설정 합니다 <xref:System.Windows.Controls.UserControl> .</span><span class="sxs-lookup"><span data-stu-id="6e3a4-121">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="6e3a4-122">에 두 번째 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 컨트롤을 추가 하 <xref:System.Windows.Controls.ContentControl.Content%2A> 고속성의값을OK로설정<xref:System.Windows.Controls.UserControl> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-122">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="6e3a4-123">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-123">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="6e3a4-124">WPF 컨트롤에 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="6e3a4-124">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="6e3a4-125">WPF 컨트롤에 다른 스타일을 적용하여 모양과 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-125">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="6e3a4-126">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-126">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="6e3a4-127">**도구 상자**에서을 두 번 클릭 `UserControl1` 하 여 폼에서의 `UserControl1` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-127">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="6e3a4-128">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-128">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="6e3a4-129">에 대 한 `elementHost1`스마트 태그 패널의 드롭다운 목록에서 **호스트 된 콘텐츠 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-129">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

     <span data-ttu-id="6e3a4-130">`UserControl1`이 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-130">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

1. <span data-ttu-id="6e3a4-131">XAML 뷰에서 `<UserControl>` 여는 태그 뒤에 다음 XAML을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-131">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>

     <span data-ttu-id="6e3a4-132">이 XAML은 대비되는 그라데이션 테두리가 있는 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-132">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="6e3a4-133">컨트롤을 클릭하면 그라데이션이 변경되어 눌린 단추 모양을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-133">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="6e3a4-134">자세한 내용은 [스타일 지정 및 템플릿](../../wpf/controls/styling-and-templating.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-134">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="6e3a4-135">다음 XAML을 취소 단추의 `<Button>` 태그에 삽입하여 이전 단계에서 정의된 `SimpleButton` 스타일을 취소 단추에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-135">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="6e3a4-136">단추 선언은 다음 XAML과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-136">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="6e3a4-137">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-137">Build the project.</span></span>

1. <span data-ttu-id="6e3a4-138">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-138">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="6e3a4-139">단추 컨트롤에 새 스타일이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-139">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="6e3a4-140">**디버그** 메뉴에서 **디버깅 시작** 을 선택 하 여 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-140">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="6e3a4-141">확인 및 취소 단추를 클릭하고 차이점을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a4-141">Click the OK and Cancel buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e3a4-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e3a4-142">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6e3a4-143">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="6e3a4-143">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="6e3a4-144">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="6e3a4-144">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="6e3a4-145">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="6e3a4-145">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6e3a4-146">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="6e3a4-146">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="6e3a4-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="6e3a4-147">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
