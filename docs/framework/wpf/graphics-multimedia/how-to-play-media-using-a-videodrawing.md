---
title: '방법: VideoDrawing을 사용하여 미디어 재생'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203615"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="5fbb0-102">방법: VideoDrawing을 사용하여 미디어 재생</span><span class="sxs-lookup"><span data-stu-id="5fbb0-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="5fbb0-103">오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="5fbb0-104">미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-104">There are two ways to load and play media.</span></span> <span data-ttu-id="5fbb0-105">첫 번째 사용 하는 것을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들어보십시오 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fbb0-106">애플리케이션을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="5fbb0-107">대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fbb0-108">예제</span><span class="sxs-lookup"><span data-stu-id="5fbb0-108">Example</span></span>  
 <span data-ttu-id="5fbb0-109">다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="5fbb0-110">미디어에 대해 추가 타이밍 제어 권한을 사용 하 여는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 합니다 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="5fbb0-111"><xref:System.Windows.Media.MediaTimeline> 여 비디오 반복 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fbb0-112">예제</span><span class="sxs-lookup"><span data-stu-id="5fbb0-112">Example</span></span>  
 <span data-ttu-id="5fbb0-113">다음 예에서는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 합니다 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 반복적으로 비디오를 재생 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="5fbb0-114">이때 사용 하는 경우를 <xref:System.Windows.Media.MediaTimeline>, 대화형를 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된를 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 의 속성을 <xref:System.Windows.Media.MediaClock> 의 대화형 메서드 대신 미디어 재생을 제어 하 <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="5fbb0-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbb0-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fbb0-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="5fbb0-116">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="5fbb0-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
