---
title: Transform 개요
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111961"
---
# <a name="transforms-overview"></a>Transform 개요
이 항목에서는 2D <xref:System.Windows.Media.Transform> 클래스를 사용하여 객체를 회전, 배율 <xref:System.Windows.FrameworkElement> 조정, 이동(변환) 및 기울이는 방법을 설명합니다.  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>변환이란?  
 A는 <xref:System.Windows.Media.Transform> 한 좌표 공간에서 다른 좌표 공간으로 점을 매핑하거나 변환하는 방법을 정의합니다. 이 매핑은 값의 <xref:System.Windows.Media.Matrix>세 열이 있는 세 행의 <xref:System.Double> 컬렉션인 변환에 의해 설명됩니다.  
  
> [!NOTE]
> WPF(Windows 프레젠테이션 파운데이션)는 행-주요 행렬을 사용합니다. 벡터는 열 벡터가 아니라 행 벡터로 표시됩니다.  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 행렬의 구조를 보여 줍니다.  
  
### <a name="a-2d-transformation-matrix"></a>2D 변환 매트릭스  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 기본값: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 기본값: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 기본값: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 기본값: 0.0|1.0|  
  
 행렬 값을 조작하여 개체를 회전, 크기 조정, 기울이기 및 이동(변환)할 수 있습니다. 예를 들어 세 번째 행의 첫 번째 <xref:System.Windows.Media.Matrix.OffsetX%2A> 열(값)의 값을 100으로 변경하면 x축을 따라 객체 100 단위를 이동할 수 있습니다. 두 번째 행의 두 번째 열에 있는 값을 3으로 변경하는 경우 이를 사용하여 개체를 현재 높이의 3배로 늘릴 수 있습니다. 두 값을 모두 변경하는 경우 x축을 따라 100개 단위씩 개체가 이동되고 높이가 3배로 늘어납니다. WPF(Windows 프레젠테이션 파운데이션)는 affine 변환만 지원하므로 오른쪽 열의 값은 항상 0, 0, 1입니다.  
  
 WPF(Windows 프레젠테이션 Foundation)를 사용하면 행렬 값을 직접 조작할 <xref:System.Windows.Media.Transform> 수 있지만 기본 행렬 구조가 어떻게 구성되는지 모르고 개체를 변환할 수 있는 여러 클래스도 제공합니다. 예를 들어 <xref:System.Windows.Media.ScaleTransform> 클래스를 사용하면 변환 행렬을 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 조작하는 대신 객체와 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성을 설정하여 개체의 배율을 조정할 수 있습니다. 마찬가지로 클래스를 <xref:System.Windows.Media.RotateTransform> 사용하면 속성을 설정하기만 하면 <xref:System.Windows.Media.RotateTransform.Angle%2A> 개체를 회전할 수 있습니다.  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>변환 클래스  
 WPF(Windows 프레젠테이션 재단)는 일반적인 <xref:System.Windows.Media.Transform> 변환 작업에 대해 다음과 같은 2D 클래스를 제공합니다.  
  
|클래스|Description|예제|그림|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|지정된 <xref:System.Windows.Media.RotateTransform.Angle%2A>요소별로 요소를 회전합니다.|[개체 회전](how-to-rotate-an-object.md)|![회전 설명](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|지정된 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 양과 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 양으로 요소를 배율 조정합니다.|[요소 배율 조정](how-to-scale-an-element.md)|![배율 조정 설명](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|요소를 지정된 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 양과 양으로 왜곡합니다. <xref:System.Windows.Media.SkewTransform.AngleY%2A>|[요소 기울이기](how-to-skew-an-element.md)|![기울이기 설명](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|지정된 <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform.Y%2A> 양으로 요소를 이동(변환)합니다.|[요소 변환](how-to-translate-an-element.md)|![변환 설명](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 보다 복잡한 변환을 만들기 위해 WPF(Windows 프레젠테이션 재단)는 다음 두 가지 클래스를 제공합니다.  
  
|클래스|Description|예제|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|여러 <xref:System.Windows.Media.TransformGroup> 객체를 단일 <xref:System.Windows.Media.Transform> 객체로 그룹화한 다음 속성을 변환하기 위해 적용할 수 있습니다.|[개체에 다중 변환 적용](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|다른 <xref:System.Windows.Media.Transform> 클래스에서 제공하지 않는 사용자 지정 변환을 만듭니다. 을 <xref:System.Windows.Media.MatrixTransform>사용하면 행렬을 직접 조작합니다.|[MatrixTransform을 사용하여 사용자 지정 변환 만들기](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 WPF(Windows 프레젠테이션 파운데이션)는 3D 변환도 제공합니다. 자세한 내용은 <xref:System.Windows.Media.Media3D.Transform3D> 클래스를 참조하세요.  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>사용자 지정 변환 속성  
 개체를 변환하는 한 가지 방법은 <xref:System.Windows.Media.Transform> 적절한 형식을 선언하고 개체의 변환 속성에 적용하는 것입니다. 개체의 형식이 다르면 변환 속성 형식도 다릅니다. 다음 표에는 일반적으로 사용되는 WPF(Windows 프레젠테이션 파운데이션) 형식 과 해당 변환 속성이 나열되어 있습니다.  
  
|Type|변환 속성|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>
## <a name="transformations-and-coordinate-systems"></a>변환 및 좌표계  
 개체를 변환하는 경우 개체만 단지 변환하는 것이 아니라 개체가 있는 좌표 공간을 변환하게 됩니다. 기본적으로 변환은 대상 개체의 좌표계 원점 (0,0)을 중심으로 합니다. 유일한 예외는 <xref:System.Windows.Media.TranslateTransform>; a에는 <xref:System.Windows.Media.TranslateTransform> 변환 효과가 중심위치에 관계없이 동일하기 때문에 설정할 중심 속성이 없습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform> a를 <xref:System.Windows.Shapes.Rectangle> 사용하여 기본 중심(0, 0)에 대해 <xref:System.Windows.FrameworkElement>45도씩 요소(의 유형)를 회전시킵니다. 다음 그림에서는 회전의 결과를 보여 줍니다.  
  
 ![&#40;0,0&#41;을 기준으로 45도 회전된 FrameworkElement](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
점 (0,0)을 기준으로 45도 회전된 Rectangle 요소  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 기본적으로 요소는 왼쪽 위 구석 (0,0)을 기준으로 회전합니다. 및 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ScaleTransform> <xref:System.Windows.Media.SkewTransform> 클래스는 변환이 적용되는 지점을 지정할 수 있는 CenterX 및 CenterY 속성을 제공합니다.  
  
 다음 예제에서는 a를 <xref:System.Windows.Media.RotateTransform> 사용하여 <xref:System.Windows.Shapes.Rectangle> 요소를 45도 회전합니다. 그러나, 이번에는 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 속성이 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 중심(25, 25)을 <xref:System.Windows.Media.RotateTransform> 가지게 되도록 설정된다. 다음 그림에서는 회전의 결과를 보여 줍니다.  
  
 ![&#40;25, 25&#41;를 기준으로 45도 회전된 기하 도형](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
점 (25, 25)를 기준으로 45도 회전된 Rectangle 요소  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>FrameworkElement 변환  
 <xref:System.Windows.FrameworkElement>에 변환을 적용하려면 을 <xref:System.Windows.Media.Transform> 만들고 클래스가 <xref:System.Windows.FrameworkElement> 제공하는 두 속성 중 하나에 적용합니다.  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– 레이아웃이 통과하기 전에 적용되는 변환입니다. 이 변환을 적용된 후 레이아웃 시스템은 요소의 변환된 크기와 위치를 처리합니다.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>– 요소의 모양을 수정하지만 레이아웃 통과가 완료된 후 적용되는 변환입니다. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성 대신 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용하면 성능 이점을 얻을 수 있습니다.  
  
 어떤 속성을 사용해야 할까요? 성능상의 이점 때문에 가능하면, <xref:System.Windows.UIElement.RenderTransform%2A> 특히 애니메이션 <xref:System.Windows.Media.Transform> 오브젝트를 사용할 때 속성을 사용합니다. 크기 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 조정, 회전 또는 기울이기 할 때 속성을 사용하고 요소의 부모가 요소의 변형된 크기에 맞게 조정해야 합니다. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성과 함께 사용될 때 <xref:System.Windows.Media.TranslateTransform> 객체는 요소에 영향을 주지 않는 것처럼 보입니다. 레이아웃 시스템이 변환된 요소를 처리 과정의 일부로 원래 위치로 되돌리기 때문입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 레이아웃에 대한 추가 정보를 보려면 [레이아웃](../advanced/layout.md) 개요를 참조하세요.  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>예제: FrameworkElement를 45도로 회전  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform> a를 사용하여 버튼을 시계 방향으로 45도 회전합니다. 단추는 두 개의 <xref:System.Windows.Controls.StackPanel> 다른 버튼이 있는 에 포함되어 있습니다.  
  
 기본적으로 점은 <xref:System.Windows.Media.RotateTransform> 점(0, 0)을 가리킵니다. 이 예제에서는 중심 값을 지정하지 않으므로 단추는 왼쪽 위 구석에 해당하는 점 (0,0)에 대해 회전합니다. 는 <xref:System.Windows.Media.RotateTransform> 속성에 <xref:System.Windows.UIElement.RenderTransform%2A> 적용됩니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![RenderTransform을 사용하여 변환된 단추](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
왼쪽 위 구석에서 시계 방향으로 45도 회전  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 다음 예제에서는 a를 <xref:System.Windows.Media.RotateTransform> 사용하여 버튼을 시계 방향으로 45도 회전하지만 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 단추의 집합도 (0.5, 0.5)으로 설정합니다. 속성값은 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 단추 크기를 기준으로 합니다. 결과적으로, 회전은 왼쪽 위 구석 대신 단추의 중심에 적용됩니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![가운데를 중심으로 변환된 단추](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
중심을 기준으로 시계 방향으로 45도 회전  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성 대신 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용하여 단추를 회전합니다.  그러면 변환이 단추의 레이아웃에 영향을 미쳐 레이아웃 시스템의 전체 패스를 트리거합니다. 결과적으로 크기가 변경되었기 때문에 단추는 회전한 다음 재배치됩니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![LayoutTransform을 사용하여 변환된 단추](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
단추 회전에 사용된 LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>변환에 애니메이션 효과 주기  
 <xref:System.Windows.Media.Animation.Animatable> 클래스에서 상속하기 때문에 <xref:System.Windows.Media.Transform> 클래스를 애니메이션할 수 있습니다. <xref:System.Windows.Media.Transform>에 애니메이션을 적용하려면 애니메이션할 속성에 호환되는 형식의 애니메이션을 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> a와 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.RotateTransform> a를 사용하여 <xref:System.Windows.Controls.Button> 클릭할 때 스핀을 제자리에 배치합니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오. 애니메이션에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Freezable 기능  
 클래스에서 상속하기 때문에 클래스는 <xref:System.Windows.Media.Transform> 여러 가지 <xref:System.Windows.Media.Transform> 특수 기능을 제공합니다: 개체를 [리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언하고, 여러 개체 간에 공유되고, 읽기 전용으로 만들어 성능을 향상시키고, 복제하고, 스레드를 안전하게 만들었습니다. <xref:System.Windows.Freezable> 개체에서 <xref:System.Windows.Freezable> 제공하는 다양한 기능에 대한 자세한 내용은 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [방법 주제](transformations-how-to-topics.md)
- [2D 변환 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
