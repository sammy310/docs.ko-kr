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
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671688"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="11770-102">방법: GIF 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="11770-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="11770-103">다음 예에서는 특정 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 개체를 사용 하 여 GIF (그래픽 교환 형식) 이미지를 디코드 하 고 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11770-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11770-104">예제</span><span class="sxs-lookup"><span data-stu-id="11770-104">Example</span></span>  
 <span data-ttu-id="11770-105">이 예제에서는 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> <xref:System.IO.FileStream>에서를 사용 하 여 GIF 이미지를 디코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11770-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="11770-106">예제</span><span class="sxs-lookup"><span data-stu-id="11770-106">Example</span></span>  
 <span data-ttu-id="11770-107">이 예제에서는를 <xref:System.Windows.Media.Imaging.BitmapSource> <xref:System.Windows.Media.Imaging.GifBitmapEncoder>사용 하 여를 GIF 이미지로 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11770-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="11770-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="11770-108">See also</span></span>

- [<span data-ttu-id="11770-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="11770-109">Imaging Overview</span></span>](imaging-overview.md)
