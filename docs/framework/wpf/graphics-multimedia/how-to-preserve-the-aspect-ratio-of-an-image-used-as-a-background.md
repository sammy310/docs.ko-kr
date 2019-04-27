---
title: '방법: 배경으로 사용된 이미지의 가로 세로 비율 유지'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 4ae6f1242548038bcd54b7218783e5063fa67872
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921765"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="c1a41-102">방법: 배경으로 사용된 이미지의 가로 세로 비율 유지</span><span class="sxs-lookup"><span data-stu-id="c1a41-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="c1a41-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 의 속성을 <xref:System.Windows.Media.ImageBrush> 이미지의 가로 세로 비율을 유지 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="c1a41-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="c1a41-104">기본적으로 사용 하는 경우는 <xref:System.Windows.Media.ImageBrush> 영역을 그리려면, 해당 콘텐츠가 출력 영역을 완전히 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="c1a41-105">출력 영역과 이미지의 가로 세로 비율이 다르면 이미지가 확장되면서 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="c1a41-106">있도록는 <xref:System.Windows.Media.ImageBrush> 이미지의 가로 세로 비율 유지를 설정 합니다 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch.Uniform> 또는 <xref:System.Windows.Media.Stretch.UniformToFill>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1a41-107">예제</span><span class="sxs-lookup"><span data-stu-id="c1a41-107">Example</span></span>  
 <span data-ttu-id="c1a41-108">다음 예제에서는 두 개의 <xref:System.Windows.Media.ImageBrush> 두 개의 사각형을 그릴 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="c1a41-109">각 사각형은 300 × 150픽셀 크기이며 각각 300 x 300픽셀 이미지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="c1a41-110">합니다 <xref:System.Windows.Media.TileBrush.Stretch%2A> 첫 번째 브러시의 속성이로 설정 되어 <xref:System.Windows.Media.Stretch.Uniform>, 및 <xref:System.Windows.Media.TileBrush.Stretch%2A> 두 번째 브러시의 속성이 <xref:System.Windows.Media.Stretch.UniformToFill>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="c1a41-111">다음 그림에 나와 있는 첫 번째 브러시의 출력을 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정은 <xref:System.Windows.Media.Stretch.Uniform>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="c1a41-112">![Uniform 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="c1a41-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="c1a41-113">다음 그림에서는 있는 두 번째 브러시의 출력을 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정 <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="c1a41-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="c1a41-114">![UniformToFill 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="c1a41-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="c1a41-115">합니다 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 다른 동일 하 게 동작 <xref:System.Windows.Media.TileBrush> 개체, 즉,에 대 한 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="c1a41-116">에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 집합과 <xref:System.Windows.Media.TileBrush> 개체를 참조 하세요 [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="c1a41-117">또한 있지만 합니다 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성이 표시 되도록 하는 방법을 <xref:System.Windows.Media.TileBrush> 콘텐츠가 출력 영역에 맞게 확장, 실제로 지정 하는 방법을 <xref:System.Windows.Media.TileBrush> 콘텐츠 기본 타일에 맞게 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="c1a41-118">자세한 내용은 <xref:System.Windows.Media.TileBrush>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a41-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="c1a41-119">이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="c1a41-120">전체 샘플을 참조 하세요 [ImageBrush 샘플](https://go.microsoft.com/fwlink/?LinkID=160005)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a41-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a41-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1a41-121">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="c1a41-122">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="c1a41-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
