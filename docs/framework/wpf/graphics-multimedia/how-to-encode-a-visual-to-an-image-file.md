---
title: '방법: 시각적 요소를 이미지 파일로 인코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 2d5da0bde243128bc0d7aa29bf865ca9bfbd1d9a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355998"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>방법: 시각적 요소를 이미지 파일로 인코딩
인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Visual> 개체를 사용 하 여 이미지 파일에는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>합니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Media.DrawingVisual> 사용 하 여 만들어집니다를 <xref:System.Windows.Media.Imaging.BitmapImage> 하 고 <xref:System.Windows.Media.FormattedText> 으로 렌더링 되는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>합니다. 렌더링 된 비트맵은 만드는 데 다음을 <xref:System.Windows.Media.Imaging.BitmapFrame> 에 추가 되는 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 새 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 파일입니다.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 하지만 파생 된 모든이 예제에서 사용한 <xref:System.Windows.Media.Imaging.BitmapEncoder> 개체는 이미지 파일을 만드는 데 사용 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.DrawingContext>
- [이미징 개요](imaging-overview.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
- [DrawingVisual 개체 사용](using-drawingvisual-objects.md)
