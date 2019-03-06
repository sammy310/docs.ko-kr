---
title: '방법: VideoDrawing을 사용하여 미디어 재생'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2397662c79af208f2528f6eedcd5995cfac9526c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363100"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>방법: VideoDrawing을 사용하여 미디어 재생
오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째 사용 하는 것을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들어보십시오 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
> [!NOTE]
>  애플리케이션을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 하도록 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대해 추가 타이밍 제어 권한을 사용 하 여는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 합니다 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다. <xref:System.Windows.Media.MediaTimeline> 여 비디오 반복 여부를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 합니다 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 반복적으로 비디오를 재생 하는 개체입니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 이때 사용 하는 경우를 <xref:System.Windows.Media.MediaTimeline>, 대화형를 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된를 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 의 속성을 <xref:System.Windows.Media.MediaClock> 의 대화형 메서드 대신 미디어 재생을 제어 하 <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.VideoDrawing>
- [Drawing 개체 개요](drawing-objects-overview.md)
