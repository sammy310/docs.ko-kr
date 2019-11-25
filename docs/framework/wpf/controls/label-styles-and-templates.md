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
ms.openlocfilehash: 35fcd9c15bf44d15a08c16d58847698c5ec6e574
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283502"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="7b95f-102">Label 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7b95f-102">Label Styles and Templates</span></span>
<span data-ttu-id="7b95f-103">이 항목에서는 <xref:System.Windows.Controls.Label> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="7b95f-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7b95f-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b95f-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="7b95f-106">레이블 파트</span><span class="sxs-lookup"><span data-stu-id="7b95f-106">Label Parts</span></span>  
 <span data-ttu-id="7b95f-107"><xref:System.Windows.Controls.Label> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="7b95f-108">레이블 상태</span><span class="sxs-lookup"><span data-stu-id="7b95f-108">Label States</span></span>  
 <span data-ttu-id="7b95f-109">다음 표에서는 <xref:System.Windows.Controls.Label> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="7b95f-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="7b95f-110">VisualState Name</span></span>|<span data-ttu-id="7b95f-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="7b95f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7b95f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7b95f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7b95f-113">유효</span><span class="sxs-lookup"><span data-stu-id="7b95f-113">Valid</span></span>|<span data-ttu-id="7b95f-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7b95f-114">ValidationStates</span></span>|<span data-ttu-id="7b95f-115">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7b95f-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7b95f-116">InvalidFocused</span></span>|<span data-ttu-id="7b95f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7b95f-117">ValidationStates</span></span>|<span data-ttu-id="7b95f-118">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7b95f-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7b95f-119">InvalidUnfocused</span></span>|<span data-ttu-id="7b95f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7b95f-120">ValidationStates</span></span>|<span data-ttu-id="7b95f-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7b95f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="7b95f-122">레이블 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="7b95f-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="7b95f-123">다음 예제에서는 <xref:System.Windows.Controls.Label> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="7b95f-124"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95f-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7b95f-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b95f-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b95f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b95f-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7b95f-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7b95f-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7b95f-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7b95f-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7b95f-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7b95f-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7b95f-130">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="7b95f-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
