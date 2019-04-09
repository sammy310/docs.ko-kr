---
title: 선과 곡선의 앤티 앨리어싱
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078500"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="663b0-102">선과 곡선의 앤티 앨리어싱</span><span class="sxs-lookup"><span data-stu-id="663b0-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="663b0-103">사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선을 그릴 시작 지점 및 끝 줄의 지점 제공 되지만 줄에 각 픽셀에 대 한 정보를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="663b0-104">특정 디스플레이 장치에 선을 표시 하려면 어떤 픽셀이 켜 집니다 결정할 디스플레이 드라이버 소프트웨어와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="663b0-105">별칭 지정</span><span class="sxs-lookup"><span data-stu-id="663b0-105">Aliasing</span></span>  
 <span data-ttu-id="663b0-106">바로 빨간색 선이 (4, 2) 지점에서 점 (16, 10)으로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="663b0-107">좌표 시스템의 왼쪽 위 모퉁이에 원점 및 측정 단위는 픽셀을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="663b0-108">또한 해당 x 축 지점 y 축 지점과 오른쪽 아래로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="663b0-109">다음 그림에서는 컬러 배경에 그려진 빨간색 선은의 확대 된 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="663b0-110">![선, 앤티 앨리어싱](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="663b0-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="663b0-111">선을 렌더링 하는 데 빨간색 픽셀은 불투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="663b0-112">줄에서 부분적으로 투명 한 픽셀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="663b0-113">이 유형의 선 렌더링을 사용 하면 선이 가변된 모양 및 약간 계단 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="663b0-114">이 기술은 계단식으로 선을 나타내는 별칭; 라고 합니다. 계단은 이론적인 선의 대 한 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="663b0-115">앤티 앨리어싱</span><span class="sxs-lookup"><span data-stu-id="663b0-115">Antialiasing</span></span>  
 <span data-ttu-id="663b0-116">줄을 렌더링 하기 위한 보다 복잡 한 기술에서는 부분적으로 투명 한 픽셀 불투명 한 픽셀와 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="663b0-117">픽셀 순수 빨강으로 설정 됩니다 또는 레드 팀 및 배경색을 혼합 하려면 정도 따라 줄으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="663b0-118">이러한 유형의 렌더링 앤티 앨리어싱 라고 및 사람의 눈에 게 더 부드러운 줄에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="663b0-119">다음 그림에서는 특정 픽셀 앤티 앨리어싱 선을 위해 배경색과 혼합 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="663b0-120">![선 앤티 앨리어싱](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="663b0-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="663b0-121">앤티 앨리어싱, 다듬기, 라고도 곡선에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="663b0-122">다음 그림에서는 평활된 타원의 확대 된 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="663b0-123">![곡선 앤티 앨리어싱](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="663b0-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="663b0-124">다음 그림에서는 실제 크기에 한 번 앤티 앨리어싱 앤티 앨리어싱 없이 한 번에 동일한 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="663b0-125">![앤티 앨리어싱 예](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="663b0-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="663b0-126">앤티 앨리어싱을 사용 하는 선과 곡선을 그릴의 인스턴스를 만듭니다는 <xref:System.Drawing.Graphics> 클래스 설정 및 해당 <xref:System.Drawing.Graphics.SmoothingMode%2A> 속성을 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 또는 <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>합니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="663b0-127">다음 중 하나를 호출 하는 그리기 메서드 같은 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="663b0-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="663b0-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="663b0-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="663b0-129">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="663b0-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="663b0-130">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="663b0-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
