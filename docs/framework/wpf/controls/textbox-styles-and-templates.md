---
title: TextBox 스타일 및 템플릿
description: Windows Presentation Foundation TextBox 컨트롤에 대 한 스타일 및 템플릿에 대해 알아봅니다. ControlTemplate를 수정 하 여 컨트롤에 고유한 모양을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164728"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="bae0d-104">TextBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bae0d-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="bae0d-105">이 항목에서는 컨트롤의 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="bae0d-106">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bae0d-107">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bae0d-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="bae0d-108">텍스트 상자 파트</span><span class="sxs-lookup"><span data-stu-id="bae0d-108">TextBox Parts</span></span>  
 <span data-ttu-id="bae0d-109">다음 표에서는 컨트롤의 명명 된 파트를 나열 합니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="bae0d-110">부분</span><span class="sxs-lookup"><span data-stu-id="bae0d-110">Part</span></span>|<span data-ttu-id="bae0d-111">Type</span><span class="sxs-lookup"><span data-stu-id="bae0d-111">Type</span></span>|<span data-ttu-id="bae0d-112">Description</span><span class="sxs-lookup"><span data-stu-id="bae0d-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bae0d-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="bae0d-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bae0d-114">을 포함할 수 있는 시각적 요소입니다 <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="bae0d-115">의 텍스트가 <xref:System.Windows.Controls.TextBox> 이 요소에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="bae0d-116">텍스트 상자 상태</span><span class="sxs-lookup"><span data-stu-id="bae0d-116">TextBox States</span></span>  
 <span data-ttu-id="bae0d-117">다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="bae0d-118">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="bae0d-118">VisualState Name</span></span>|<span data-ttu-id="bae0d-119">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="bae0d-119">VisualStateGroup Name</span></span>|<span data-ttu-id="bae0d-120">설명</span><span class="sxs-lookup"><span data-stu-id="bae0d-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="bae0d-121">보통</span><span class="sxs-lookup"><span data-stu-id="bae0d-121">Normal</span></span>|<span data-ttu-id="bae0d-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-122">CommonStates</span></span>|<span data-ttu-id="bae0d-123">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-123">The default state.</span></span>|  
|<span data-ttu-id="bae0d-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bae0d-124">MouseOver</span></span>|<span data-ttu-id="bae0d-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-125">CommonStates</span></span>|<span data-ttu-id="bae0d-126">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="bae0d-127">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="bae0d-127">Disabled</span></span>|<span data-ttu-id="bae0d-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-128">CommonStates</span></span>|<span data-ttu-id="bae0d-129">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-129">The control is disabled.</span></span>|  
|<span data-ttu-id="bae0d-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bae0d-130">ReadOnly</span></span>|<span data-ttu-id="bae0d-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-131">CommonStates</span></span>|<span data-ttu-id="bae0d-132">사용자가의 텍스트를 변경할 수 없습니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="bae0d-133">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="bae0d-133">Focused</span></span>|<span data-ttu-id="bae0d-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-134">FocusStates</span></span>|<span data-ttu-id="bae0d-135">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-135">The control has focus.</span></span>|  
|<span data-ttu-id="bae0d-136">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="bae0d-136">Unfocused</span></span>|<span data-ttu-id="bae0d-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-137">FocusStates</span></span>|<span data-ttu-id="bae0d-138">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="bae0d-139">Valid</span><span class="sxs-lookup"><span data-stu-id="bae0d-139">Valid</span></span>|<span data-ttu-id="bae0d-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-140">ValidationStates</span></span>|<span data-ttu-id="bae0d-141">컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bae0d-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bae0d-142">InvalidFocused</span></span>|<span data-ttu-id="bae0d-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-143">ValidationStates</span></span>|<span data-ttu-id="bae0d-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bae0d-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bae0d-145">InvalidUnfocused</span></span>|<span data-ttu-id="bae0d-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bae0d-146">ValidationStates</span></span>|<span data-ttu-id="bae0d-147"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="bae0d-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="bae0d-148">텍스트 상자 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="bae0d-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="bae0d-149">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="bae0d-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="bae0d-150">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bae0d-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bae0d-151">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bae0d-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae0d-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bae0d-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bae0d-153">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bae0d-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bae0d-154">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bae0d-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bae0d-155">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="bae0d-155">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bae0d-156">컨트롤의 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="bae0d-156">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
