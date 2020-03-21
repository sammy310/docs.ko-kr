---
title: '방법: 이미지로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186060"
---
# <a name="how-to-paint-an-area-with-an-image"></a>방법: 이미지로 영역 그리기
이 예제에서는 클래스를 <xref:System.Windows.Media.ImageBrush> 사용하여 이미지로 영역을 페인칠하는 방법을 보여 주며 있습니다. 속성에 <xref:System.Windows.Media.ImageBrush> 의해 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 지정된 단일 이미지가 표시됩니다.  
  
## <a name="example"></a>예제  
 다음 예제는 을 <xref:System.Windows.Controls.Control.Background%2A> 사용하여 단추를 <xref:System.Windows.Media.ImageBrush>그립니다.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 기본적으로 이미지를 <xref:System.Windows.Media.ImageBrush> 늘이면 페인팅할 영역을 완전히 채울 수 있습니다. 위의 예제에서는 이미지가 단추를 채우도록 확장되므로 이미지가 왜곡될 수 있습니다. <xref:System.Windows.Media.TileBrush.Stretch%2A> 브러시가 이미지의 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> 가로 세로 비율을 <xref:System.Windows.Media.Stretch.UniformToFill>유지하도록 하는 의 속성을 또는 에 설정하여 이 동작을 제어할 수 있습니다.  
  
 <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.TileMode%2A> 및 의 속성을 설정하는 경우 반복 패턴을 만들 <xref:System.Windows.Media.ImageBrush>수 있습니다. 다음 예제에서는 이미지에서 만들어지는 패턴을 사용하여 단추를 그립니다.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 클래스에 <xref:System.Windows.Media.ImageBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
 이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다. 전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
