---
title: '방법: 애니메이션이 있는 미디어 재생'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079905"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="f0edb-102">방법: 애니메이션이 있는 미디어 재생</span><span class="sxs-lookup"><span data-stu-id="f0edb-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="f0edb-103">사용 하 여 동시 미디어 및 애니메이션을 재생 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 하 고 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="f0edb-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0edb-104">예제</span><span class="sxs-lookup"><span data-stu-id="f0edb-104">Example</span></span>  
 <span data-ttu-id="f0edb-105">하나를 사용할 수 있습니다 <xref:System.Windows.Media.MediaTimeline> 개체를 <xref:System.Windows.Media.Animation.Storyboard> 다른 함께 <xref:System.Windows.Media.Animation.Timeline> 애니메이션 등의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f0edb-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="f0edb-106">다음 예제에서는 합니다 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Storyboard> 값으로 `Slip`, 애니메이션 (이 예제의 비디오) 미디어 진행 될 때까지 진행 되지 않습니다. 지정 하는.</span><span class="sxs-lookup"><span data-stu-id="f0edb-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="f0edb-107">이 기능은 로드 시간 때문에 미디어 재생을 지연해야 할 경우에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0edb-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f0edb-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0edb-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="f0edb-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f0edb-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="f0edb-110">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="f0edb-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="f0edb-111">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f0edb-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f0edb-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f0edb-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f0edb-113">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="f0edb-113">Graphics and Multimedia</span></span>](index.md)
