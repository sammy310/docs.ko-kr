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
ms.openlocfilehash: 1cbb8d54a544b70b4a484c06c6bb2e9ca25029da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156327"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="0b310-102">ToolBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0b310-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="0b310-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="0b310-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0b310-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b310-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="0b310-106">도구 모음의 부분</span><span class="sxs-lookup"><span data-stu-id="0b310-106">ToolBar Parts</span></span>  
 <span data-ttu-id="0b310-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="0b310-108">파트</span><span class="sxs-lookup"><span data-stu-id="0b310-108">Part</span></span>|<span data-ttu-id="0b310-109">형식</span><span class="sxs-lookup"><span data-stu-id="0b310-109">Type</span></span>|<span data-ttu-id="0b310-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b310-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0b310-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="0b310-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="0b310-112">컨트롤에 포함 된 개체는 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="0b310-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="0b310-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="0b310-114">넘침 영역에 있는 컨트롤을 포함 하는 개체는 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="0b310-115">만들 때를 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ToolBar>, 템플릿에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="0b310-116">(합니다 <xref:System.Windows.Controls.ItemsPresenter> 에 각 항목을 표시 합니다 <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤을 사용할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="0b310-117">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직접 자식이 아닌 합니다 <xref:System.Windows.Controls.ScrollViewer>, 부여 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="0b310-118">도구 모음 상태</span><span class="sxs-lookup"><span data-stu-id="0b310-118">ToolBar States</span></span>  
 <span data-ttu-id="0b310-119">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="0b310-120">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="0b310-120">VisualState Name</span></span>|<span data-ttu-id="0b310-121">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="0b310-121">VisualStateGroup Name</span></span>|<span data-ttu-id="0b310-122">설명</span><span class="sxs-lookup"><span data-stu-id="0b310-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0b310-123">유효</span><span class="sxs-lookup"><span data-stu-id="0b310-123">Valid</span></span>|<span data-ttu-id="0b310-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0b310-124">ValidationStates</span></span>|<span data-ttu-id="0b310-125">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0b310-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0b310-126">InvalidFocused</span></span>|<span data-ttu-id="0b310-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0b310-127">ValidationStates</span></span>|<span data-ttu-id="0b310-128">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0b310-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0b310-129">InvalidUnfocused</span></span>|<span data-ttu-id="0b310-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0b310-130">ValidationStates</span></span>|<span data-ttu-id="0b310-131">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="0b310-132">도구 모음 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="0b310-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0b310-133">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="0b310-134">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b310-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0b310-135">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b310-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b310-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b310-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0b310-137">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0b310-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0b310-138">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0b310-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0b310-139">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0b310-139">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0b310-140">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0b310-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
