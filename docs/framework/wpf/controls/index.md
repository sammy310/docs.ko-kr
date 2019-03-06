---
title: 컨트롤
ms.date: 03/30/2017
dev_langs:
  - csharp
  - vb
helpviewer_keywords:
  - 'controls [WPF], about WPF controls'
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
---
# <a name="controls"></a>컨트롤
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 많은 등 거의 모든 Windows 응용 프로그램에 사용 되는 일반적인 UI 구성 요소와 함께 제공 됩니다 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, 및 <xref:System.Windows.Controls.ListBox>합니다. 지금까지 이러한 개체는 컨트롤이라고 불렀습니다. 동안 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK "컨트롤" 이라는 용어를 사용 하 여 응용 프로그램에서 표시 되는 개체를 나타내는 모든 클래스를 대략적인 의미로 계속 것이 중요 클래스에서 상속할 필요가 없습니다를 <xref:System.Windows.Controls.Control> 시각적 존재가 클래스입니다. 클래스에서 상속 되는 <xref:System.Windows.Controls.Control> 클래스에 포함를 <xref:System.Windows.Controls.ControlTemplate>, 소비자 컨트롤의 새 하위 클래스를 만들지 않고도 컨트롤의 모양을 대폭 변경할 수 있습니다.  이 항목에 설명 하는 방법을 컨트롤 (모두 해당에서 상속 받는 합니다 <xref:System.Windows.Controls.Control> 클래스와 상속 받지 않는)은 일반적으로 사용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>컨트롤의 인스턴스 만들기  
 사용 하 여 응용 프로그램 컨트롤을 추가할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다.  다음 예제에서는 사용자에게 이름과 성을 묻는 간단한 애플리케이션을 만드는 방법을 보여 줍니다.  이 예제에서는 6 개의 컨트롤을 만듭니다: 두 개의 레이블, 두 개의 텍스트 상자 및에 2 개의 단추 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 모든 컨트롤을 유사하게 만들 수 있습니다.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 코드로 동일한 애플리케이션을 만듭니다. 간 결함을 생성 합니다 <xref:System.Windows.Controls.Grid>, `grid1`, 샘플에서 제외 되었습니다. `grid1` 동일한 열과 행의 정의는 이전에 표시 된 것과 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제입니다.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>컨트롤의 모양 변경  
 일반적으로 애플리케이션의 모양과 느낌에 맞게 컨트롤의 모양을 변경합니다. 수행하려는 작업에 따라 다음 중 하나를 수행하여 컨트롤의 모양을 변경할 수 있습니다.  
  
-   컨트롤의 속성 값을 변경합니다.  
  
-   만들기는 <xref:System.Windows.Style> 컨트롤에 대 한 합니다.  
  
-   새 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한 합니다.  
  
### <a name="changing-a-controls-property-value"></a>컨트롤의 속성 값 변경  
 많은 컨트롤 같은 컨트롤이 표시 하는 방법을 변경할 수 있도록 하는 속성이 합니다 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button>합니다. 모두 값 속성을 설정할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드입니다. 다음 예제에서는 합니다 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, 및 <xref:System.Windows.Controls.Control.FontWeight%2A> 속성에는 <xref:System.Windows.Controls.Button> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 다음 예제에서는 코드로 동일한 속성을 설정합니다.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>컨트롤에 대한 스타일 만들기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 각 인스턴스에서 만들어 속성을 설정 하는 대신 컨트롤의 모양을 대량으로 지정 하는 기능 제공을 <xref:System.Windows.Style>입니다. 다음 예제는 <xref:System.Windows.Style> 각각에 적용 되는 <xref:System.Windows.Controls.Button> 응용 프로그램에서 합니다. <xref:System.Windows.Style> 정의에 일반적으로 정의 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 에 <xref:System.Windows.ResourceDictionary>와 같은 <xref:System.Windows.FrameworkElement.Resources%2A> 의 속성은 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 스타일에 키를 할당 하 고에서 해당 키를 지정 하 여 특정 형식의 특정 컨트롤에 스타일을 적용할 수도 있습니다는 `Style` 컨트롤의 속성입니다.  스타일에 대 한 자세한 내용은 참조 하세요. [스타일 및 템플릿](styling-and-templating.md)합니다.  
  
### <a name="creating-a-controltemplate"></a>ControlTemplate 만들기  
 A <xref:System.Windows.Style> 한 번에 여러 컨트롤의 속성을 설정할 수 있지만의 모양을 사용자 지정 하려는 경우에 따라를 <xref:System.Windows.Controls.Control> 만들어 수행할 수 이상으로 <xref:System.Windows.Style>입니다. 클래스에서 상속 되는 <xref:System.Windows.Controls.Control> 클래스를 <xref:System.Windows.Controls.ControlTemplate>의 모양과 구조를 정의 하는 <xref:System.Windows.Controls.Control>합니다. <xref:System.Windows.Controls.Control.Template%2A> 의 속성을 <xref:System.Windows.Controls.Control> 가 지정할 수 있는 public이 <xref:System.Windows.Controls.Control> 는 <xref:System.Windows.Controls.ControlTemplate> 기본값과. 새 자주 지정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Control> 의 표시를 사용자 지정 컨트롤에서 상속 하는 대신 한 <xref:System.Windows.Controls.Control>합니다.  
  
 매우 일반적인 컨트롤인 것이 좋습니다 <xref:System.Windows.Controls.Button>합니다.  기본 동작을 <xref:System.Windows.Controls.Button> 취해야 하는 사용자가 클릭 하면 응용 프로그램을 사용 하는 것입니다.  기본적으로 <xref:System.Windows.Controls.Button> 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 은 볼록한 사각형으로 표시 됩니다.  응용 프로그램을 개발 하는 동안의 동작을 활용 하려는 <xref:System.Windows.Controls.Button>-즉, 단추의 클릭 이벤트를 처리 하 여 있지만 단추의 속성을 변경 하 여 수행할 수 있는 작업 이상으로 단추의 모양을 변경할 수 있습니다.  이 경우 만들어야 새 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 다음 예제는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>합니다.  합니다 <xref:System.Windows.Controls.ControlTemplate> 만듭니다는 <xref:System.Windows.Controls.Button> 둥근된 모서리와 그라데이션 배경이 합니다.  <xref:System.Windows.Controls.ControlTemplate> 포함을 <xref:System.Windows.Controls.Border> 인 <xref:System.Windows.Controls.Border.Background%2A> 는 <xref:System.Windows.Media.LinearGradientBrush> 두 개의 <xref:System.Windows.Media.GradientStop> 개체입니다.  첫 번째 <xref:System.Windows.Media.GradientStop> 바인딩할 데이터 바인딩을 사용 하는 <xref:System.Windows.Media.GradientStop.Color%2A> 의 속성을 <xref:System.Windows.Media.GradientStop> 단추의 배경색을 합니다.  설정 하는 경우는 <xref:System.Windows.Controls.Control.Background%2A> 의 속성을 <xref:System.Windows.Controls.Button>, 첫 번째 값의 색을 사용할지 <xref:System.Windows.Media.GradientStop>합니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요. 예제에서는 <xref:System.Windows.Trigger> 의 모양을 변경 하는 <xref:System.Windows.Controls.Button> 때 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 는 `true`합니다.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control.Background%2A> 의 속성을 <xref:System.Windows.Controls.Button> 로 설정 되어야 합니다는 <xref:System.Windows.Media.SolidColorBrush> 예제가 제대로 작동 되려면.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>이벤트 구독  
 사용 하 여 컨트롤의 이벤트를 구독할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 코드 있지만 개체만 처리할 수 있는 코드에서 이벤트 또는 합니다.  다음 예제에서는 구독 하는 방법을 보여 줍니다 합니다 `Click` 의 이벤트는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 다음 예제에서는 처리 합니다 `Click` 의 이벤트는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>컨트롤의 풍부한 콘텐츠  
 대부분의 클래스에서 상속 되는 <xref:System.Windows.Controls.Control> 클래스 풍부한 콘텐츠를 포함 하는 역량을 보유 합니다. 예를 들어를 <xref:System.Windows.Controls.Label> 문자열과 같은 개체를 포함할 수는 <xref:System.Windows.Controls.Image>, 또는 <xref:System.Windows.Controls.Panel>합니다.  다음 클래스는 다양 한 콘텐츠에 대 한 지원을 제공 하며 대부분의 컨트롤에 대 한 기본 클래스로 작동 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
-   <xref:System.Windows.Controls.ContentControl>-이 클래스에서 상속 된 클래스의 일부의 예로 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Controls.ToolTip>합니다.  
  
-   <xref:System.Windows.Controls.ItemsControl>-이 클래스에서 상속 된 클래스의 일부의 예로 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, 및 <xref:System.Windows.Controls.Primitives.StatusBar>합니다.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>-이 클래스에서 상속 된 클래스의 일부의 예로 <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, 및 <xref:System.Windows.Controls.Expander>합니다.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>-이 클래스에서 상속 된 클래스의 일부의 예로 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, 및 <xref:System.Windows.Controls.ToolBar>합니다.  

  
 이러한 기본 클래스에 대 한 자세한 내용은 참조 하세요. [WPF 콘텐츠 모델](wpf-content-model.md)합니다.  
  
## <a name="see-also"></a>참고자료
- [스타일 지정 및 템플릿](styling-and-templating.md)
- [범주별 컨트롤](controls-by-category.md)
- [컨트롤 라이브러리](control-library.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [데이터 바인딩 개요](../data/data-binding-overview.md)
- [입력](../advanced/input-wpf.md)
- [명령 사용](../advanced/how-to-enable-a-command.md)
- [연습: 사용자 지정 애니메이션된 단추 만들기](walkthroughs-create-a-custom-animated-button.md)
- [컨트롤 사용자 지정](control-customization.md)
