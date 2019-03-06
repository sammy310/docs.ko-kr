---
title: '방법: PNG 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 132ccc2fca4b1b3984c88f1e75d3fd1934d8bf24
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358095"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="360f2-102">방법: PNG 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="360f2-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="360f2-103">다음 예제를 디코딩 및 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.PngBitmapDecoder> 고 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="360f2-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="360f2-104">예제</span><span class="sxs-lookup"><span data-stu-id="360f2-104">Example</span></span>  
 <span data-ttu-id="360f2-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] 를 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.PngBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="360f2-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="360f2-106">예제</span><span class="sxs-lookup"><span data-stu-id="360f2-106">Example</span></span>  
 <span data-ttu-id="360f2-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>입니다.</span><span class="sxs-lookup"><span data-stu-id="360f2-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="360f2-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="360f2-108">See also</span></span>
- [<span data-ttu-id="360f2-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="360f2-109">Imaging Overview</span></span>](imaging-overview.md)
