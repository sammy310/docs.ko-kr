---
title: '방법: 요소 기울이기'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 47f671f493e7b379c36f9bf4b50ec9d185d10b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144965"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="32428-102">방법: 요소 기울이기</span><span class="sxs-lookup"><span data-stu-id="32428-102">How to: Skew an Element</span></span>
<span data-ttu-id="32428-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SkewTransform> 요소 기울이기 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="32428-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="32428-104">전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="32428-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="32428-105">일반적인 한 가지 용도 <xref:System.Windows.Media.SkewTransform> 시뮬레이션입니다 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 깊이 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="32428-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="32428-106">사용 하 여는 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 가운데를 지정 하는 속성의 가리킨는 <xref:System.Windows.Media.SkewTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="32428-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="32428-107">사용 된 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 속성 x 축 및 y 축 기울기 각도 지정 하 고 이러한 축 따라 현재 좌표계를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="32428-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="32428-108">기울이기 변환 효과 예측 하는 것이 좋습니다 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 는 원래 좌표계를 기준으로 x 축 값을 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="32428-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="32428-109">따라서는 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30 y 축은 원점을 30도 회전 및 값 x-해당 원점에서 30도 만큼 기울어집니다.</span><span class="sxs-lookup"><span data-stu-id="32428-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="32428-110">마찬가지로,는 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 도형의 y 값 원점에서 30도 만큼 기울어집니다.</span><span class="sxs-lookup"><span data-stu-id="32428-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="32428-111">이것은 좌표 시스템을 x 또는 y축으로 30도만큼 변환(이동)하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32428-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="32428-112">다음 예에서는 45도의 가로 기울이기를 적용을 <xref:System.Windows.Shapes.Rectangle> (0, 0)의 중심점에서.</span><span class="sxs-lookup"><span data-stu-id="32428-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32428-113">예제</span><span class="sxs-lookup"><span data-stu-id="32428-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="32428-114">다음 예에서는 45도의 가로 기울이기를 적용을 <xref:System.Windows.Shapes.Rectangle> (25, 25)의 중심점에서.</span><span class="sxs-lookup"><span data-stu-id="32428-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="32428-115">다음 예에서는 45도의 세로 기울이기를 적용을 <xref:System.Windows.Shapes.Rectangle> (25, 25)의 중심점에서.</span><span class="sxs-lookup"><span data-stu-id="32428-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="32428-116">다음 그림에서는 이 예제에서 사용되는 다양한 기울이기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32428-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="32428-117">![SkewTransform 예제](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="32428-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="32428-118">세 개의 SkewTransform 예제 그림</span><span class="sxs-lookup"><span data-stu-id="32428-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="32428-119">전체 샘플을 보려면 [2차원 변환 샘플](https://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32428-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32428-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="32428-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="32428-121">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="32428-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="32428-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="32428-122">How-to Topics</span></span>](transformations-how-to-topics.md)
