---
title: ContextMenu 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 6650d5a7be8ebe8fc2dcd7af7c854da669de87f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123047"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="f0962-102">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="f0962-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="f0962-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="f0962-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f0962-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0962-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="f0962-106">ContextMenu 파트</span><span class="sxs-lookup"><span data-stu-id="f0962-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="f0962-107"><xref:System.Windows.Controls.ContextMenu> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="f0962-108">만들 때를 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ContextMenu>, 템플릿에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="f0962-109">(합니다 <xref:System.Windows.Controls.ItemsPresenter> 에 각 항목을 표시 합니다 <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤을 사용할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="f0962-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직접 자식이 아닌 합니다 <xref:System.Windows.Controls.ScrollViewer>, 부여 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="f0962-111">ContextMenu 상태</span><span class="sxs-lookup"><span data-stu-id="f0962-111">ContextMenu States</span></span>  
 <span data-ttu-id="f0962-112">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="f0962-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="f0962-113">VisualState Name</span></span>|<span data-ttu-id="f0962-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="f0962-114">VisualStateGroup Name</span></span>|<span data-ttu-id="f0962-115">설명</span><span class="sxs-lookup"><span data-stu-id="f0962-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f0962-116">유효</span><span class="sxs-lookup"><span data-stu-id="f0962-116">Valid</span></span>|<span data-ttu-id="f0962-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0962-117">ValidationStates</span></span>|<span data-ttu-id="f0962-118">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f0962-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f0962-119">InvalidFocused</span></span>|<span data-ttu-id="f0962-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0962-120">ValidationStates</span></span>|<span data-ttu-id="f0962-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f0962-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f0962-122">InvalidUnfocused</span></span>|<span data-ttu-id="f0962-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0962-123">ValidationStates</span></span>|<span data-ttu-id="f0962-124">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="f0962-125">ContextMenu ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="f0962-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="f0962-126">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="f0962-127"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0962-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f0962-128">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0962-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0962-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0962-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f0962-130">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="f0962-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f0962-131">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f0962-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f0962-132">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="f0962-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f0962-133">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f0962-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
