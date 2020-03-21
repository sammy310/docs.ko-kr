---
title: '방법: 브러시 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187332"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="9ae90-102">방법: 브러시 변환</span><span class="sxs-lookup"><span data-stu-id="9ae90-102">How to: Transform a Brush</span></span>
<span data-ttu-id="9ae90-103">이 예제에서는 두 <xref:System.Windows.Media.Brush> 가지 변환 속성 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A>을 사용하여 개체를 변환하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="9ae90-104">다음 예제는 a를 <xref:System.Windows.Media.RotateTransform> 사용하여 a의 <xref:System.Windows.Media.ImageBrush> 컨텐츠를 45도씩 회전시다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="9ae90-105">다음 그림에서는 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform> 적용된 및 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.Transform%2A> 속성에 적용된 을 가없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="9ae90-106">![Brush RelativeTransform 및 Transform 설정](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="9ae90-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ae90-107">예제</span><span class="sxs-lookup"><span data-stu-id="9ae90-107">Example</span></span>  
 <span data-ttu-id="9ae90-108">첫 번째 예제는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 의 속성에 a를 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.RotateTransform> 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="9ae90-109">개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 모두 0.5로 설정되며, 이 좌표는 이 콘텐츠의 중심점의 상대 좌표입니다. <xref:System.Windows.Media.RotateTransform></span><span class="sxs-lookup"><span data-stu-id="9ae90-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="9ae90-110">결과적으로 콘텐츠가 <xref:System.Windows.Media.ImageBrush> 중심을 중심으로 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="9ae90-111">두 번째 예제는 <xref:System.Windows.Media.RotateTransform> a를 <xref:System.Windows.Media.ImageBrush>에도 적용합니다. 그러나 이 예제에서는 <xref:System.Windows.Media.Brush.Transform%2A> 속성 대신 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="9ae90-112">중심을 중심으로 브러시를 회전하려면 <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> <xref:System.Windows.Media.RotateTransform> 이 예제에서는 오브젝트의 및 속성을 절대 좌표로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="9ae90-113">브러시는 175 x 90 셀 사각형을 그리기 때문에 사각형의 중심점은 (87.5, 45)입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae90-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="9ae90-114">및 속성의 <xref:System.Windows.Media.Brush.Transform%2A> 작동 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 방식에 대한 설명은 [브러시 변환 개요를](brush-transformation-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ae90-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="9ae90-115">전체 샘플을 보려면 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ae90-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="9ae90-116">브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ae90-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae90-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ae90-117">See also</span></span>

- [<span data-ttu-id="9ae90-118">브러시 변환 개요</span><span class="sxs-lookup"><span data-stu-id="9ae90-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="9ae90-119">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="9ae90-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="9ae90-120">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="9ae90-120">Transforms Overview</span></span>](transforms-overview.md)
