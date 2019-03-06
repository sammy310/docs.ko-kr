---
title: '방법: TileBrush의 바둑판 크기 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 2b603345e00ae3067c4be860b6aad1cf7b9883c5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354455"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="94030-102">방법: TileBrush의 바둑판 크기 설정</span><span class="sxs-lookup"><span data-stu-id="94030-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="94030-103">에 대 한 타일 크기를 설정 하는 방법을 보여주는이 예제는 <xref:System.Windows.Media.TileBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="94030-104">기본적으로 <xref:System.Windows.Media.TileBrush> 는 사용자가 칠하고 있는 영역을 완전히 채우는 단일 타일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="94030-105">설정 하 여이 동작을 재정의할 수는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 고 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="94030-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="94030-106">합니다 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성에 대 한 타일 크기를 지정 된 <xref:System.Windows.Media.TileBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="94030-107">기본적으로 값을 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성은 그리는 영역의 크기를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="94030-108">수 있도록 합니다 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성이 절대 타일 크기를 지정 설정 합니다 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 <xref:System.Windows.Media.BrushMappingMode.Absolute>입니다.</span><span class="sxs-lookup"><span data-stu-id="94030-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94030-109">예제</span><span class="sxs-lookup"><span data-stu-id="94030-109">Example</span></span>  
 <span data-ttu-id="94030-110">다음 예제에서는 <xref:System.Windows.Media.ImageBrush>, 형식의 <xref:System.Windows.Media.TileBrush>, 타일을 사용 하 여 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="94030-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="94030-111">이 예제에서는 각 타일을 출력 영역(사각형)의 50% x 50%로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="94030-112">결과적으로 이미지 프로젝션 4개를 사용한 사각형이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="94030-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="94030-113">다음 그림에서는 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94030-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="94030-114">![이미지 브러시를 사용한 바둑판식 배열 예제](./media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="94030-114">![Example of tiling with an image brush](./media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="94030-115">다음 예제에서는 <xref:System.Windows.Media.ImageBrush>, 설정 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 를 `0,0,25,25` 고 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 에 <xref:System.Windows.Media.BrushMappingMode.Absolute>, 하는 다른 사각형을 그리는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="94030-116">결과적으로 이 브러시는 너비 및 높이가 각각 25픽셀인 타일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="94030-117">다음 그림에서는 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94030-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="94030-118">![Viewport가 0,0,0.25,0.25인 바둑판 모양의 TileBrush](./media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="94030-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](./media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="94030-119">앞의 예제는 큰 샘플의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="94030-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="94030-120">전체 샘플을 참조 하세요 [ImageBrush 샘플](https://go.microsoft.com/fwlink/?LinkID=160005)합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="94030-121">이 예제에서는 합니다 <xref:System.Windows.Media.ImageBrush> 클래스를 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 다른 동일 하 게 작동 <xref:System.Windows.Media.TileBrush> 개체, 즉,에 대 한 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="94030-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="94030-122">에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 집합과 <xref:System.Windows.Media.TileBrush> 개체를 참조 하세요 [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94030-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94030-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="94030-123">See also</span></span>
- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="94030-124">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="94030-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="94030-125">TileBrush로 다른 바둑판식 배열 패턴 만들기</span><span class="sxs-lookup"><span data-stu-id="94030-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
