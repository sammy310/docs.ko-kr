---
title: Frame 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 89f4fc21637d20ca226507463093bc6bae2241fc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460317"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="61c5e-102">Frame 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="61c5e-102">Frame Styles and Templates</span></span>
<span data-ttu-id="61c5e-103">이 항목에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="61c5e-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="61c5e-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c5e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="61c5e-106">프레임 파트</span><span class="sxs-lookup"><span data-stu-id="61c5e-106">Frame Parts</span></span>  
 <span data-ttu-id="61c5e-107">다음 표에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="61c5e-108">파트</span><span class="sxs-lookup"><span data-stu-id="61c5e-108">Part</span></span>|<span data-ttu-id="61c5e-109">Type</span><span class="sxs-lookup"><span data-stu-id="61c5e-109">Type</span></span>|<span data-ttu-id="61c5e-110">설명</span><span class="sxs-lookup"><span data-stu-id="61c5e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61c5e-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="61c5e-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="61c5e-112">콘텐츠 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="61c5e-113">프레임 상태</span><span class="sxs-lookup"><span data-stu-id="61c5e-113">Frame States</span></span>  
 <span data-ttu-id="61c5e-114">다음 표에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="61c5e-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="61c5e-115">VisualState Name</span></span>|<span data-ttu-id="61c5e-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="61c5e-116">VisualStateGroup Name</span></span>|<span data-ttu-id="61c5e-117">설명</span><span class="sxs-lookup"><span data-stu-id="61c5e-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61c5e-118">유효</span><span class="sxs-lookup"><span data-stu-id="61c5e-118">Valid</span></span>|<span data-ttu-id="61c5e-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c5e-119">ValidationStates</span></span>|<span data-ttu-id="61c5e-120">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="61c5e-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="61c5e-121">InvalidFocused</span></span>|<span data-ttu-id="61c5e-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c5e-122">ValidationStates</span></span>|<span data-ttu-id="61c5e-123">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="61c5e-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="61c5e-124">InvalidUnfocused</span></span>|<span data-ttu-id="61c5e-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c5e-125">ValidationStates</span></span>|<span data-ttu-id="61c5e-126">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="61c5e-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="61c5e-127">Frame ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="61c5e-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="61c5e-128">다음 예제에서는 <xref:System.Windows.Controls.Frame> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="61c5e-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c5e-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="61c5e-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c5e-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c5e-131">참조</span><span class="sxs-lookup"><span data-stu-id="61c5e-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="61c5e-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="61c5e-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="61c5e-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="61c5e-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="61c5e-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="61c5e-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="61c5e-135">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="61c5e-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
