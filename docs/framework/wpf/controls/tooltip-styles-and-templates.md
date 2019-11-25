---
title: ToolTip 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: c7a14034d665c124d01e8a4b43c5d42968241925
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283642"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="6ef9d-102">ToolTip 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="6ef9d-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="6ef9d-103">이 항목에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="6ef9d-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6ef9d-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="6ef9d-106">도구 설명 파트</span><span class="sxs-lookup"><span data-stu-id="6ef9d-106">ToolTip Parts</span></span>  
 <span data-ttu-id="6ef9d-107"><xref:System.Windows.Controls.ToolTip> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="6ef9d-108">도구 설명 상태</span><span class="sxs-lookup"><span data-stu-id="6ef9d-108">ToolTip States</span></span>  
 <span data-ttu-id="6ef9d-109">다음 표에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="6ef9d-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="6ef9d-110">VisualState Name</span></span>|<span data-ttu-id="6ef9d-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="6ef9d-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6ef9d-112">설명</span><span class="sxs-lookup"><span data-stu-id="6ef9d-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6ef9d-113">Closed</span><span class="sxs-lookup"><span data-stu-id="6ef9d-113">Closed</span></span>|<span data-ttu-id="6ef9d-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="6ef9d-114">OpenStates</span></span>|<span data-ttu-id="6ef9d-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-115">The default state.</span></span>|  
|<span data-ttu-id="6ef9d-116">열기</span><span class="sxs-lookup"><span data-stu-id="6ef9d-116">Open</span></span>|<span data-ttu-id="6ef9d-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="6ef9d-117">OpenStates</span></span>|<span data-ttu-id="6ef9d-118"><xref:System.Windows.Controls.ToolTip> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="6ef9d-119">유효</span><span class="sxs-lookup"><span data-stu-id="6ef9d-119">Valid</span></span>|<span data-ttu-id="6ef9d-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ef9d-120">ValidationStates</span></span>|<span data-ttu-id="6ef9d-121">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6ef9d-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6ef9d-122">InvalidFocused</span></span>|<span data-ttu-id="6ef9d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ef9d-123">ValidationStates</span></span>|<span data-ttu-id="6ef9d-124">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6ef9d-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6ef9d-125">InvalidUnfocused</span></span>|<span data-ttu-id="6ef9d-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ef9d-126">ValidationStates</span></span>|<span data-ttu-id="6ef9d-127">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="6ef9d-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="6ef9d-128">ToolTip ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="6ef9d-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="6ef9d-129">다음 예제에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="6ef9d-130">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6ef9d-131">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef9d-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef9d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ef9d-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6ef9d-133">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="6ef9d-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6ef9d-134">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="6ef9d-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6ef9d-135">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="6ef9d-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="6ef9d-136">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="6ef9d-136">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
