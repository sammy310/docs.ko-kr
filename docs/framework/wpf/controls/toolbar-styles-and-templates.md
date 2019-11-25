---
title: ToolBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: a984311234386cb205d5db35f18a743ca535ff05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283664"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="35cbc-102">ToolBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35cbc-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="35cbc-103">이 항목에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="35cbc-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="35cbc-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35cbc-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="35cbc-106">도구 모음 파트</span><span class="sxs-lookup"><span data-stu-id="35cbc-106">ToolBar Parts</span></span>  
 <span data-ttu-id="35cbc-107">다음 표에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="35cbc-108">부분</span><span class="sxs-lookup"><span data-stu-id="35cbc-108">Part</span></span>|<span data-ttu-id="35cbc-109">형식</span><span class="sxs-lookup"><span data-stu-id="35cbc-109">Type</span></span>|<span data-ttu-id="35cbc-110">설명</span><span class="sxs-lookup"><span data-stu-id="35cbc-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="35cbc-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="35cbc-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="35cbc-112"><xref:System.Windows.Controls.ToolBar>에 대 한 컨트롤을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="35cbc-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="35cbc-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="35cbc-114"><xref:System.Windows.Controls.ToolBar>의 오버플로 영역에 있는 컨트롤을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="35cbc-115"><xref:System.Windows.Controls.ToolBar>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="35cbc-116"><xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.ToolBar>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="35cbc-117"><xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="35cbc-118">도구 모음 상태</span><span class="sxs-lookup"><span data-stu-id="35cbc-118">ToolBar States</span></span>  
 <span data-ttu-id="35cbc-119">다음 표에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="35cbc-120">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="35cbc-120">VisualState Name</span></span>|<span data-ttu-id="35cbc-121">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="35cbc-121">VisualStateGroup Name</span></span>|<span data-ttu-id="35cbc-122">설명</span><span class="sxs-lookup"><span data-stu-id="35cbc-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="35cbc-123">유효</span><span class="sxs-lookup"><span data-stu-id="35cbc-123">Valid</span></span>|<span data-ttu-id="35cbc-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35cbc-124">ValidationStates</span></span>|<span data-ttu-id="35cbc-125">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="35cbc-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="35cbc-126">InvalidFocused</span></span>|<span data-ttu-id="35cbc-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35cbc-127">ValidationStates</span></span>|<span data-ttu-id="35cbc-128">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="35cbc-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="35cbc-129">InvalidUnfocused</span></span>|<span data-ttu-id="35cbc-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35cbc-130">ValidationStates</span></span>|<span data-ttu-id="35cbc-131">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="35cbc-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="35cbc-132">ToolBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="35cbc-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="35cbc-133">다음 예제에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="35cbc-134">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="35cbc-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="35cbc-135">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35cbc-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cbc-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35cbc-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="35cbc-137">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35cbc-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="35cbc-138">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="35cbc-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="35cbc-139">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35cbc-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="35cbc-140">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="35cbc-140">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
