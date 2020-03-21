---
title: '방법: 요소 기울이기'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112026"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="eeb5b-102">방법: 요소 기울이기</span><span class="sxs-lookup"><span data-stu-id="eeb5b-102">How to: Skew an Element</span></span>
<span data-ttu-id="eeb5b-103">이 예제에서는 a를 <xref:System.Windows.Media.SkewTransform> 사용하여 요소를 왜곡하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="eeb5b-104">전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="eeb5b-105">a의 <xref:System.Windows.Media.SkewTransform> 일반적인 용도 중 하나는 2D 개체에서 3D 깊이를 시뮬레이션하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="eeb5b-106"><xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 속성과 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 속성을 사용하여 의 중심점을 지정합니다. <xref:System.Windows.Media.SkewTransform></span><span class="sxs-lookup"><span data-stu-id="eeb5b-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="eeb5b-107"><xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 속성을 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 사용하여 x축 및 y축의 기울이기 각도를 지정하고 이러한 축을 따라 현재 좌표계를 기울이도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="eeb5b-108">기울이기 변환의 효과를 예측하려면 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 원래 좌표계를 기준으로 x축 값을 기울이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="eeb5b-109">따라서 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30의 경우 y축은 원점을 통해 30도 회전하고 해당 원점에서 30도 씩 값을 x-씩 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="eeb5b-110">마찬가지로 30의 값은 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 모양의 y-값을 원점에서 30도 기울이게 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="eeb5b-111">이것은 좌표 시스템을 x 또는 y축으로 30도만큼 변환(이동)하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="eeb5b-112">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(0,0)에서 45도의 수평 스큐를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb5b-113">예제</span><span class="sxs-lookup"><span data-stu-id="eeb5b-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="eeb5b-114">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(25,25)에서 45도의 수평 스큐를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="eeb5b-115">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(25,25)에서 45도의 수직 스큐를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="eeb5b-116">다음 그림에서는 이 예제에서 사용되는 다양한 기울이기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="eeb5b-117">![SkewTransform 예제](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="eeb5b-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="eeb5b-118">세 개의 SkewTransform 예제 그림</span><span class="sxs-lookup"><span data-stu-id="eeb5b-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="eeb5b-119">전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eeb5b-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb5b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeb5b-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="eeb5b-121">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="eeb5b-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="eeb5b-122">방법 주제</span><span class="sxs-lookup"><span data-stu-id="eeb5b-122">How-to Topics</span></span>](transformations-how-to-topics.md)
