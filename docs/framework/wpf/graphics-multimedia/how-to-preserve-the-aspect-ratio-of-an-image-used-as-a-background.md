---
title: '방법: 배경으로 사용된 이미지의 가로 세로 비율 유지'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186024"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="b55f0-102">방법: 배경으로 사용된 이미지의 가로 세로 비율 유지</span><span class="sxs-lookup"><span data-stu-id="b55f0-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="b55f0-103">이 예제에서는 이미지의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 가로 <xref:System.Windows.Media.ImageBrush> 세로 비율을 유지하기 위해 a의 속성을 사용하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="b55f0-104">기본적으로 영역을 <xref:System.Windows.Media.ImageBrush> 사용하여 페인트할 때 해당 콘텐츠가 늘어나 출력 영역을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="b55f0-105">출력 영역과 이미지의 가로 세로 비율이 다르면 이미지가 확장되면서 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="b55f0-106">이미지의 <xref:System.Windows.Media.ImageBrush> 가로 세로 비율을 유지하려면 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 또는 <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b55f0-107">예제</span><span class="sxs-lookup"><span data-stu-id="b55f0-107">Example</span></span>  
 <span data-ttu-id="b55f0-108">다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 두 개의 오브젝트를 사용하여 두 개의 사각형을 페인칠합니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="b55f0-109">각 사각형은 300 × 150픽셀 크기이며 각각 300 x 300픽셀 이미지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="b55f0-110">첫 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 브러시의 속성이 <xref:System.Windows.Media.Stretch.Uniform>로 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정되고 두 번째 브러시의 속성이 로 <xref:System.Windows.Media.Stretch.UniformToFill>설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="b55f0-111">다음 그림에서는 의 설정이 있는 첫 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 <xref:System.Windows.Media.Stretch.Uniform>브러시의 출력을 보여 주며, 이 브러시의 출력을 보여 주면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="b55f0-112">![Uniform 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="b55f0-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="b55f0-113">다음 그림에서는 의 설정이 있는 두 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 <xref:System.Windows.Media.Stretch.UniformToFill>브러시의 출력을 보여 주며, 이 두 번째 브러시의 출력을 보여 주면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="b55f0-114">![UniformToFill 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="b55f0-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="b55f0-115">속성은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 다른 <xref:System.Windows.Media.TileBrush> 개체, 즉 에 대해 <xref:System.Windows.Media.DrawingBrush> 와 동일한 것으로 <xref:System.Windows.Media.VisualBrush>작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="b55f0-116">및 기타 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.ImageBrush> 객체에 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b55f0-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="b55f0-117">또한 속성이 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.TileBrush> 출력 영역에 맞게 콘텐츠가 늘어나는 방법을 지정하는 것처럼 보이지만 실제로 <xref:System.Windows.Media.TileBrush> 는 콘텐츠가 기본 타일을 채우기 위해 늘어나는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="b55f0-118">자세한 내용은 <xref:System.Windows.Media.TileBrush>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b55f0-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="b55f0-119">이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b55f0-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="b55f0-120">전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b55f0-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55f0-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b55f0-121">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="b55f0-122">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="b55f0-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
