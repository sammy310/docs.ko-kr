---
title: '방법: 도구 설명 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 811818fe6e7c0d8ce9e2aa058b42bf592ada4b92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212351"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="c8993-102">방법: 도구 설명 배치</span><span class="sxs-lookup"><span data-stu-id="c8993-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="c8993-103">이 예제에는 화면의 도구 설명의 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8993-104">예제</span><span class="sxs-lookup"><span data-stu-id="c8993-104">Example</span></span>  
 <span data-ttu-id="c8993-105">둘 다에 정의 된 5 가지 속성 집합을 사용 하 여 도구 설명을 배치할 수 있습니다 합니다 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="c8993-106">다음 표에서 이러한 두 속성을 5 개를 표시 하 고 클래스에 따라 해당 참조 설명서에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="c8993-107">클래스에 따라 해당 도구 설명 속성</span><span class="sxs-lookup"><span data-stu-id="c8993-107">Corresponding tooltip properties according to class</span></span>  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> <span data-ttu-id="c8993-108">클래스 속성</span><span class="sxs-lookup"><span data-stu-id="c8993-108">class properties</span></span>|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> <span data-ttu-id="c8993-109">클래스 속성</span><span class="sxs-lookup"><span data-stu-id="c8993-109">class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="c8993-110">사용 하 여 도구 설명의 내용을 정의 하는 경우는 <xref:System.Windows.Controls.ToolTip> 개체 클래스의 속성을 사용할 수 있지만 <xref:System.Windows.Controls.ToolTipService> 속성 보다 우선적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="c8993-111">사용 된 <xref:System.Windows.Controls.ToolTipService> 속성으로 정의 되어 있지 않은 도구 설명에 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="c8993-112">다음 그림은 이러한 속성을 사용 하 여 도구 설명을 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="c8993-113">하지만, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이러한 그림과 예제에 정의 된 속성을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ToolTip> 클래스의 해당 속성을 <xref:System.Windows.Controls.ToolTipService> 클래스 동일한 레이아웃 규칙에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="c8993-114">배치 속성에 대 한 가능한 값에 대 한 자세한 내용은 참조 하세요. [Popup 배치 동작](popup-placement-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  
 
 <span data-ttu-id="c8993-115">다음 이미지는 배치 속성을 사용 하 여 tooltip 배치를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![배치 속성을 사용 하 여 ToolTip 배치를 보여 주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)
 
 <span data-ttu-id="c8993-117">다음 이미지는 배치 및 PlacementRectangle 속성을 사용 하 여 tooltip 배치를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>   

 ![PlacementRectangle 속성을 사용 하 여 ToolTip 배치를 보여 주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  
 
 <span data-ttu-id="c8993-119">다음 이미지는 배치, PlacementRectangle, 및 오프셋 속성을 사용 하 여 tooltip 배치를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>   
  
 ![오프셋 속성을 사용 하 여 ToolTip 배치를 보여 주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="c8993-121">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.ToolTip> 내용이 도구 설명의 위치를 지정 하는 속성을 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="c8993-122">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.ToolTipService> 내용이 아닙니다. 도구 설명의 위치를 지정 하는 속성을 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c8993-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="c8993-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8993-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="c8993-124">방법 항목</span><span class="sxs-lookup"><span data-stu-id="c8993-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="c8993-125">도구 설명 개요</span><span class="sxs-lookup"><span data-stu-id="c8993-125">ToolTip Overview</span></span>](tooltip-overview.md)
