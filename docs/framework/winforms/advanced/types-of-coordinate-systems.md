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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159808"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="6eabe-102">좌표계 형식</span><span class="sxs-lookup"><span data-stu-id="6eabe-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="6eabe-103">GDI +-세 가지 좌표 공간을 사용 하는 중: 전역, 페이지 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="6eabe-104">세계 좌표 좌표 특정 그래픽 월드를 모델링 하는 데 사용 되며.NET Framework의 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="6eabe-105">페이지 좌표는 폼 또는 컨트롤과 같은 그리기 화면에서 사용 하는 좌표계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="6eabe-106">장치 좌표는 화면이 나 용지와 같이 그려지는 실제 장치에서 사용 하는 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="6eabe-107">`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`호출 하는 경우 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 (`(0, 0)` 및 `(160, 80)`)에 전달 하는 지점은 세계 좌표 공간에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="6eabe-108">GDI +에서 화면에 선을 그리려면 좌표는 일련의 변환으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="6eabe-109">세계 좌표 변환 이라고 하는 한 가지 변환은 세계 좌표를 페이지 좌표로 변환 하 고 페이지 변환 이라고 하는 다른 변환은 페이지 좌표를 장치 좌표로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="6eabe-110">시스템 변환 및 조정</span><span class="sxs-lookup"><span data-stu-id="6eabe-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="6eabe-111">왼쪽 위 모퉁이가 아닌 클라이언트 영역의 본문에서 원점이 있는 좌표계를 사용 하 려 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="6eabe-112">예를 들어, 클라이언트 영역의 왼쪽 가장자리에서 100 픽셀, 클라이언트 영역의 맨 위에 있는 50 픽셀을 기준으로 픽셀을 만들려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="6eabe-113">다음 그림에서는 이러한 좌표 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="6eabe-114">![좌표계](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="6eabe-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="6eabe-115">`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`호출 하는 경우 다음 그림에 표시 된 줄을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6eabe-116">![좌표계](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="6eabe-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="6eabe-117">세 좌표 공간의 선 끝점 좌표는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6eabe-118">World</span><span class="sxs-lookup"><span data-stu-id="6eabe-118">World</span></span>|<span data-ttu-id="6eabe-119">(0, 0) ~ (160, 80)</span><span class="sxs-lookup"><span data-stu-id="6eabe-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="6eabe-120">페이지</span><span class="sxs-lookup"><span data-stu-id="6eabe-120">Page</span></span>|<span data-ttu-id="6eabe-121">(100, 50) to (260, 130)</span><span class="sxs-lookup"><span data-stu-id="6eabe-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="6eabe-122">디바이스</span><span class="sxs-lookup"><span data-stu-id="6eabe-122">Device</span></span>|<span data-ttu-id="6eabe-123">(100, 50) to (260, 130)</span><span class="sxs-lookup"><span data-stu-id="6eabe-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="6eabe-124">페이지 좌표 공간의 원점은 클라이언트 영역의 왼쪽 위 모퉁이에 있습니다. 이는 항상입니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="6eabe-125">또한 측정 단위가 픽셀 이므로 장치 좌표는 페이지 좌표와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="6eabe-126">측정 단위를 픽셀 (예: 인치) 이외의 다른 항목으로 설정 하는 경우에는 장치 좌표가 페이지 좌표와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="6eabe-127">세계 좌표를 페이지 좌표로 매핑하는 세계 변환은 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.Transform%2A> 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="6eabe-128">앞의 예제에서 전 세계 변환은 x 방향으로 변환 100 단위이 고 y 방향으로 50 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="6eabe-129">다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 전역 변환을 설정한 다음 해당 <xref:System.Drawing.Graphics> 개체를 사용 하 여 앞의 그림에 표시 된 줄을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="6eabe-130">페이지 변환은 페이지 좌표를 장치 좌표로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="6eabe-131"><xref:System.Drawing.Graphics> 클래스는 페이지 변환을 조작 하기 위한 <xref:System.Drawing.Graphics.PageUnit%2A> 및 <xref:System.Drawing.Graphics.PageScale%2A> 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="6eabe-132"><xref:System.Drawing.Graphics> 클래스는 표시 장치의 가로 및 세로 dpi를 검사 하는 두 개의 읽기 전용 속성인 <xref:System.Drawing.Graphics.DpiX%2A> 및 <xref:System.Drawing.Graphics.DpiY%2A>도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="6eabe-133"><xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 사용 하 여 픽셀 이외의 측정 단위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eabe-134"><xref:System.Drawing.Graphics.PageUnit%2A> 속성을 <xref:System.Drawing.GraphicsUnit.World>로 설정할 수 없습니다 .이는 물리적 단위가 아니므로 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="6eabe-135">다음 예에서는 (0, 0)에서 (2, 1) 사이의 줄을 그립니다. 여기서 point (2, 1)는 오른쪽의 2 인치이 고 점 (0, 0)에서 1 인치가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="6eabe-136">펜을 생성할 때 펜 너비를 지정 하지 않으면 앞의 예제에서는 1 인치 너비의 줄을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="6eabe-137"><xref:System.Drawing.Pen> 생성자에 대 한 두 번째 인수에서 펜 너비를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="6eabe-138">디스플레이 장치에 가로 방향으로 96 dpi가 있고 세로 방향으로 96 점이 있는 경우 위의 예제에서 선의 끝점에는 세 좌표 공간에 다음 좌표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6eabe-139">World</span><span class="sxs-lookup"><span data-stu-id="6eabe-139">World</span></span>|<span data-ttu-id="6eabe-140">(0, 0)-(2, 1)</span><span class="sxs-lookup"><span data-stu-id="6eabe-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6eabe-141">페이지</span><span class="sxs-lookup"><span data-stu-id="6eabe-141">Page</span></span>|<span data-ttu-id="6eabe-142">(0, 0)-(2, 1)</span><span class="sxs-lookup"><span data-stu-id="6eabe-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6eabe-143">디바이스</span><span class="sxs-lookup"><span data-stu-id="6eabe-143">Device</span></span>|<span data-ttu-id="6eabe-144">(0, 0) ~ (192, 96)</span><span class="sxs-lookup"><span data-stu-id="6eabe-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="6eabe-145">세계 좌표 공간의 원점이 클라이언트 영역의 왼쪽 위 모퉁이에 있기 때문에 페이지 좌표는 세계 좌표와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="6eabe-146">전 세계와 페이지 변형을 결합 하 여 다양 한 효과를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="6eabe-147">예를 들어 인치를 측정 단위로 사용 하 고 좌표계의 원점을 클라이언트 영역의 왼쪽 가장자리에서 2 인치로, 클라이언트 영역의 위쪽에서 1/2 인치로 만들려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="6eabe-148">다음 예에서는 <xref:System.Drawing.Graphics> 개체의 전 세계 및 페이지 변환을 설정 하 고 (0, 0)에서 (2, 1)로 줄을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="6eabe-149">다음 그림에서는 선 및 좌표계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="6eabe-150">![좌표계](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="6eabe-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="6eabe-151">디스플레이 장치에 가로 방향으로 96 dpi가 있고 세로 방향으로 96 점이 있는 경우 위의 예제에서 선의 끝점에는 세 좌표 공간에 다음 좌표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eabe-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6eabe-152">World</span><span class="sxs-lookup"><span data-stu-id="6eabe-152">World</span></span>|<span data-ttu-id="6eabe-153">(0, 0)-(2, 1)</span><span class="sxs-lookup"><span data-stu-id="6eabe-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6eabe-154">페이지</span><span class="sxs-lookup"><span data-stu-id="6eabe-154">Page</span></span>|<span data-ttu-id="6eabe-155">(2, 0.5) ~ (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="6eabe-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="6eabe-156">디바이스</span><span class="sxs-lookup"><span data-stu-id="6eabe-156">Device</span></span>|<span data-ttu-id="6eabe-157">(192, 48) to (384, 144)</span><span class="sxs-lookup"><span data-stu-id="6eabe-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6eabe-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6eabe-158">See also</span></span>

- [<span data-ttu-id="6eabe-159">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="6eabe-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="6eabe-160">매트릭스에 의한 변형 표시</span><span class="sxs-lookup"><span data-stu-id="6eabe-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
