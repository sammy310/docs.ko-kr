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
ms.openlocfilehash: 0d6860af587da89094663779c894689e8a911af8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357393"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="9e70d-102">Frame 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9e70d-102">Frame Styles and Templates</span></span>
<span data-ttu-id="9e70d-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="9e70d-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9e70d-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e70d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="9e70d-106">프레임 부분</span><span class="sxs-lookup"><span data-stu-id="9e70d-106">Frame Parts</span></span>  
 <span data-ttu-id="9e70d-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="9e70d-108">파트</span><span class="sxs-lookup"><span data-stu-id="9e70d-108">Part</span></span>|<span data-ttu-id="9e70d-109">형식</span><span class="sxs-lookup"><span data-stu-id="9e70d-109">Type</span></span>|<span data-ttu-id="9e70d-110">설명</span><span class="sxs-lookup"><span data-stu-id="9e70d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9e70d-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="9e70d-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="9e70d-112">콘텐츠 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="9e70d-113">프레임 상태</span><span class="sxs-lookup"><span data-stu-id="9e70d-113">Frame States</span></span>  
 <span data-ttu-id="9e70d-114">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="9e70d-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="9e70d-115">VisualState Name</span></span>|<span data-ttu-id="9e70d-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="9e70d-116">VisualStateGroup Name</span></span>|<span data-ttu-id="9e70d-117">설명</span><span class="sxs-lookup"><span data-stu-id="9e70d-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9e70d-118">유효</span><span class="sxs-lookup"><span data-stu-id="9e70d-118">Valid</span></span>|<span data-ttu-id="9e70d-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e70d-119">ValidationStates</span></span>|<span data-ttu-id="9e70d-120">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9e70d-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9e70d-121">InvalidFocused</span></span>|<span data-ttu-id="9e70d-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e70d-122">ValidationStates</span></span>|<span data-ttu-id="9e70d-123">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9e70d-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9e70d-124">InvalidUnfocused</span></span>|<span data-ttu-id="9e70d-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e70d-125">ValidationStates</span></span>|<span data-ttu-id="9e70d-126">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="9e70d-127">프레임 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="9e70d-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="9e70d-128">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="9e70d-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e70d-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9e70d-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e70d-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e70d-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e70d-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9e70d-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9e70d-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9e70d-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9e70d-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9e70d-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9e70d-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="9e70d-135">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9e70d-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
