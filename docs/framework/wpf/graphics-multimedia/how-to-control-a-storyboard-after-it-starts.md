---
title: '방법: 시작 된 Storyboard 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 98eba600f64c8b656e3597b429cc69766f398f7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361059"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="e7dd5-102">방법: 시작 된 Storyboard 제어</span><span class="sxs-lookup"><span data-stu-id="e7dd5-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="e7dd5-103">컨트롤에 코드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후입니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="e7dd5-104">스토리 보드 제어 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Trigger> 및 <xref:System.Windows.TriggerAction> 개체, 참조 예를 들어 [이벤트 트리거는 Storyboard를 시작한 후 제어를 사용 하 여](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="e7dd5-105">Storyboard를 시작 하려면 해당 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 분산 스토리 보드의 애니메이션 속성에 애니메이션을 적용 하며 storyboard를 시작 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="e7dd5-106">Storyboard를 제어할 수 있도록 하려면 사용 합니다 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 **true** 두 번째 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="e7dd5-107">그런 다음 일시 중지, 다시 시작, 검색, 중지, 속도, 또는 스토리 보드를 저하 또는 채우기 기간으로 이동 하려면 스토리 보드의 대화형 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="e7dd5-108">다음은 스토리 보드의 대화형 메서드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="e7dd5-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Storyboard를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="e7dd5-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지 된 storyboard를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="e7dd5-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: 스토리 보드의 대화형 속도 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="e7dd5-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: 스토리 보드 지정된 된 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="e7dd5-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: 지정된 된 위치에 스토리 보드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="e7dd5-114">달리는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드를이 작업의 다음 틱 보다 먼저 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="e7dd5-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: 있는 경우 채우기 기간이 스토리 보드를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="e7dd5-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Storyboard를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="e7dd5-117">다음 예제에서는 여러 스토리 보드 메서드는 스토리 보드를 대화형으로 제어 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="e7dd5-118">**참고:** 트리거를 사용 하 여 storyboard 제어의 예제를 보려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 참조 하세요 [제어는 Storyboard를 시작한 후 이벤트 트리거를 사용 하 여](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="e7dd5-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7dd5-119">예제</span><span class="sxs-lookup"><span data-stu-id="e7dd5-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e7dd5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7dd5-120">See also</span></span>
- [<span data-ttu-id="e7dd5-121">Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어</span><span class="sxs-lookup"><span data-stu-id="e7dd5-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
