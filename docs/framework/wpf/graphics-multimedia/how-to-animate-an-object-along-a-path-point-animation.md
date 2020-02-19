---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452898"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="449c2-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="449c2-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="449c2-103">이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 개체를 사용 하 여 곡선 경로를 따라 <xref:System.Windows.Point>에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="449c2-104">예제</span><span class="sxs-lookup"><span data-stu-id="449c2-104">Example</span></span>  
 <span data-ttu-id="449c2-105">다음 예에서는 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 <xref:System.Windows.Media.EllipseGeometry>를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="449c2-106"><xref:System.Windows.Point> 값을 사용 하는 타원 기 하 도형의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성은 해당 위치를 지정 합니다. 타원 기 하 도형을 이동 하려면 해당 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="449c2-107">이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath>를 사용 하 여 <xref:System.Windows.Media.EllipseGeometry> 개체의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="449c2-108">전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="449c2-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="449c2-109">이전 샘플의 코드 버전은 하나의 애니메이션만 적용 된 경우에도 <xref:System.Windows.Media.EllipseGeometry>에 애니메이션 효과를 주기 위해 <xref:System.Windows.Media.Animation.Storyboard>를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="449c2-110"><xref:System.Windows.Media.Animation.Storyboard>는 동일한 <xref:System.Windows.Media.Animation.Storyboard>에 의해 제어 될 수 있으므로 여러 애니메이션을 적용 하는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="449c2-111">그러나 코드를 사용할 때 속성에 단일 애니메이션을 적용 하는 보다 쉬운 방법은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="449c2-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="449c2-112">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="449c2-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="449c2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="449c2-113">See also</span></span>

- [<span data-ttu-id="449c2-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="449c2-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="449c2-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="449c2-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="449c2-116">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="449c2-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
