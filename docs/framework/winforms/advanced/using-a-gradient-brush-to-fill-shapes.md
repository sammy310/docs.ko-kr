---
title: 그라데이션 브러시를 사용하여 도형 채우기
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954466"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="de446-102">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="de446-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="de446-103">그라데이션 브러시 효과 사용 하 여 도형 채우기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de446-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="de446-104">예를 들어, 오른쪽 가장자리에 모양의 왼쪽된 가장자리에서 이동 하면 점진적으로 변경 하는 색으로 모양을 채울 가로 그라데이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de446-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="de446-105">사각형 왼쪽된 가장자리는 검정을 사용 하 여 imagine (0, 0, 0 빨강, 녹색 및 파랑 구성 요소에 의해 표현 됨) 및 오른쪽 가장자리 빨강 (255, 0, 0)입니다.</span><span class="sxs-lookup"><span data-stu-id="de446-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="de446-106">256 픽셀 사각형의 면이 지정 된 픽셀의 빨강 구성 요소는 왼쪽에 있는 픽셀의 빨강 구성 요소 보다 큰 하나가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de446-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="de446-107">행에서 가장 왼쪽 픽셀의 색 구성 요소 (0, 0, 0), 두 번째 픽셀 (1, 0, 0)에 세 번째 픽셀 (2, 0, 0)에 등에 오른쪽에 있는 픽셀의 색 구성 요소 (255, 0, 0)에 도달할 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="de446-108">이러한 방식된으로 색 값 색 그라데이션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="de446-109">가로, 세로 이동 하거나 지정된 된 기울어진된 줄으로 병렬 선형 그라데이션 색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="de446-110">내부 및 경로 경계에 대 한 이동 경로 그라데이션 색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="de446-111">경로 그라데이션 다양 한 효과 달성 하기 위해 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de446-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="de446-112">다음 그림에서는 선형 그라데이션 브러시를 사용 하 여 채워진 사각형 및 타원 경로 그라데이션 브러시를 사용 하 여 입력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de446-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="de446-113">![Gradient](./media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="de446-113">![Gradient](./media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de446-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="de446-114">In This Section</span></span>  
 [<span data-ttu-id="de446-115">방법: 선형 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="de446-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="de446-116">선형 그라데이션을 만드는 방법을 보여 줍니다는 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="de446-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="de446-117">방법: 경로 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="de446-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="de446-118">사용 하 여 경로 그라데이션 하는 방법에 설명 합니다 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="de446-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="de446-119">방법: 그라데이션에 감마 보정 적용</span><span class="sxs-lookup"><span data-stu-id="de446-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="de446-120">그라데이션 브러시를 사용 하 여 감마 보정을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="de446-121">참조</span><span class="sxs-lookup"><span data-stu-id="de446-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="de446-122">이 클래스에 대 한 설명을 포함 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="de446-123">이 클래스에 대 한 설명을 포함 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="de446-123">Contains a description of this class and has links to all of its members.</span></span>
