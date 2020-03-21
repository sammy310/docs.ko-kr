---
title: 맞춤, 여백 및 안쪽 여백 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145477"
---
# <a name="alignment-margins-and-padding-overview"></a>맞춤, 여백 및 안쪽 여백 개요
클래스는 <xref:System.Windows.FrameworkElement> 자식 요소를 정확하게 배치하는 데 사용되는 여러 속성을 노출합니다. 이 항목에서는 가장 중요한 속성 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>중 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>네 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>가지에 대해 설명합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 애플리케이션에서의 요소 위치를 제어하기 위한 기반을 제공하기 때문에 이 속성의 결과를 이해하는 것이 중요합니다.  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>요소 위치 지정 소개  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 요소를 배치하는 방법은 여러 가지가 있습니다. 그러나 이상적인 레이아웃을 달성하는 것은 <xref:System.Windows.Controls.Panel> 단순히 올바른 요소를 선택하는 것 이상입니다. 위치 지정을 세밀하게 제어하려면 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>에 대한 이해가 필요합니다.  
  
 다음 그림에서는 여러 위치 지정 속성을 사용하는 레이아웃 시나리오를 보여줍니다.  
  
 ![WPF 위치 지정 속성 샘플](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 언뜻 보기에 <xref:System.Windows.Controls.Button> 이 그림의 요소는 임의로 배치된 것처럼 보일 수 있습니다. 그러나 해당 위치는 여백, 맞춤 및 안쪽 여백의 조합을 사용하여 실제로 정확하게 제어됩니다.  
  
 다음 예제에서는 앞의 그림에서 레이아웃을 만드는 방법을 설명합니다. <xref:System.Windows.Controls.Border> 요소는 15장치 독립 픽셀의 <xref:System.Windows.Controls.Border.Padding%2A> 값으로 부모를 <xref:System.Windows.Controls.StackPanel>캡슐화합니다. 이것은 아이를 <xref:System.Windows.Media.Brushes.LightBlue%2A> <xref:System.Windows.Controls.StackPanel>둘러싸고있는 좁은 밴드를 차지합니다. 의 <xref:System.Windows.Controls.StackPanel> 자식 요소는 이 항목에서 자세히 설명하는 다양한 위치 지정 속성 각각을 설명하는 데 사용됩니다. 세 <xref:System.Windows.Controls.Button> 가지 요소는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성과 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 모두 보여 주는 데 사용됩니다.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 다음 다이어그램은 이전 샘플에서 사용되는 다양한 위치 지정 속성의 자세히 보기를 제공합니다. 이 항목의 후속 섹션에서는 각 위치 지정 속성을 사용하는 방법을 자세히 설명합니다.  
  
 ![화면 호출&#45;아웃이 있는 위치 지정 속성](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>맞춤 속성 이해  
 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성은 부모 요소의 할당된 레이아웃 공간 내에 자식 요소를 배치하는 방법을 설명합니다. 이러한 속성을 함께 사용하여 자식 요소를 정확하게 배치할 수 있습니다. 예를 들어, a의 <xref:System.Windows.Controls.DockPanel> 자식 요소는 네 <xref:System.Windows.HorizontalAlignment.Left>가지 <xref:System.Windows.HorizontalAlignment.Right>가로 <xref:System.Windows.HorizontalAlignment.Center>선형(또는 사용 가능한 공간을 채우기 위해)을 지정할 수 <xref:System.Windows.HorizontalAlignment.Stretch> 있습니다. 비슷한 값을 세로 위치 지정에 사용할 수 있습니다.  
  
> [!NOTE]
> 요소에 대한 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> 명시적으로 설정 및 속성이 <xref:System.Windows.HorizontalAlignment.Stretch> 속성 값보다 우선합니다. <xref:System.Windows.FrameworkElement.Height%2A>을 <xref:System.Windows.FrameworkElement.Width%2A>설정하고 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> `Stretch` 결과 값을 설정하려고 하면 `Stretch` 요청이 무시됩니다.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>HorizontalAlignment 속성  
 이 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성은 자식 요소에 적용할 수평 맞춤 특성을 선언합니다. 다음 표에서는 속성의 가능한 각 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값을 보여 주며 있습니다.  
  
|멤버|Description|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 왼쪽에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Center>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 중앙에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Right>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 오른쪽에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Stretch>(기본값)|자식 요소는 부모 요소의 할당된 레이아웃 공간을 채우도록 확대됩니다. <xref:System.Windows.FrameworkElement.Width%2A> 명시적 <xref:System.Windows.FrameworkElement.Height%2A> 및 값이 우선합니다.|  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.Controls.Button> 요소에 속성을 적용하는 방법을 보여 주어집니다. 다양한 렌더링 동작의 이해를 돕기 위해 각 특성 값이 표시됩니다.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 앞의 코드는 다음 이미지와 비슷한 레이아웃을 만듭니다. 각 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값의 위치 지정 효과는 그림에 표시됩니다.  
  
 ![HorizontalAlignment 샘플](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>VerticalAlignment 속성  
 이 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성은 자식 요소에 적용할 수직 맞춤 특성을 설명합니다. 다음 표에서는 속성에 대해 가능한 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 각 값을 보여 주며 있습니다.  
  
|멤버|Description|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 위에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Center>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 중앙에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 아래에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Stretch>(기본값)|자식 요소는 부모 요소의 할당된 레이아웃 공간을 채우도록 확대됩니다. <xref:System.Windows.FrameworkElement.Width%2A> 명시적 <xref:System.Windows.FrameworkElement.Height%2A> 및 값이 우선합니다.|  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.Controls.Button> 요소에 속성을 적용하는 방법을 보여 주어집니다. 다양한 렌더링 동작의 이해를 돕기 위해 각 특성 값이 표시됩니다. 이 샘플에서는 각 <xref:System.Windows.Controls.Grid> 속성 값의 레이아웃 동작을 더 잘 설명하기 위해 표시되는 격자선이 있는 요소를 부모로 사용합니다.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 앞의 코드는 다음 이미지와 비슷한 레이아웃을 만듭니다. 각 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 값의 위치 지정 효과는 그림에 표시됩니다.  
  
 ![VerticalAlignment 속성 샘플](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>여백 속성 이해  
 속성은 <xref:System.Windows.FrameworkElement.Margin%2A> 요소와 해당 자식 또는 피어 사이의 거리를 설명합니다. <xref:System.Windows.FrameworkElement.Margin%2A>와 같은 `Margin="20"`구문을 사용하여 값이 균일 할 수 있습니다. 이 구문을 사용하면 <xref:System.Windows.FrameworkElement.Margin%2A> 요소에 20개의 장치 독립 픽셀이 균일하게 적용됩니다. <xref:System.Windows.FrameworkElement.Margin%2A>값은 또한 네 개의 별개의 값의 형태를 취할 수 있습니다, 각 값은 왼쪽, 상단, 오른쪽 `Margin="0,10,5,25"`및 아래쪽 (그 순서)에 적용할 수있는 별개의 여백을 설명하는 . <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 적절하게 사용하면 요소의 렌더링 위치와 이웃 요소 및 자식의 렌더링 위치를 매우 세밀하게 제어할 수 있습니다.  
  
> [!NOTE]
> 0이 아닌 여백은 요소 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 요소 그룹에 균일한 여백을 적용하는 방법을 보여 주어집니다. <xref:System.Windows.Controls.Button> 요소는 각 방향에서 10픽셀 여백 버퍼로 균등하게 간격을 두십니까가 됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 대부분의 경우 균일한 여백이 적합하지 않습니다. 이러한 경우, 균일하지 않은 여백을 적용할 수 있습니다. 다음 예제에서는 자식 요소에 균일하지 않은 여백을 적용하는 방법을 보여 줍니다. 여백은 왼쪽, 위, 오른쪽, 아래의 순서로 설명됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>
## <a name="understanding-the-padding-property"></a>안쪽 여백 속성 이해  
 패딩은 대부분의 <xref:System.Windows.FrameworkElement.Margin%2A> 면에서 유사합니다. <xref:System.Windows.Documents.Block>패딩 속성은 주로 편의를 <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Control>위해 몇 가지 클래스에만 <xref:System.Windows.Controls.TextBlock> 노출되며 패딩 속성을 노출하는 클래스의 샘플입니다. 속성은 <xref:System.Windows.Controls.Border.Padding%2A> 자식 요소의 유효 크기를 지정된 <xref:System.Windows.Thickness> 값으로 확대합니다.  
  
 다음 예제에서는 상위 <xref:System.Windows.Controls.Border.Padding%2A> <xref:System.Windows.Controls.Border> 요소에 적용하는 방법을 보여 주며 있습니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>애플리케이션에서 맞춤, 여백 및 안쪽 여백 사용  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>을 위해 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]복합체를 만드는 데 필요한 위치 지정 컨트롤을 제공합니다. <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A> 각 속성의 결과를 사용하여 자식 요소 위치를 변경하면 동적 애플리케이션과 사용자 환경을 만드는 유연성을 사용할 수 있습니다.  
  
 다음 예제에서는 이 항목에 설명된 각 개념을 보여 줍니다. 이 항목의 첫 번째 샘플에서 찾은 인프라를 <xref:System.Windows.Controls.Grid> 기반으로 하는 이 <xref:System.Windows.Controls.Border> 예제에서는 첫 번째 샘플에서 요소를 하위 요소로 추가합니다. <xref:System.Windows.Controls.Border.Padding%2A>부모 <xref:System.Windows.Controls.Border> 요소에 적용됩니다. 는 <xref:System.Windows.Controls.Grid> 세 자식 <xref:System.Windows.Controls.StackPanel> 요소 사이의 공간을 분할하는 데 사용됩니다. <xref:System.Windows.Controls.Button>요소는 다시 의 다양한 효과를 <xref:System.Windows.FrameworkElement.Margin%2A> 표시하는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>데 사용됩니다. <xref:System.Windows.Controls.TextBlock>각 열의 <xref:System.Windows.Controls.ColumnDefinition> 요소에 적용된 다양한 속성을 <xref:System.Windows.Controls.Button> 더 잘 정의하기 위해 요소가 각각 추가됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 컴파일 시, 이전 애플리케이션은 다음 그림과 유사한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다. 다양한 속성 값의 효과는 요소 간의 간격에서 분명하게 나타나며 각 열의 요소에 대한 <xref:System.Windows.Controls.TextBlock> 중요한 속성 값은 요소 내에 표시됩니다.  
  
 ![하나의 응용 프로그램에서 여러 위치 지정 속성](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>다음 단계  
 클래스에 <xref:System.Windows.FrameworkElement> 의해 정의된 위치 지정 속성을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에서 요소 배치를 미세하게 제어할 수 있습니다. 이제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 요소 배치에 사용할 수 있는 여러 기술을 사용할 수 있습니다.  
  
 자세하게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃을 설명하는 추가 리소스를 사용할 수 있습니다. [패널 개요](../controls/panels-overview.md) 항목에는 다양한 <xref:System.Windows.Controls.Panel> 요소에 대한 자세한 내용이 포함되어 있습니다. 연습 [주제: 첫 번째 WPF 데스크톱 응용 프로그램은](../getting-started/walkthrough-my-first-wpf-desktop-application.md) 레이아웃 요소를 사용하여 구성 요소를 배치하고 해당 작업을 데이터 원본에 바인딩하는 고급 기술을 소개합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [패널 개요](../controls/panels-overview.md)
- [레이아웃](layout.md)
- [WPF 레이아웃 갤러리 샘플](https://go.microsoft.com/fwlink/?LinkID=160054)
