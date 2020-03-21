---
title: '방법: 개체 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112065"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="4133c-102">방법: 개체 회전</span><span class="sxs-lookup"><span data-stu-id="4133c-102">How to: Rotate an Object</span></span>
<span data-ttu-id="4133c-103">이 예제에서는 개체를 회전하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="4133c-104">예제는 먼저 <xref:System.Windows.Media.RotateTransform> a를 생성한 <xref:System.Windows.Media.RotateTransform.Angle%2A> 다음 도를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="4133c-105">다음 예제는 오브젝트를 <xref:System.Windows.Shapes.Polyline> 왼쪽 위 모서리를 45도 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4133c-106">예제</span><span class="sxs-lookup"><span data-stu-id="4133c-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="4133c-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 <xref:System.Windows.Media.RotateTransform> 오브젝트가 회전되는 점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="4133c-108">이 중심점은 변환되는 요소의 좌표 공간으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="4133c-109">기본적으로 회전은 변환할 개체의 왼쪽 위 구석에 해당하는 (0,0)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="4133c-110">다음 예제에서는 <xref:System.Windows.Shapes.Polyline> 점(25,50)에 대해 물체를 시계 방향으로 45도 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="4133c-111">다음 그림에서는 두 오브젝트에 <xref:System.Windows.Media.Transform> a를 적용한 결과를 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="4133c-112">![여러 중심점을 사용한 45도 회전](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="4133c-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="4133c-113">서로 다른 회전 중심에서 45도로 회전하는 두 개체</span><span class="sxs-lookup"><span data-stu-id="4133c-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="4133c-114">이전 <xref:System.Windows.Shapes.Polyline> 예제의 는 <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="4133c-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="4133c-115"><xref:System.Windows.UIElement>의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성에 <xref:System.Windows.Media.Transform> <xref:System.Windows.UIElement.RenderTransform%2A> a를 적용하는 경우 속성을 사용하여 요소에 적용하는 모든 <xref:System.Windows.Media.Transform> 요소에 대한 원점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="4133c-116">속성은 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 상대 좌표를 사용하므로 크기를 모르는 경우에도 요소의 중심에 변환을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4133c-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="4133c-117">자세한 정보 및 예제에서는 [상대 값을 사용하여 변환의 원원 지정을](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4133c-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="4133c-118">전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4133c-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4133c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4133c-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="4133c-120">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="4133c-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="4133c-121">방법 주제</span><span class="sxs-lookup"><span data-stu-id="4133c-121">How-to Topics</span></span>](transformations-how-to-topics.md)
