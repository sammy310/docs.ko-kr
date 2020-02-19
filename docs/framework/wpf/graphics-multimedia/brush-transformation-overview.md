---
title: 브러시 변환 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 1d3a56014e0975f3616b7f90021b4290ced5daab
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453132"
---
# <a name="brush-transformation-overview"></a>브러시 변환 개요
Brush 클래스는 <xref:System.Windows.Media.Brush.Transform%2A> 및 <xref:System.Windows.Media.Brush.RelativeTransform%2A>의 두 가지 변환 속성을 제공 합니다. 이러한 속성을 사용하여 브러시의 콘텐츠를 회전, 비율 크기 조정, 기울이기 및 변환할 수 있습니다. 이 항목에서는 이러한 두 속성 간의 차이점을 설명하고 사용 예제를 제공합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>사전 요구 사항  
 이 항목을 이해하려면 변환하는 브러시의 기능을 이해해야 합니다. <xref:System.Windows.Media.LinearGradientBrush> 및 <xref:System.Windows.Media.RadialGradientBrush>의 경우 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조 하세요. <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>또는 <xref:System.Windows.Media.VisualBrush>는 [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)를 참조 하세요. [변환 개요](transforms-overview.md)에 설명된 2D 변환에도 익숙해야 합니다.  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Transform 및 RelativeTransform 속성 간 차이점  
 브러시의 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 변환을 적용 하는 경우 해당 가운데에 대 한 브러시 콘텐츠를 변환 하려면 그려지는 영역의 크기를 알고 있어야 합니다. 그려지는 영역의 디바이스 독립적 픽셀 크기를 너비 200, 높이 150으로 가정합니다.  <xref:System.Windows.Media.RotateTransform>를 사용 하 여 중심을 기준으로 브러시의 45도를 회전 하면 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 100 및 75 <xref:System.Windows.Media.RotateTransform.CenterY%2A>를 제공 합니다.  
  
 브러시의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 변환을 적용 하는 경우 출력이 그리기 영역에 매핑되므로 해당 변환이 브러시에 적용 됩니다. 다음 목록에서는 브러시 콘텐츠가 처리되고 변환되는 순서를 보여 줍니다.  
  
1. 브러시의 콘텐츠를 처리합니다. <xref:System.Windows.Media.GradientBrush>이는 그라데이션 영역을 결정 하는 것입니다. <xref:System.Windows.Media.TileBrush>에 대 한 <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑됩니다. 이것이 브러시의 출력이 됩니다.  
  
2. 브러시의 출력을 1 x 1 변환 사각형에 프로젝션합니다.  
  
3. 브러시의 <xref:System.Windows.Media.Brush.RelativeTransform%2A>(있는 경우)을 적용 합니다.  
  
4. 변환된 출력을 그릴 영역에 프로젝션합니다.  
  
5. 브러시의 <xref:System.Windows.Media.Transform>(있는 경우)을 적용 합니다.  
  
 브러시의 출력이 1 x 1 사각형에 매핑되는 동안 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 적용 되므로 변환 중심 및 오프셋 값은 상대적으로 표시 됩니다. 예를 들어 <xref:System.Windows.Media.RotateTransform>를 사용 하 여 중심을 기준으로 브러시의 45도를 회전 하는 경우 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 0.5 및 0.5 <xref:System.Windows.Media.RotateTransform.CenterY%2A>를 제공 합니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용 하 여 45 각도로 회전 된 여러 브러시의 출력을 보여 줍니다.  
  
 ![RelativeTransform 및 Transform 속성](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>TileBrush에서 RelativeTransform 사용  
 타일 브러시는 다른 브러시 보다 더 복잡 하기 때문에 <xref:System.Windows.Media.Brush.RelativeTransform%2A>를 적용 하면 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 다음 이미지를 살펴보세요.  
  
 ![원본 이미지](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 다음 예에서는 <xref:System.Windows.Media.ImageBrush>를 사용 하 여 앞의 이미지로 사각형 영역을 그립니다. <xref:System.Windows.Media.ImageBrush> 개체의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 <xref:System.Windows.Media.RotateTransform>를 적용 하 고 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch.UniformToFill>로 설정 합니다 .이 속성은 사각형을 완전히 채우도록 스트레치 될 때 이미지의 가로 세로 비율을 유지 해야 합니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 이 예에서 생성되는 출력은 다음과 같습니다.  
  
 ![변환 된 출력입니다.](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch.UniformToFill>설정 된 경우에도 이미지가 비틀어 지는 것을 알 수 있습니다. 이는 브러시의 <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑된 후에 상대 변환이 적용 되기 때문입니다. 다음 목록에서는 프로세스의 각 단계를 설명합니다.  
  
1. 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정을 사용 하 여 브러시의 콘텐츠 (<xref:System.Windows.Media.TileBrush.Viewbox%2A>)를 기본 타일 (<xref:System.Windows.Media.TileBrush.Viewport%2A>)에 프로젝션 합니다.  
  
     ![뷰포트에 맞게 Viewbox 늘이기](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. 기본 타일을 1 x 1 변환 사각형에 프로젝션합니다.  
  
     ![뷰포트를 변환 사각형에 매핑](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. <xref:System.Windows.Media.RotateTransform>을 적용 합니다.  
  
     ![상대 변형 적용](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. 변환된 기본 타일을 그릴 영역에 프로젝션합니다.  
  
     ![변환 된 브러시를 출력 영역으로 프로젝션](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>예제: ImageBrush를 45도 회전  
 다음 예에서는 <xref:System.Windows.Media.RotateTransform>를 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용 합니다. <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 모두 콘텐츠 중심점의 상대 좌표로 0.5로 설정 됩니다. 결과적으로 브러시 콘텐츠는 중심을 기준으로 회전합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>에도 <xref:System.Windows.Media.RotateTransform> 적용 하지만 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성 대신 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용 합니다. 브러시를 중심으로 회전 하려면 <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 절대 좌표로 설정 되어야 합니다. 브러시에 의해 그려지는 사각형은 175 x 90 픽셀이기 때문에 중심점은 (87.5, 45)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 다음 그림에서는 변환이 없는 브러시를 보여 줍니다. 변환은 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용 되 고 변환은 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 적용 됩니다.  
  
 ![Brush RelativeTransform 및 변환 설정](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플을 보려면 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조하세요. 브러시에 대한 자세한 내용은 [WPF 브러시 개요](wpf-brushes-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Transform 개요](transforms-overview.md)
