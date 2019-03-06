---
title: '방법: Visual로 비트맵 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 429aacc99d8ead5a18e9be7602b19a74773b419a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362866"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>방법: Visual로 비트맵 만들기
비트맵을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Visual>합니다. A <xref:System.Windows.Media.DrawingVisual> 와 함께 렌더링 된 <xref:System.Windows.Media.FormattedText>합니다. 합니다 <xref:System.Windows.Media.Visual> 다음에 렌더링 되는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 지정된 된 텍스트의 비트맵을 만들 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.DrawingContext>
- [이미징 개요](imaging-overview.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
- [DrawingVisual 개체 사용](using-drawingvisual-objects.md)
