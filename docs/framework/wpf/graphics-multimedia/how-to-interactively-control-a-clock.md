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
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951344"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="96279-102">방법: 대화형 시계 제어</span><span class="sxs-lookup"><span data-stu-id="96279-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="96279-103">개체 <xref:System.Windows.Media.Animation.Clock> 의<xref:System.Windows.Media.Animation.ClockController> 속성을 사용 하면 대화형으로 시작, 일시 중지, 재개, 검색, 시계를 채우기 기간으로 이동 하 고 clock을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96279-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="96279-104">타이밍 트리의 루트 클록만 대화형으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96279-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96279-105">시계로 직접 작업 하지 않아도 되는 애니메이션을 대화형으로 제어 하는 다른 방법이 있습니다. 스토리 보드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96279-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="96279-106">스토리 보드는 태그와 코드 모두에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96279-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="96279-107">예제를 보려면 Storyboard 또는 [애니메이션 개요](animation-overview.md)를 [사용 하 여 속성에 애니메이션 효과 주기](how-to-animate-a-property-by-using-a-storyboard.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96279-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="96279-108">다음 예제에서는 여러 단추를 사용 하 여 애니메이션 clock을 대화형으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="96279-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96279-109">예제</span><span class="sxs-lookup"><span data-stu-id="96279-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="96279-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="96279-110">See also</span></span>

- [<span data-ttu-id="96279-111">Storyboard를 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="96279-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="96279-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="96279-112">Animation Overview</span></span>](animation-overview.md)
