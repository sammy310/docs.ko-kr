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
ms.openlocfilehash: b143106092235b42044d264189c135d2cd65426c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153363"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="42f6d-102">방법: WDP 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="42f6d-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="42f6d-103">다음 예제를 디코딩 및 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> 고 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="42f6d-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42f6d-104">예제</span><span class="sxs-lookup"><span data-stu-id="42f6d-104">Example</span></span>  
 <span data-ttu-id="42f6d-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] 를 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> 에서 <xref:System.Uri>합니다.</span><span class="sxs-lookup"><span data-stu-id="42f6d-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="42f6d-106">예제</span><span class="sxs-lookup"><span data-stu-id="42f6d-106">Example</span></span>  
 <span data-ttu-id="42f6d-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] 사용 하 여 이미지를 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>입니다.</span><span class="sxs-lookup"><span data-stu-id="42f6d-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="42f6d-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="42f6d-108">See also</span></span>

- [<span data-ttu-id="42f6d-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="42f6d-109">Imaging Overview</span></span>](imaging-overview.md)
