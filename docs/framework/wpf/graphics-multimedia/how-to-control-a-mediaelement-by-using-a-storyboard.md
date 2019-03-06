---
title: '방법: Storyboard를 사용하여 MediaElement 제어'
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
ms.openlocfilehash: 51d567101ee49095e27e9d440016a81cd49fa876
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369112"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="753f9-102">방법: Storyboard를 사용하여 MediaElement 제어</span><span class="sxs-lookup"><span data-stu-id="753f9-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="753f9-103">제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.MediaElement> 를 사용 하 여는 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="753f9-104">예제</span><span class="sxs-lookup"><span data-stu-id="753f9-104">Example</span></span>  
 <span data-ttu-id="753f9-105">사용 하는 경우를 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard> 의 타이밍을 제어 하는 <xref:System.Windows.Controls.MediaElement>, 기능은 다른 기능과 동일한 <xref:System.Windows.Media.Animation.Timeline> 애니메이션 등의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="753f9-106">예를 들어,를 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 <xref:System.Windows.Media.Animation.Timeline> 등의 속성을 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 시작 하는 시기를 지정 하는 속성을 <xref:System.Windows.Controls.MediaElement> (미디어 재생을 시작 합니다.).</span><span class="sxs-lookup"><span data-stu-id="753f9-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="753f9-107">또한 사용 하 여는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 통해 지정 시간 <xref:System.Windows.Controls.MediaElement> 활성 (미디어 재생 기간).</span><span class="sxs-lookup"><span data-stu-id="753f9-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="753f9-108">사용에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Timeline> 사용 하 여 개체를 <xref:System.Windows.Media.Animation.Storyboard>를 참조 하세요 [Storyboard 개요](storyboards-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="753f9-109">이 예제에 사용 하는 간단한 미디어 플레이어를 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.MediaTimeline> 재생을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="753f9-110">Media player에는 재생, 일시 중지, 재개 및 중지 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="753f9-111">플레이어가 있습니다를 <xref:System.Windows.Controls.Slider> 역할 진행률 표시줄을 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="753f9-112">다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] media player에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="753f9-113">다음 예제에서는 진행률 표시줄에 대 한 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="753f9-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="753f9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="753f9-114">See also</span></span>
- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="753f9-115">MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)</span><span class="sxs-lookup"><span data-stu-id="753f9-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="753f9-116">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="753f9-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="753f9-117">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="753f9-117">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="753f9-118">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="753f9-118">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="753f9-119">방법 항목</span><span class="sxs-lookup"><span data-stu-id="753f9-119">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="753f9-120">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="753f9-120">Graphics and Multimedia</span></span>](index.md)
