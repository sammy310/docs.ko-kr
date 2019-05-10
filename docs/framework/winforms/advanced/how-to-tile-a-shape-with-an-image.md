---
title: '방법: 이미지에 도형을 바둑판식으로 배열'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063733"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="e9ff2-102">방법: 이미지에 도형을 바둑판식으로 배열</span><span class="sxs-lookup"><span data-stu-id="e9ff2-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="e9ff2-103">층에 맞게 서로 옆에 있는 타일을 배치할 수 있습니다, 처럼 채우기 (타일) 셰이프를 서로 옆에 있는 사각형 이미지에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="e9ff2-104">도형의 내부를 타일을 질감 브러시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="e9ff2-105">생성 하는 경우는 <xref:System.Drawing.TextureBrush> 개체 생성자에 전달 하는 인수 중 하나는 <xref:System.Drawing.Image> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="e9ff2-106">질감 브러시를 사용 하 여 도형의 내부를 그리는 경우 셰이프가이 이미지의 복사본을 반복적된으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="e9ff2-107">랩 모드 속성을 <xref:System.Drawing.TextureBrush> 개체는 사각형 그리드 안의 반복적으로 이미지 방향는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="e9ff2-108">그리드에서 타일에 있는 모든 같은 방향으로 만들거나 다음 그리드 위치에서 대칭 이동 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="e9ff2-109">대칭 이동의 가로, 수 세로 축 또는 둘 다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="e9ff2-110">다음 예에서는 대칭 이동 하는 다양 한 유형의 바둑판식 배열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="e9ff2-111">이미지 타일</span><span class="sxs-lookup"><span data-stu-id="e9ff2-111">To tile an image</span></span>  
  
- <span data-ttu-id="e9ff2-112">이 예제에서는 200 × 200 사각형에 바둑판식으로 배열 하 다음 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![빨간색 집 및 트리를 보여 주는 타일 이미지입니다.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="e9ff2-114">다음 그림에서는 이미지를 사용 하 여 사각형을 바둑판식으로 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="e9ff2-115">모든 타일이 동일한 방향을;에 있는 참고 대칭 이동 안 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![모든 타일에 대 한 동일한 방향을 사용 하 여 이미지를 사용 하 여 바둑판식으로 배열 하는 사각형입니다.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="e9ff2-117">가로 바둑판식 배열 하는 동안 이미지를 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="e9ff2-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="e9ff2-118">이 예제에서는 200 × 200 사각형에 맞게 동일한 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="e9ff2-119">이미지를 가로로 대칭 이동 하려면 줄 바꿈 모드를 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="e9ff2-120">다음 그림에서는 이미지를 사용 하 여 사각형을 바둑판식으로 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="e9ff2-121">지정된 된 행의 다음 한 타일에서 이동 하면 이미지를 좌우 대칭는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![가로로 대칭 이동 이미지를 사용 하 여 바둑판식으로 배열 하는 사각형입니다.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="e9ff2-123">세로 바둑판식 배열 하는 동안 이미지를 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="e9ff2-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="e9ff2-124">이 예제에서는 200 × 200 사각형에 맞게 동일한 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="e9ff2-125">이미지를 세로로 대칭 이동 하려면 줄 바꿈 모드를 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="e9ff2-126">바둑판식으로 배열 하는 동안 가로 및 세로로 이미지를 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="e9ff2-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="e9ff2-127">이 예제에서는 200 × 200 사각형에 바둑판식으로 배열 하 동일한 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="e9ff2-128">줄 바꿈 모드는 이미지를 대칭으로 가로 세로 방향으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="e9ff2-129">다음 그림에서는 이미지에서 사각형은 바둑판식으로 배열 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="e9ff2-130">타일이 하나만 지정된 된 행의 다음 단계로 이동 하면 이미지를 가로로 대칭는 및 이미지를 상하 대칭은 지정된 된 열 다음 한 타일에서 이동할 때.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![가로 및 세로로 대칭 이동 이미지를 사용 하 여 바둑판식으로 배열 하는 사각형입니다.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="e9ff2-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9ff2-132">See also</span></span>

- [<span data-ttu-id="e9ff2-133">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="e9ff2-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
