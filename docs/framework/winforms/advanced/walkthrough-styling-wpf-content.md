---
title: '연습: WPF 콘텐츠 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 581fcbfdfd7806b8f0f70347ac96f1bf09fa9098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460942"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="03543-102">연습: WPF 콘텐츠 스타일</span><span class="sxs-lookup"><span data-stu-id="03543-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="03543-103">이 문서에서는 Windows Form에 호스팅된 Windows Presentation Foundation (WPF) 컨트롤에 스타일을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03543-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03543-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="03543-104">Prerequisites</span></span>

<span data-ttu-id="03543-105">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="03543-106">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03543-106">Create the project</span></span>

<span data-ttu-id="03543-107">Visual Studio를 열고 Visual Basic 또는 `StylingWpfContent`라는 시각적 개체 C# 에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03543-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="03543-108">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="03543-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="03543-109">WPF 컨트롤 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="03543-109">Create the WPF control types</span></span>

<span data-ttu-id="03543-110">프로젝트에 WPF 컨트롤 형식을 추가한 후 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03543-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="03543-111">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="03543-112">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="03543-113">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03543-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="03543-114">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="03543-115">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="03543-116"><xref:System.Windows.Controls.Button?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl>에 추가 하 고 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성의 값을 **취소**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="03543-117"><xref:System.Windows.Controls.UserControl>에 두 번째 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 컨트롤을 추가 하 고 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성의 값을 **확인**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="03543-118">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="03543-119">WPF 컨트롤에 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="03543-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="03543-120">WPF 컨트롤에 다른 스타일을 적용하여 모양과 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03543-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="03543-121">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03543-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="03543-122">**도구 상자**에서 `UserControl1`를 두 번 클릭 하 여 폼에 `UserControl1`의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03543-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="03543-123">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="03543-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="03543-124">`elementHost1`에 대 한 스마트 태그 패널의 드롭다운 목록에서 **호스트 된 콘텐츠 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="03543-125">`UserControl1` WPF 디자이너에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="03543-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="03543-126">XAML 뷰에서 `<UserControl>` 여는 태그 뒤에 다음 XAML을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="03543-127">이 XAML은 대비되는 그라데이션 테두리가 있는 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03543-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="03543-128">컨트롤을 클릭하면 그라데이션이 변경되어 눌린 단추 모양을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="03543-129">자세한 내용은 [스타일 지정 및 템플릿](../../wpf/controls/styling-and-templating.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03543-129">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

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

1. <span data-ttu-id="03543-130">**취소** 단추의 `<Button>` 태그에 다음 XAML을 삽입 하 여 이전 단계에서 정의한 `SimpleButton` 스타일을 취소 단추에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="03543-131">단추 선언은 다음 XAML과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="03543-132">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-132">Build the project.</span></span>

1. <span data-ttu-id="03543-133">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03543-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="03543-134">단추 컨트롤에 새 스타일이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03543-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="03543-135">**디버그** 메뉴에서 **디버깅 시작** 을 선택 하 여 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="03543-136">**확인** 및 **취소** 단추를 클릭 하 고 차이점을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03543-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="03543-137">참조</span><span class="sxs-lookup"><span data-stu-id="03543-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="03543-138">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="03543-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="03543-139">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="03543-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="03543-140">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="03543-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="03543-141">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="03543-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="03543-142">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="03543-142">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
