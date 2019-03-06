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
ms.openlocfilehash: f85a6fb31adac71541eed31a1ccfde9e06028af7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361150"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="8333a-102">ScrollBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="8333a-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="8333a-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="8333a-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8333a-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8333a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="8333a-106">스크롤 막대 부분</span><span class="sxs-lookup"><span data-stu-id="8333a-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="8333a-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="8333a-108">파트</span><span class="sxs-lookup"><span data-stu-id="8333a-108">Part</span></span>|<span data-ttu-id="8333a-109">형식</span><span class="sxs-lookup"><span data-stu-id="8333a-109">Type</span></span>|<span data-ttu-id="8333a-110">설명</span><span class="sxs-lookup"><span data-stu-id="8333a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8333a-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="8333a-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="8333a-112">위치를 나타내는 요소에 대 한 컨테이너를 <xref:System.Windows.Controls.Primitives.ScrollBar>입니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="8333a-113">스크롤 막대 상태</span><span class="sxs-lookup"><span data-stu-id="8333a-113">ScrollBar States</span></span>  
 <span data-ttu-id="8333a-114">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="8333a-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="8333a-115">VisualState Name</span></span>|<span data-ttu-id="8333a-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="8333a-116">VisualStateGroup Name</span></span>|<span data-ttu-id="8333a-117">설명</span><span class="sxs-lookup"><span data-stu-id="8333a-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="8333a-118">보통</span><span class="sxs-lookup"><span data-stu-id="8333a-118">Normal</span></span>|<span data-ttu-id="8333a-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8333a-119">CommonStates</span></span>|<span data-ttu-id="8333a-120">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-120">The default state.</span></span>|  
|<span data-ttu-id="8333a-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8333a-121">MouseOver</span></span>|<span data-ttu-id="8333a-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8333a-122">CommonStates</span></span>|<span data-ttu-id="8333a-123">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="8333a-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8333a-124">Disabled</span></span>|<span data-ttu-id="8333a-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8333a-125">CommonStates</span></span>|<span data-ttu-id="8333a-126">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-126">The control is disabled.</span></span>|  
|<span data-ttu-id="8333a-127">유효</span><span class="sxs-lookup"><span data-stu-id="8333a-127">Valid</span></span>|<span data-ttu-id="8333a-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8333a-128">ValidationStates</span></span>|<span data-ttu-id="8333a-129">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8333a-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8333a-130">InvalidFocused</span></span>|<span data-ttu-id="8333a-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8333a-131">ValidationStates</span></span>|<span data-ttu-id="8333a-132">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8333a-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8333a-133">InvalidUnfocused</span></span>|<span data-ttu-id="8333a-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8333a-134">ValidationStates</span></span>|<span data-ttu-id="8333a-135">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="8333a-136">스크롤 막대 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="8333a-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="8333a-137">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="8333a-138">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8333a-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8333a-139">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8333a-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8333a-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="8333a-140">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8333a-141">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="8333a-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8333a-142">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8333a-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8333a-143">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="8333a-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="8333a-144">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8333a-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
