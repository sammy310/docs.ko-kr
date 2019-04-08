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
ms.openlocfilehash: 5ef8e4b44bc2b6072fa730f33c10191b64954f7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078995"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="ab762-102">GroupBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ab762-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="ab762-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="ab762-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ab762-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab762-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="ab762-106">GroupBox 파트</span><span class="sxs-lookup"><span data-stu-id="ab762-106">GroupBox Parts</span></span>  
 <span data-ttu-id="ab762-107"><xref:System.Windows.Controls.GroupBox> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="ab762-108">GroupBox 상태</span><span class="sxs-lookup"><span data-stu-id="ab762-108">GroupBox States</span></span>  
 <span data-ttu-id="ab762-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="ab762-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="ab762-110">VisualState Name</span></span>|<span data-ttu-id="ab762-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="ab762-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ab762-112">설명</span><span class="sxs-lookup"><span data-stu-id="ab762-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ab762-113">유효</span><span class="sxs-lookup"><span data-stu-id="ab762-113">Valid</span></span>|<span data-ttu-id="ab762-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab762-114">ValidationStates</span></span>|<span data-ttu-id="ab762-115">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ab762-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ab762-116">InvalidFocused</span></span>|<span data-ttu-id="ab762-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab762-117">ValidationStates</span></span>|<span data-ttu-id="ab762-118">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ab762-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ab762-119">InvalidUnfocused</span></span>|<span data-ttu-id="ab762-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab762-120">ValidationStates</span></span>|<span data-ttu-id="ab762-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="ab762-122">GroupBox ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="ab762-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="ab762-123">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="ab762-124"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab762-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ab762-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab762-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab762-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab762-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ab762-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ab762-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ab762-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ab762-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ab762-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="ab762-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="ab762-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ab762-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
