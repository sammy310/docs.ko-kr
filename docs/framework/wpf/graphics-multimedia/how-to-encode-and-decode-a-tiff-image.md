---
title: '방법: TIFF 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 173a30e785b16a3617b82b771c463083356d6e6e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835297"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="e9b77-102">방법: TIFF 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="e9b77-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="e9b77-103">다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> 개체를 사용 하 여 TIFF (태그가 지정 된 이미지 파일 형식) 이미지를 디코드 하 고 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9b77-103">The following examples show how to decode and encode a Tagged Image File Format (TIFF) image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9b77-104">예제</span><span class="sxs-lookup"><span data-stu-id="e9b77-104">Example</span></span>  
 <span data-ttu-id="e9b77-105">이 예제에서는 <xref:System.Uri>에서 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder>을 사용 하 여 TIFF 이미지를 디코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9b77-105">This example demonstrates how to decode a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e9b77-106">예제</span><span class="sxs-lookup"><span data-stu-id="e9b77-106">Example</span></span>  
 <span data-ttu-id="e9b77-107">이 예제에서는 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>을 사용 하 여 <xref:System.Windows.Media.Imaging.BitmapSource>을 TIFF 이미지로 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9b77-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e9b77-108">참조</span><span class="sxs-lookup"><span data-stu-id="e9b77-108">See also</span></span>

- [<span data-ttu-id="e9b77-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="e9b77-109">Imaging Overview</span></span>](imaging-overview.md)
