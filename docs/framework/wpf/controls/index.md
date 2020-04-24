---
title: 컨트롤
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2aab0fc8adaf17a8e9820a6269a740ef09540cda
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646483"
---
# <a name="controls"></a>컨트롤
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 거의 모든 Windows 응용 <xref:System.Windows.Controls.Button>프로그램에서 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Menu>사용되는 많은 공통 UI 구성 요소와 <xref:System.Windows.Controls.ListBox>함께 제공됩니다. 지금까지 이러한 개체는 컨트롤이라고 불렀습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK는 응용 프로그램에서 보이는 개체를 나타내는 클래스를 느슨하게 의미하기 위해 "control"이라는 용어를 계속 사용하지만 클래스가 보이는 <xref:System.Windows.Controls.Control> 존재를 갖기 위해 클래스에서 상속할 필요가 없다는 점에 유의해야 합니다. <xref:System.Windows.Controls.Control> 클래스에서 상속하는 클래스에는 <xref:System.Windows.Controls.ControlTemplate>컨트롤의 소비자가 새 하위 클래스를 만들지 않고도 컨트롤의 모양을 근본적으로 변경할 수 있는 을 포함합니다.  이 항목에서는 <xref:System.Windows.Controls.Control> 컨트롤(클래스에서 상속하는 컨트롤과 클래스에서 상속하지 않는 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]모두)이 에서 일반적으로 사용되는 방법에 대해 설명합니다.  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>컨트롤의 인스턴스 만들기  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드를 사용하여 응용 프로그램에 컨트롤을 추가할 수 있습니다.  다음 예제에서는 사용자에게 이름과 성을 묻는 간단한 애플리케이션을 만드는 방법을 보여 줍니다.  이 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 두 개의 레이블, 두 개의 텍스트 상자 및 두 개의 단추등 6개의 컨트롤을 만듭니다. 모든 컨트롤을 유사하게 만들 수 있습니다.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 코드로 동일한 애플리케이션을 만듭니다. 간결하게 하기 위해 <xref:System.Windows.Controls.Grid>에서 `grid1`를 만들면 샘플에서 제외됩니다. `grid1`이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 같이 동일한 열 및 행 정의가 있습니다.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>컨트롤의 모양 변경  
 일반적으로 애플리케이션의 모양과 느낌에 맞게 컨트롤의 모양을 변경합니다. 수행하려는 작업에 따라 다음 중 하나를 수행하여 컨트롤의 모양을 변경할 수 있습니다.  
  
- 컨트롤의 속성 값을 변경합니다.  
  
- 컨트롤에 <xref:System.Windows.Style> 대한 a를 만듭니다.  
  
- 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 대한 새 만들기  
  
### <a name="changing-a-controls-property-value"></a>컨트롤의 속성 값 변경  
 대부분의 컨트롤에는 의 와 같이 컨트롤이 표시되는 방식을 <xref:System.Windows.Controls.Control.Background%2A> 변경할 <xref:System.Windows.Controls.Button>수 있는 속성이 있습니다. 값 속성과 코드 모두에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 설정할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Controls.Control.Background%2A>에서 <xref:System.Windows.Controls.Control.FontSize%2A>에서 <xref:System.Windows.Controls.Control.FontWeight%2A> 의 <xref:System.Windows.Controls.Button> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 및 속성을 설정합니다.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 다음 예제에서는 코드로 동일한 속성을 설정합니다.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>컨트롤에 대한 스타일 만들기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 만들어 응용 프로그램의 각 인스턴스에 속성을 설정하는 대신 컨트롤 도매의 모양을 <xref:System.Windows.Style>지정할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Style> 응용 프로그램의 각 <xref:System.Windows.Controls.Button> 에 적용 되는 a를 만듭니다. <xref:System.Windows.Style>정의는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 일반적으로 <xref:System.Windows.ResourceDictionary>에 정의됩니다. <xref:System.Windows.FrameworkElement.Resources%2A> <xref:System.Windows.FrameworkElement>  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 스타일에 키를 할당하고 컨트롤 속성에 해당 키를 지정하여 특정 형식의 특정 컨트롤에만 `Style` 스타일을 적용할 수도 있습니다.  스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿을](../../../desktop-wpf/fundamentals/styles-templates-overview.md)참조하십시오.  
  
### <a name="creating-a-controltemplate"></a>ControlTemplate 만들기  
 A를 <xref:System.Windows.Style> 사용하면 한 번에 여러 컨트롤에 속성을 설정할 수 있지만 <xref:System.Windows.Controls.Control> <xref:System.Windows.Style>때로는 을 만들어 수행할 수 있는 것 이상으로 모양을 사용자 지정할 수 있습니다. <xref:System.Windows.Controls.Control> 클래스에서 상속하는 클래스에는 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control>의 구조와 모양을 정의하는 .가 있습니다. a의 <xref:System.Windows.Controls.Control.Template%2A> <xref:System.Windows.Controls.Control> 속성은 공용이므로 기본값과 <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> 다른 a를 제공할 수 있습니다. 컨트롤에서 상속하는 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control> 대신 에 대한 새 를 지정하여 <xref:System.Windows.Controls.Control>의 모양을 사용자 지정할 수 있습니다.  
  
 매우 일반적인 컨트롤을 <xref:System.Windows.Controls.Button>고려하십시오.  a의 <xref:System.Windows.Controls.Button> 주요 동작은 사용자가 클릭할 때 응용 프로그램이 일부 작업을 수행할 수 있도록 하는 것입니다.  기본적으로 in은 <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 발생한 사각형으로 나타납니다.  응용 프로그램을 개발하는 동안 단추의 클릭 이벤트를 처리하여 <xref:System.Windows.Controls.Button>a-의 동작을 활용할 수 있지만 단추의 속성을 변경하여 수행할 수 있는 것 이상으로 단추모양을 변경할 수 있습니다.  이 경우 새 <xref:System.Windows.Controls.ControlTemplate>을 만들 수 있습니다.  
  
 다음 예제는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>합니다.  는 <xref:System.Windows.Controls.ControlTemplate> 둥근 <xref:System.Windows.Controls.Button> 모서리와 그라데이션 배경을 가진 을 만듭니다.  에는 <xref:System.Windows.Controls.ControlTemplate> 두 <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> 개의 <xref:System.Windows.Media.GradientStop> <xref:System.Windows.Media.LinearGradientBrush> 개체가 있는 있는 개체가 포함되어 있습니다.  첫 <xref:System.Windows.Media.GradientStop> 번째는 데이터 바인딩을 <xref:System.Windows.Media.GradientStop.Color%2A> 사용하여 <xref:System.Windows.Media.GradientStop> 단추의 배경 색에 의 속성을 바인딩합니다.  의 <xref:System.Windows.Controls.Control.Background%2A> 속성을 설정하면 해당 값의 색상이 첫 번째 <xref:System.Windows.Media.GradientStop>로 사용됩니다. <xref:System.Windows.Controls.Button> 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조하세요. 또한 이 <xref:System.Windows.Trigger> 예제는 <xref:System.Windows.Controls.Button> when의 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 모양을 변경하는 `true`a를 만듭니다.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> 예제가 <xref:System.Windows.Controls.Control.Background%2A> 제대로 <xref:System.Windows.Controls.Button> 작동하려면 의 <xref:System.Windows.Media.SolidColorBrush> 속성을 a로 설정해야 합니다.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>이벤트 구독  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드를 사용하여 컨트롤의 이벤트를 구독할 수 있지만 코드에서만 이벤트를 처리할 수 있습니다.  다음 예제에서는 `Click` <xref:System.Windows.Controls.Button>의 이벤트를 구독하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 다음 예제는 `Click` <xref:System.Windows.Controls.Button>의 이벤트를 처리합니다.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>컨트롤의 풍부한 콘텐츠  
 <xref:System.Windows.Controls.Control> 클래스에서 상속되는 대부분의 클래스에는 풍부한 콘텐츠를 포함할 수 있는 능력이 있습니다. 예를 들어 <xref:System.Windows.Controls.Label> a는 문자열, <xref:System.Windows.Controls.Image>. 또는 와 같은 <xref:System.Windows.Controls.Panel>모든 개체를 포함할 수 있습니다.  다음 클래스는 리치 콘텐츠를 지원하고 의 대부분의 컨트롤에 대한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기본 클래스 역할을 합니다.  
  
- <xref:System.Windows.Controls.ContentControl>-- 이 클래스에서 상속되는 클래스의 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button>몇 <xref:System.Windows.Controls.ToolTip>가지 예는 .  
  
- <xref:System.Windows.Controls.ItemsControl>-- 이 클래스에서 상속되는 클래스의 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.Menu>몇 <xref:System.Windows.Controls.Primitives.StatusBar>가지 예는 .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- 이 클래스에서 상속되는 클래스의 <xref:System.Windows.Controls.TabItem> <xref:System.Windows.Controls.GroupBox>몇 <xref:System.Windows.Controls.Expander>가지 예는 .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--이 클래스에서 상속되는 클래스의 <xref:System.Windows.Controls.MenuItem>몇 <xref:System.Windows.Controls.TreeViewItem>가지 <xref:System.Windows.Controls.ToolBar>예는 " 및 .  

 이러한 기본 클래스에 대한 자세한 내용은 [WPF 콘텐츠 모델을](wpf-content-model.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤 범주](controls-by-category.md)
- [컨트롤 라이브러리](control-library.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [입력](../advanced/input-wpf.md)
- [명령 사용](../advanced/how-to-enable-a-command.md)
- [연습: 사용자 지정 애니메이션 효과가 있는 단추 만들기](walkthroughs-create-a-custom-animated-button.md)
- [컨트롤 사용자 지정](control-customization.md)
