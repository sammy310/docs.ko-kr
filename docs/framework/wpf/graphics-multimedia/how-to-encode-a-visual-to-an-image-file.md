---
title: '방법: Visual을 이미지 파일에 인코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545297"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="3dd09-102">방법: Visual을 이미지 파일에 인코딩</span><span class="sxs-lookup"><span data-stu-id="3dd09-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="3dd09-103">이 예제에서는 <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및를 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>사용 하 여 개체를 이미지 파일로 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3dd09-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd09-104">예제</span><span class="sxs-lookup"><span data-stu-id="3dd09-104">Example</span></span>  
 <span data-ttu-id="3dd09-105">는로 <xref:System.Windows.Media.Imaging.BitmapImage> 렌더링되<xref:System.Windows.Media.FormattedText> 는 및를 사용 하 여 만들어집니다. <xref:System.Windows.Media.Imaging.RenderTargetBitmap> <xref:System.Windows.Media.DrawingVisual></span><span class="sxs-lookup"><span data-stu-id="3dd09-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="3dd09-106">렌더링 된 비트맵은 새 png (이동식 네트워크 <xref:System.Windows.Media.Imaging.BitmapFrame> 그래픽) 파일을 만들기 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 위해에 추가 되는를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd09-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="3dd09-107">이 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 예제에서는를 사용 했지만 이미지 파일을 만드는 데 <xref:System.Windows.Media.Imaging.BitmapEncoder> 파생 된 개체를 사용 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd09-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd09-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="3dd09-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="3dd09-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="3dd09-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="3dd09-110">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="3dd09-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="3dd09-111">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="3dd09-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
