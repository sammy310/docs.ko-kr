---
title: '방법: 대화형 시계 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186591"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="d10d7-102">방법: 대화형 시계 제어</span><span class="sxs-lookup"><span data-stu-id="d10d7-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="d10d7-103">A <xref:System.Windows.Media.Animation.Clock> 개체의 <xref:System.Windows.Media.Animation.ClockController> 속성을 사용 하면 대화형으로 시작, 일시 중지, 다시 시작, 검색, 채우기 기간이 시계를 이동 하 고 시계를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="d10d7-104">타이밍 트리의 루트 클록만 대화형으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d10d7-105">대화식으로 클록에 직접 작업할 필요 하지 않은 컨트롤 애니메이션에 대 한 가지 다른: 스토리 보드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="d10d7-106">스토리 보드는 태그와 코드 모두에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="d10d7-107">예를 들어 참조 [Storyboard를 사용 하 여 속성에 애니메이션 효과](how-to-animate-a-property-by-using-a-storyboard.md) 또는 [애니메이션 개요](animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="d10d7-108">다음 예에서 애니메이션 클록을 대화형으로 제어 하는 여러 단추 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d10d7-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d10d7-109">예제</span><span class="sxs-lookup"><span data-stu-id="d10d7-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d10d7-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="d10d7-110">See also</span></span>

- [<span data-ttu-id="d10d7-111">Storyboard를 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="d10d7-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="d10d7-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="d10d7-112">Animation Overview</span></span>](animation-overview.md)
