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
ms.openlocfilehash: de853198c97c99319bea4a816c9a6eca5dc5d917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283741"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="159e2-102">Frame 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="159e2-102">Frame Styles and Templates</span></span>
<span data-ttu-id="159e2-103">이 항목에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="159e2-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="159e2-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="159e2-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="159e2-106">프레임 파트</span><span class="sxs-lookup"><span data-stu-id="159e2-106">Frame Parts</span></span>  
 <span data-ttu-id="159e2-107">다음 표에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="159e2-108">부분</span><span class="sxs-lookup"><span data-stu-id="159e2-108">Part</span></span>|<span data-ttu-id="159e2-109">형식</span><span class="sxs-lookup"><span data-stu-id="159e2-109">Type</span></span>|<span data-ttu-id="159e2-110">설명</span><span class="sxs-lookup"><span data-stu-id="159e2-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="159e2-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="159e2-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="159e2-112">콘텐츠 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="159e2-113">프레임 상태</span><span class="sxs-lookup"><span data-stu-id="159e2-113">Frame States</span></span>  
 <span data-ttu-id="159e2-114">다음 표에서는 <xref:System.Windows.Controls.Frame> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="159e2-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="159e2-115">VisualState Name</span></span>|<span data-ttu-id="159e2-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="159e2-116">VisualStateGroup Name</span></span>|<span data-ttu-id="159e2-117">설명</span><span class="sxs-lookup"><span data-stu-id="159e2-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="159e2-118">유효</span><span class="sxs-lookup"><span data-stu-id="159e2-118">Valid</span></span>|<span data-ttu-id="159e2-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="159e2-119">ValidationStates</span></span>|<span data-ttu-id="159e2-120">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="159e2-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="159e2-121">InvalidFocused</span></span>|<span data-ttu-id="159e2-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="159e2-122">ValidationStates</span></span>|<span data-ttu-id="159e2-123">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="159e2-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="159e2-124">InvalidUnfocused</span></span>|<span data-ttu-id="159e2-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="159e2-125">ValidationStates</span></span>|<span data-ttu-id="159e2-126">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="159e2-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="159e2-127">Frame ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="159e2-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="159e2-128">다음 예제에서는 <xref:System.Windows.Controls.Frame> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="159e2-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="159e2-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="159e2-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="159e2-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159e2-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="159e2-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="159e2-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="159e2-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="159e2-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="159e2-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="159e2-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="159e2-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="159e2-135">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="159e2-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
