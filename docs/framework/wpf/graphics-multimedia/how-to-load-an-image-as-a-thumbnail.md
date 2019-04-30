---
title: '방법: 썸네일 이미지로 로드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: f984293a395e925368b20cef6aa0cd902bd6fc15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003186"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="8995f-102">방법: 썸네일 이미지로 로드</span><span class="sxs-lookup"><span data-stu-id="8995f-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="8995f-103">다음 예제에서는 로드 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Image> 응용 프로그램 메모리를 절약 하기 위해를 축소판으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8995f-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8995f-104">예제</span><span class="sxs-lookup"><span data-stu-id="8995f-104">Example</span></span>  
 <span data-ttu-id="8995f-105">다음 예제에서는 합니다 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 의 속성을 <xref:System.Windows.Media.Imaging.BitmapImage> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이미지를 로드 하는 데 필요한 메모리를 줄일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8995f-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="8995f-106">예제</span><span class="sxs-lookup"><span data-stu-id="8995f-106">Example</span></span>  
 <span data-ttu-id="8995f-107">다음 예제에서는 합니다 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 의 속성을 <xref:System.Windows.Media.Imaging.BitmapImage> 이미지를 로드 하는 데 필요한 메모리를 줄이기 위해 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8995f-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="8995f-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="8995f-108">See also</span></span>

- [<span data-ttu-id="8995f-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="8995f-109">Imaging Overview</span></span>](imaging-overview.md)
