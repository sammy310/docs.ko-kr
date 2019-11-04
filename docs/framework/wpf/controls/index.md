---
title: 컨트롤
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 42596c8adf1b8b27f250fa7a3cf6cc173a63e2eb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459451"
---
# <a name="controls"></a>컨트롤
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ListBox>등 거의 모든 Windows 응용 프로그램에서 사용 되는 대부분의 공통 UI 구성 요소와 함께 제공 됩니다. 지금까지 이러한 개체는 컨트롤이라고 불렀습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK는 계속 해 서 "컨트롤" 이라는 용어를 사용 하 여 응용 프로그램에서 표시 되는 개체를 나타내는 모든 클래스를 사용 하는 반면, 클래스는 표시 된 상태를 유지 하기 위해 <xref:System.Windows.Controls.Control> 클래스에서 상속 하지 않아도 된다는 점을 명심 해야 합니다. <xref:System.Windows.Controls.Control> 클래스에서 상속 되는 클래스에는 <xref:System.Windows.Controls.ControlTemplate>포함 되어 있습니다 .이를 통해 컨트롤의 소비자가 새 하위 클래스를 만들지 않고도 컨트롤의 모양을 크게 변경할 수 있습니다.  이 항목에서는 컨트롤 (<xref:System.Windows.Controls.Control> 클래스에서 상속 되는 컨트롤과 그렇지 않은 컨트롤)이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 일반적으로 사용 되는 방법에 대해 설명 합니다.  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>컨트롤의 인스턴스 만들기  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드를 사용 하 여 응용 프로그램에 컨트롤을 추가할 수 있습니다.  다음 예제에서는 사용자에게 이름과 성을 묻는 간단한 애플리케이션을 만드는 방법을 보여 줍니다.  이 예제에서는 두 개의 레이블, 두 개의 텍스트 상자 및 두 개의 단추 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 만듭니다. 모든 컨트롤을 유사하게 만들 수 있습니다.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 코드로 동일한 애플리케이션을 만듭니다. 간단히 하기 위해 <xref:System.Windows.Controls.Grid>`grid1`는 샘플에서 제외 되었습니다. 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제에 표시 된 것과 같은 열 및 행 정의를 `grid1` 합니다.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>컨트롤의 모양 변경  
 일반적으로 애플리케이션의 모양과 느낌에 맞게 컨트롤의 모양을 변경합니다. 수행하려는 작업에 따라 다음 중 하나를 수행하여 컨트롤의 모양을 변경할 수 있습니다.  
  
- 컨트롤의 속성 값을 변경합니다.  
  
- 컨트롤에 대 한 <xref:System.Windows.Style>를 만듭니다.  
  
- 컨트롤에 대 한 새 <xref:System.Windows.Controls.ControlTemplate>를 만듭니다.  
  
### <a name="changing-a-controls-property-value"></a>컨트롤의 속성 값 변경  
 많은 컨트롤에는 <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Control.Background%2A>와 같이 컨트롤이 표시 되는 방법을 변경할 수 있는 속성이 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드 모두에서 value 속성을 설정할 수 있습니다. 다음 예에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 <xref:System.Windows.Controls.Button>에 대 한 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>및 <xref:System.Windows.Controls.Control.FontWeight%2A> 속성을 설정 합니다.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 다음 예제에서는 코드로 동일한 속성을 설정합니다.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>컨트롤에 대한 스타일 만들기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하면 <xref:System.Windows.Style>를 만들어 응용 프로그램의 각 인스턴스에 대해 속성을 설정 하는 대신, 컨트롤의 모양을 전체적으로 지정할 수 있습니다. 다음 예제에서는 응용 프로그램의 각 <xref:System.Windows.Controls.Button>에 적용 되는 <xref:System.Windows.Style>을 만듭니다. <xref:System.Windows.Style> 정의는 일반적으로 <xref:System.Windows.FrameworkElement>의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성과 같이 <xref:System.Windows.ResourceDictionary>의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의 됩니다.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 또한 스타일에 키를 할당 하 고 컨트롤의 `Style` 속성에서 해당 키를 지정 하 여 특정 형식의 특정 컨트롤에만 스타일을 적용할 수 있습니다.  스타일에 대 한 자세한 내용은 스타일 지정 [및 템플릿](styling-and-templating.md)을 참조 하세요.  
  
### <a name="creating-a-controltemplate"></a>ControlTemplate 만들기  
 <xref:System.Windows.Style>를 사용 하면 한 번에 여러 컨트롤의 속성을 설정할 수 있지만, 경우에 따라 <xref:System.Windows.Style>을 만들어 수행할 수 있는 것 이상의 <xref:System.Windows.Controls.Control> 모양을 사용자 지정할 수 있습니다. <xref:System.Windows.Controls.Control> 클래스에서 상속 되는 클래스에는 <xref:System.Windows.Controls.Control>의 구조와 모양을 정의 하는 <xref:System.Windows.Controls.ControlTemplate>있습니다. <xref:System.Windows.Controls.Control>의 <xref:System.Windows.Controls.Control.Template%2A> 속성은 public 이므로 기본값과 다른 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control>를 제공할 수 있습니다. 컨트롤에서 상속 하는 대신 <xref:System.Windows.Controls.Control>에 대 한 새 <xref:System.Windows.Controls.ControlTemplate>를 지정 하 여 <xref:System.Windows.Controls.Control>모양을 사용자 지정할 수 있습니다.  
  
 매우 일반적인 컨트롤인 <xref:System.Windows.Controls.Button>을 고려 합니다.  <xref:System.Windows.Controls.Button>의 기본 동작은 사용자가 클릭할 때 응용 프로그램이 작업을 수행할 수 있도록 하는 것입니다.  기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 <xref:System.Windows.Controls.Button>는 볼록 사각형으로 나타납니다.  응용 프로그램을 개발 하는 동안 단추의 click 이벤트를 처리 하 여 <xref:System.Windows.Controls.Button>동작을 활용할 수 있지만 단추의 속성을 변경 하 여 수행할 수 있는 작업 이상으로 단추의 모양을 변경할 수 있습니다.  이 경우 새 <xref:System.Windows.Controls.ControlTemplate>을 만들 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Button>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만듭니다.  <xref:System.Windows.Controls.ControlTemplate> 모퉁이가 둥근 모퉁이와 그라데이션 배경을 사용 하 여 <xref:System.Windows.Controls.Button>를 만듭니다.  <xref:System.Windows.Controls.ControlTemplate>에는 <xref:System.Windows.Controls.Border.Background%2A>가 두 개의 <xref:System.Windows.Media.GradientStop> 개체와 <xref:System.Windows.Media.LinearGradientBrush> 인 <xref:System.Windows.Controls.Border> 포함 되어 있습니다.  첫 번째 <xref:System.Windows.Media.GradientStop>는 데이터 바인딩을 사용 하 여 <xref:System.Windows.Media.GradientStop>의 <xref:System.Windows.Media.GradientStop.Color%2A> 속성을 단추의 배경 색에 바인딩합니다.  <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A> 속성을 설정 하면 해당 값의 색이 첫 번째 <xref:System.Windows.Media.GradientStop>사용 됩니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조하세요. 또한이 예제에서는 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true`때 <xref:System.Windows.Controls.Button>의 모양을 변경 하는 <xref:System.Windows.Trigger>을 만듭니다.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> 예제가 제대로 작동 하려면 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A> 속성을 <xref:System.Windows.Media.SolidColorBrush>으로 설정 해야 합니다.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>이벤트 구독  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드 중 하나를 사용 하 여 컨트롤의 이벤트를 구독할 수 있지만 이벤트를 코드 에서만 처리할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.Button>의 `Click` 이벤트를 구독 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 다음 예에서는 <xref:System.Windows.Controls.Button>의 `Click` 이벤트를 처리 합니다.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>컨트롤의 풍부한 콘텐츠  
 <xref:System.Windows.Controls.Control> 클래스에서 상속 되는 대부분의 클래스에는 풍부한 콘텐츠를 포함할 수 있는 용량이 있습니다. 예를 들어 <xref:System.Windows.Controls.Label>는 문자열, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.Panel>등의 모든 개체를 포함할 수 있습니다.  다음 클래스는 다양 한 콘텐츠에 대 한 지원을 제공 하며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 대부분의 컨트롤에 대 한 기본 클래스로 작동 합니다.  
  
- <xref:System.Windows.Controls.ContentControl>-이 클래스에서 상속 하는 클래스의 몇 가지 예는 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>및 <xref:System.Windows.Controls.ToolTip>입니다.  
  
- <xref:System.Windows.Controls.ItemsControl>-이 클래스에서 상속 하는 클래스의 몇 가지 예는 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>및 <xref:System.Windows.Controls.Primitives.StatusBar>입니다.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-이 클래스에서 상속 하는 클래스의 몇 가지 예는 <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>및 <xref:System.Windows.Controls.Expander>입니다.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>-이 클래스에서 상속 하는 클래스의 몇 가지 예는 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>및 <xref:System.Windows.Controls.ToolBar>입니다.  

 이러한 기본 클래스에 대 한 자세한 내용은 [WPF 콘텐츠 모델](wpf-content-model.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [스타일 지정 및 템플릿](styling-and-templating.md)
- [범주별 컨트롤](controls-by-category.md)
- [컨트롤 라이브러리](control-library.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [입력](../advanced/input-wpf.md)
- [명령 사용](../advanced/how-to-enable-a-command.md)
- [연습: 사용자 지정 애니메이션 단추 만들기](walkthroughs-create-a-custom-animated-button.md)
- [컨트롤 사용자 지정](control-customization.md)
