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
ms.openlocfilehash: a04465c31b160f97568ed88c434e7e3a5126ebb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975756"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="5ec18-102">방법: 경로 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="5ec18-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="5ec18-103"><xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스 점진적으로 색을 변경 하 여 셰이프를 입력 하는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="5ec18-104">예를 들어 경로의 센터에 대 한 한 가지 색 및 경로 경계에 다른 색을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="5ec18-105">또한 각 패스의 경계를 따라 여러 지점에 대 한 별도 색을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec18-106">GDI +에서 경로 선 및 곡선에서 유지 관리의 시퀀스를 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="5ec18-107">GDI + 경로 대 한 자세한 내용은 참조 하세요. [GDI +의 그래픽 경로](graphics-paths-in-gdi.md) 하 고 [Constructing 및 그리기 경로](constructing-and-drawing-paths.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="5ec18-108">이 문서의 예제에서는 컨트롤에서 호출 되는 메서드는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="5ec18-109">타원을 채우도록 경로 그라데이션</span><span class="sxs-lookup"><span data-stu-id="5ec18-109">To fill an ellipse with a path gradient</span></span>  
  
-   <span data-ttu-id="5ec18-110">다음 예제에서는 경로 그라데이션 브러시를 사용 하 여 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="5ec18-111">가운데 색은 파랑으로 설정 하 고 경계 색 바다색으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="5ec18-112">다음 그림은 채워진된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![그라데이션 경로 타원을 채웁니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="5ec18-114">기본적으로 경로 그라데이션 브러시를 경로의 경계 외부로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="5ec18-115">경로 그라데이션 브러시를 사용 하 여 경로 경계를 넘어 확장 하는 그림에 맞게 경로 외부 화면 영역의 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="5ec18-116">다음 그림에서는 변경 하는 경우 어떻게 되나요 합니다 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> 에 다음 코드에서 호출 `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span><span class="sxs-lookup"><span data-stu-id="5ec18-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![그라데이션 경로 경로 경계를 벗어나 확장입니다.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="5ec18-118">앞의 코드 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 합니다 <xref:System.Windows.Forms.PaintEventArgs> 매개 변수는 e의 <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5ec18-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="5ec18-119">경계에 요소를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="5ec18-119">To specify points on the boundary</span></span>  
  
-   <span data-ttu-id="5ec18-120">다음 예제에서는 별 모양 경로에서 경로 그라데이션 브러시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="5ec18-121">코드 집합을 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 빨간색 별모양의 중심에서 색을 설정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="5ec18-122">코드 설정 하 여는 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> 다양 한 색을 지정 하려면 속성 (에 저장 합니다 `colors` 배열) 개별 지점에는 `points` 배열.</span><span class="sxs-lookup"><span data-stu-id="5ec18-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="5ec18-123">코드의 마지막 문에서 경로 그라데이션 브러시를 사용 하 여 별 모양 경로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   <span data-ttu-id="5ec18-124">다음 예제에서는 그립니다 없이 경로 그라데이션을 <xref:System.Drawing.Drawing2D.GraphicsPath> 코드에서이 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="5ec18-125">특정 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> 예제의 생성자 점의 배열을 받지만 필요 하지 않습니다는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="5ec18-126">또한는 <xref:System.Drawing.Drawing2D.PathGradientBrush> 경로가 아닌 사각형을 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="5ec18-127">사각형은 사각형의 일부 브러시에 의해 칠하지 않습니다 있도록 브러시를 정의 하는 데 닫힌된 경로 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="5ec18-128">다음 그림에서는 사각형 (점선) 및 경로 그라데이션 브러시로 칠하는 사각형의 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span> 
  
     ![경로 그라데이션 브러시 그라데이션 부분입니다.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="5ec18-130">경로 그라데이션 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="5ec18-130">To customize a path gradient</span></span>  
  
-   <span data-ttu-id="5ec18-131">설정 하는 경로 그라데이션 브러시를 사용자 지정 하는 한 가지 방법은 해당 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="5ec18-132">기본 경로 내에 있는 내부 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="5ec18-133">가운데 색 어디에서 나 내부 경로의 대신 중심점에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="5ec18-134">다음 예제에서는 타원형 경로 기반 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="5ec18-135">코드 경계 색을 파란색를 설정 하 고, 가운데 색을 바다색으로 설정 하는 원형 경로 맞게 경로 그라데이션 브러시를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="5ec18-136">그런 다음 코드는 포커스 범위의 경로 그라데이션 브러시를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="5ec18-137">X 포커스 확장 0.3 집합과 y 포커스 확장 0.8로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="5ec18-138">호출을 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드를 <xref:System.Drawing.Graphics> 개체 있도록 후속 호출 <xref:System.Drawing.Graphics.FillPath%2A> 첫 번째 타원의 오른쪽에 있는 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="5ec18-139">포커스 눈금의 효과 보려면 주 타원을 중심을 공유 하는 작은 타원을 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="5ec18-140">작은 (내부) 타원은 주 타원 (가운데를 중심으로)까지 가로로 크기가 조정 0.3에서 세로로 0.8의 비율로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="5ec18-141">외부 타원의 경계에서 내부 타원의 경계를 이동 하면 색 변경 점진적으로 파랑에서을 바다색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="5ec18-142">공유 센터로 바다색 색 계속 내부 타원의 경계에서 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="5ec18-143">다음 그림에서는 다음 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="5ec18-144">왼쪽 타원 바다색 중심점에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="5ec18-145">오른쪽 타원 바다색 내부 경로 내 어디에서 나이입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![포커스 눈금의 그라데이션 효과](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="5ec18-147">보간을 사용 하 여 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="5ec18-147">To customize with interpolation</span></span>  
  
-   <span data-ttu-id="5ec18-148">경로 그라데이션 브러시를 사용자 지정 하는 또 다른 방법은 보간 색의 배열 및 보간 위치 배열을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="5ec18-149">다음 예제에서는 삼각형을 기반으로 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="5ec18-150">코드 집합을 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 보간 위치 (0, 0.25, 1)의 배열 및 보간 색 (진한 녹색, aqua, 파란색)의 배열을 지정 경로 그라데이션 브러시의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="5ec18-151">중심점에 삼각형의 경계에서 이동 하면 색 변경 점진적으로 진한 녹색 바다색 이동한 다음 바다색에서 파랑으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="5ec18-152">Aqua 진한 녹색 변경 진한 녹색에서 파란색 거리의 25%에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="5ec18-153">다음 그림에서는 사용자 지정 경로 그라데이션 브러시를 사용 하 여 채운 삼각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![사용자 지정 경로 그라데이션 브러시를 사용 하 여 삼각형이 채워집니다.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="5ec18-155">중심점을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5ec18-155">To set the center point</span></span>  
  
-   <span data-ttu-id="5ec18-156">기본적으로 경로 그라데이션 브러시의 중심점 브러시를 생성 하는 데 사용 되는 경로의 중심에는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="5ec18-157">설정 하 여 중심점의 위치를 변경할 수는 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 의 속성을 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="5ec18-158">다음 예제에서는 타원을 기반으로 경로 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="5ec18-159">타원의 중심에는 (70, 35) 되지만 경로 그라데이션 브러시의 중심점 설정 됩니다 (120, 40).</span><span class="sxs-lookup"><span data-stu-id="5ec18-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="5ec18-160">다음 그림은 채워진된 타원 및 경로 그라데이션 브러시의 중심점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![채워진 타원 및 센터 지점과 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
-   <span data-ttu-id="5ec18-162">경로 브러시를 생성 하는 데 사용 된 외부 위치 경로 그라데이션 브러시의 중심점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="5ec18-163">다음 예제에서는 대체 설정에 대 한 호출을 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 위의 코드에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="5ec18-164">다음 그림에서는이 변경으로 인해 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-164">The following illustration shows the output with this change:</span></span>  
  
     ![패스의 외부 영역 중심점을 사용 하 여 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="5ec18-166">앞의 그림에서 타원의 오른쪽 끝에 있는 점 없는 순수 파란색 (근접 하지만).</span><span class="sxs-lookup"><span data-stu-id="5ec18-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="5ec18-167">그라데이션의 색 채우기 색 (0, 0, 255) 순수 파란색 수 없는 지점 (145, 35)에 도달 하는 경우에 따라 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="5ec18-168">채우기에 도달 하지 않습니다 하지만 (145, 35) 해당 경로 내 에서만 경로 그라데이션 브러시를 그리는 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ec18-169">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5ec18-169">Compiling the Code</span></span>  
 <span data-ttu-id="5ec18-170">앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요할 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec18-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec18-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ec18-171">See also</span></span>

- [<span data-ttu-id="5ec18-172">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="5ec18-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
