---
title: '방법: 비디오로 영역 칠하기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151179"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="b868f-102">방법: 비디오로 영역 칠하기</span><span class="sxs-lookup"><span data-stu-id="b868f-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="b868f-103">이 예제에서는 미디어를 사용 하 여 영역을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="b868f-104">미디어를 사용 하 여 영역을 그리는 방법 중 하나를 사용 하는 것을 <xref:System.Windows.Controls.MediaElement> 와 함께 <xref:System.Windows.Media.VisualBrush>입니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="b868f-105">사용 하 여는 <xref:System.Windows.Controls.MediaElement> 로드 하 고 재생할 미디어를 사용 하 여 설정 하는 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 속성을 <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="b868f-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="b868f-106">사용할 수는 <xref:System.Windows.Media.VisualBrush> 로드 된 미디어를 사용 하 여 영역을 그리는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b868f-107">예제</span><span class="sxs-lookup"><span data-stu-id="b868f-107">Example</span></span>  
 <span data-ttu-id="b868f-108">다음 예에서는 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.VisualBrush> 그릴 합니다 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 비디오를 사용 하 여 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="b868f-109">설정 하는이 예제는 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 의 속성을 <xref:System.Windows.Controls.MediaElement> 에 `true` 사운드가 재생 되지 않습니다 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="b868f-110">예제</span><span class="sxs-lookup"><span data-stu-id="b868f-110">Example</span></span>  
 <span data-ttu-id="b868f-111">때문에 <xref:System.Windows.Media.VisualBrush> 에서 상속 되는 <xref:System.Windows.Media.TileBrush> 클래스는 몇 가지 바둑판식 배열 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="b868f-112">설정 하 여는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 의 속성을 <xref:System.Windows.Media.VisualBrush> 하 <xref:System.Windows.Media.TileMode.Tile> 설정 하 고 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 사용자가 칠하고 있는 영역 보다 작은 값으로 속성에는 바둑판식 배열된 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="b868f-113">다음 예제는 점을 제외 하면 이전 예제와 동일 합니다 <xref:System.Windows.Media.VisualBrush> 비디오에서 패턴을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="b868f-114">응용 프로그램에 미디어 파일과 같은 콘텐츠 파일을 추가 하는 방법에 대 한 정보를 참조 하세요. [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../app-development/wpf-application-resource-content-and-data-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="b868f-115">미디어 파일을 추가한 경우 리소스 파일 아니라 콘텐츠 파일로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b868f-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b868f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b868f-116">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="b868f-117">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="b868f-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="b868f-118">TileBrush 개요</span><span class="sxs-lookup"><span data-stu-id="b868f-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="b868f-119">멀티미디어 개요</span><span class="sxs-lookup"><span data-stu-id="b868f-119">Multimedia Overview</span></span>](multimedia-overview.md)
