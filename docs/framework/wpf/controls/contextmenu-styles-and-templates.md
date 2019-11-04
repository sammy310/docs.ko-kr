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
ms.openlocfilehash: 4112306dab648d022e171401f5b9b362f2c91fdc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460755"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="bb832-102">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb832-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="bb832-103">이 항목에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="bb832-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bb832-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb832-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="bb832-106">ContextMenu 파트</span><span class="sxs-lookup"><span data-stu-id="bb832-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="bb832-107"><xref:System.Windows.Controls.ContextMenu> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="bb832-108"><xref:System.Windows.Controls.ContextMenu>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="bb832-109"><xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.ContextMenu>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="bb832-110"><xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="bb832-111">ContextMenu 상태</span><span class="sxs-lookup"><span data-stu-id="bb832-111">ContextMenu States</span></span>  
 <span data-ttu-id="bb832-112">다음 표에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="bb832-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="bb832-113">VisualState Name</span></span>|<span data-ttu-id="bb832-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="bb832-114">VisualStateGroup Name</span></span>|<span data-ttu-id="bb832-115">설명</span><span class="sxs-lookup"><span data-stu-id="bb832-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bb832-116">유효</span><span class="sxs-lookup"><span data-stu-id="bb832-116">Valid</span></span>|<span data-ttu-id="bb832-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb832-117">ValidationStates</span></span>|<span data-ttu-id="bb832-118">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bb832-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bb832-119">InvalidFocused</span></span>|<span data-ttu-id="bb832-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb832-120">ValidationStates</span></span>|<span data-ttu-id="bb832-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bb832-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bb832-122">InvalidUnfocused</span></span>|<span data-ttu-id="bb832-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb832-123">ValidationStates</span></span>|<span data-ttu-id="bb832-124">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="bb832-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="bb832-125">ContextMenu ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="bb832-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="bb832-126">다음 예제에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="bb832-127"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb832-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bb832-128">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb832-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb832-129">참조</span><span class="sxs-lookup"><span data-stu-id="bb832-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bb832-130">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb832-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bb832-131">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bb832-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bb832-132">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bb832-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bb832-133">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bb832-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
