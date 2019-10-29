---
title: '방법: WDP 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: 8c5c312c7e58d48a865e493c38c3defd3f5f3d1d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040772"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="cd4f0-102">방법: WDP 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="cd4f0-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="cd4f0-103">다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder>와 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> 개체를 사용 하 여 Microsoft Windows Media Photo 이미지를 디코드 하 고 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd4f0-103">The following examples show how to decode and encode a Microsoft Windows Media Photo image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4f0-104">예제</span><span class="sxs-lookup"><span data-stu-id="cd4f0-104">Example</span></span>  
 <span data-ttu-id="cd4f0-105">이 예제에서는 <xref:System.Uri>의 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder>를 사용 하 여 Windows Media 사진 이미지를 디코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd4f0-105">This example demonstrates how to decode a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="cd4f0-106">예제</span><span class="sxs-lookup"><span data-stu-id="cd4f0-106">Example</span></span>  
 <span data-ttu-id="cd4f0-107">이 예제에서는 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>를 사용 하 여 <xref:System.Windows.Media.Imaging.BitmapSource>를 Windows Media 사진 이미지로 인코딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd4f0-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cd4f0-108">참조</span><span class="sxs-lookup"><span data-stu-id="cd4f0-108">See also</span></span>

- [<span data-ttu-id="cd4f0-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="cd4f0-109">Imaging Overview</span></span>](imaging-overview.md)
