---
title: 그래픽 및 멀티미디어
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112039"
---
# <a name="graphics-and-multimedia"></a>그래픽 및 멀티미디어

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 멀티미디어, 벡터 그래픽, 애니메이션 및 콘텐츠 컴퍼지션을 지원하여 개발자가 흥미로운 사용자 인터페이스 및 콘텐츠를 쉽게 작성할 수 있도록 합니다. Visual Studio를 사용하여 벡터 그래픽 또는 복잡한 애니메이션을 만들고 응용 프로그램에 미디어를 통합할 수 있습니다.

이 항목에서는 그래픽, 전환 효과, 소리 및 비디오를 애플리케이션에 추가할 수 있도록 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 그래픽, 애니메이션 및 미디어 기능을 소개합니다.

> [!NOTE]
> Windows 서비스에서 WPF 유형을 사용해서는 안 됩니다. Windows 서비스에서 WPF 유형을 사용하려고 하면 서비스가 예상대로 작동하지 않을 수 있습니다.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>WPF 4에 포함된 그래픽 및 멀티미디어의 새로운 기능

그래픽 및 애니메이션에 관련해서 몇 가지 사항이 변경되었습니다.

- 레이아웃 조정

  개체 가장자리가 픽셀 디바이스 중앙에 놓이면 DPI 독립적 그래픽 시스템은 흐릿한 가장자리 또는 반투명 가장자리와 같은 렌더링 아티팩트를 만들 수 있습니다. 이전 버전의 WPF에는 이러한 경우를 처리하는 데 도움이 되는 픽셀 맞추기 기능이 포함되어 있습니다. Silverlight 2에서는 가장자리가 전체 픽셀 경계에 딱 맞게 요소를 이동하는 또 다른 방법인 레이아웃 조정이 도입되었습니다. 이제 WPF는 에 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> <xref:System.Windows.FrameworkElement>연결된 속성으로 레이아웃 반올림을 지원합니다.

- 캐시된 컴퍼지션

  새 <xref:System.Windows.Media.BitmapCache> 클래스와 <xref:System.Windows.Media.BitmapCacheBrush> 클래스를 사용하면 시각적 트리의 복잡한 부분을 비트맵으로 캐시하고 렌더링 시간을 크게 향상시킬 수 있습니다. 비트맵은 마우스 클릭 같은 사용자 입력에 응답하며, 브러시처럼 다른 요소에 칠할 수 있습니다.

- 픽셀 셰이더 3 지원

  WPF 4는 응용 프로그램이 <xref:System.Windows.Media.Effects.ShaderEffect> 픽셀 샤더(PS) 버전 3.0을 사용하여 효과를 작성할 수 있도록 하여 WPF 3.5 SP1에 도입된 지원 위에 빌드됩니다. PS 3.0 셰이더 모델은 PS 2.0보다 더 정교해졌으며 지원되는 하드웨어에 더 많은 영향을 미칠 수 있습니다.

- 감속/가속 함수

  감속/가속 함수를 사용하여 애니메이션을 개선하고 동작을 좀 더 강력히 제어할 수 있습니다. 예를 들어 애니메이션에 <xref:System.Windows.Media.Animation.ElasticEase> 애니메이션을 적용하여 애니메이션에 탄력적인 동작을 제공할 수 있습니다. 자세한 내용은 <xref:System.Windows.Media.Animation> 네임스페이스의 감속/가속 형식을 참조하십시오.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>그래픽 및 렌더링

WPF에는 고품질 2D 그래픽에 대한 지원이 포함되어 있습니다. 기능으로는 브러시, 기하 도형, 이미지, 도형 및 변환 기능이 있습니다. 자세한 내용은 [그래픽](graphics.md)을 참조하세요. 그래픽 요소의 렌더링은 클래스를 <xref:System.Windows.Media.Visual> 기반으로 합니다. 화면의 시각적 개체 구조는 시각적 트리로 설명됩니다. 자세한 내용은 [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)를 참조하세요.

### <a name="2d-shapes"></a>2D 셰이프

WPF는 다음 그림에서 보여 드리는 사각형 및 타원과 같이 일반적으로 사용되는 벡터 로그린 2D 셰이프 라이브러리를 제공합니다.

![타원과 사각형을 보여주는 다이어그램입니다.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

이러한 고유 WPF 셰이프는 단순한 셰이프가 아니라 키보드 및 마우스 입력을 포함한 가장 일반적인 컨트롤에서 기대하는 많은 기능을 구현하는 프로그래밍 가능한 요소입니다. 다음 예제에서는 <xref:System.Windows.UIElement.MouseUp> <xref:System.Windows.Shapes.Ellipse> 요소를 클릭하여 발생한 이벤트를 처리하는 방법을 보여 주며 있습니다.

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

다음 그림에서는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 코드 숨김에 대한 출력을 보여 줍니다.

!["타원을 클릭했습니다!" 라는 메시지 상자가 있습니다.](./media/index/messagebox-text-output.png)

자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)를 참조하세요. 기본 샘플을 보려면 [도형 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조하세요.

### <a name="2d-geometries"></a>2D 지오메트리

WPF가 제공하는 2D 셰이프가 충분하지 않은 경우 형상 및 패스에 WPF 지원을 사용하여 직접 만들 수 있습니다. 다음 그림에서는 형상을 사용하여 셰이프를 만들고, 드로잉 브러시로, 다른 WPF 요소를 잘라내는 방법을 보여 주어집니다.

![형상을 사용하여 셰이프를 만드는 방법을 보여주는 스크린샷입니다.](./media/index/use-geometries-create-shapes.png)

자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오. 기본 샘플을 보려면 [기하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조하세요.

### <a name="2d-effects"></a>2D 효과

WPF는 다양한 효과를 만드는 데 사용할 수 있는 2D 클래스 라이브러리를 제공합니다. WPF의 2D 렌더링 기능은 그라데이션, 비트맵, 드로잉 및 비디오가 있는 요소를 페인칠하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 기능을 제공합니다. 회전, 배율 조정 및 기울이기를 사용하여 조작할 수 있습니다. 다음 그림에서는 WPF 브러시를 사용하여 얻을 수 있는 다양한 효과의 예를 제공합니다.

![다양한 WPF 브러시 및 페인트 요소를 보여주는 그림입니다.](./media/index/brushes-paint-elements.png)

자세한 내용은 [WPF 브러시 개요를](wpf-brushes-overview.md)참조하십시오. 기본 샘플을 보려면 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조하세요.

<a name="rendering"></a>

## <a name="3d-rendering"></a>3D 렌더링

WPF는 WPF의 2D 그래픽 지원과 통합되는 일련의 3D 렌더링 기능을 제공하여 보다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]흥미로운 레이아웃, 데이터 시각화를 만들 수 있습니다. 스펙트럼의 한쪽 끝에서 WPF를 사용하면 다음 그림에서 보여 주는 3D 셰이프의 표면에 2D 이미지를 렌더링할 수 있습니다.

![다른 텍스처를 가진 3D 모양을 보여주는 샘플의 스크린샷입니다.](./media/index/visual-three-dimensional-shape.png)

자세한 내용은 [3D 그래픽 개요를](3-d-graphics-overview.md)참조하십시오. 소개 샘플은 [3D 솔리드 샘플을](https://go.microsoft.com/fwlink/?LinkID=159964)참조하십시오.

<a name="animation"></a>

## <a name="animation"></a>애니메이션

애니메이션으로 컨트롤 및 요소가 커지거나, 흔들리거나, 회전하거나, 사라지도록 하여 흥미로운 페이지 전환 등을 만들 수 있습니다. WPF를 사용하면 대부분의 속성에 애니메이션을 만들 수 있을 뿐만 아니라 대부분의 WPF 개체에 애니메이션을 만들 수 있으므로 WPF를 사용하여 만든 사용자 지정 개체에 애니메이션을 애니메이션할 수도 있습니다.

![애니메이션된 큐브의 스크린샷입니다.](./media/index/animate-custom-objects.png)

자세한 내용은 [애니메이션 개요를](animation-overview.md)참조하십시오. 기본 샘플을 보려면 [애니메이션 예제 갤러리](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)를 참조하세요.

<a name="media"></a>

## <a name="media"></a>미디어

이미지, 비디오 및 오디오는 미디어를 통해 정보 및 사용자 환경을 전달하는 방법입니다.

### <a name="images"></a>이미지

아이콘, 배경 및 애니메이션 일부를 포함하는 이미지는 대부분의 애플리케이션에서 핵심적인 부분입니다. 이미지를 자주 사용해야 하기 때문에 WPF는 다양한 방법으로 이미지를 사용할 수 있는 기능을 노출합니다. 다음 그림에서는 해당 방법 중 하나만 보여 줍니다.

![샘플 스크린샷 스타일링](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

자세한 내용은 [이미징 개요를](imaging-overview.md)참조하십시오.

### <a name="video-and-audio"></a>비디오 및 오디오

WPF 의 그래픽 기능의 핵심 기능은 비디오 및 오디오를 포함하는 멀티미디어 작업에 대한 기본 지원을 제공하는 것입니다. 다음 예제에서는 미디어 플레이어를 애플리케이션에 삽입하는 방법을 보여 줍니다.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>비디오와 오디오를 모두 재생할 수 있으며 사용자 지정 UI를 쉽게 만들 수 있을 만큼 확장할 수 있습니다.

자세한 내용은 [멀티미디어 개요](multimedia-overview.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [애니메이션 및 타이밍 방법 항목](animation-and-timing-how-to-topics.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [멀티미디어 개요](multimedia-overview.md)
