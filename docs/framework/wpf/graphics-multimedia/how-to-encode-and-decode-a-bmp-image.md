---
title: '방법: BMP 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: b7d5ace8aead864cb69a9e696a3f1f925e232600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947643"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="2e108-102">방법: BMP 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="2e108-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="2e108-103">다음 예제를 디코딩 및 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> 고 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2e108-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e108-104">예제</span><span class="sxs-lookup"><span data-stu-id="2e108-104">Example</span></span>  
 <span data-ttu-id="2e108-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 를 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> 에서 <xref:System.Uri>합니다.</span><span class="sxs-lookup"><span data-stu-id="2e108-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="2e108-106">예제</span><span class="sxs-lookup"><span data-stu-id="2e108-106">Example</span></span>  
 <span data-ttu-id="2e108-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>입니다.</span><span class="sxs-lookup"><span data-stu-id="2e108-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2e108-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e108-108">See also</span></span>

- [<span data-ttu-id="2e108-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="2e108-109">Imaging Overview</span></span>](imaging-overview.md)
