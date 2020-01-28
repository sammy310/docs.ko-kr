---
title: Windows Forms에 대 한 WPF 컨트롤 선택
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746805"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="06ab0-102">연습: 디자인 타임에 Windows Forms에 WPF 콘텐츠 할당</span><span class="sxs-lookup"><span data-stu-id="06ab0-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="06ab0-103">이 문서에서는 폼에 표시 하려는 Windows Presentation Foundation (WPF) 컨트롤 형식을 선택 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="06ab0-104">프로젝트에 포함 된 모든 WPF 컨트롤 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="06ab0-105">전제 조건</span><span class="sxs-lookup"><span data-stu-id="06ab0-105">Prerequisites</span></span>

<span data-ttu-id="06ab0-106">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="06ab0-107">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-107">Create the project</span></span>

<span data-ttu-id="06ab0-108">Visual Studio를 열고 Visual Basic 또는 `SelectingWpfContent`라는 시각적 개체 C# 에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="06ab0-109">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="06ab0-110">WPF 컨트롤 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="06ab0-110">Create the WPF control types</span></span>

<span data-ttu-id="06ab0-111">프로젝트에 WPF 컨트롤 형식을 추가한 후 다양한 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="06ab0-112">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="06ab0-113">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="06ab0-114">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ab0-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="06ab0-115">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="06ab0-116">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="06ab0-117"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl>에 추가 하 고 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **Hosted Content**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="06ab0-118">프로젝트에 두 번째 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="06ab0-119">컨트롤 형식의 기본 이름인 `UserControl2.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="06ab0-120">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="06ab0-121"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl>에 추가 하 고 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **호스트 된 콘텐츠 2**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06ab0-122">일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="06ab0-123"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="06ab0-124">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="06ab0-125">WPF 컨트롤 선택</span><span class="sxs-lookup"><span data-stu-id="06ab0-125">Select WPF controls</span></span>

<span data-ttu-id="06ab0-126">이미 콘텐츠를 호스트하고 있는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 다른 WPF 콘텐츠를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="06ab0-127">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="06ab0-128">**도구 상자**에서 `UserControl1`를 두 번 클릭 하 여 폼에 `UserControl1`의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="06ab0-129">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="06ab0-130">`elementHost1`에 대 한 스마트 태그 패널에서 **호스팅된 콘텐츠 선택** 드롭다운 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="06ab0-131">드롭다운 목록 상자에서 **UserControl2** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="06ab0-132">이제 `elementHost1` 컨트롤이 `UserControl2` 형식의 인스턴스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="06ab0-133">**속성** 창에서 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl2**으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="06ab0-134">**도구 상자**의 **WPF 상호 운용성** 그룹에서 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="06ab0-135">새 컨트롤의 기본 이름은 `elementHost2`입니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="06ab0-136">`elementHost2`에 대 한 스마트 태그 패널에서 **호스팅된 콘텐츠 선택** 드롭다운 목록을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="06ab0-137">드롭다운 목록에서 **UserControl1** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="06ab0-138">이제 `elementHost2` 컨트롤이 `UserControl1` 형식의 인스턴스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="06ab0-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="06ab0-139">참조</span><span class="sxs-lookup"><span data-stu-id="06ab0-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="06ab0-140">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="06ab0-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="06ab0-141">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="06ab0-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="06ab0-142">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="06ab0-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
