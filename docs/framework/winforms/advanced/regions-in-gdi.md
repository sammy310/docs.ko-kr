---
title: GDI+의 영역
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076031"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="6d625-102">GDI+의 영역</span><span class="sxs-lookup"><span data-stu-id="6d625-102">Regions in GDI+</span></span>
<span data-ttu-id="6d625-103">영역은 출력 장치의 표시 영역의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="6d625-104">지역 (단일 사각형) 단순 또는 복합 (다각형 및 닫힌된 곡선의 조합) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="6d625-105">다음 그림에서는 두 지역: 사각형에서 생성 된 하나 및 다른 경로에서 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="6d625-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="6d625-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="6d625-107">영역 사용</span><span class="sxs-lookup"><span data-stu-id="6d625-107">Using Regions</span></span>  
 <span data-ttu-id="6d625-108">지역은 클리핑에 주로 사용 됩니다 및 적중 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="6d625-109">클리핑은의 표시 영역을 업데이트 해야 하는 부분에 일반적으로 특정 지역에 대 한 그리기를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="6d625-110">적중 테스트는 마우스 단추를 누르면 화면의 특정 지역의 커서 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="6d625-111">사각형 또는 경로에서 영역을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="6d625-112">또한 기존 영역을 결합 하 여 복잡 한 영역을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="6d625-113">합니다 <xref:System.Drawing.Region> 영역을 결합 하는 데 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>를 <xref:System.Drawing.Region.Exclude%2A>, 및 <xref:System.Drawing.Region.Complement%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="6d625-114">두 개의 지역 교집합 두 지역 모두에 속하는 모든 점의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="6d625-115">공용 구조체에는 하나 또는 다른 또는 두 지역 모두에 속하는 모든 데이터 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="6d625-116">지역의 보수는 지역에 있지 않은 모든 데이터 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="6d625-117">다음 그림에서는 교차와 앞의 그림에 표시 된 두 개의 지역의 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="6d625-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="6d625-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="6d625-119"><xref:System.Drawing.Region.Xor%2A> 메서드를 지역 쌍에 적용 한 지역 또는 다른 하지만 둘 다에 속하는 모든 요소를 포함 하는 영역의 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="6d625-120"><xref:System.Drawing.Region.Exclude%2A> 지역 쌍에 적용 하는 메서드를 두 번째 지역에 있지 않은 첫 번째 지역에서 모든 요소를 포함 하는 영역의 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="6d625-121">다음 그림에서는 적용에서 발생 하는 지역이 표시 합니다 <xref:System.Drawing.Region.Xor%2A> 및 <xref:System.Drawing.Region.Exclude%2A> 이 항목의 시작 부분에 표시 된 두 개의 지역 메서드.</span><span class="sxs-lookup"><span data-stu-id="6d625-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="6d625-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="6d625-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="6d625-123">영역을 채울 필요는 <xref:System.Drawing.Graphics> 개체를 <xref:System.Drawing.Brush> 개체 및 <xref:System.Drawing.Region> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="6d625-124"><xref:System.Drawing.Graphics> 개체를 제공 합니다 <xref:System.Drawing.Graphics.FillRegion%2A> 메서드 및 <xref:System.Drawing.Brush> 채우기 색 또는 패턴 등의 특성을 저장 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="6d625-125">다음 예제에서는 단색으로 영역을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6d625-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="6d625-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="6d625-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="6d625-127">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="6d625-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="6d625-128">영역 사용</span><span class="sxs-lookup"><span data-stu-id="6d625-128">Using Regions</span></span>](using-regions.md)
