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
ms.openlocfilehash: deac1be2fd19703055b76af8173111b4453f0d6b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186524"
---
# <a name="brush-transformation-overview"></a>브러시 변환 개요
Brush 클래스는 두 가지 <xref:System.Windows.Media.Brush.Transform%2A> <xref:System.Windows.Media.Brush.RelativeTransform%2A>변환 속성을 제공합니다. 이러한 속성을 사용하여 브러시의 콘텐츠를 회전, 비율 크기 조정, 기울이기 및 변환할 수 있습니다. 이 항목에서는 이러한 두 속성 간의 차이점을 설명하고 사용 예제를 제공합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 변환하는 브러시의 기능을 이해해야 합니다. 및 에 대한 [단색 및 그라데이션 개요와 그림을](painting-with-solid-colors-and-gradients-overview.md)참조하십시오. <xref:System.Windows.Media.RadialGradientBrush> <xref:System.Windows.Media.LinearGradientBrush> 에 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>대 <xref:System.Windows.Media.VisualBrush>한 , 또는 의 [이미지, 그림 및 시각적 개체와 함께 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오. [변환 개요](transforms-overview.md)에 설명된 2D 변환에도 익숙해야 합니다.  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Transform 및 RelativeTransform 속성 간 차이점  
 브러시 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 변환을 적용할 때 해당 중심에 대한 브러시 내용을 변환하려면 페인팅된 영역의 크기를 알아야 합니다. 그려지는 영역의 디바이스 독립적 픽셀 크기를 너비 200, 높이 150으로 가정합니다.  a를 <xref:System.Windows.Media.RotateTransform> 사용하여 브러시의 출력을 중심으로 45도 회전하는 경우 100과 75의 <xref:System.Windows.Media.RotateTransform> a를 <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> 지정합니다.  
  
 브러시 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 변환을 적용하면 출력이 페인팅된 영역에 매핑되기 전에 해당 변환이 브러시에 적용됩니다. 다음 목록에서는 브러시 콘텐츠가 처리되고 변환되는 순서를 보여 줍니다.  
  
1. 브러시의 콘텐츠를 처리합니다. 의 <xref:System.Windows.Media.GradientBrush>경우 그라데이션 영역을 결정하는 것을 의미합니다. 의 <xref:System.Windows.Media.TileBrush>경우 <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑됩니다. 이것이 브러시의 출력이 됩니다.  
  
2. 브러시의 출력을 1 x 1 변환 사각형에 프로젝션합니다.  
  
3. 브러시가 있는 <xref:System.Windows.Media.Brush.RelativeTransform%2A>경우 를 적용합니다.  
  
4. 변환된 출력을 그릴 영역에 프로젝션합니다.  
  
5. 브러시가 있는 <xref:System.Windows.Media.Transform>경우 를 적용합니다.  
  
 브러시의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 출력이 1 x 1 사각형에 매핑되는 동안 적용되므로 변환 중심 및 간격띄우기 값이 상대적인 것으로 나타납니다. 예를 <xref:System.Windows.Media.RotateTransform> 들어 a를 사용하여 브러시의 출력을 중심으로 45도 회전하는 경우 <xref:System.Windows.Media.RotateTransform> 0.5와 0.5의 a를 <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> 지정합니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용하여 45도 회전된 여러 브러시의 출력을 보여 주습니다.  
  
 ![RelativeTransform 및 Transform 속성](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>TileBrush에서 RelativeTransform 사용  
 타일 브러시는 다른 브러시보다 복잡하기 때문에 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 하나에 적용하면 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 다음 이미지를 살펴보세요.  
  
 ![소스 이미지](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> a를 사용하여 앞의 이미지와 함께 직사각형 영역을 페인팅합니다. <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.Brush.RelativeTransform%2A> 개체의 <xref:System.Windows.Media.RotateTransform> 속성에 a를 적용하고 해당 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch.UniformToFill>로 설정하여 사각형을 완전히 채우기 위해 늘어날 때 이미지의 가로 세로 비율을 유지해야 합니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 이 예에서 생성되는 출력은 다음과 같습니다.  
  
 ![변형된 출력](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 브러시가 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch.UniformToFill>로 설정되어 있더라도 이미지가 왜곡됩니다. 이는 브러시가 <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑된 후 상대 변환이 적용되기 때문입니다. 다음 목록에서는 프로세스의 각 단계를 설명합니다.  
  
1. 브러시의 설정을 사용하여<xref:System.Windows.Media.TileBrush.Viewbox%2A><xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.Stretch%2A> 브러시의 내용 ()을 기본 타일()에 투영합니다.  
  
     ![Viewbox를 뷰포트에 맞게 늘이기](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. 기본 타일을 1 x 1 변환 사각형에 프로젝션합니다.  
  
     ![뷰포트를 변환 사각형에 매핑](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. 을 <xref:System.Windows.Media.RotateTransform>적용합니다.  
  
     ![상대 변환 적용](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. 변환된 기본 타일을 그릴 영역에 프로젝션합니다.  
  
     ![변형된 브러시를 출력 영역으로 프로젝션](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>예제: ImageBrush를 45도 회전  
 다음 예제는 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 a를 적용합니다. <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterY%2A> 오브젝트와 속성은 모두 콘텐츠 중심점의 상대 좌표인 0.5로 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 설정됩니다. 결과적으로 브러시 콘텐츠는 중심을 기준으로 회전합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 다음 <xref:System.Windows.Media.RotateTransform> 예제에서는 <xref:System.Windows.Media.ImageBrush>에 a를 적용하지만 <xref:System.Windows.Media.Brush.Transform%2A> <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성 대신 속성을 사용합니다. 브러쉬를 중심을 중심으로 회전하려면 오브젝트의 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 좌표와 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 절대 좌표로 설정해야 합니다. 브러시에 의해 그려지는 사각형은 175 x 90 픽셀이기 때문에 중심점은 (87.5, 45)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 다음 그림에서는 변환이 없는 브러시와 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용된 변환 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 적용된 변환을 보여 주습니다.  
  
 ![Brush RelativeTransform 및 Transform 설정](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 브러시 [샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)참조하십시오. 브러시에 대한 자세한 내용은 [WPF 브러시 개요](wpf-brushes-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Transform 개요](transforms-overview.md)
