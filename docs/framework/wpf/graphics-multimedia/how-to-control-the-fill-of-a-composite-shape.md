---
title: '방법: 복합 도형의 채우기 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 89f69d392e8838af99538c759a2f06453e1bcd60
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855905"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a><span data-ttu-id="15998-102">방법: 복합 도형의 채우기 제어</span><span class="sxs-lookup"><span data-stu-id="15998-102">How to: Control the Fill of a Composite Shape</span></span>

<span data-ttu-id="15998-103">또는<xref:System.Windows.Media.GeometryGroup> 의속성<xref:System.Windows.Media.GeometryGroup.FillRule%2A> 은 복합 셰이프가 지정 된 점이 기 하 도형의 일부 인지 여부를 확인 하는 데 사용 하는 "규칙"을 지정 합니다. <xref:System.Windows.Media.PathGeometry></span><span class="sxs-lookup"><span data-stu-id="15998-103">The <xref:System.Windows.Media.GeometryGroup.FillRule%2A> property of a <xref:System.Windows.Media.GeometryGroup> or a <xref:System.Windows.Media.PathGeometry>, specifies a "rule" which the composite shape uses to determine whether a given point is part of the geometry.</span></span> <span data-ttu-id="15998-104">에는 <xref:System.Windows.Media.FillRule> <xref:System.Windows.Media.FillRule.EvenOdd> 및 의두가지값을사용할수있습니다.<xref:System.Windows.Media.FillRule.Nonzero></span><span class="sxs-lookup"><span data-stu-id="15998-104">There are two possible values for <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> and <xref:System.Windows.Media.FillRule.Nonzero>.</span></span> <span data-ttu-id="15998-105">다음 섹션에서는 이러한 두 가지 규칙을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15998-105">The following sections will describe how to use these two rules.</span></span>

<span data-ttu-id="15998-106">**EvenOdd:** 이 규칙은 해당 점에서 모든 방향으로 무한대로 광선을 그리고 광선이 교차 하는 지정 된 도형 내에서 경로 세그먼트 수를 계산 하 여 채우기 영역에 점이 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15998-106">**EvenOdd:** This rule determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction and counting the number of path segments within the given shape that the ray crosses.</span></span> <span data-ttu-id="15998-107">이 숫자가 홀수이면 점이 안에 있고, 짝수이면 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-107">If this number is odd, the point is inside; if even, the point is outside.</span></span>

<span data-ttu-id="15998-108">예를 들어 아래 XAML은가 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 로 <xref:System.Windows.Media.FillRule.EvenOdd>설정 된 일련의 동심 링 (대상)으로 구성 된 복합 셰이프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15998-108">For example, the XAML below creates a composite shape made up of a series of concentric rings (target) with a <xref:System.Windows.Media.GeometryGroup.FillRule%2A> set to <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

<span data-ttu-id="15998-109">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15998-109">The following illustration shows the shape created in the previous example.</span></span>

![교대로 반복 되는 색을 사용 하는 계열 동심 링으로 구성 된 원입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

<span data-ttu-id="15998-111">위의 그림에서 중심과 세 번째 링은 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-111">In the previous illustration, notice that the center and third ring are not filled.</span></span> <span data-ttu-id="15998-112">두 링 중 하나에 있는 점에서 그린 광선이 짝수의 세그먼트를 통과하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="15998-112">This is because a ray drawn from any point within either of those two rings passes through an even number of segments.</span></span> <span data-ttu-id="15998-113">다음 그림을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15998-113">See the following illustration:</span></span>

![원에 그려진 EvenOdd 광선을 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

<span data-ttu-id="15998-115">**0이 아닌** 이 규칙은 해당 점에서 모든 방향으로 무한대로 광선을 그린 다음 도형의 세그먼트가 광선과 교차 하는 위치를 검사 하 여 경로의 채우기 영역에 점이 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15998-115">**NonZero:** This rule determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction and then examining the places where a segment of the shape crosses the ray.</span></span> <span data-ttu-id="15998-116">0부터 시작하여 세그먼트가 왼쪽에서 오른쪽으로 광선과 교차할 때마다 1을 추가하고 경로 세그먼트가 오른쪽에서 왼쪽으로 광선과 교차할 때마다 1을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="15998-116">Starting with a count of zero, add one each time a Segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left.</span></span> <span data-ttu-id="15998-117">교차 수를 계산한 후 결과가 0이면 점이 경로의 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-117">After counting the crossings, if the result is zero then the point is outside the path.</span></span> <span data-ttu-id="15998-118">그렇지 않으면 점이 내부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-118">Otherwise, it is inside.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

<span data-ttu-id="15998-119">이전 예제를 사용 하는 경우 <xref:System.Windows.Media.FillRule.Nonzero> 에 대 한 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 값은 다음 그림을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15998-119">Using the previous example, a value of <xref:System.Windows.Media.FillRule.Nonzero> for <xref:System.Windows.Media.GeometryGroup.FillRule%2A> gives the following illustration as a result:</span></span>

![계열 동심 링으로 구성 된 원은 모두 동일한 색으로 채워집니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

<span data-ttu-id="15998-121">여기에서 볼 수 있듯이 모든 링이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15998-121">As you can see, all the rings are filled.</span></span> <span data-ttu-id="15998-122">모든 세그먼트가 같은 방향으로 실행되므로 임의 점에서 그린 광선이 하나 이상의 세그먼트와 교차하고 교차의 합계가 0이 아니기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="15998-122">This is because all the segments are running in the same direction and so a ray drawn from any point will cross one or more segments and the sum of the crossings will not equal zero.</span></span> <span data-ttu-id="15998-123">예를 들어 다음 그림에서 빨간색 화살표는 세그먼트가 그려지는 방향을 나타내고 흰색 화살표는 가장 안쪽 링의 지점에서 실행 되는 임의의 광선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15998-123">For example, in the following illustration, the red arrows represent the direction the segments are drawn and the white arrow represents an arbitrary ray running from a point in the innermost ring.</span></span> <span data-ttu-id="15998-124">광선이 교차하는 각 세그먼트에 대해 0 값부터 시작할 경우 세그먼트가 왼쪽에서 오른쪽으로 광선과 교차하므로 1이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="15998-124">Starting with a value of zero, for each segment that the ray crosses, a value of one is added because the segment crosses the ray from left to right.</span></span>

![0이 아닌 값과 같은 FillRule 속성 값을 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

<span data-ttu-id="15998-126">규칙의 <xref:System.Windows.Media.FillRule.Nonzero> 동작을 더 잘 보여 주기 위해 다른 방향으로 실행 되는 세그먼트가 있는 보다 복잡 한 모양이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="15998-126">To better demonstrate the behavior of <xref:System.Windows.Media.FillRule.Nonzero> rule a more complex shape with segments running in different directions is required.</span></span> <span data-ttu-id="15998-127">아래 XAML 코드는 앞의 예제와 비슷한 모양의 도형을 만듭니다. 단,이는를 사용 <xref:System.Windows.Media.PathGeometry> 하 여 만든 <xref:System.Windows.Media.EllipseGeometry> 다음이를 사용 하 여 네 개의 동심 원호를 만든 다음이를 사용 하 여 완전히 폐쇄형 동심 원을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15998-127">The XAML code below creates a similar shape as the previous example except that it is created with a <xref:System.Windows.Media.PathGeometry> rather then a <xref:System.Windows.Media.EllipseGeometry> which creates four concentric arcs rather then fully closed concentric circles.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

<span data-ttu-id="15998-128">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15998-128">The following illustration shows the shape created in the previous example.</span></span>

![세 번째 호를 채우지 않고 교대로 반복 되는 색을 사용 하는 계열 동심 링으로 구성 된 원입니다.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

<span data-ttu-id="15998-130">중심에서 세 번째 호까지는 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-130">Notice that the third arc from the center is not filled.</span></span> <span data-ttu-id="15998-131">다음 그림에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15998-131">The following illustration shows why this is.</span></span> <span data-ttu-id="15998-132">이 그림에서 빨간색 화살표는 세그먼트가 그려진 방향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15998-132">In the illustration, the red arrows represent the direction the segments are drawn.</span></span> <span data-ttu-id="15998-133">두 개의 흰색 화살표는 “채워지지 않은” 영역의 점에서 외부로 이동되는 2개의 임의 광선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15998-133">The two white arrows represent two arbitrary rays that move out from a point in the "non-filled" region.</span></span> <span data-ttu-id="15998-134">이 그림에서 볼 수 있듯이 해당 경로에서 세그먼트를 교차하는 지정된 광선의 값 합계는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="15998-134">As can be seen from the illustration, the sum of the values from a given ray crossing the segments in its path is zero.</span></span> <span data-ttu-id="15998-135">앞에서 정의한 대로 합계가 0이 *아닌* 경우는 해당 점이 형상에 속하는 것을 의미하지만 합계가 0이라는 사실은 해당 점이 형상에 속하지 않음을 의미합니다(채우기의 일부가 아님).</span><span class="sxs-lookup"><span data-stu-id="15998-135">As defined above, a sum of zero means that the point is not part of the geometry (not part of the fill) while a sum that is *not* zero, including a negative value, is part of the geometry.</span></span>

![세그먼트를 교차 하는 임의의 광선을 보여 주는 다이어그램](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> <span data-ttu-id="15998-137">의 <xref:System.Windows.Media.FillRule>목적을 위해 모든 셰이프는 닫힌 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15998-137">For the purposes of <xref:System.Windows.Media.FillRule>, all shapes are considered closed.</span></span> <span data-ttu-id="15998-138">세그먼트에 틈이 있으면 가상선을 그려 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-138">If there is a gap in a segment, draw an imaginary line to close it.</span></span> <span data-ttu-id="15998-139">위의 예제에서는 링에 작은 틈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-139">In the example above, there are small gaps in the rings.</span></span> <span data-ttu-id="15998-140">이점을 고려할 때 이러한 틈을 지나가는 광선이 다른 결과를 가져와 광선이 다른 방향으로 진행될 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15998-140">Given this, one might expect a ray that runs through the gap to give a different result then a ray running in another direction.</span></span> <span data-ttu-id="15998-141">다음은 이러한 간격과 "허수 세그먼트" (를 <xref:System.Windows.Media.FillRule>적용 하기 위해 그려진 세그먼트) 중 하나를 닫는 확대 된 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="15998-141">Below is an enlarged illustration of one of these gaps and the "imaginary segment" (segment that is drawn for purposes of applying the <xref:System.Windows.Media.FillRule>) that closes it.</span></span>

![항상 닫혀 있는 FillRule 세그먼트를 보여 주는 다이어그램](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a><span data-ttu-id="15998-143">예제</span><span class="sxs-lookup"><span data-stu-id="15998-143">Example</span></span>

## <a name="see-also"></a><span data-ttu-id="15998-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="15998-144">See also</span></span>

- [<span data-ttu-id="15998-145">복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="15998-145">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="15998-146">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="15998-146">Geometry Overview</span></span>](geometry-overview.md)
