---
title: '방법: AnimationClock을 사용하여 속성에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 4fa9efc593461d26eabaee5e2f62c1a17da1b543
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201366"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="4323e-102">방법: AnimationClock을 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="4323e-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="4323e-103">이 예제에 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Media.Animation.Clock> 속성 애니메이션을 적용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="4323e-104">종속성 속성에 애니메이션을 적용하는 방법에는 다음 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="4323e-105">만들기는 <xref:System.Windows.Media.Animation.AnimationTimeline> 를 사용 하 여 해당 속성을 사용 하 여 연결을 <xref:System.Windows.Media.Animation.Storyboard>입니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="4323e-106">개체를 사용 하 여 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 단일 적용 방법 <xref:System.Windows.Media.Animation.AnimationTimeline> 대상 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="4323e-107">만들기는 <xref:System.Windows.Media.Animation.AnimationClock> 에서 <xref:System.Windows.Media.Animation.AnimationTimeline> 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="4323e-108"><xref:System.Windows.Media.Animation.Storyboard> 개체 및 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 방법을 사용 하면 직접 만들어 시계를 배포 하지 않고 속성에 애니메이션 효과를 (예를 참조 하십시오 [Storyboard를 사용 하 여 속성에 애니메이션 효과](how-to-animate-a-property-by-using-a-storyboard.md) 및 [를 속성 없이 애니메이션 효과 주기 스토리 보드를 사용 하 여](how-to-animate-a-property-without-using-a-storyboard.md)); 클록 생성 및 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4323e-109">예제</span><span class="sxs-lookup"><span data-stu-id="4323e-109">Example</span></span>  
 <span data-ttu-id="4323e-110">다음 예제에서는 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.AnimationClock> 두 개의 비슷한 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="4323e-111">대화형으로 제어 하는 방법을 보여 주는 예는 <xref:System.Windows.Media.Animation.Clock> 시작 되 면 참조 [대화형으로 Clock 제어](how-to-interactively-control-a-clock.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="4323e-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4323e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="4323e-112">See also</span></span>

- [<span data-ttu-id="4323e-113">Storyboard를 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="4323e-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="4323e-114">Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="4323e-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="4323e-115">속성 애니메이션 기술 개요</span><span class="sxs-lookup"><span data-stu-id="4323e-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
