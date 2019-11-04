---
title: TextBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 7c4680a3ea9352e94d628e786fc8e4fd71018d00
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458245"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="b2a7a-102">TextBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b2a7a-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="b2a7a-103">이 항목에서는 <xref:System.Windows.Controls.TextBox> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="b2a7a-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b2a7a-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="b2a7a-106">텍스트 상자 파트</span><span class="sxs-lookup"><span data-stu-id="b2a7a-106">TextBox Parts</span></span>  
 <span data-ttu-id="b2a7a-107">다음 표에서는 <xref:System.Windows.Controls.TextBox> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="b2a7a-108">파트</span><span class="sxs-lookup"><span data-stu-id="b2a7a-108">Part</span></span>|<span data-ttu-id="b2a7a-109">Type</span><span class="sxs-lookup"><span data-stu-id="b2a7a-109">Type</span></span>|<span data-ttu-id="b2a7a-110">설명</span><span class="sxs-lookup"><span data-stu-id="b2a7a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b2a7a-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="b2a7a-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="b2a7a-112"><xref:System.Windows.FrameworkElement>포함할 수 있는 시각적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b2a7a-113"><xref:System.Windows.Controls.TextBox> 텍스트가이 요소에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="b2a7a-114">텍스트 상자 상태</span><span class="sxs-lookup"><span data-stu-id="b2a7a-114">TextBox States</span></span>  
 <span data-ttu-id="b2a7a-115">다음 표에서는 <xref:System.Windows.Controls.TextBox> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="b2a7a-116">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="b2a7a-116">VisualState Name</span></span>|<span data-ttu-id="b2a7a-117">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="b2a7a-117">VisualStateGroup Name</span></span>|<span data-ttu-id="b2a7a-118">설명</span><span class="sxs-lookup"><span data-stu-id="b2a7a-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="b2a7a-119">보통</span><span class="sxs-lookup"><span data-stu-id="b2a7a-119">Normal</span></span>|<span data-ttu-id="b2a7a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-120">CommonStates</span></span>|<span data-ttu-id="b2a7a-121">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-121">The default state.</span></span>|  
|<span data-ttu-id="b2a7a-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b2a7a-122">MouseOver</span></span>|<span data-ttu-id="b2a7a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-123">CommonStates</span></span>|<span data-ttu-id="b2a7a-124">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b2a7a-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="b2a7a-125">Disabled</span></span>|<span data-ttu-id="b2a7a-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-126">CommonStates</span></span>|<span data-ttu-id="b2a7a-127">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-127">The control is disabled.</span></span>|  
|<span data-ttu-id="b2a7a-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b2a7a-128">ReadOnly</span></span>|<span data-ttu-id="b2a7a-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-129">CommonStates</span></span>|<span data-ttu-id="b2a7a-130">사용자는 <xref:System.Windows.Controls.TextBox>의 텍스트를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="b2a7a-131">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="b2a7a-131">Focused</span></span>|<span data-ttu-id="b2a7a-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-132">FocusStates</span></span>|<span data-ttu-id="b2a7a-133">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-133">The control has focus.</span></span>|  
|<span data-ttu-id="b2a7a-134">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="b2a7a-134">Unfocused</span></span>|<span data-ttu-id="b2a7a-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-135">FocusStates</span></span>|<span data-ttu-id="b2a7a-136">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="b2a7a-137">유효</span><span class="sxs-lookup"><span data-stu-id="b2a7a-137">Valid</span></span>|<span data-ttu-id="b2a7a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-138">ValidationStates</span></span>|<span data-ttu-id="b2a7a-139">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b2a7a-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b2a7a-140">InvalidFocused</span></span>|<span data-ttu-id="b2a7a-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-141">ValidationStates</span></span>|<span data-ttu-id="b2a7a-142">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b2a7a-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b2a7a-143">InvalidUnfocused</span></span>|<span data-ttu-id="b2a7a-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2a7a-144">ValidationStates</span></span>|<span data-ttu-id="b2a7a-145">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="b2a7a-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="b2a7a-146">텍스트 상자 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="b2a7a-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="b2a7a-147">다음 예제에서는 <xref:System.Windows.Controls.TextBox> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="b2a7a-148">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b2a7a-149">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2a7a-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a7a-150">참조</span><span class="sxs-lookup"><span data-stu-id="b2a7a-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b2a7a-151">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b2a7a-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b2a7a-152">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b2a7a-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b2a7a-153">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b2a7a-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b2a7a-154">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b2a7a-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
