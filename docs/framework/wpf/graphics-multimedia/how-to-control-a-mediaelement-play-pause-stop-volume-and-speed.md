---
title: '방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)'
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
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930157"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="a62d4-102">방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)</span><span class="sxs-lookup"><span data-stu-id="a62d4-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="a62d4-103">다음 예제에서는를 <xref:System.Windows.Controls.MediaElement>사용 하 여 미디어 재생을 제어 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a62d4-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="a62d4-104">이 예에서는 미디어에서 재생, 일시 중지, 중지 및 건너뛰기를 수행할 뿐만 아니라 볼륨 및 속도 비율을 조정할 수 있는 간단한 미디어 플레이어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a62d4-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a62d4-105">예제</span><span class="sxs-lookup"><span data-stu-id="a62d4-105">Example</span></span>  
 <span data-ttu-id="a62d4-106">아래 코드는 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a62d4-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a62d4-107">미디어 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 를 대화형 <xref:System.Windows.Controls.MediaElement> 으로 중지, 일시 `Manual` 중지 및 재생할 수 있도록의 속성은로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62d4-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="a62d4-108">예제</span><span class="sxs-lookup"><span data-stu-id="a62d4-108">Example</span></span>  
 <span data-ttu-id="a62d4-109">아래 코드는 샘플 UI 컨트롤의 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62d4-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="a62d4-110"><xref:System.Windows.Controls.MediaElement.Play%2A>, 및메서드<xref:System.Windows.Controls.MediaElement.Stop%2A> 는 각각 미디어를 재생, 일시 중지 및 중지 하는 데 사용 됩니다. <xref:System.Windows.Controls.MediaElement.Pause%2A></span><span class="sxs-lookup"><span data-stu-id="a62d4-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="a62d4-111">의 속성 <xref:System.Windows.Controls.MediaElement.Position%2A> 을 변경 하면 미디어를 건너뛸 수있습니다.<xref:System.Windows.Controls.MediaElement></span><span class="sxs-lookup"><span data-stu-id="a62d4-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="a62d4-112">마지막으로 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 및 속성은 미디어의 볼륨 및 재생 속도를 조정 하는 데 사용 됩니다. <xref:System.Windows.Controls.MediaElement.Volume%2A></span><span class="sxs-lookup"><span data-stu-id="a62d4-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a62d4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a62d4-113">See also</span></span>

- [<span data-ttu-id="a62d4-114">Storyboard를 사용하여 MediaElement 제어</span><span class="sxs-lookup"><span data-stu-id="a62d4-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
