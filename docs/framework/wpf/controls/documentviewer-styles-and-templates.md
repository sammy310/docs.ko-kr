---
title: DocumentViewer 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 4e91a640b36e4793567c9e728fd71ec8ce596743
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158420"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="e8416-102">DocumentViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e8416-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="e8416-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="e8416-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e8416-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8416-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="e8416-106">DocumentViewer 파트</span><span class="sxs-lookup"><span data-stu-id="e8416-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="e8416-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="e8416-108">파트</span><span class="sxs-lookup"><span data-stu-id="e8416-108">Part</span></span>|<span data-ttu-id="e8416-109">형식</span><span class="sxs-lookup"><span data-stu-id="e8416-109">Type</span></span>|<span data-ttu-id="e8416-110">설명</span><span class="sxs-lookup"><span data-stu-id="e8416-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8416-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="e8416-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="e8416-112">콘텐츠 및 스크롤 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="e8416-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="e8416-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="e8416-114">기본적으로 맨 위에 있는 검색 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="e8416-115">DocumentViewer 상태</span><span class="sxs-lookup"><span data-stu-id="e8416-115">DocumentViewer States</span></span>  
 <span data-ttu-id="e8416-116">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="e8416-117">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="e8416-117">VisualState Name</span></span>|<span data-ttu-id="e8416-118">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="e8416-118">VisualStateGroup Name</span></span>|<span data-ttu-id="e8416-119">설명</span><span class="sxs-lookup"><span data-stu-id="e8416-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8416-120">유효</span><span class="sxs-lookup"><span data-stu-id="e8416-120">Valid</span></span>|<span data-ttu-id="e8416-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8416-121">ValidationStates</span></span>|<span data-ttu-id="e8416-122">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e8416-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e8416-123">InvalidFocused</span></span>|<span data-ttu-id="e8416-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8416-124">ValidationStates</span></span>|<span data-ttu-id="e8416-125">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e8416-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e8416-126">InvalidUnfocused</span></span>|<span data-ttu-id="e8416-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8416-127">ValidationStates</span></span>|<span data-ttu-id="e8416-128">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="e8416-129">DocumentViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="e8416-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="e8416-130">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.DocumentViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="e8416-131">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8416-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e8416-132">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8416-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8416-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8416-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e8416-134">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e8416-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e8416-135">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e8416-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e8416-136">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e8416-136">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="e8416-137">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e8416-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
