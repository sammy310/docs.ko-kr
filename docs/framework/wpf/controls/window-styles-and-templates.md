---
title: Window 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 48fe5887ebad86efad1b1aae39ba03a26fda3bd8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460025"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="b3787-102">Window 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b3787-102">Window Styles and Templates</span></span>
<span data-ttu-id="b3787-103">이 항목에서는 <xref:System.Windows.Window> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="b3787-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b3787-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3787-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="b3787-106">창 파트</span><span class="sxs-lookup"><span data-stu-id="b3787-106">Window Parts</span></span>  
 <span data-ttu-id="b3787-107"><xref:System.Windows.Window> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="b3787-108">창 상태</span><span class="sxs-lookup"><span data-stu-id="b3787-108">Window States</span></span>  
 <span data-ttu-id="b3787-109">다음 표에서는 <xref:System.Windows.Window> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="b3787-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="b3787-110">VisualState Name</span></span>|<span data-ttu-id="b3787-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="b3787-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b3787-112">설명</span><span class="sxs-lookup"><span data-stu-id="b3787-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b3787-113">유효</span><span class="sxs-lookup"><span data-stu-id="b3787-113">Valid</span></span>|<span data-ttu-id="b3787-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3787-114">ValidationStates</span></span>|<span data-ttu-id="b3787-115">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b3787-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b3787-116">InvalidFocused</span></span>|<span data-ttu-id="b3787-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3787-117">ValidationStates</span></span>|<span data-ttu-id="b3787-118">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b3787-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b3787-119">InvalidUnfocused</span></span>|<span data-ttu-id="b3787-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3787-120">ValidationStates</span></span>|<span data-ttu-id="b3787-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="b3787-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="b3787-122">Window ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="b3787-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="b3787-123">다음 예제에서는 <xref:System.Windows.Window> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="b3787-124"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3787-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b3787-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3787-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3787-126">참조</span><span class="sxs-lookup"><span data-stu-id="b3787-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b3787-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b3787-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b3787-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b3787-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b3787-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b3787-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b3787-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b3787-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
