---
title: Menu 스타일 및 템플릿
description: 메뉴 컨트롤 Windows Presentation Foundation 스타일 및 템플릿에 대해 알아봅니다. ControlTemplate를 수정 하 여 컨트롤에 고유한 모양을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 5187e4a479609686e39e043808931141ca52078c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164547"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="bb0d2-104">Menu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb0d2-104">Menu Styles and Templates</span></span>
<span data-ttu-id="bb0d2-105">이 항목에서는 컨트롤의 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Menu> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="bb0d2-106">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bb0d2-107">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="bb0d2-108">메뉴 파트</span><span class="sxs-lookup"><span data-stu-id="bb0d2-108">Menu Parts</span></span>  
 <span data-ttu-id="bb0d2-109"><xref:System.Windows.Controls.Menu>컨트롤에 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-109">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="bb0d2-110">에 대해를 만들 때 <xref:System.Windows.Controls.ControlTemplate> 템플릿에는 내에 <xref:System.Windows.Controls.Menu> 이 포함 될 수 있습니다 <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-110">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="bb0d2-111">는의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목을 표시 하 <xref:System.Windows.Controls.Menu> 고,는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-111">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="bb0d2-112"><xref:System.Windows.Controls.ItemsPresenter>이의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ScrollViewer> 이름을 지정 해야 합니다 <xref:System.Windows.Controls.ItemsPresenter> `ItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-112">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="bb0d2-113">메뉴 상태</span><span class="sxs-lookup"><span data-stu-id="bb0d2-113">Menu States</span></span>  
 <span data-ttu-id="bb0d2-114">다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.Menu> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-114">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="bb0d2-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="bb0d2-115">VisualState Name</span></span>|<span data-ttu-id="bb0d2-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="bb0d2-116">VisualStateGroup Name</span></span>|<span data-ttu-id="bb0d2-117">설명</span><span class="sxs-lookup"><span data-stu-id="bb0d2-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bb0d2-118">Valid</span><span class="sxs-lookup"><span data-stu-id="bb0d2-118">Valid</span></span>|<span data-ttu-id="bb0d2-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-119">ValidationStates</span></span>|<span data-ttu-id="bb0d2-120">컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bb0d2-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bb0d2-121">InvalidFocused</span></span>|<span data-ttu-id="bb0d2-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-122">ValidationStates</span></span>|<span data-ttu-id="bb0d2-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bb0d2-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bb0d2-124">InvalidUnfocused</span></span>|<span data-ttu-id="bb0d2-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-125">ValidationStates</span></span>|<span data-ttu-id="bb0d2-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="bb0d2-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="bb0d2-127">MenuItem 부분</span><span class="sxs-lookup"><span data-stu-id="bb0d2-127">MenuItem Parts</span></span>  
 <span data-ttu-id="bb0d2-128">다음 표에서는 컨트롤의 명명 된 파트를 나열 합니다 <xref:System.Windows.Controls.Menu> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-128">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="bb0d2-129">부분</span><span class="sxs-lookup"><span data-stu-id="bb0d2-129">Part</span></span>|<span data-ttu-id="bb0d2-130">Type</span><span class="sxs-lookup"><span data-stu-id="bb0d2-130">Type</span></span>|<span data-ttu-id="bb0d2-131">Description</span><span class="sxs-lookup"><span data-stu-id="bb0d2-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bb0d2-132">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="bb0d2-132">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="bb0d2-133">하위 메뉴의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-133">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="bb0d2-134">에 대해를 만들 때 <xref:System.Windows.Controls.ControlTemplate> 템플릿에는 내에 <xref:System.Windows.Controls.MenuItem> 이 포함 될 수 있습니다 <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-134">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="bb0d2-135">는의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목을 표시 하 <xref:System.Windows.Controls.MenuItem> 고,는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-135">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="bb0d2-136"><xref:System.Windows.Controls.ItemsPresenter>이의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ScrollViewer> 이름을 지정 해야 합니다 <xref:System.Windows.Controls.ItemsPresenter> `ItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-136">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="bb0d2-137">MenuItem 상태</span><span class="sxs-lookup"><span data-stu-id="bb0d2-137">MenuItem States</span></span>  
 <span data-ttu-id="bb0d2-138">다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.MenuItem> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-138">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="bb0d2-139">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="bb0d2-139">VisualState Name</span></span>|<span data-ttu-id="bb0d2-140">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="bb0d2-140">VisualStateGroup Name</span></span>|<span data-ttu-id="bb0d2-141">설명</span><span class="sxs-lookup"><span data-stu-id="bb0d2-141">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bb0d2-142">Valid</span><span class="sxs-lookup"><span data-stu-id="bb0d2-142">Valid</span></span>|<span data-ttu-id="bb0d2-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-143">ValidationStates</span></span>|<span data-ttu-id="bb0d2-144">컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-144">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bb0d2-145">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bb0d2-145">InvalidFocused</span></span>|<span data-ttu-id="bb0d2-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-146">ValidationStates</span></span>|<span data-ttu-id="bb0d2-147"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bb0d2-148">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bb0d2-148">InvalidUnfocused</span></span>|<span data-ttu-id="bb0d2-149">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb0d2-149">ValidationStates</span></span>|<span data-ttu-id="bb0d2-150"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="bb0d2-150">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="bb0d2-151">Menu 및 MenuItem ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="bb0d2-151">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="bb0d2-152">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Menu> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-152">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="bb0d2-153">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.MenuItem> .</span><span class="sxs-lookup"><span data-stu-id="bb0d2-153">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="bb0d2-154">다음 예제에서는 `MenuScrollViewer` 이전 예제에서 사용 되는을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-154">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="bb0d2-155">이 <xref:System.Windows.Controls.ControlTemplate> 예제에서는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-155">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bb0d2-156">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb0d2-156">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0d2-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb0d2-157">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bb0d2-158">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb0d2-158">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bb0d2-159">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bb0d2-159">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bb0d2-160">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb0d2-160">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bb0d2-161">컨트롤의 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="bb0d2-161">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
