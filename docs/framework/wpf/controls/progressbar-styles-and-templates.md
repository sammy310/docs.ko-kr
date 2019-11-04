---
title: ProgressBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459876"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="3a236-102">ProgressBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3a236-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="3a236-103">이 항목에서는 <xref:System.Windows.Controls.ProgressBar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="3a236-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3a236-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a236-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="3a236-106">ProgressBar 파트</span><span class="sxs-lookup"><span data-stu-id="3a236-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="3a236-107">다음 표에서는 <xref:System.Windows.Controls.ProgressBar> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="3a236-108">파트</span><span class="sxs-lookup"><span data-stu-id="3a236-108">Part</span></span>|<span data-ttu-id="3a236-109">Type</span><span class="sxs-lookup"><span data-stu-id="3a236-109">Type</span></span>|<span data-ttu-id="3a236-110">설명</span><span class="sxs-lookup"><span data-stu-id="3a236-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3a236-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="3a236-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3a236-112">진행률을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="3a236-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="3a236-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3a236-114">진행률 표시기의 경로를 정의 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="3a236-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="3a236-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3a236-116">진행률 표시줄을 embellishes 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="3a236-117">ProgressBar 상태</span><span class="sxs-lookup"><span data-stu-id="3a236-117">ProgressBar States</span></span>  
 <span data-ttu-id="3a236-118">다음 표에서는 <xref:System.Windows.Controls.ProgressBar> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="3a236-119">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="3a236-119">VisualState Name</span></span>|<span data-ttu-id="3a236-120">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="3a236-120">VisualStateGroup Name</span></span>|<span data-ttu-id="3a236-121">설명</span><span class="sxs-lookup"><span data-stu-id="3a236-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3a236-122">활성화 상태의</span><span class="sxs-lookup"><span data-stu-id="3a236-122">Determinate</span></span>|<span data-ttu-id="3a236-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3a236-123">CommonStates</span></span>|<span data-ttu-id="3a236-124"><xref:System.Windows.Controls.ProgressBar> <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성을 기반으로 진행률을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="3a236-125">않음</span><span class="sxs-lookup"><span data-stu-id="3a236-125">Indeterminate</span></span>|<span data-ttu-id="3a236-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3a236-126">CommonStates</span></span>|<span data-ttu-id="3a236-127"><xref:System.Windows.Controls.ProgressBar>는 반복 패턴으로 일반적인 진행률을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="3a236-128">유효</span><span class="sxs-lookup"><span data-stu-id="3a236-128">Valid</span></span>|<span data-ttu-id="3a236-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a236-129">ValidationStates</span></span>|<span data-ttu-id="3a236-130">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3a236-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3a236-131">InvalidFocused</span></span>|<span data-ttu-id="3a236-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a236-132">ValidationStates</span></span>|<span data-ttu-id="3a236-133">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3a236-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3a236-134">InvalidUnfocused</span></span>|<span data-ttu-id="3a236-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a236-135">ValidationStates</span></span>|<span data-ttu-id="3a236-136">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="3a236-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="3a236-137">ProgressBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="3a236-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="3a236-138">다음 예제에서는 <xref:System.Windows.Controls.ProgressBar> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="3a236-139">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a236-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3a236-140">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a236-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a236-141">참조</span><span class="sxs-lookup"><span data-stu-id="3a236-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3a236-142">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3a236-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3a236-143">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3a236-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3a236-144">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3a236-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3a236-145">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3a236-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
