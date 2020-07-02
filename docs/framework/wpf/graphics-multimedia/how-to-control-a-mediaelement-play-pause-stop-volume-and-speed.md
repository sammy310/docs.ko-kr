---
title: '방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)'
description: WPF (Windows Presentation foundation)에서 미디어의 재생을 제어 합니다. 시작, 중지, 일시 중지, 앞뒤로 건너뛰고 볼륨 및 속도를 조정 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853598"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)
다음 예제에서는를 사용 하 여 미디어 재생을 제어 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.MediaElement> . 이 예에서는 미디어에서 재생, 일시 중지, 중지 및 건너뛰기를 수행할 뿐만 아니라 볼륨 및 속도 비율을 조정할 수 있는 간단한 미디어 플레이어를 만듭니다.  
  
## <a name="example"></a>예제  
 아래 코드는 UI를 만듭니다.  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>미디어를 대화형으로 중지, 일시 중지 및 재생할 수 있도록의 속성은 <xref:System.Windows.Controls.MediaElement> 로 설정 되어야 합니다 `Manual` .  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>예제  
 아래 코드는 샘플 UI 컨트롤의 기능을 구현 합니다. <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> 및 메서드는 <xref:System.Windows.Controls.MediaElement.Stop%2A> 각각 미디어를 재생, 일시 중지 및 중지 하는 데 사용 됩니다. <xref:System.Windows.Controls.MediaElement.Position%2A>의 속성을 변경 하면 <xref:System.Windows.Controls.MediaElement> 미디어를 건너뛸 수 있습니다. 마지막으로 <xref:System.Windows.Controls.MediaElement.Volume%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성은 미디어의 볼륨 및 재생 속도를 조정 하는 데 사용 됩니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>참조

- [스토리보드를 사용하여 MediaElement 제어](how-to-control-a-mediaelement-by-using-a-storyboard.md)
