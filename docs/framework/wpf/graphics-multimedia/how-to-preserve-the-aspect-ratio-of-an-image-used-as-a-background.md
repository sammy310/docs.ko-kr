---
title: '방법: 배경으로 사용된 이미지의 가로 세로 비율 유지'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186024"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>방법: 배경으로 사용된 이미지의 가로 세로 비율 유지
이 예제에서는 이미지의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 가로 <xref:System.Windows.Media.ImageBrush> 세로 비율을 유지하기 위해 a의 속성을 사용하는 방법을 보여 주습니다.  
  
 기본적으로 영역을 <xref:System.Windows.Media.ImageBrush> 사용하여 페인트할 때 해당 콘텐츠가 늘어나 출력 영역을 완전히 채웁니다. 출력 영역과 이미지의 가로 세로 비율이 다르면 이미지가 확장되면서 왜곡됩니다.  
  
 이미지의 <xref:System.Windows.Media.ImageBrush> 가로 세로 비율을 유지하려면 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 또는 <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>으로 설정합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 두 개의 오브젝트를 사용하여 두 개의 사각형을 페인칠합니다. 각 사각형은 300 × 150픽셀 크기이며 각각 300 x 300픽셀 이미지를 포함합니다. 첫 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 브러시의 속성이 <xref:System.Windows.Media.Stretch.Uniform>로 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정되고 두 번째 브러시의 속성이 로 <xref:System.Windows.Media.Stretch.UniformToFill>설정됩니다.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 다음 그림에서는 의 설정이 있는 첫 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 <xref:System.Windows.Media.Stretch.Uniform>브러시의 출력을 보여 주며, 이 브러시의 출력을 보여 주면 됩니다.  
  
 ![Uniform 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 다음 그림에서는 의 설정이 있는 두 <xref:System.Windows.Media.TileBrush.Stretch%2A> 번째 <xref:System.Windows.Media.Stretch.UniformToFill>브러시의 출력을 보여 주며, 이 두 번째 브러시의 출력을 보여 주면 됩니다.  
  
 ![UniformToFill 늘이기를 사용한 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 속성은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 다른 <xref:System.Windows.Media.TileBrush> 개체, 즉 에 대해 <xref:System.Windows.Media.DrawingBrush> 와 동일한 것으로 <xref:System.Windows.Media.VisualBrush>작동합니다. 및 기타 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.ImageBrush> 객체에 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
 또한 속성이 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.TileBrush> 출력 영역에 맞게 콘텐츠가 늘어나는 방법을 지정하는 것처럼 보이지만 실제로 <xref:System.Windows.Media.TileBrush> 는 콘텐츠가 기본 타일을 채우기 위해 늘어나는 방법을 지정합니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush>을 참조하세요.  
  
 이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다. 전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.TileBrush>
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
