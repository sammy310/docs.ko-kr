---
title: 전역 및 지역 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955187"
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="7fdd5-102">전역 및 지역 변환</span><span class="sxs-lookup"><span data-stu-id="7fdd5-102">Global and Local Transformations</span></span>
<span data-ttu-id="7fdd5-103">전역 변환은 지정 <xref:System.Drawing.Graphics> 된 개체에 의해 그려지는 모든 항목에 적용 되는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="7fdd5-104">반면 로컬 변환은 그릴 특정 항목에 적용 되는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="7fdd5-105">전역 변환</span><span class="sxs-lookup"><span data-stu-id="7fdd5-105">Global Transformations</span></span>  
 <span data-ttu-id="7fdd5-106">전역 변환을 만들려면 <xref:System.Drawing.Graphics> 개체를 생성 한 다음 해당 <xref:System.Drawing.Graphics.Transform%2A> 속성을 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="7fdd5-107"><xref:System.Drawing.Graphics.Transform%2A> 속성<xref:System.Drawing.Drawing2D.Matrix> 은 개체 이므로 상관 변환의 모든 시퀀스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="7fdd5-108"><xref:System.Drawing.Graphics.Transform%2A> 속성에 저장 된 변환을 전역 변환 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="7fdd5-109">클래스 <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.MultiplyTransform%2A>는,, 및 <xref:System.Drawing.Graphics.ScaleTransform%2A> <xref:System.Drawing.Graphics.RotateTransform%2A> 복합세계변환을빌드하기위한여러메서드<xref:System.Drawing.Graphics.TranslateTransform%2A>를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="7fdd5-110">다음 예제에서는 타원을 두 번 그립니다. 전 세계 변환을 만들고 한 번은 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="7fdd5-111">변환은 먼저 y 방향으로 0.5의 비율로 크기를 조정 하 고 x 방향으로 50 단위를 변환한 다음 30도 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="7fdd5-112">다음 그림에서는 변환과 관련 된 행렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="7fdd5-113">![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="7fdd5-113">![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fdd5-114">앞의 예제에서는 클라이언트 영역의 왼쪽 위 모퉁이에 있는 좌표계의 원점에 대해 타원이 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="7fdd5-115">그러면 타원을 자체 중심으로 회전 하는 것과 다른 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="7fdd5-116">로컬 변환</span><span class="sxs-lookup"><span data-stu-id="7fdd5-116">Local Transformations</span></span>  
 <span data-ttu-id="7fdd5-117">로컬 변환은 그릴 특정 항목에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="7fdd5-118">예를 들어 개체 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> 에는 해당 경로의 데이터 요소를 변환 하는 데 사용할 수 있는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="7fdd5-119">다음 예제에서는 변환이 없고 회전 변환이 있는 경로를 사용 하 여 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="7fdd5-120">(전 세계 변환이 없는 것으로 가정)</span><span class="sxs-lookup"><span data-stu-id="7fdd5-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="7fdd5-121">전역 변환을 로컬 변환과 결합 하 여 다양 한 결과를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="7fdd5-122">예를 들어 세계 변형을 사용 하 여 좌표계를 수정 하 고 로컬 변형을 사용 하 여 새 좌표계에 그려진 개체를 회전 하 고 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="7fdd5-123">클라이언트 영역의 왼쪽 가장자리에서 200 픽셀의 원점 및 클라이언트 영역의 위쪽에서 150 픽셀을 가진 좌표계를 만들려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="7fdd5-124">또한 측정 단위가 픽셀 임을 가정 합니다. x 축이 오른쪽을 가리키고 y 축은 위쪽을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="7fdd5-125">기본 좌표계에는 y 축이 있고 가로 축에서 반사를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="7fdd5-126">다음 그림에서는 이러한 리플렉션의 행렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="7fdd5-127">![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="7fdd5-127">![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="7fdd5-128">다음으로, 200 단위를 오른쪽으로 이동 하 고 150 단위를 종료 해야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="7fdd5-129">다음 예에서는 <xref:System.Drawing.Graphics> 개체의 세계 변형을 설정 하 여 설명한 대로 좌표계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="7fdd5-130">이전 예제의 끝에 있는 다음 코드는 새 좌표계의 원점에서 왼쪽 아래 모퉁이가 있는 단일 사각형으로 구성 된 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="7fdd5-131">사각형은 로컬 변환이 없고 로컬 변환을 사용 하 여 한 번 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="7fdd5-132">로컬 변환은 요소 2의 가로 크기 조정 후 30도 회전으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="7fdd5-133">다음 그림에서는 새 좌표계와 두 개의 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fdd5-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="7fdd5-134">![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="7fdd5-134">![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fdd5-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fdd5-135">See also</span></span>

- [<span data-ttu-id="7fdd5-136">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="7fdd5-136">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="7fdd5-137">관리 GDI+에서 변형 사용</span><span class="sxs-lookup"><span data-stu-id="7fdd5-137">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
