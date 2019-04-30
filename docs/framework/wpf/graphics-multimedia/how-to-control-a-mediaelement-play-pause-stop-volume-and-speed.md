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
ms.openlocfilehash: bb7319fc7ccec0220cbd79a32d5d015f9f2422d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984048"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="0f005-102">방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)</span><span class="sxs-lookup"><span data-stu-id="0f005-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="0f005-103">다음 예제에서는 사용 하 여 미디어 재생을 제어 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MediaElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="0f005-104">이 예제에서는 재생, 일시 중지, 중지 및 미디어에서 앞뒤로 건너뛸 뿐만 볼륨 및 속도 비율을 조정할 수 있는 간단한 미디어 플레이어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f005-105">예제</span><span class="sxs-lookup"><span data-stu-id="0f005-105">Example</span></span>  
 <span data-ttu-id="0f005-106">아래 코드는 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f005-107">합니다 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 속성을 <xref:System.Windows.Controls.MediaElement> 로 설정 되어야 합니다 `Manual` 있으려면 대화형으로 중지, 일시 중지 및 미디어를 재생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="0f005-108">예제</span><span class="sxs-lookup"><span data-stu-id="0f005-108">Example</span></span>  
 <span data-ttu-id="0f005-109">아래 코드 샘플 UI 컨트롤의 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="0f005-110">합니다 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A> 메서드는 각각 재생, 일시 중지 및 미디어를 중지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="0f005-111">변경 합니다 <xref:System.Windows.Controls.MediaElement.Position%2A> 의 속성을 <xref:System.Windows.Controls.MediaElement> 미디어에서 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="0f005-112">마지막으로, 합니다 <xref:System.Windows.Controls.MediaElement.Volume%2A> 고 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성은 미디어의 볼륨 및 재생 속도 조정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f005-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0f005-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f005-113">See also</span></span>

- [<span data-ttu-id="0f005-114">Storyboard를 사용하여 MediaElement 제어</span><span class="sxs-lookup"><span data-stu-id="0f005-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
