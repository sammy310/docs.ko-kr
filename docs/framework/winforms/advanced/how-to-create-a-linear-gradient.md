---
title: '방법: 선형 그라데이션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e47707d040cd7bf67008fab33ac482706963ce39
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725248"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="3482e-102">방법: 선형 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="3482e-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3482e-103">가로, 세로 및 대각선 선형 그라데이션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="3482e-104">기본적으로 선형 그라데이션에 색이 균일 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="3482e-105">그러나 균일 하지 않은 방식으로 색이 변경 되도록 선형 그라데이션을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="3482e-106">다음 예제에서는 선, 타원, 및 가로 선형 그라데이션 브러시를 사용 하 여 사각형을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="3482e-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자는 네 개의 인수를 받습니다: 두 색으로 및 두 점입니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="3482e-108">첫 번째 지점 (0, 10) 첫 번째 색 (빨강)에 연결 되며 두 번째 점 (200, 10)는 두 번째 색 (파란색)를 사용 하 여 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="3482e-109">예상한 대로에서 가져온 줄 (0, 10)를 (200, 10) 빨간색에서 파란색 점진적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="3482e-110">점 (50, 10) 및 (200, 10)에서 10 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="3482e-111">두 점 동일한 두 번째 좌표에는 중요 한 것-연결 선은 가로입니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="3482e-112">타원 및 사각형 변경할 수도 점진적으로 빨간색에서 가로 좌표 이동 0에서 200으로 파란색입니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="3482e-113">다음 그림은 선, 타원 및 사각형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="3482e-114">참고는 색 그라데이션 반복 하는 가로 좌표는 200 개 이상 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="3482e-115">![선형 그라데이션](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="3482e-115">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="3482e-116">가로 선형 그라데이션 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="3482e-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="3482e-117">불투명 한 빨강 및 불투명 파란색 세 번째와 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="3482e-118">앞의 예제에서 200에서 가로 좌표 0 가로 좌표에서 이동 색 구성 요소 선형적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="3482e-119">예를 들어, 첫 번째 좌표가 0과 200 사이의 중간 지점 0과 255 사이의 중간에 있는 파란색 구성 요소를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3482e-120">이 기능을 사용 하면 다른 색이 변하는 그라데이션의 한쪽 가장자리에서 방식을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="3482e-121">검정에서 다음 표에 따라 빨강으로 변경 하는 그라데이션 브러시를 만들려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="3482e-122">가로 좌표</span><span class="sxs-lookup"><span data-stu-id="3482e-122">Horizontal coordinate</span></span>|<span data-ttu-id="3482e-123">RGB 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3482e-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="3482e-124">0</span><span class="sxs-lookup"><span data-stu-id="3482e-124">0</span></span>|<span data-ttu-id="3482e-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="3482e-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="3482e-126">40</span><span class="sxs-lookup"><span data-stu-id="3482e-126">40</span></span>|<span data-ttu-id="3482e-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="3482e-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="3482e-128">200</span><span class="sxs-lookup"><span data-stu-id="3482e-128">200</span></span>|<span data-ttu-id="3482e-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="3482e-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="3482e-130">빨강 구성 요소는 농도가 절반 경우 가로 좌표는 0에서 방법 200의 20%만 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="3482e-131">다음 예제에서는 합니다 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> 의 속성을 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 세 상대 강도 세 가지 상대 위치를 사용 하 여 연결할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="3482e-132">앞의 표에서 같이 0.5의 상대 강도 0.2의 상대적 위치와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="3482e-133">그라데이션 브러시를 사용 하 여 사각형 및 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="3482e-134">다음 그림에서는 결과 타원 및 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="3482e-135">![선형 그라데이션](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="3482e-135">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="3482e-136">선형 그라데이션 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="3482e-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="3482e-137">불투명 한 검정 픽셀과 불투명 한 빨강의 세 번째 및 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="3482e-138">이전 예제의 그라데이션 가로; 되었습니다. 즉, 색 가로 줄에 따라 점진적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="3482e-139">세로 그라데이션 및 대각선 그라데이션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="3482e-140">에 점 (0, 0) 및 (200, 100)를 전달 하는 다음 예제는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="3482e-141">파란색 연관 된 (0, 0)와 연결 되는 녹색 (200, 100).</span><span class="sxs-lookup"><span data-stu-id="3482e-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="3482e-142">(펜 굵기 10)이 있는 선 및 타원 선형 그라데이션 브러시를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="3482e-143">다음 그림에서는 줄 및 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="3482e-144">참고는 타원 변경에서 색 점진적으로 하나를 따라 이동 하면 줄을 통과 하는 줄에 병렬 되 (0, 0) 및 (200, 100).</span><span class="sxs-lookup"><span data-stu-id="3482e-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="3482e-145">![선형 그라데이션](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="3482e-145">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="3482e-146">대각선 선형 그라데이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3482e-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="3482e-147">불투명 파란색 픽셀과 불투명 한 녹색 세 번째와 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="3482e-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="3482e-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="3482e-148">See also</span></span>
- [<span data-ttu-id="3482e-149">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="3482e-149">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="3482e-150">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="3482e-150">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
