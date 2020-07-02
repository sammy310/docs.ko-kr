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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>방법: Storyboard를 사용하여 MediaElement 제어
이 예제에서는에서를 사용 하 여을 제어 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>예제  
 에서를 사용 하 여의 타이밍을 제어 하는 경우 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.MediaElement> 이 기능은 애니메이션과 같은 다른 개체의 기능과 동일 합니다 <xref:System.Windows.Media.Animation.Timeline> . 예를 들어, <xref:System.Windows.Media.MediaTimeline> 는 <xref:System.Windows.Media.Animation.Timeline> 속성과 같은 속성을 사용 하 여 시작 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 시점 <xref:System.Windows.Controls.MediaElement> (미디어 재생 시작)을 지정 합니다. 또한 속성을 사용 하 여 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 이 활성 상태인 기간 <xref:System.Windows.Controls.MediaElement> (미디어 재생 기간)을 지정 합니다. 에서 개체를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Storyboard> [storyboard 개요](storyboards-overview.md)를 참조 하세요.  
  
 이 예제에서는를 사용 하 여 재생을 제어 하는 간단한 미디어 플레이어를 만드는 방법을 보여 줍니다 <xref:System.Windows.Media.MediaTimeline> . 미디어 플레이어에는 재생, 일시 중지, 다시 시작 및 중지 단추가 포함 됩니다. 플레이어에는 <xref:System.Windows.Controls.Slider> 진행률 표시줄의 역할을 하는 컨트롤도 있습니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 미디어 플레이어에 대 한를 만듭니다.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 다음 예에서는 진행률 표시줄의 기능을 만듭니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [Storyboard 개요](storyboards-overview.md)
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [애니메이션 개요](animation-overview.md)
- [방법 도움말 항목](audio-and-video-how-to-topics.md)
- [그래픽 및 멀티미디어](index.md)
