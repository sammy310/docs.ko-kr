---
title: 좌표계 형식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 24079f24bdae5fefd785a20dda9b29a190fb4068
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505256"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="28bd1-102">좌표계 형식</span><span class="sxs-lookup"><span data-stu-id="28bd1-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="28bd1-103">GDI +-세 가지 좌표 공간을 사용 하는 중: 전역, 페이지 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="28bd1-104">세계 좌표 좌표 특정 그래픽 월드를 모델링 하는 데 사용 되며.NET Framework의 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="28bd1-105">페이지 좌표 양식이 나 컨트롤 같은 그리기 화면을 사용 하는 좌표계를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="28bd1-106">장치 좌표는 화면이 나 용지 같이 항목이 그려지는 실제 장치에서 사용 된 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="28bd1-107">호출이 이루어지면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`에 전달 하는 지점 합니다 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드-`(0, 0)` 및 `(160, 80)`-세계 좌표 공간에 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="28bd1-108">GDI + 화면의 줄을 그릴 수 있습니다, 전에 좌표를 일련의 변환을 통해 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="28bd1-109">월드 변형을 호출 하는 하나의 변환 세계 좌표를 페이지 좌표로 변환 하는 페이지 변환을 통해 다른 변환 페이지 좌표 장치 좌표에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="28bd1-110">변환 및 좌표계</span><span class="sxs-lookup"><span data-stu-id="28bd1-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="28bd1-111">원점은 왼쪽 위 모퉁이 사용 하지 않고 클라이언트 영역의 본문에는 좌표계를 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="28bd1-112">예를 들어, 원본 클라이언트 영역의 왼쪽된 가장자리에서 100 픽셀인 클라이언트 영역의 위쪽에서 50 픽셀 이어야 한다고 가정해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="28bd1-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="28bd1-113">다음 그림에서는 이러한 좌표 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="28bd1-114">![좌표계](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="28bd1-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="28bd1-115">호출을 수행 하면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, 다음 그림에 표시 된 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="28bd1-116">![좌표계](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="28bd1-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="28bd1-117">세 가지 좌표 공간에서 선의 끝점 좌표는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28bd1-118">전 세계</span><span class="sxs-lookup"><span data-stu-id="28bd1-118">World</span></span>|<span data-ttu-id="28bd1-119">(0, 0)를 (160, 80)</span><span class="sxs-lookup"><span data-stu-id="28bd1-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="28bd1-120">페이지</span><span class="sxs-lookup"><span data-stu-id="28bd1-120">Page</span></span>|<span data-ttu-id="28bd1-121">(100, 50)를 (260, 130)</span><span class="sxs-lookup"><span data-stu-id="28bd1-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="28bd1-122">디바이스</span><span class="sxs-lookup"><span data-stu-id="28bd1-122">Device</span></span>|<span data-ttu-id="28bd1-123">(100, 50)를 (260, 130)</span><span class="sxs-lookup"><span data-stu-id="28bd1-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="28bd1-124">페이지 좌표 공간을 사용 하는 참고; 클라이언트 영역의 왼쪽 위 모퉁이 원점 이 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="28bd1-125">측정 단위를 픽셀 이기 때문에 장치 좌표는 페이지 좌표와 같은 note도 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="28bd1-126">측정 단위를 픽셀 (예를 들어, 인치) 이외의 값으로 설정한 경우 장치 좌표 다 페이지 좌표를 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="28bd1-127">영역 좌표를 페이지 좌표로 매핑하, 세계 변환에 저장 된 합니다 <xref:System.Drawing.Graphics.Transform%2A> 의 속성을 <xref:System.Drawing.Graphics> 클래스.</span><span class="sxs-lookup"><span data-stu-id="28bd1-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="28bd1-128">앞의 예에서 월드의 x 방향의 100 단위 및 y 방향의 50 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="28bd1-129">월드 변형을 설정 하는 다음 예제는 <xref:System.Drawing.Graphics> 개체 및을 사용 하 여 <xref:System.Drawing.Graphics> 위의 그림에 표시 된 줄을 그릴 개체:</span><span class="sxs-lookup"><span data-stu-id="28bd1-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="28bd1-130">페이지 변형 장치 좌표로 페이지 좌표를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="28bd1-131">합니다 <xref:System.Drawing.Graphics> 클래스를 제공 합니다 <xref:System.Drawing.Graphics.PageUnit%2A> 및 <xref:System.Drawing.Graphics.PageScale%2A> 페이지 변환 조작에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="28bd1-132"><xref:System.Drawing.Graphics> 클래스에서는 두 개의 읽기 전용 속성 <xref:System.Drawing.Graphics.DpiX%2A> 및 <xref:System.Drawing.Graphics.DpiY%2A>, 가로 및 세로 인치당 디스플레이 장치의 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="28bd1-133">사용할 수는 <xref:System.Drawing.Graphics.PageUnit%2A> 의 속성을 <xref:System.Drawing.Graphics> 픽셀 이외의 측정 단위를 지정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28bd1-134">설정할 수 없습니다는 <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 <xref:System.Drawing.GraphicsUnit.World>처럼 하지 물리적 단위 이며 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="28bd1-135">다음 예제에서 선을 그립니다 (0, 0)를 (2, 1) 점 (2, 1) 인 2 인치 오른쪽 및 아래쪽 1 인치 지점 (0, 0)에서:</span><span class="sxs-lookup"><span data-stu-id="28bd1-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="28bd1-136">펜을 생성 하는 경우 펜 굵기를 지정 하지 않으면, 앞의 예제 1 인치 와이드 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="28bd1-137">두 번째 인수에 펜 너비를 지정할 수는 <xref:System.Drawing.Pen> 생성자:</span><span class="sxs-lookup"><span data-stu-id="28bd1-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="28bd1-138">디스플레이 장치에는 가로 방향 인치당 96 도트와 세로 방향 인치당 96 도트를 가정 하는 경우 앞의 예제에서 선의 끝점 좌표는 다음과 세 좌표 공간에서:</span><span class="sxs-lookup"><span data-stu-id="28bd1-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28bd1-139">전 세계</span><span class="sxs-lookup"><span data-stu-id="28bd1-139">World</span></span>|<span data-ttu-id="28bd1-140">(0, 0)를 (2, 1)</span><span class="sxs-lookup"><span data-stu-id="28bd1-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="28bd1-141">페이지</span><span class="sxs-lookup"><span data-stu-id="28bd1-141">Page</span></span>|<span data-ttu-id="28bd1-142">(0, 0)를 (2, 1)</span><span class="sxs-lookup"><span data-stu-id="28bd1-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="28bd1-143">디바이스</span><span class="sxs-lookup"><span data-stu-id="28bd1-143">Device</span></span>|<span data-ttu-id="28bd1-144">(0, 0에 (192, 96)</span><span class="sxs-lookup"><span data-stu-id="28bd1-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="28bd1-145">클라이언트 영역의 왼쪽 위 모퉁이에서 세계 좌표 공간의 원본 이기 때문에 페이지 좌표는 전 세계 좌표와 같은 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="28bd1-146">다양 한 효과 달성 하기 위해 월드 및 페이지 변형을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="28bd1-147">예를 들어 인치를 측정 단위로 사용 하려는 하 고 클라이언트 영역 및 1/2 인치 클라이언트 영역의 위쪽에서 왼쪽된 가장자리 로부터 2 인치 좌표 시스템의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="28bd1-148">다음 예제에서는 설정의 월드 및 페이지 변형을 <xref:System.Drawing.Graphics> 개체 및 선을 그립니다 (0, 0)를 (2, 1):</span><span class="sxs-lookup"><span data-stu-id="28bd1-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="28bd1-149">다음 그림은 줄 및 좌표계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28bd1-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="28bd1-150">![좌표계](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="28bd1-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="28bd1-151">디스플레이 장치에는 가로 방향 인치당 96 도트와 세로 방향 인치당 96 도트를 가정 하는 경우 앞의 예제에서 선의 끝점 좌표는 다음과 세 좌표 공간에서:</span><span class="sxs-lookup"><span data-stu-id="28bd1-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28bd1-152">전 세계</span><span class="sxs-lookup"><span data-stu-id="28bd1-152">World</span></span>|<span data-ttu-id="28bd1-153">(0, 0)를 (2, 1)</span><span class="sxs-lookup"><span data-stu-id="28bd1-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="28bd1-154">페이지</span><span class="sxs-lookup"><span data-stu-id="28bd1-154">Page</span></span>|<span data-ttu-id="28bd1-155">(2, 0.5)를 (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="28bd1-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="28bd1-156">디바이스</span><span class="sxs-lookup"><span data-stu-id="28bd1-156">Device</span></span>|<span data-ttu-id="28bd1-157">(192, 48)를 (384, 144)</span><span class="sxs-lookup"><span data-stu-id="28bd1-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28bd1-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="28bd1-158">See also</span></span>

- [<span data-ttu-id="28bd1-159">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="28bd1-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="28bd1-160">매트릭스에 의한 변형 표시</span><span class="sxs-lookup"><span data-stu-id="28bd1-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
