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
ms.openlocfilehash: ebd21829591b8fefe87aeba0b86280f18eff4f06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203732"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="0d86f-102">Window 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d86f-102">Window Styles and Templates</span></span>
<span data-ttu-id="0d86f-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="0d86f-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0d86f-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d86f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="0d86f-106">창의 부분</span><span class="sxs-lookup"><span data-stu-id="0d86f-106">Window Parts</span></span>  
 <span data-ttu-id="0d86f-107"><xref:System.Windows.Window> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="0d86f-108">창 상태</span><span class="sxs-lookup"><span data-stu-id="0d86f-108">Window States</span></span>  
 <span data-ttu-id="0d86f-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="0d86f-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="0d86f-110">VisualState Name</span></span>|<span data-ttu-id="0d86f-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="0d86f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0d86f-112">설명</span><span class="sxs-lookup"><span data-stu-id="0d86f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0d86f-113">유효</span><span class="sxs-lookup"><span data-stu-id="0d86f-113">Valid</span></span>|<span data-ttu-id="0d86f-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d86f-114">ValidationStates</span></span>|<span data-ttu-id="0d86f-115">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0d86f-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0d86f-116">InvalidFocused</span></span>|<span data-ttu-id="0d86f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d86f-117">ValidationStates</span></span>|<span data-ttu-id="0d86f-118">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0d86f-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0d86f-119">InvalidUnfocused</span></span>|<span data-ttu-id="0d86f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d86f-120">ValidationStates</span></span>|<span data-ttu-id="0d86f-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="0d86f-122">창 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="0d86f-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="0d86f-123">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="0d86f-124"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d86f-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0d86f-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d86f-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d86f-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d86f-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0d86f-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d86f-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0d86f-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0d86f-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0d86f-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d86f-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0d86f-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0d86f-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
