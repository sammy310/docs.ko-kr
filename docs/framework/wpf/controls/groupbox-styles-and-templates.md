---
title: GroupBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187473"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="a64c9-102">GroupBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a64c9-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="a64c9-103">이 항목에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤의 스타일과 템플릿에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="a64c9-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a64c9-105">자세한 내용은 [컨트롤에 대한 템플릿 만들기를](../../../desktop-wpf/themes/how-to-create-apply-template.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a64c9-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="a64c9-106">그룹박스 부품</span><span class="sxs-lookup"><span data-stu-id="a64c9-106">GroupBox Parts</span></span>  
 <span data-ttu-id="a64c9-107">컨트롤에는 <xref:System.Windows.Controls.GroupBox> 명명된 부품이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="a64c9-108">그룹박스 상태</span><span class="sxs-lookup"><span data-stu-id="a64c9-108">GroupBox States</span></span>  
 <span data-ttu-id="a64c9-109">다음 표에는 컨트롤의 시각적 <xref:System.Windows.Controls.GroupBox> 상태가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="a64c9-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="a64c9-110">VisualState Name</span></span>|<span data-ttu-id="a64c9-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="a64c9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a64c9-112">Description</span><span class="sxs-lookup"><span data-stu-id="a64c9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a64c9-113">Valid</span><span class="sxs-lookup"><span data-stu-id="a64c9-113">Valid</span></span>|<span data-ttu-id="a64c9-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a64c9-114">ValidationStates</span></span>|<span data-ttu-id="a64c9-115">컨트롤은 클래스를 <xref:System.Windows.Controls.Validation> 사용하고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 `false`속성은 입니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a64c9-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a64c9-116">InvalidFocused</span></span>|<span data-ttu-id="a64c9-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a64c9-117">ValidationStates</span></span>|<span data-ttu-id="a64c9-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a64c9-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a64c9-119">InvalidUnfocused</span></span>|<span data-ttu-id="a64c9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a64c9-120">ValidationStates</span></span>|<span data-ttu-id="a64c9-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="a64c9-122">그룹박스 제어템플릿 예제</span><span class="sxs-lookup"><span data-stu-id="a64c9-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="a64c9-123">다음 예제에서는 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 대한 <xref:System.Windows.Controls.GroupBox> a를 정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="a64c9-124">은 <xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a64c9-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a64c9-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a64c9-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64c9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a64c9-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a64c9-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a64c9-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a64c9-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a64c9-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a64c9-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a64c9-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a64c9-130">컨트롤용 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="a64c9-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
