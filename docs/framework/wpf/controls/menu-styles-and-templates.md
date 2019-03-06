---
title: Menu 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: d5b170bff841369e48d082f018577ee8f6f09f39
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355625"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="db9ab-102">Menu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="db9ab-102">Menu Styles and Templates</span></span>
<span data-ttu-id="db9ab-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="db9ab-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="db9ab-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db9ab-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="db9ab-106">메뉴 파트</span><span class="sxs-lookup"><span data-stu-id="db9ab-106">Menu Parts</span></span>  
 <span data-ttu-id="db9ab-107"><xref:System.Windows.Controls.Menu> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="db9ab-108">만들 때를 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Menu>, 템플릿에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="db9ab-109">(합니다 <xref:System.Windows.Controls.ItemsPresenter> 에 각 항목을 표시 합니다 <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤을 사용할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="db9ab-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직접 자식이 아닌 합니다 <xref:System.Windows.Controls.ScrollViewer>, 부여 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="db9ab-111">메뉴 상태</span><span class="sxs-lookup"><span data-stu-id="db9ab-111">Menu States</span></span>  
 <span data-ttu-id="db9ab-112">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="db9ab-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="db9ab-113">VisualState Name</span></span>|<span data-ttu-id="db9ab-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="db9ab-114">VisualStateGroup Name</span></span>|<span data-ttu-id="db9ab-115">설명</span><span class="sxs-lookup"><span data-stu-id="db9ab-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="db9ab-116">유효</span><span class="sxs-lookup"><span data-stu-id="db9ab-116">Valid</span></span>|<span data-ttu-id="db9ab-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-117">ValidationStates</span></span>|<span data-ttu-id="db9ab-118">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="db9ab-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="db9ab-119">InvalidFocused</span></span>|<span data-ttu-id="db9ab-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-120">ValidationStates</span></span>|<span data-ttu-id="db9ab-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="db9ab-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="db9ab-122">InvalidUnfocused</span></span>|<span data-ttu-id="db9ab-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-123">ValidationStates</span></span>|<span data-ttu-id="db9ab-124">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="db9ab-125">MenuItem 파트</span><span class="sxs-lookup"><span data-stu-id="db9ab-125">MenuItem Parts</span></span>  
 <span data-ttu-id="db9ab-126">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="db9ab-127">파트</span><span class="sxs-lookup"><span data-stu-id="db9ab-127">Part</span></span>|<span data-ttu-id="db9ab-128">형식</span><span class="sxs-lookup"><span data-stu-id="db9ab-128">Type</span></span>|<span data-ttu-id="db9ab-129">설명</span><span class="sxs-lookup"><span data-stu-id="db9ab-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="db9ab-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="db9ab-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="db9ab-131">하위 메뉴에 대 한 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="db9ab-132">만들 때를 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.MenuItem>, 템플릿에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="db9ab-133">(합니다 <xref:System.Windows.Controls.ItemsPresenter> 에 각 항목을 표시 합니다 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤을 사용할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="db9ab-134">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직접 자식이 아닌 합니다 <xref:System.Windows.Controls.ScrollViewer>, 부여 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="db9ab-135">MenuItem 상태</span><span class="sxs-lookup"><span data-stu-id="db9ab-135">MenuItem States</span></span>  
 <span data-ttu-id="db9ab-136">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.MenuItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="db9ab-137">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="db9ab-137">VisualState Name</span></span>|<span data-ttu-id="db9ab-138">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="db9ab-138">VisualStateGroup Name</span></span>|<span data-ttu-id="db9ab-139">설명</span><span class="sxs-lookup"><span data-stu-id="db9ab-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="db9ab-140">유효</span><span class="sxs-lookup"><span data-stu-id="db9ab-140">Valid</span></span>|<span data-ttu-id="db9ab-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-141">ValidationStates</span></span>|<span data-ttu-id="db9ab-142">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="db9ab-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="db9ab-143">InvalidFocused</span></span>|<span data-ttu-id="db9ab-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-144">ValidationStates</span></span>|<span data-ttu-id="db9ab-145">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="db9ab-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="db9ab-146">InvalidUnfocused</span></span>|<span data-ttu-id="db9ab-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="db9ab-147">ValidationStates</span></span>|<span data-ttu-id="db9ab-148">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="db9ab-149">메뉴 및 MenuItem ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="db9ab-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="db9ab-150">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="db9ab-151">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.MenuItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="db9ab-152">다음 예제에서는 정의 된 `MenuScrollViewer`, 이전 예제에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="db9ab-153"><xref:System.Windows.Controls.ControlTemplate> 예제에서는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9ab-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="db9ab-154">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db9ab-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9ab-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="db9ab-155">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="db9ab-156">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="db9ab-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="db9ab-157">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="db9ab-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="db9ab-158">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="db9ab-158">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="db9ab-159">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="db9ab-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
