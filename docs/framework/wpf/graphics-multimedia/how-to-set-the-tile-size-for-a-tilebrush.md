---
title: '방법: TileBrush의 바둑판 크기 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186830"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="90ad4-102">방법: TileBrush의 바둑판 크기 설정</span><span class="sxs-lookup"><span data-stu-id="90ad4-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="90ad4-103">이 예제에서는 <xref:System.Windows.Media.TileBrush>에 대한 타일 크기를 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="90ad4-104">기본적으로 페인팅할 <xref:System.Windows.Media.TileBrush> 영역을 완전히 채우는 단일 타일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="90ad4-105">및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 설정하여 이 <xref:System.Windows.Media.TileBrush.Viewport%2A> 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="90ad4-106">속성은 <xref:System.Windows.Media.TileBrush.Viewport%2A> 에 대한 타일 크기를 <xref:System.Windows.Media.TileBrush>지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="90ad4-107">기본적으로 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성 값은 페인팅되는 영역의 크기에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="90ad4-108">속성이 <xref:System.Windows.Media.TileBrush.Viewport%2A> 절대 타일 크기를 지정하도록 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 하려면 <xref:System.Windows.Media.BrushMappingMode.Absolute>속성을 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="90ad4-109">예제</span><span class="sxs-lookup"><span data-stu-id="90ad4-109">Example</span></span>

<span data-ttu-id="90ad4-110">다음 예제에서는 <xref:System.Windows.Media.ImageBrush>"의 유형 <xref:System.Windows.Media.TileBrush>"를 사용하여 사각형을 타일로 페인칠합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="90ad4-111">이 예제에서는 각 타일을 출력 영역(사각형)의 50%씩 50%로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="90ad4-112">결과적으로 이미지 프로젝션 4개를 사용한 사각형이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="90ad4-113">다음 그림에서는 예제에서 생성하는 출력을 보여 주며, 다음 그림은 다음과 같은 결과를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-113">The following illustration shows the output that the example produces:</span></span>

![이미지 브러시로 타일링을 보여주는 4 개의 체리가있는 직사각형.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="90ad4-115">다음 예제에서는 <xref:System.Windows.Media.ImageBrush>을 만들고 <xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` 그 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 에 <xref:System.Windows.Media.BrushMappingMode.Absolute>대해 설정하고 그 를 에 로 설정하고 이를 사용하여 다른 사각형을 페인칠합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="90ad4-116">결과적으로 이 브러시는 너비 및 높이가 각각 25픽셀인 타일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="90ad4-117">다음 그림에서는 예제에서 생성하는 출력을 보여 주며, 다음 그림은 다음과 같은 결과를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-117">The following illustration shows the output that the example produces:</span></span>

![뷰포트가 있는 타일 브러시를 보여주는 48개의 체리가 있는 직사각형.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="90ad4-119">앞의 예제는 큰 샘플의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="90ad4-120">전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="90ad4-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="90ad4-121">이 예제에서는 <xref:System.Windows.Media.ImageBrush> 클래스를 <xref:System.Windows.Media.TileBrush.Viewport%2A> 사용하지만 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성은 다른 <xref:System.Windows.Media.TileBrush> 개체, 즉 <xref:System.Windows.Media.DrawingBrush> 에 <xref:System.Windows.Media.VisualBrush>대해 와 동일한 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ad4-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="90ad4-122">및 기타 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.ImageBrush> 객체에 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="90ad4-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90ad4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90ad4-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="90ad4-124">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="90ad4-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="90ad4-125">TileBrush로 다른 바둑판식 배열 패턴 만들기</span><span class="sxs-lookup"><span data-stu-id="90ad4-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
