---
title: Label 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: d2bb348fc9c0348fd8093452e022df7ab4e0b3f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137087"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="5f3a0-102">Label 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5f3a0-102">Label Styles and Templates</span></span>
<span data-ttu-id="5f3a0-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Label> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="5f3a0-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5f3a0-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="5f3a0-106">레이블 부분</span><span class="sxs-lookup"><span data-stu-id="5f3a0-106">Label Parts</span></span>  
 <span data-ttu-id="5f3a0-107"><xref:System.Windows.Controls.Label> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="5f3a0-108">레이블 상태</span><span class="sxs-lookup"><span data-stu-id="5f3a0-108">Label States</span></span>  
 <span data-ttu-id="5f3a0-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Label> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="5f3a0-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="5f3a0-110">VisualState Name</span></span>|<span data-ttu-id="5f3a0-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="5f3a0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5f3a0-112">설명</span><span class="sxs-lookup"><span data-stu-id="5f3a0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5f3a0-113">유효</span><span class="sxs-lookup"><span data-stu-id="5f3a0-113">Valid</span></span>|<span data-ttu-id="5f3a0-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f3a0-114">ValidationStates</span></span>|<span data-ttu-id="5f3a0-115">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5f3a0-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5f3a0-116">InvalidFocused</span></span>|<span data-ttu-id="5f3a0-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f3a0-117">ValidationStates</span></span>|<span data-ttu-id="5f3a0-118">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5f3a0-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5f3a0-119">InvalidUnfocused</span></span>|<span data-ttu-id="5f3a0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f3a0-120">ValidationStates</span></span>|<span data-ttu-id="5f3a0-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="5f3a0-122">레이블 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="5f3a0-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="5f3a0-123">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Label> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="5f3a0-124"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5f3a0-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f3a0-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3a0-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f3a0-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5f3a0-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5f3a0-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5f3a0-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5f3a0-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5f3a0-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5f3a0-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="5f3a0-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5f3a0-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
