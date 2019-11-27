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
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283547"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="68e5b-102">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="68e5b-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="68e5b-103">이 항목에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="68e5b-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="68e5b-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68e5b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="68e5b-106">ContextMenu 파트</span><span class="sxs-lookup"><span data-stu-id="68e5b-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="68e5b-107"><xref:System.Windows.Controls.ContextMenu> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="68e5b-108"><xref:System.Windows.Controls.ContextMenu>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="68e5b-109"><xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.ContextMenu>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="68e5b-110"><xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="68e5b-111">ContextMenu 상태</span><span class="sxs-lookup"><span data-stu-id="68e5b-111">ContextMenu States</span></span>  
 <span data-ttu-id="68e5b-112">다음 표에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="68e5b-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="68e5b-113">VisualState Name</span></span>|<span data-ttu-id="68e5b-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="68e5b-114">VisualStateGroup Name</span></span>|<span data-ttu-id="68e5b-115">설명</span><span class="sxs-lookup"><span data-stu-id="68e5b-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="68e5b-116">Valid</span><span class="sxs-lookup"><span data-stu-id="68e5b-116">Valid</span></span>|<span data-ttu-id="68e5b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="68e5b-117">ValidationStates</span></span>|<span data-ttu-id="68e5b-118">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="68e5b-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="68e5b-119">InvalidFocused</span></span>|<span data-ttu-id="68e5b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="68e5b-120">ValidationStates</span></span>|<span data-ttu-id="68e5b-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="68e5b-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="68e5b-122">InvalidUnfocused</span></span>|<span data-ttu-id="68e5b-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="68e5b-123">ValidationStates</span></span>|<span data-ttu-id="68e5b-124">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="68e5b-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="68e5b-125">ContextMenu ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="68e5b-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="68e5b-126">다음 예제에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="68e5b-127"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e5b-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="68e5b-128">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68e5b-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e5b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68e5b-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="68e5b-130">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="68e5b-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="68e5b-131">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="68e5b-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="68e5b-132">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="68e5b-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="68e5b-133">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="68e5b-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
