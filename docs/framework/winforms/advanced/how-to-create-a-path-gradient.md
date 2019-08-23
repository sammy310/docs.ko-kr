---
title: '방법: 경로 그라데이션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964412"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="abb97-102">방법: 경로 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="abb97-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="abb97-103">클래스 <xref:System.Drawing.Drawing2D.PathGradientBrush> 를 사용 하 여 점차적으로 색을 변경 하는 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="abb97-104">예를 들어 경로의 중앙에 대해 한 색을 지정 하 고 경로의 경계에 대해 다른 색을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="abb97-105">경로의 경계를 따라 여러 점에 대해 별도의 색을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abb97-106">Gdi +에서 경로는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에 의해 유지 관리 되는 선 및 곡선의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="abb97-107">GDI + 경로에 대 한 자세한 내용은 [GDI +의 그래픽 경로](graphics-paths-in-gdi.md) 및 [생성 및 그리기 경로](constructing-and-drawing-paths.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abb97-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="abb97-108">이 문서의 예제는 컨트롤의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에서 호출 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="abb97-109">경로 그라데이션을 사용 하 여 타원을 채우려면</span><span class="sxs-lookup"><span data-stu-id="abb97-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="abb97-110">다음 예제에서는 타원을 경로 그라데이션 브러시로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="abb97-111">가운데 색이 파란색으로 설정 되 고 경계 색이 바다색으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="abb97-112">다음 그림에서는 채워진 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![그라데이션 패스가 타원을 채웁니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="abb97-114">기본적으로 경로 그라데이션 브러시는 경로 경계 밖으로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="abb97-115">경로 그라데이션 브러시를 사용 하 여 경로의 경계를 벗어나 확장 되는 그림을 채울 경우 경로 밖의 화면 영역이 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="abb97-116">다음 그림에서는에 대 한 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> 호출을 다음 코드로 변경 하는 경우 발생 하는 상황을 `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![경로 경계를 벗어나 확장 된 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="abb97-118">위의 코드 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며의 <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.PaintEventHandler>매개 변수인 e가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="abb97-119">경계에서 점에 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="abb97-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="abb97-120">다음 예제에서는 별 모양 패스에서 경로 그라데이션 브러시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="abb97-121">이 코드는 별 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 중심의 색을 빨강으로 설정 하는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="abb97-122">그런 다음 코드는 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> `points` 배열의 개별 지점에서 속성을 설정 하 여 `colors` 배열에 저장 된 다양 한 색을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="abb97-123">최종 코드 문은 별 모양 경로를 경로 그라데이션 브러시로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="abb97-124">다음 예제에서는 코드에 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체 없이 경로 그라데이션을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="abb97-125">예제의 특정 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> 생성자는 점의 배열을 받지만 개체는 <xref:System.Drawing.Drawing2D.GraphicsPath> 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="abb97-126">또한는 <xref:System.Drawing.Drawing2D.PathGradientBrush> 경로가 아닌 사각형을 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="abb97-127">사각형은 브러시를 정의 하는 데 사용 된 닫힌 경로 보다 크므로 브러시에 의해 사각형이 그려지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="abb97-128">다음 그림은 사각형 (점선) 및 경로 그라데이션 브러시로 그린 사각형의 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span> 
  
     ![경로 그라데이션 브러시로 칠하는 그라데이션 부분입니다.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="abb97-130">경로 그라데이션을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="abb97-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="abb97-131">경로 그라데이션 브러시를 사용자 지정 하는 한 가지 방법은 해당 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 속성을 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="abb97-132">포커스 배율이 주 경로 내에 있는 내부 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="abb97-133">가운데 색은 중심점 뿐만 아니라 내부 경로 내부에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="abb97-134">다음 예제에서는 타원형 경로를 기반으로 하는 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="abb97-135">이 코드는 경계 색을 파랑으로 설정 하 고 가운데 색을 바다색으로 설정한 다음 경로 그라데이션 브러시를 사용 하 여 타원형 경로를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="abb97-136">그런 다음 코드는 경로 그라데이션 브러시의 포커스 배율을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="abb97-137">X 포커스 눈금은 0.3로 설정 되 고 y 포커스 눈금은 0.8로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="abb97-138">이 코드는에 <xref:System.Drawing.Graphics.TranslateTransform%2A> 대 <xref:System.Drawing.Graphics.FillPath%2A> 한 후속 <xref:System.Drawing.Graphics> 호출에서 첫 번째 타원의 오른쪽에 있는 타원을 채우도록 개체의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="abb97-139">포커스 눈금의 효과를 확인 하려면 주 타원과 중심을 공유 하는 작은 타원이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="abb97-140">작은 (내부) 타원은 0.3의 요소를 기준으로 세로 방향으로 조정 된 주 타원 (가운데 정보) 이며, 0.8의 경우 세로로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="abb97-141">외부 타원의 경계에서 안쪽 타원의 경계로 이동할 때 색은 파란색에서 바다색으로 점차 변합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="abb97-142">내부 타원의 경계에서 공유 가운데로 이동할 때 색은 바다색으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="abb97-143">다음 그림에서는 다음 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="abb97-144">왼쪽의 타원은 중심점 에서만 바다색입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="abb97-145">오른쪽의 타원은 내부 경로 내에서 바다색입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![포커스 눈금의 그라데이션 효과](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="abb97-147">보간을 사용 하 여 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="abb97-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="abb97-148">경로 그라데이션 브러시를 사용자 지정 하는 또 다른 방법은 보간 색 배열과 보간 위치의 배열을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="abb97-149">다음 예제에서는 삼각형을 기반으로 하는 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="abb97-150">이 코드는 경로 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 그라데이션 브러시의 속성을 설정 하 여 보간 색의 배열 (진한 녹색, 바다색, 파랑) 및 보간 위치 배열 (0, 0.25, 1)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="abb97-151">삼각형의 경계에서 중심점으로 이동 하면 색이 진한 녹색에서 바다색으로 점진적으로 변경 된 다음 바다색에서 파랑으로 변합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="abb97-152">진한 녹색에서 바다색으로 변경 하는 경우에는 진한 녹색에서 파랑으로의 25%가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="abb97-153">다음 그림은 사용자 지정 경로 그라데이션 브러시로 채워진 삼각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![사용자 지정 경로 그라데이션 브러시로 채운 삼각형입니다.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="abb97-155">중심점을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="abb97-155">To set the center point</span></span>  
  
- <span data-ttu-id="abb97-156">기본적으로 경로 그라데이션 브러시의 중심점은 브러시를 생성 하는 데 사용 되는 경로의 중심에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="abb97-157">클래스의 속성을 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 설정 하 여 중심점의 위치를 변경할 수 있습니다. <xref:System.Drawing.Drawing2D.PathGradientBrush></span><span class="sxs-lookup"><span data-stu-id="abb97-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="abb97-158">다음 예제에서는 타원을 기반으로 하는 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="abb97-159">타원의 중심은 (70, 35)에 있지만 경로 그라데이션 브러시의 중심점은 (120, 40)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="abb97-160">다음 그림에서는 채워진 타원과 경로 그라데이션 브러시의 중심점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![채워진 타원과 중심점을 사용 하는 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="abb97-162">패스 그라데이션 브러시의 중심점을 브러시를 생성 하는 데 사용 된 경로 외부의 위치로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="abb97-163">다음 예제에서는 위의 코드에서 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 속성을 설정 하는 호출을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="abb97-164">다음 그림에서는 이러한 변경 내용의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-164">The following illustration shows the output with this change:</span></span>  
  
     ![중심점을 경로 외부에 있는 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="abb97-166">위의 그림에서 타원의 맨 오른쪽에 있는 점은 매우 가까이 있지만 순수한 파랑은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="abb97-167">그라데이션의 색은 채우기가 순수한 파란색 (0, 0, 255) 인 점 (145, 35)에 도달 하는 것 처럼 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="abb97-168">그러나 경로 그라데이션 브러시는 해당 경로 내부에만 그리기 때문에 채우기는 (145, 35)에 도달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abb97-169">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="abb97-169">Compiling the Code</span></span>  
 <span data-ttu-id="abb97-170">위의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인가 필요 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="abb97-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb97-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="abb97-171">See also</span></span>

- [<span data-ttu-id="abb97-172">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="abb97-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
