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
ms.openlocfilehash: a83f3b1c046e94faa8816e8c310f438b4711048a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769379"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="81410-102">방법: 브러시 변환</span><span class="sxs-lookup"><span data-stu-id="81410-102">How to: Transform a Brush</span></span>
<span data-ttu-id="81410-103">이 예제에서는 변환 하는 방법을 보여 줍니다 <xref:System.Windows.Media.Brush> 변환 속성을 사용 하 여 개체: <xref:System.Windows.Media.Brush.RelativeTransform%2A> 고 <xref:System.Windows.Media.Brush.Transform%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="81410-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="81410-104">다음 예에서는 <xref:System.Windows.Media.RotateTransform> 의 콘텐츠를 회전 하는 <xref:System.Windows.Media.ImageBrush> 으로 45도 합니다.</span><span class="sxs-lookup"><span data-stu-id="81410-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="81410-105">다음 그림에 표시를 <xref:System.Windows.Media.ImageBrush> 없이 <xref:System.Windows.Media.RotateTransform>를 사용 하 여를 <xref:System.Windows.Media.RotateTransform> 적용할를 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을와 <xref:System.Windows.Media.RotateTransform> 적용할를 <xref:System.Windows.Media.Brush.Transform%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="81410-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="81410-106">![Brush RelativeTransform 및 Transform 설정](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="81410-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="81410-107">예제</span><span class="sxs-lookup"><span data-stu-id="81410-107">Example</span></span>  
 <span data-ttu-id="81410-108">적용 하는 첫 번째 예제는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 의 속성을 <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="81410-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="81410-109">합니다 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 의 속성을 <xref:System.Windows.Media.RotateTransform> 개체는 둘 다이 콘텐츠 중심점의 상대 좌표 인 0.5로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81410-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="81410-110">결과적으로 <xref:System.Windows.Media.ImageBrush> 콘텐츠 가운데를 중심으로 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="81410-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="81410-111">두 번째 예제도 적용 됩니다는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.ImageBrush>하지만이 예제에서는 <xref:System.Windows.Media.Brush.Transform%2A> 속성 대신는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="81410-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="81410-112">가운데를 중심으로 브러시를 회전 하려면이 예제에서는 설정 합니다 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform> 절대 좌표를 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="81410-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="81410-113">브러시는 175 x 90 셀 사각형을 그리기 때문에 사각형의 중심점은 (87.5, 45)입니다.</span><span class="sxs-lookup"><span data-stu-id="81410-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="81410-114">설명에 대 한 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 하 고 <xref:System.Windows.Media.Brush.Transform%2A> 속성 작업을 참조 하십시오.는 [브러시 변환 개요](brush-transformation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81410-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="81410-115">전체 샘플을 보려면 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81410-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="81410-116">브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81410-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81410-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="81410-117">See also</span></span>

- [<span data-ttu-id="81410-118">브러시 변환 개요</span><span class="sxs-lookup"><span data-stu-id="81410-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="81410-119">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="81410-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="81410-120">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="81410-120">Transforms Overview</span></span>](transforms-overview.md)
