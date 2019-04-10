---
title: '방법: 스토리보드가 시작되면 이벤트 트리거를 사용하여 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170653"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="32bbe-102">방법: 스토리보드가 시작되면 이벤트 트리거를 사용하여 제어</span><span class="sxs-lookup"><span data-stu-id="32bbe-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="32bbe-103">제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="32bbe-104">시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Media.Animation.BeginStoryboard>, 개체 및 속성에 애니메이션을 적용 하 고 시작한 다음 스토리 보드에 애니메이션을 배포 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="32bbe-105">제공 하는 경우 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 만들면 제어 가능한 storyboard입니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="32bbe-106">제어할 수 있습니다 다음 대화형으로 스토리 보드 시작 된 후.</span><span class="sxs-lookup"><span data-stu-id="32bbe-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="32bbe-107">와 함께 다음 스토리 보드 작업을 사용 하 여 <xref:System.Windows.EventTrigger> storyboard를 제어 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard><span data-ttu-id="32bbe-108">: Storyboard를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-108">: Pauses the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard><span data-ttu-id="32bbe-109">: 일시 중지 된 storyboard를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-109">: Resumes a paused storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio><span data-ttu-id="32bbe-110">: Storyboard 속도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-110">: Changes the storyboard speed.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill><span data-ttu-id="32bbe-111">: 있는 경우 해당 채우기 기간의 끝에 스토리 보드를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-111">: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard><span data-ttu-id="32bbe-112">: Storyboard를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-112">: Stops the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard><span data-ttu-id="32bbe-113">: 리소스를 확보 하 여 storyboard를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-113">: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32bbe-114">예제</span><span class="sxs-lookup"><span data-stu-id="32bbe-114">Example</span></span>  
 <span data-ttu-id="32bbe-115">다음 예제에서는 제어 가능한 storyboard 작업이 storyboard를 대화형으로 제어 하려면</span><span class="sxs-lookup"><span data-stu-id="32bbe-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="32bbe-116">**참고:** 코드를 사용 하 여 스토리 보드 제어의 예제를 보려면 [컨트롤을 스토리 보드 후 해당 시작를 사용 하 여 해당 대화형 메서드](how-to-control-a-storyboard-after-it-starts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="32bbe-117">추가 예제를 보려면 합니다 [애니메이션 예제 갤러리](https://go.microsoft.com/fwlink/?LinkID=159969)합니다.</span><span class="sxs-lookup"><span data-stu-id="32bbe-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bbe-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="32bbe-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="32bbe-119">대화형 메서드를 사용하여 이미 시작된 스토리보드 제어</span><span class="sxs-lookup"><span data-stu-id="32bbe-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="32bbe-120">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="32bbe-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="32bbe-121">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="32bbe-121">Storyboards Overview</span></span>](storyboards-overview.md)
