---
title: '방법: GIF 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: 35bd08f0d5e4d2ee9b8731706c9f1d770d67f633
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124743"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="f1e7e-102">방법: GIF 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="f1e7e-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="f1e7e-103">다음 예제를 디코딩 및 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 고 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7e-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1e7e-104">예제</span><span class="sxs-lookup"><span data-stu-id="f1e7e-104">Example</span></span>  
 <span data-ttu-id="f1e7e-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 를 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7e-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f1e7e-106">예제</span><span class="sxs-lookup"><span data-stu-id="f1e7e-106">Example</span></span>  
 <span data-ttu-id="f1e7e-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.GifBitmapEncoder>입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7e-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f1e7e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1e7e-108">See also</span></span>

- [<span data-ttu-id="f1e7e-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="f1e7e-109">Imaging Overview</span></span>](imaging-overview.md)
