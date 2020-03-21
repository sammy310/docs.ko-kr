---
title: 불투명 마스크 개요
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: 0c859659c35e2a5806b8585214c87c18fbcb62d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187684"
---
# <a name="opacity-masks-overview"></a>불투명 마스크 개요
불투명 마스크를 사용하여 요소 또는 시각적 개체의 부분을 투명하게 또는 부분적으로 투명하게 만들 수 있습니다. 불투명도 마스크를 만들려면 요소 또는 <xref:System.Windows.Media.Brush> 의 <xref:System.Windows.UIElement.OpacityMask%2A> 속성에 a를 적용합니다. <xref:System.Windows.Media.Visual>  브러시가 요소 또는 시각적 개체에 매핑되고, 각 브러시 픽셀의 불투명도 값을 사용하여 요소 또는 시각적 개체의 각 해당 픽셀에 대한 결과 불투명도가 결정됩니다.  
  
<a name="prereqs"></a>
## <a name="prerequisites"></a>전제 조건  
 이 개요에서는 개체에 익숙하다고 <xref:System.Windows.Media.Brush> 가정합니다. 브러시 사용에 대한 지침을 보려면 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조하세요. 및 <xref:System.Windows.Media.DrawingBrush>에 <xref:System.Windows.Media.ImageBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="opacitymasks"></a>
## <a name="creating-visual-effects-with-opacity-masks"></a>불투명 마스크를 사용하여 시각 효과 만들기  
 불투명 마스크는 요소 또는 시각적 개체에 콘텐츠를 매핑하여 작동합니다. 그런 후 각 브러시의 픽셀의 알파 채널을 사용하여 요소 또는 시각적 개체의 해당 픽셀에 대한 결과 불투명도를 결정하며 브러시의 실제 색은 무시됩니다. 브러시의 특정 부분이 투명하면 요소 또는 시각적 개체의 해당 부분도 투명해 집니다. 브러시의 특정 부분이 불투명하면 요소 또는 시각적 개체의 해당 부분에 대한 불투명도는 달라지지 않습니다. 불투명 마스크로 지정된 불투명도는 요소 또는 시각적 개체의 불투명도 설정과 조합됩니다. 예를 들어 요소가 25% 불투명하고 완전 불투명에서 완전 투명으로 전환되는 불투명 마스크가 적용되면 요소는 25% 불투명에서 완전 투명으로 전환됩니다.  
  
> [!NOTE]
> 이 개요의 예제에서는 이미지 요소에 불투명도 마스크의 사용을 보여 주지만 불투명도 마스크는 패널 <xref:System.Windows.Media.Visual>및 컨트롤을 포함한 모든 요소 또는 요소에 적용될 수 있습니다.  
  
 불투명 마스크는 보기에서 페이드되는 이미지나 단추를 만들거나, 요소에 질감을 추가하거나, 그라데이션을 조합하여 유리같은 표면을 생성하는 등의 흥미로운 시각 효과를 만드는 데 사용됩니다. 다음 그림에서는 불투명 마스크의 사용을 보여 줍니다. 마스크의 투명한 부분을 표시하는 데 바둑판 배경이 사용됩니다.  
  
 ![LinearGradientBrush 불투명 마스크가 있는 개체](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
불투명 마스크 예제  
  
<a name="creatingopacitymasks"></a>
## <a name="creating-an-opacity-mask"></a>불투명 마스크 만들기  
 불투명도 마스크를 작성하려면 요소를 작성하고 <xref:System.Windows.Media.Brush> 요소 또는 <xref:System.Windows.UIElement.OpacityMask%2A> 시각적 개체의 속성에 적용합니다. 모든 유형의 <xref:System.Windows.Media.Brush> 불투명도 마스크를 사용할 수 있습니다.  
  
- <xref:System.Windows.Media.LinearGradientBrush>: <xref:System.Windows.Media.RadialGradientBrush>요소 또는 시각적 페이드를 보기에서 페이드하는 데 사용됩니다.  
  
     다음 이미지는 불투명도 마스크로 <xref:System.Windows.Media.LinearGradientBrush> 사용되는 것을 보여 주며,  
  
     ![LinearGradientBrush 불투명 마스크가 있는 개체](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
LinearGradientBrush 불투명 마스크 예제  
  
- <xref:System.Windows.Media.ImageBrush>: 질감과 부드럽고 찢어진 가장자리 효과를 만드는 데 사용됩니다.  
  
     다음 이미지는 불투명도 마스크로 <xref:System.Windows.Media.ImageBrush> 사용되는 것을 보여 주며,  
  
     ![ImageBrush 불투명 마스크가 있는 개체](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
LinearGradientBrush 불투명 마스크 예제  
  
- <xref:System.Windows.Media.DrawingBrush>: 모양, 이미지 및 그라데이션 패턴에서 복잡한 불투명도 마스크를 만드는 데 사용됩니다.  
  
     다음 이미지는 불투명도 마스크로 <xref:System.Windows.Media.DrawingBrush> 사용되는 것을 보여 주며,  
  
     ![DrawingBrush 불투명 마스크가 있는 개체](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
DrawingBrush 불투명 마스크 예제  
  
 그라데이션 브러쉬(및)는<xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush>특히 불투명도 마스크로 사용하기에 적합합니다. 영역을 <xref:System.Windows.Media.SolidColorBrush> 균일한 색상으로 채우기 때문에 불투명도 마스크가 불량합니다. 를 <xref:System.Windows.Media.SolidColorBrush> 사용하는 것은 요소 또는 시각적 개체의 <xref:System.Windows.UIElement.OpacityMask%2A> 속성을 설정하는 것과 같습니다.  
  
<a name="creatingopacitymaskswithgradients"></a>
## <a name="using-a-gradient-as-an-opacity-mask"></a>그라데이션을 불투명 마스크로 사용  
 그라데이션 채우기를 만들려면 두 개 이상의 그라데이션 중지점을 지정합니다. 각 그라데이션 중지점은 색과 위치에 대한 설명을 포함합니다(그라데이션 만들기 및 사용에 대한 자세한 내용은 [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md) 참조). 해당 프로세스는 불투명 마스크 그라데이션이 색을 혼합하는 대신, 알파 채널 값을 혼합한다는 점을 제외한다면 그라데이션을 불투명 마스크로 사용할 때와 같습니다. 따라서 그라데이션의 콘텐츠의 실제 색은 중요하지 않으며 각 색의 알파 채널 또는 불투명도만 중요합니다. 다음은 이에 대한 예입니다.  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>불투명 마스크에 대한 그라데이션 중지점 지정  
 이전 예제에서는 시스템 정의 색상이 <xref:System.Windows.Media.Colors.Black%2A> 그라데이션의 시작 색상으로 사용됩니다. 을 제외한 <xref:System.Windows.Media.Colors> <xref:System.Windows.Media.Colors.Transparent%2A>클래스의 모든 색상은 완전히 불투명하므로 그라데이션 불투명도 마스크의 시작 색상을 정의하는 데 사용할 수 있습니다.  
  
 불투명도 마스크를 정의할 때 알파 값을 추가로 제어하려면 태그에서 ARGB 육각표 표기법을 사용하거나 메서드를 <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> 사용하여 알파 색 채널을 지정할 수 있습니다.  
  
<a name="argbsyntax"></a>
### <a name="specifying-color-opacity-in-xaml"></a>"XAML"에서 색 불투명도 지정  
 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ARGB 육각표 표기형을 사용하여 개별 색상의 불투명도를 지정합니다. ARGB 육각표 표기법은 다음 구문을 사용합니다.  
  
 `#` **aa** *rrggbb*  
  
 이전 줄의 *aa*는 색의 불투명도 지정하는 데 사용되는 2자리 16진수 값을 나타냅니다. *rr*, *gg* 및 *bb* 각각은 색에서 빨강, 녹색 및 파랑의 양을 지정하는 데 사용되는 2자리 16진수 값을 나타냅니다. 각 16진수 숫자는 0-9 또는 A-F의 값을 가질 수 있습니다. 0이 가장 작은 값이고 F가 가장 큰 값입니다. 알파 값 00은 완전히 투명한 색을 지정하지만 알파 값 FF는 완전히 불투명한 색을 만듭니다.  다음 예제에서는 육각형 ARGB 표기명이 두 가지 색상을 지정하는 데 사용됩니다. 첫 번째는 완전히 불투명하고 두 번째는 완전히 투명합니다.  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>
## <a name="using-an-image-as-an-opacity-mask"></a>이미지를 불투명 마스크로 사용  
 이미지를 불투명 마스크로 사용할 수도 있습니다. 다음 이미지에 예가 나와 있습니다. 마스크의 투명한 부분을 표시하는 데 바둑판 배경이 사용됩니다.  
  
 ![ImageBrush 불투명 마스크가 있는 개체](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
불투명 마스크 예제  
  
 이미지를 불투명 마스크로 사용하려면 이미지를 포함하려면 를 <xref:System.Windows.Media.ImageBrush> 사용합니다. 불투명 마스크로 사용할 이미지를 만들 때 PNG(휴대용 네트워크 그래픽)와 같은 여러 수준의 투명도를 지원하는 형식으로 이미지를 저장합니다. 다음 예제에서는 이전 그림을 만드는 데 사용된 코드를 보여 줍니다.  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>바둑판식 배열 이미지를 불투명 마스크로 사용  
 다음 예제에서는 동일한 이미지가 다른 <xref:System.Windows.Media.ImageBrush>이미지와 함께 사용되지만 브러시의 타일링 피쳐는 이미지 50픽셀 정사각형의 타일을 생성하는 데 사용됩니다.  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>
## <a name="creating-an-opacity-mask-from-a-drawing"></a>그리기에서 불투명 마스크 만들기  
 그리기를 불투명 마스크로 사용할 수 있습니다. 그리기 내에 포함된 도형 자체를 그라데이션, 단색, 이미지, 심지어 다른 그리기로 채울 수 있습니다. 다음 그림에서는 불투명 마스크로 사용되는 그리기 예제를 보여 줍니다. 마스크의 투명한 부분을 표시하는 데 바둑판 배경이 사용됩니다.  
  
 ![DrawingBrush 불투명 마스크가 있는 개체](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
DrawingBrush 불투명 마스크 예제  
  
 도면을 불투명 마스크로 사용하려면 를 <xref:System.Windows.Media.DrawingBrush> 사용하여 도면을 포함합니다. 다음 예제에서는 이전 그림을 만드는 데 사용된 코드를 보여 줍니다.  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>바둑판식 배열 그리기를 불투명 마스크로 사용  
 와 <xref:System.Windows.Media.ImageBrush>마찬가지로 <xref:System.Windows.Media.DrawingBrush> 드로잉을 타일로 배열할 수 있습니다. 다음 예제에서는 그리기 브러시를 사용하여 바둑판식으로 배열된 불투명 마스크를 만듭니다.  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>참고 항목

- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
