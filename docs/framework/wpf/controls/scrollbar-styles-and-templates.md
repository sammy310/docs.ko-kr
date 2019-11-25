---
title: ScrollBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283409"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="4f540-102">ScrollBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4f540-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="4f540-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="4f540-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4f540-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f540-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="4f540-106">스크롤 막대 부분</span><span class="sxs-lookup"><span data-stu-id="4f540-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="4f540-107">다음 표에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4f540-108">부분</span><span class="sxs-lookup"><span data-stu-id="4f540-108">Part</span></span>|<span data-ttu-id="4f540-109">형식</span><span class="sxs-lookup"><span data-stu-id="4f540-109">Type</span></span>|<span data-ttu-id="4f540-110">설명</span><span class="sxs-lookup"><span data-stu-id="4f540-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4f540-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="4f540-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="4f540-112"><xref:System.Windows.Controls.Primitives.ScrollBar>의 위치를 나타내는 요소에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="4f540-113">스크롤 막대 상태</span><span class="sxs-lookup"><span data-stu-id="4f540-113">ScrollBar States</span></span>  
 <span data-ttu-id="4f540-114">다음 표에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4f540-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="4f540-115">VisualState Name</span></span>|<span data-ttu-id="4f540-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="4f540-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4f540-117">설명</span><span class="sxs-lookup"><span data-stu-id="4f540-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4f540-118">보통</span><span class="sxs-lookup"><span data-stu-id="4f540-118">Normal</span></span>|<span data-ttu-id="4f540-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4f540-119">CommonStates</span></span>|<span data-ttu-id="4f540-120">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-120">The default state.</span></span>|  
|<span data-ttu-id="4f540-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4f540-121">MouseOver</span></span>|<span data-ttu-id="4f540-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4f540-122">CommonStates</span></span>|<span data-ttu-id="4f540-123">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4f540-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4f540-124">Disabled</span></span>|<span data-ttu-id="4f540-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4f540-125">CommonStates</span></span>|<span data-ttu-id="4f540-126">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-126">The control is disabled.</span></span>|  
|<span data-ttu-id="4f540-127">유효</span><span class="sxs-lookup"><span data-stu-id="4f540-127">Valid</span></span>|<span data-ttu-id="4f540-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f540-128">ValidationStates</span></span>|<span data-ttu-id="4f540-129">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4f540-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4f540-130">InvalidFocused</span></span>|<span data-ttu-id="4f540-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f540-131">ValidationStates</span></span>|<span data-ttu-id="4f540-132">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="4f540-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4f540-133">InvalidUnfocused</span></span>|<span data-ttu-id="4f540-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f540-134">ValidationStates</span></span>|<span data-ttu-id="4f540-135">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="4f540-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="4f540-136">ScrollBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="4f540-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="4f540-137">다음 예제에서는 <xref:System.Windows.Controls.Primitives.ScrollBar> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="4f540-138">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f540-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4f540-139">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f540-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f540-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f540-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4f540-141">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4f540-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4f540-142">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4f540-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4f540-143">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4f540-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4f540-144">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="4f540-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
