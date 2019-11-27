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
ms.openlocfilehash: 3ce0be1fdeeee1465c2facb414cc7a081b268eb5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283474"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="c2f68-102">Menu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c2f68-102">Menu Styles and Templates</span></span>
<span data-ttu-id="c2f68-103">이 항목에서는 <xref:System.Windows.Controls.Menu> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="c2f68-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c2f68-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2f68-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="c2f68-106">메뉴 파트</span><span class="sxs-lookup"><span data-stu-id="c2f68-106">Menu Parts</span></span>  
 <span data-ttu-id="c2f68-107"><xref:System.Windows.Controls.Menu> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="c2f68-108"><xref:System.Windows.Controls.Menu>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="c2f68-109"><xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.Menu>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="c2f68-110"><xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="c2f68-111">메뉴 상태</span><span class="sxs-lookup"><span data-stu-id="c2f68-111">Menu States</span></span>  
 <span data-ttu-id="c2f68-112">다음 표에서는 <xref:System.Windows.Controls.Menu> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="c2f68-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="c2f68-113">VisualState Name</span></span>|<span data-ttu-id="c2f68-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="c2f68-114">VisualStateGroup Name</span></span>|<span data-ttu-id="c2f68-115">설명</span><span class="sxs-lookup"><span data-stu-id="c2f68-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c2f68-116">Valid</span><span class="sxs-lookup"><span data-stu-id="c2f68-116">Valid</span></span>|<span data-ttu-id="c2f68-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-117">ValidationStates</span></span>|<span data-ttu-id="c2f68-118">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c2f68-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c2f68-119">InvalidFocused</span></span>|<span data-ttu-id="c2f68-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-120">ValidationStates</span></span>|<span data-ttu-id="c2f68-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c2f68-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c2f68-122">InvalidUnfocused</span></span>|<span data-ttu-id="c2f68-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-123">ValidationStates</span></span>|<span data-ttu-id="c2f68-124">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c2f68-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="c2f68-125">MenuItem 부분</span><span class="sxs-lookup"><span data-stu-id="c2f68-125">MenuItem Parts</span></span>  
 <span data-ttu-id="c2f68-126">다음 표에서는 <xref:System.Windows.Controls.Menu> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="c2f68-127">파트</span><span class="sxs-lookup"><span data-stu-id="c2f68-127">Part</span></span>|<span data-ttu-id="c2f68-128">형식</span><span class="sxs-lookup"><span data-stu-id="c2f68-128">Type</span></span>|<span data-ttu-id="c2f68-129">설명</span><span class="sxs-lookup"><span data-stu-id="c2f68-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c2f68-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="c2f68-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="c2f68-131">하위 메뉴의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="c2f68-132"><xref:System.Windows.Controls.MenuItem>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="c2f68-133"><xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.MenuItem>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="c2f68-134"><xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="c2f68-135">MenuItem 상태</span><span class="sxs-lookup"><span data-stu-id="c2f68-135">MenuItem States</span></span>  
 <span data-ttu-id="c2f68-136">다음 표에서는 <xref:System.Windows.Controls.MenuItem> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="c2f68-137">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="c2f68-137">VisualState Name</span></span>|<span data-ttu-id="c2f68-138">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="c2f68-138">VisualStateGroup Name</span></span>|<span data-ttu-id="c2f68-139">설명</span><span class="sxs-lookup"><span data-stu-id="c2f68-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c2f68-140">Valid</span><span class="sxs-lookup"><span data-stu-id="c2f68-140">Valid</span></span>|<span data-ttu-id="c2f68-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-141">ValidationStates</span></span>|<span data-ttu-id="c2f68-142">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c2f68-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c2f68-143">InvalidFocused</span></span>|<span data-ttu-id="c2f68-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-144">ValidationStates</span></span>|<span data-ttu-id="c2f68-145">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c2f68-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c2f68-146">InvalidUnfocused</span></span>|<span data-ttu-id="c2f68-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c2f68-147">ValidationStates</span></span>|<span data-ttu-id="c2f68-148">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c2f68-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="c2f68-149">Menu 및 MenuItem ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="c2f68-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="c2f68-150">다음 예제에서는 <xref:System.Windows.Controls.Menu> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="c2f68-151">다음 예제에서는 <xref:System.Windows.Controls.MenuItem> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="c2f68-152">다음 예제에서는 이전 예제에서 사용 되는 `MenuScrollViewer`를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="c2f68-153"><xref:System.Windows.Controls.ControlTemplate> 예제에서는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f68-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c2f68-154">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2f68-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f68-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2f68-155">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c2f68-156">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c2f68-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c2f68-157">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c2f68-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c2f68-158">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c2f68-158">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c2f68-159">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="c2f68-159">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
