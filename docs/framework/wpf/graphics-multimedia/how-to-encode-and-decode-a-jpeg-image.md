---
title: '방법: JPEG 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947513"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="d60f9-102">방법: JPEG 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="d60f9-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="d60f9-103">다음 예제를 디코딩 및 특정을 사용 하 여 JPEG 이미지를 인코딩하는 방법을 보여 줍니다 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 고 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d60f9-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="d60f9-104">예제-를 JPEG 이미지 디코딩</span><span class="sxs-lookup"><span data-stu-id="d60f9-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="d60f9-105">사용 하 여 JPEG 이미지를 디코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f9-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="d60f9-106">예제-를 JPEG 이미지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d60f9-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="d60f9-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> JPEG를 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>입니다.</span><span class="sxs-lookup"><span data-stu-id="d60f9-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d60f9-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="d60f9-108">See also</span></span>

- [<span data-ttu-id="d60f9-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="d60f9-109">Imaging Overview</span></span>](imaging-overview.md)
