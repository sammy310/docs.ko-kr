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
ms.openlocfilehash: 7a812ff913703e3aa8408da8a11d28ee5adfa7fd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460341"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="a2be0-102">DocumentViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a2be0-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="a2be0-103">이 항목에서는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="a2be0-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a2be0-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2be0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="a2be0-106">DocumentViewer 파트</span><span class="sxs-lookup"><span data-stu-id="a2be0-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="a2be0-107">다음 표에서는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="a2be0-108">파트</span><span class="sxs-lookup"><span data-stu-id="a2be0-108">Part</span></span>|<span data-ttu-id="a2be0-109">Type</span><span class="sxs-lookup"><span data-stu-id="a2be0-109">Type</span></span>|<span data-ttu-id="a2be0-110">설명</span><span class="sxs-lookup"><span data-stu-id="a2be0-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a2be0-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="a2be0-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="a2be0-112">콘텐츠 및 스크롤 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="a2be0-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="a2be0-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="a2be0-114">기본적으로 아래쪽에 있는 검색 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="a2be0-115">DocumentViewer 상태</span><span class="sxs-lookup"><span data-stu-id="a2be0-115">DocumentViewer States</span></span>  
 <span data-ttu-id="a2be0-116">다음 표에서는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="a2be0-117">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="a2be0-117">VisualState Name</span></span>|<span data-ttu-id="a2be0-118">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="a2be0-118">VisualStateGroup Name</span></span>|<span data-ttu-id="a2be0-119">설명</span><span class="sxs-lookup"><span data-stu-id="a2be0-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a2be0-120">유효</span><span class="sxs-lookup"><span data-stu-id="a2be0-120">Valid</span></span>|<span data-ttu-id="a2be0-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2be0-121">ValidationStates</span></span>|<span data-ttu-id="a2be0-122">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a2be0-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a2be0-123">InvalidFocused</span></span>|<span data-ttu-id="a2be0-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2be0-124">ValidationStates</span></span>|<span data-ttu-id="a2be0-125">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a2be0-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a2be0-126">InvalidUnfocused</span></span>|<span data-ttu-id="a2be0-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2be0-127">ValidationStates</span></span>|<span data-ttu-id="a2be0-128">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="a2be0-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="a2be0-129">DocumentViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="a2be0-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="a2be0-130">다음 예제에서는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="a2be0-131">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2be0-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a2be0-132">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2be0-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2be0-133">참조</span><span class="sxs-lookup"><span data-stu-id="a2be0-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a2be0-134">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a2be0-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a2be0-135">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2be0-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a2be0-136">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a2be0-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a2be0-137">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2be0-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
