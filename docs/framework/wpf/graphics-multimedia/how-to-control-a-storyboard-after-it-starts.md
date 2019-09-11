---
title: '방법: 스토리 보드가 시작 된 후 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855868"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="ccbd9-102">방법: 스토리 보드가 시작 된 후 제어</span><span class="sxs-lookup"><span data-stu-id="ccbd9-102">How to: Control a Storyboard After It Starts</span></span>

<span data-ttu-id="ccbd9-103">이 예제에서는 코드를 사용 하 여를 <xref:System.Windows.Media.Animation.Storyboard> 시작한 후 제어 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="ccbd9-104">에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]storyboard를 제어 하려면 및 <xref:System.Windows.TriggerAction> 개체 <xref:System.Windows.Trigger> 를 사용 합니다. 예를 들어 [이벤트 트리거를 사용 하 여 storyboard를 시작한 후 제어를](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

<span data-ttu-id="ccbd9-105">Storyboard를 시작 하려면 해당 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용 합니다 .이 메서드는 스토리 보드의 애니메이션을 애니메이션 효과를 주는 속성에 배포 하 고 스토리 보드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>

<span data-ttu-id="ccbd9-106">Storyboard를 제어 가능 하 게 만들려면 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용 하 고 **true** 를 두 번째 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="ccbd9-107">그런 다음 storyboard의 대화형 메서드를 사용 하 여 스토리 보드를 일시 중지, 다시 시작, 검색, 중지, 속도를 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="ccbd9-108">다음은 storyboard의 대화형 메서드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-108">The following is a list of the storyboard's interactive methods:</span></span>

- <span data-ttu-id="ccbd9-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: 스토리 보드를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>

- <span data-ttu-id="ccbd9-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지 된 스토리 보드를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="ccbd9-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: 스토리 보드의 대화형 속도를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>

- <span data-ttu-id="ccbd9-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: 지정 된 위치에서 storyboard를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>

- <span data-ttu-id="ccbd9-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: 지정 된 위치에 대 한 storyboard를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="ccbd9-114"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드와 달리이 작업은 다음 틱 보다 먼저 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>

- <span data-ttu-id="ccbd9-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: 스토리 보드를 채우기 기간 (있는 경우)으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>

- <span data-ttu-id="ccbd9-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: 스토리 보드를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>

<span data-ttu-id="ccbd9-117">다음 예제에서는 스토리 보드를 대화형으로 제어 하기 위해 여러 storyboard 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="ccbd9-118">에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]트리거를 사용 하 여 스토리 보드를 제어 하는 예를 보려면 [시작 후 이벤트 트리거를 사용 하 여 스토리 보드 제어를](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ccbd9-118">To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

## <a name="example"></a><span data-ttu-id="ccbd9-119">예제</span><span class="sxs-lookup"><span data-stu-id="ccbd9-119">Example</span></span>

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a><span data-ttu-id="ccbd9-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ccbd9-120">See also</span></span>

- [<span data-ttu-id="ccbd9-121">Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어</span><span class="sxs-lookup"><span data-stu-id="ccbd9-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
