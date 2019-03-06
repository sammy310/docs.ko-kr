---
title: '방법: Storyboard 애니메이션 간의 HandoffBehavior 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: a919fe2a87cb11ca2197465b288eac7a17976cc3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379070"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="3ad90-102">방법: Storyboard 애니메이션 간의 HandoffBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="3ad90-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="3ad90-103">이 예제에서는 storyboard 애니메이션 간의 전달 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="3ad90-104">합니다 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 의 속성 <xref:System.Windows.Media.Animation.BeginStoryboard> 새로운 애니메이션 지정 속성에 이미 적용 된 기존 애니메이션과 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ad90-105">예제</span><span class="sxs-lookup"><span data-stu-id="3ad90-105">Example</span></span>  
 <span data-ttu-id="3ad90-106">다음 예제에서는 두 개의 단추 위로 마우스 커서를 움직이면 확대 커지고 커서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="3ad90-107">단추 위로 마우스를 가져가면 다음 커서를 신속 하 게 제거 하는 경우 두 번째 애니메이션이 첫 번째 작업이 완료 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="3ad90-108">간의 차이 볼 수 있는 다음과 같은 두 개의 애니메이션이 겹칠 때의 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 의 값 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 및 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="3ad90-109">값이 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 애니메이션 값 간에 전환을 더 부드럽게 오버랩 애니메이션 결합 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 겹치는 이전 즉시 바꾸려면 새 애니메이션이 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad90-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3ad90-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ad90-110">See also</span></span>
- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="3ad90-111">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="3ad90-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3ad90-112">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="3ad90-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
