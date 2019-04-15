---
title: Transform 개요
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: 6f7cbd91be83c96b25248f87ddc377159ba39b64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162206"
---
# <a name="transforms-overview"></a>Transform 개요
이 항목에서는 사용 하는 방법을 설명 합니다 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> 회전, 크기 조정, 이동 하는 클래스 (변환) 및 기울이기 <xref:System.Windows.FrameworkElement> 개체입니다.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>변환이란?  
 <xref:System.Windows.Media.Transform> 매핑하거나 점을 하나의 좌표 공간에서 다른 좌표 공간으로 변환 하는 방법을 정의 합니다. 이 매핑은 변환에서 설명한 <xref:System.Windows.Media.Matrix>, 세 개의 열을 사용 하 여 3 개 행의 모음인 <xref:System.Double> 값입니다.  
  
> [!NOTE]
>  Windows Presentation Foundation (WPF) 행 중심 행렬을 사용합니다. 벡터는 열 벡터가 아니라 행 벡터로 표시됩니다.  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 행렬의 구조를 보여 줍니다.  
  
### <a name="a-2-d-transformation-matrix"></a>2차원 변형 행렬  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 기본값: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 기본값: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 기본값: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 기본값: 0.0|1.0|  
  
 행렬 값을 조작하여 개체를 회전, 크기 조정, 기울이기 및 이동(변환)할 수 있습니다. 예를 들어, 세 번째 행의 첫 번째 열에서 값을 변경 하는 경우 (의 <xref:System.Windows.Media.Matrix.OffsetX%2A> 값) 100으로 사용할 수 있습니다는 개체가 100 단위 x 축 따라 이동 합니다. 두 번째 행의 두 번째 열에 있는 값을 3으로 변경하는 경우 이를 사용하여 개체를 현재 높이의 3배로 늘릴 수 있습니다. 두 값을 모두 변경하는 경우 x축을 따라 100개 단위씩 개체가 이동되고 높이가 3배로 늘어납니다. Windows Presentation Foundation (WPF)를는 affine 변환만 지원 하므로 오른쪽 열의 값은 항상 0, 0, 1.  
  
 Windows Presentation Foundation (WPF)를 사용 하면 행렬 값을 직접 조작할 수 있습니다, 있지만 제공 여러 <xref:System.Windows.Media.Transform> 기본 행렬 구조의 구성 방식을 알지 못해도 개체를 변환 하는 데 사용할 수 있는 클래스입니다. 예를 들어 합니다 <xref:System.Windows.Media.ScaleTransform> 클래스 설정 하 여 개체를 확장할 수 있습니다 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 변환 행렬을 조작 하는 대신 속성입니다. 마찬가지로 합니다 <xref:System.Windows.Media.RotateTransform> 클래스를 사용 하면 간단히 설정 하 여 개체를 회전 하 고 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>변환 클래스  
 Windows Presentation Foundation (WPF) 다음 기능을 제공 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> 일반적인 변환 작업에 대 한 클래스:  
  
|클래스|설명|예제|그림|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|지정 된 요소를 회전 <xref:System.Windows.Media.RotateTransform.Angle%2A>합니다.|[개체 회전](how-to-rotate-an-object.md)|![회전 그림](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|지정 된 요소 크기를 조정 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 고 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 금액입니다.|[요소 배율 조정](how-to-scale-an-element.md)|![배율 조정 그림](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|지정 된 요소를 기울입니다 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 고 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 금액입니다.|[요소 기울이기](how-to-skew-an-element.md)|![기울이기 그림](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|이동 (변환)에 지정 된 요소가 <xref:System.Windows.Media.TranslateTransform.X%2A> 및 <xref:System.Windows.Media.TranslateTransform.Y%2A> 금액입니다.|[요소 변환](how-to-translate-an-element.md)|![변환 그림](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 더 복잡 한 변환을 만들기 위해 Windows Presentation Foundation (WPF)는 다음 두 클래스를 제공 합니다.  
  
|클래스|설명|예제|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|여러 그룹화 <xref:System.Windows.Media.TransformGroup> 개체를 하나의 <xref:System.Windows.Media.Transform> 그런 다음 변환 속성에 적용할 수 있습니다.|[개체에 다중 변환 적용](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|다른 사람이 제공 되지 않는 사용자 지정 변환을 만듭니다 <xref:System.Windows.Media.Transform> 클래스입니다. 사용 하는 경우는 <xref:System.Windows.Media.MatrixTransform>에 행렬을 직접 조작 합니다.|[MatrixTransform을 사용하여 사용자 지정 변환 만들기](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF)에서는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 변환 합니다. 자세한 내용은 <xref:System.Windows.Media.Media3D.Transform3D> 클래스를 참조하세요.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>사용자 지정 변환 속성  
 적절 한 선언 하는 개체를 변환 하는 한 가지 방법은 것 <xref:System.Windows.Media.Transform> 형식과 개체의 변환 속성에 적용 합니다. 개체의 형식이 다르면 변환 속성 형식도 다릅니다. 다음 표에서 몇 가지 자주 사용 되는 Windows Presentation Foundation (WPF) 형식과 해당 변환 속성이 나와 있습니다.  
  
|형식|변환 속성|  
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
 개체를 변환하는 경우 개체만 단지 변환하는 것이 아니라 개체가 있는 좌표 공간을 변환하게 됩니다. 기본적으로 변환은 대상 개체의 좌표계의 원점을 중심이: (0,0). 유일한 예외는 <xref:System.Windows.Media.TranslateTransform>는 <xref:System.Windows.Media.TranslateTransform> 번역 효과 가운데 위치에 관계 없이 동일 하기 때문에 설정할 중심 속성이 없습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform> 회전 하는 <xref:System.Windows.Shapes.Rectangle> 요소, 형식의 <xref:System.Windows.FrameworkElement>를 기본 중심에서 45도 각도로 (0, 0). 다음 그림에서는 회전의 결과를 보여 줍니다.  
  
 ![45도 회전 시킨 FrameworkElement &#40;0, 0&#41;](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
점 (0,0)을 기준으로 45도 회전된 Rectangle 요소  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 기본적으로 요소는 왼쪽 위 구석 (0,0)을 기준으로 회전합니다. 합니다 <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>, 및 <xref:System.Windows.Media.SkewTransform> 클래스는 변환이 적용 되는 시점을 지정할 수 있도록 하는 CenterX 및 CenterY 속성을 제공 합니다.  
  
 그러나 다음 예제에서는 또한 사용 하 여를 <xref:System.Windows.Media.RotateTransform> 회전 하는 <xref:System.Windows.Shapes.Rectangle> 45도 각도로; 요소이 이번을 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성이 설정 되어 있도록는 <xref:System.Windows.Media.RotateTransform> 의 가운데에 (25, 25). 다음 그림에서는 회전의 결과를 보여 줍니다.  
  
 ![45도 회전 시킨 기 하 도형 &#40;25, 25&#41;](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
점 (25, 25)를 기준으로 45도 회전된 Rectangle 요소  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>FrameworkElement 변환  
 에 변환을 적용 하는 <xref:System.Windows.FrameworkElement>를 만들기는 <xref:System.Windows.Media.Transform> 두 속성 중 하나에 적용 하는 <xref:System.Windows.FrameworkElement> 클래스를 제공:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – 레이아웃 패스 전에 적용 되는 변환입니다. 이 변환을 적용된 후 레이아웃 시스템은 요소의 변환된 크기와 위치를 처리합니다.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> – 요소의 모양을 수정 하지만 레이아웃 패스가 완료 된 후에 적용 되는 변환입니다. 사용 하 여 합니다 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 대신는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성인 성능상의 이점을 얻을 수 있습니다.  
  
 어떤 속성을 사용해야 할까요? 제공 하는 성능상의 이점 때문에 사용할 합니다 <xref:System.Windows.UIElement.RenderTransform%2A> 가능 하면 사용 하는 경우에 특히 애니메이션 효과가 적용 될 때마다 속성 <xref:System.Windows.Media.Transform> 개체입니다. 사용 된 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성 크기 조정, 회전, 기울이기 해야 요소의 변환 된 크기로 조정 하는 요소의 부모입니다. 사용 될 때는 합니다 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성인 <xref:System.Windows.Media.TranslateTransform> 개체 요소에 아무 효과도 없는 것 같습니다. 레이아웃 시스템이 변환된 요소를 처리 과정의 일부로 원래 위치로 되돌리기 때문입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 레이아웃에 대한 추가 정보를 보려면 [레이아웃](../advanced/layout.md) 개요를 참조하세요.  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>예제: FrameworkElement 회전 45도  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform> 단추를 시계 방향으로 45도 회전 합니다. 단추에 포함 된를 <xref:System.Windows.Controls.StackPanel> 는 2 개의 다른 단추가 있습니다.  
  
 기본적으로 <xref:System.Windows.Media.RotateTransform> 점 (0, 0)으로 회전 합니다. 이 예제에서는 중심 값을 지정하지 않으므로 단추는 왼쪽 위 구석에 해당하는 점 (0,0)에 대해 회전합니다. 합니다 <xref:System.Windows.Media.RotateTransform> 에 적용 되는 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![RenderTransform을 사용 하 여 변형 된 단추](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
왼쪽 위 구석에서 시계 방향으로 45도 회전  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 다음 예제에서는 또한 사용 하 여는 <xref:System.Windows.Media.RotateTransform> 설정도 하지만 단추를 시계 방향으로 45도 회전 하는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 단추 (0.5, 0.5)입니다. 값을 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성은 단추의 크기를 기준으로 합니다. 결과적으로, 회전은 왼쪽 위 구석 대신 단추의 중심에 적용됩니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![가운데를 중심으로 변형 된 단추](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
중심을 기준으로 시계 방향으로 45도 회전  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 다음 예제에서는 합니다 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성 대신는 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 단추를 회전 합니다.  그러면 변환이 단추의 레이아웃에 영향을 미쳐 레이아웃 시스템의 전체 패스를 트리거합니다. 결과적으로 크기가 변경되었기 때문에 단추는 회전한 다음 재배치됩니다. 다음 그림에서는 변환의 결과를 보여 줍니다.  
  
 ![LayoutTransform을 사용 하 여 변형 된 단추](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
단추 회전에 사용된 LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>변환에 애니메이션 효과 주기  
 상속 되는 <xref:System.Windows.Media.Animation.Animatable> 클래스는 <xref:System.Windows.Media.Transform> 클래스에 애니메이션을 적용할 수 있습니다. 애니메이션 효과를 주는 <xref:System.Windows.Media.Transform>에 애니메이션 효과 주려는 속성에 호환 가능한 형식의 애니메이션을 적용 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.DoubleAnimation> 사용 하 여를 <xref:System.Windows.Media.RotateTransform> 있도록를 <xref:System.Windows.Controls.Button> 클릭 했을 때 현재 위치에서 회전 합니다.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 전체 샘플을 보려면 [2차원 변환 샘플](https://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요. 애니메이션에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Freezable 기능  
 상속 하므로 합니다 <xref:System.Windows.Freezable> 클래스를 <xref:System.Windows.Media.Transform> 몇 가지 특별 한 기능을 제공 하는 클래스: <xref:System.Windows.Media.Transform> 로 개체를 선언할 수 있습니다 [리소스](../advanced/xaml-resources.md)개선 하기 위해 읽기 전용으로, 여러 개체 간에 공유 성능, 복제 하 고 스레드로부터 안전 합니다. 제공 하는 다양 한 기능에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [방법 항목](transformations-how-to-topics.md)
- [2 차원 변환 샘플](https://go.microsoft.com/fwlink/?LinkID=158252)
