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
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="4a3c9-102">ToolTip 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4a3c9-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="4a3c9-103">이 항목에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="4a3c9-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4a3c9-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="4a3c9-106">도구 설명 파트</span><span class="sxs-lookup"><span data-stu-id="4a3c9-106">ToolTip Parts</span></span>  
 <span data-ttu-id="4a3c9-107"><xref:System.Windows.Controls.ToolTip> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="4a3c9-108">도구 설명 상태</span><span class="sxs-lookup"><span data-stu-id="4a3c9-108">ToolTip States</span></span>  
 <span data-ttu-id="4a3c9-109">다음 표에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="4a3c9-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="4a3c9-110">VisualState Name</span></span>|<span data-ttu-id="4a3c9-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="4a3c9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4a3c9-112">설명</span><span class="sxs-lookup"><span data-stu-id="4a3c9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4a3c9-113">종결</span><span class="sxs-lookup"><span data-stu-id="4a3c9-113">Closed</span></span>|<span data-ttu-id="4a3c9-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="4a3c9-114">OpenStates</span></span>|<span data-ttu-id="4a3c9-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-115">The default state.</span></span>|  
|<span data-ttu-id="4a3c9-116">열기</span><span class="sxs-lookup"><span data-stu-id="4a3c9-116">Open</span></span>|<span data-ttu-id="4a3c9-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="4a3c9-117">OpenStates</span></span>|<span data-ttu-id="4a3c9-118"><xref:System.Windows.Controls.ToolTip> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="4a3c9-119">Valid</span><span class="sxs-lookup"><span data-stu-id="4a3c9-119">Valid</span></span>|<span data-ttu-id="4a3c9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a3c9-120">ValidationStates</span></span>|<span data-ttu-id="4a3c9-121">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4a3c9-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4a3c9-122">InvalidFocused</span></span>|<span data-ttu-id="4a3c9-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a3c9-123">ValidationStates</span></span>|<span data-ttu-id="4a3c9-124">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4a3c9-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4a3c9-125">InvalidUnfocused</span></span>|<span data-ttu-id="4a3c9-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a3c9-126">ValidationStates</span></span>|<span data-ttu-id="4a3c9-127">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="4a3c9-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="4a3c9-128">ToolTip ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="4a3c9-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="4a3c9-129">다음 예제에서는 <xref:System.Windows.Controls.ToolTip> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="4a3c9-130">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4a3c9-131">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a3c9-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3c9-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a3c9-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4a3c9-133">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4a3c9-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4a3c9-134">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4a3c9-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4a3c9-135">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="4a3c9-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4a3c9-136">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="4a3c9-136">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
