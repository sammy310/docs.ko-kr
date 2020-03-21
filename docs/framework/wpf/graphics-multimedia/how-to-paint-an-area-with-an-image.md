---
title: '방법: 이미지로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186060"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="15eee-102">방법: 이미지로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="15eee-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="15eee-103">이 예제에서는 클래스를 <xref:System.Windows.Media.ImageBrush> 사용하여 이미지로 영역을 페인칠하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="15eee-104">속성에 <xref:System.Windows.Media.ImageBrush> 의해 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 지정된 단일 이미지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15eee-105">예제</span><span class="sxs-lookup"><span data-stu-id="15eee-105">Example</span></span>  
 <span data-ttu-id="15eee-106">다음 예제는 을 <xref:System.Windows.Controls.Control.Background%2A> 사용하여 단추를 <xref:System.Windows.Media.ImageBrush>그립니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="15eee-107">기본적으로 이미지를 <xref:System.Windows.Media.ImageBrush> 늘이면 페인팅할 영역을 완전히 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="15eee-108">위의 예제에서는 이미지가 단추를 채우도록 확장되므로 이미지가 왜곡될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="15eee-109"><xref:System.Windows.Media.TileBrush.Stretch%2A> 브러시가 이미지의 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> 가로 세로 비율을 <xref:System.Windows.Media.Stretch.UniformToFill>유지하도록 하는 의 속성을 또는 에 설정하여 이 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="15eee-110"><xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.TileMode%2A> 및 의 속성을 설정하는 경우 반복 패턴을 만들 <xref:System.Windows.Media.ImageBrush>수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="15eee-111">다음 예제에서는 이미지에서 만들어지는 패턴을 사용하여 단추를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="15eee-112">클래스에 <xref:System.Windows.Media.ImageBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15eee-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="15eee-113">이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="15eee-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="15eee-114">전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15eee-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15eee-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15eee-115">See also</span></span>

- [<span data-ttu-id="15eee-116">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="15eee-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
