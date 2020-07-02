---
title: '방법: Storyboard를 사용하여 MediaElement 제어'
description: WPF (Windows Presentation foundation)에서 storyboard를 사용 하 여 미디어 재생을 제어 합니다. 간단한 미디어 플레이어를 만드는 다음 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: 5a5e41b9a28211495fd3374c1a51a655dd867bca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853737"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="c2079-104">방법: Storyboard를 사용하여 MediaElement 제어</span><span class="sxs-lookup"><span data-stu-id="c2079-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="c2079-105">이 예제에서는에서를 사용 하 여을 제어 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="c2079-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2079-106">예제</span><span class="sxs-lookup"><span data-stu-id="c2079-106">Example</span></span>  
 <span data-ttu-id="c2079-107">에서를 사용 하 여의 타이밍을 제어 하는 경우 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.MediaElement> 이 기능은 애니메이션과 같은 다른 개체의 기능과 동일 합니다 <xref:System.Windows.Media.Animation.Timeline> .</span><span class="sxs-lookup"><span data-stu-id="c2079-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="c2079-108">예를 들어, <xref:System.Windows.Media.MediaTimeline> 는 <xref:System.Windows.Media.Animation.Timeline> 속성과 같은 속성을 사용 하 여 시작 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 시점 <xref:System.Windows.Controls.MediaElement> (미디어 재생 시작)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="c2079-109">또한 속성을 사용 하 여 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 이 활성 상태인 기간 <xref:System.Windows.Controls.MediaElement> (미디어 재생 기간)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="c2079-110">에서 개체를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Storyboard> [storyboard 개요](storyboards-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2079-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="c2079-111">이 예제에서는를 사용 하 여 재생을 제어 하는 간단한 미디어 플레이어를 만드는 방법을 보여 줍니다 <xref:System.Windows.Media.MediaTimeline> .</span><span class="sxs-lookup"><span data-stu-id="c2079-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="c2079-112">미디어 플레이어에는 재생, 일시 중지, 다시 시작 및 중지 단추가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="c2079-113">플레이어에는 <xref:System.Windows.Controls.Slider> 진행률 표시줄의 역할을 하는 컨트롤도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="c2079-114">다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 미디어 플레이어에 대 한를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="c2079-115">다음 예에서는 진행률 표시줄의 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2079-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c2079-116">참조</span><span class="sxs-lookup"><span data-stu-id="c2079-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="c2079-117">MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)</span><span class="sxs-lookup"><span data-stu-id="c2079-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="c2079-118">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="c2079-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="c2079-119">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c2079-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c2079-120">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c2079-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c2079-121">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="c2079-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="c2079-122">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="c2079-122">Graphics and Multimedia</span></span>](index.md)
