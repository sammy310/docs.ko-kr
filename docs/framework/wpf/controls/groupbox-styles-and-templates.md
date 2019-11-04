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
ms.openlocfilehash: 0835c106ffbda86bca8e01bc61adebfc1ab0c2cb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459642"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="e704c-102">GroupBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e704c-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="e704c-103">이 항목에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="e704c-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e704c-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e704c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="e704c-106">GroupBox 파트</span><span class="sxs-lookup"><span data-stu-id="e704c-106">GroupBox Parts</span></span>  
 <span data-ttu-id="e704c-107"><xref:System.Windows.Controls.GroupBox> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="e704c-108">GroupBox 상태</span><span class="sxs-lookup"><span data-stu-id="e704c-108">GroupBox States</span></span>  
 <span data-ttu-id="e704c-109">다음 표에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="e704c-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="e704c-110">VisualState Name</span></span>|<span data-ttu-id="e704c-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="e704c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e704c-112">설명</span><span class="sxs-lookup"><span data-stu-id="e704c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e704c-113">유효</span><span class="sxs-lookup"><span data-stu-id="e704c-113">Valid</span></span>|<span data-ttu-id="e704c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e704c-114">ValidationStates</span></span>|<span data-ttu-id="e704c-115">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e704c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e704c-116">InvalidFocused</span></span>|<span data-ttu-id="e704c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e704c-117">ValidationStates</span></span>|<span data-ttu-id="e704c-118">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e704c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e704c-119">InvalidUnfocused</span></span>|<span data-ttu-id="e704c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e704c-120">ValidationStates</span></span>|<span data-ttu-id="e704c-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="e704c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="e704c-122">GroupBox ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="e704c-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="e704c-123">다음 예제에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="e704c-124"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e704c-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e704c-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e704c-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e704c-126">참조</span><span class="sxs-lookup"><span data-stu-id="e704c-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e704c-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e704c-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e704c-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e704c-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e704c-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e704c-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e704c-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e704c-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
