---
title: 포커스 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186663"
---
# <a name="focus-overview"></a>포커스 개요
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 포커스에 관한 두 가지 주요 개념이 있습니다. 즉, 키보드 포커스와 논리 포커스입니다.  키보드 포커스는 키보드 입력을 수신하는 요소를 나타내고 논리 포커스는 포커스가 있는 포커스 범위의 요소를 나타냅니다.  이러한 개념은 이 개요에서 자세히 설명합니다.  포커스를 얻을 수 있는 여러 영역이 있는 복잡한 애플리케이션을 작성할 때 이 개념의 차이를 이해하는 것이 중요합니다.  
  
 포커스 관리에 참여하는 주요 클래스는 <xref:System.Windows.Input.Keyboard> 클래스, <xref:System.Windows.Input.FocusManager> 클래스 및 및 <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement>와 같은 기본 요소 클래스입니다.  기본 요소에 대한 자세한 내용은 [기본 요소 개요](base-elements-overview.md)를 참조하세요.  
  
 클래스는 <xref:System.Windows.Input.Keyboard> 주로 키보드 포커스와 관련이 <xref:System.Windows.Input.FocusManager> 있으며 주로 논리적 포커스와 관련이 있지만 이것은 절대적인 구별이 아닙니다.  키보드 포커스가 있는 요소에는 논리 포커스도 있지만, 논리 포커스가 있는 요소에는 키보드 포커스가 없을 수도 있습니다.  클래스를 <xref:System.Windows.Input.Keyboard> 사용하여 키보드 포커스가 있는 요소를 설정할 때도 이러한 요소에 논리적 포커스를 설정합니다.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>키보드 포커스  
 키보드 포커스는 현재 키보드 입력을 수신 중인 요소를 나타냅니다.  키보드 포커스가 있는 전체 데스크탑에는 요소가 하나뿐이어야 합니다.  에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]키보드 포커스가 있는 요소는 <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> 로 `true`설정됩니다.  클래스의 <xref:System.Windows.Input.Keyboard> <xref:System.Windows.Input.Keyboard.FocusedElement%2A> 정적 속성은 현재 키보드 포커스가 있는 요소를 가져옵니다.  
  
 요소가 키보드 포커스를 얻으려면 <xref:System.Windows.UIElement.Focusable%2A> 기본 요소의 <xref:System.Windows.UIElement.IsVisible%2A> 및 속성을 로 `true`설정해야 합니다.  기본 클래스와 <xref:System.Windows.Controls.Panel> 같은 일부 클래스는 `false` 기본적으로 설정했습니다. <xref:System.Windows.UIElement.Focusable%2A> 따라서 이러한 요소가 <xref:System.Windows.UIElement.Focusable%2A> `true` 키보드 포커스를 얻을 수 있도록 하려면 설정해야 합니다.  
  
 키보드 포커스는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와의 상호 작용을 통해 얻을 수 있습니다(예: 요소로 탭 이동 또는 특정 요소에서 마우스 클릭).  클래스의 메서드를 사용하여 프로그래밍 방식으로 키보드 <xref:System.Windows.Input.Keyboard.Focus%2A> 포커스를 <xref:System.Windows.Input.Keyboard> 얻을 수도 있습니다.  메서드는 <xref:System.Windows.Input.Keyboard.Focus%2A> 지정된 요소 키보드 포커스를 제공 하려고 합니다.  반환된 요소는 키보드 포커스가 있는 요소입니다. 이 요소는 이전 또는 새 포커스 개체가 요청을 차단하는 경우 요청된 요소와 다를 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드를 사용하여 <xref:System.Windows.Controls.Button>에 키보드 포커스를 설정합니다.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 기본 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 요소 클래스의 속성은 요소에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  기본 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 요소 클래스의 속성은 요소 또는 시각적 자식 요소 중 하나에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  
  
 응용 프로그램 시작 시 초기 포커스를 설정할 때 포커스를 수신할 요소는 응용 프로그램에서 로드된 초기 <xref:System.Windows.UIElement.Focusable%2A> <xref:System.Windows.UIElement.IsVisible%2A> 창의 `true`시각적 트리에 있어야 하며 요소는 을 가지고 설정해야 합니다.  초기 포커스를 설정하는 데 권장되는 장소는 이벤트 처리기에 있습니다. <xref:System.Windows.FrameworkElement.Loaded>  <xref:System.Windows.Threading.Dispatcher> 콜백을 호출하거나 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>에 사용할 수도 있습니다.  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>논리 포커스  
 논리적 포커스는 <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> 포커스 범위를 나타냅니다.  포커스 범위는 해당 범위 내에서 추적을 <xref:System.Windows.Input.FocusManager.FocusedElement%2A> 유지하는 요소입니다.  키보드 포커스가 포커스 범위를 벗어나면 포커스된 요소에서 키보드 포커스를 잃지만 논리 포커스는 유지합니다.  키보드 포커스가 포커스 범위로 돌아오면 포커스된 요소가 키보드 포커스를 얻습니다.  그러면 키보드 포커스가 여러 포커스 범위 간에 변경될 수 있지만, 포커스가 포커스 범위로 돌아가면 포커스 범위에 있는 포커스된 요소가 키보드 포커스를 다시 얻습니다.  
  
 애플리케이션에 논리 포커스가 있는 요소는 여러 개일 수 있지만, 특정 포커스 범위에 논리 포커스가 있는 요소는 하나뿐일 수 있습니다.  
  
 키보드 포커스가 있는 요소에는 요소가 속해 있는 포커스 범위에 대한 논리 포커스가 있습니다.  
  
 연결된 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 속성을 로 `true` [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설정하여 요소를 포커스 범위로 설정할 수 있습니다. <xref:System.Windows.Input.FocusManager>  코드에서 요소를 호출하여 <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>포커스 범위로 변환할 수 있습니다.  
  
 다음 예제는 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 연결된 속성을 설정하여 포커스 범위로 만듭니다.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>을 사용 하 고 지정된 요소에 대 한 포커스 범위를 반환 합니다.  
  
 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 포커스 범위인 클래스는 <xref:System.Windows.Window>" <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.ToolBar>및 <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>을 받으면 지정된 포커스 범위에 대한 포커스가 있는 요소가 표시됩니다.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>은 지정된 포커스 범위에서 포커스가 있는 요소를 설정합니다.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>일반적으로 초기 포커스 요소를 설정하는 데 사용됩니다.  
  
 다음 예에서는 포커스 범위에서 포커스된 요소를 설정하고 포커스 범위의 포커스된 요소를 가져옵니다.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>키보드 탐색  
 <xref:System.Windows.Input.KeyboardNavigation> 클래스는 탐색 키 중 하나를 누를 때 기본 키보드 포커스 탐색을 구현 하는 일을 담당 합니다.  탐색 키는 TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, UPARROW, DOWNARROW, LEFTARROW 및 RIGHTARROW 키입니다.  
  
 <xref:System.Windows.Input.KeyboardNavigation> 탐색 컨테이너의 탐색 동작은 연결된 속성 <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>및 <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>을 설정하여 변경할 수 있습니다.  이러한 속성은 <xref:System.Windows.Input.KeyboardNavigationMode> 형식이며 가능한 <xref:System.Windows.Input.KeyboardNavigationMode.Continue>값은 <xref:System.Windows.Input.KeyboardNavigationMode.Contained> <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>" <xref:System.Windows.Input.KeyboardNavigationMode.Once> <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.None>  기본값은 <xref:System.Windows.Input.KeyboardNavigationMode.Continue>요소 탐색 컨테이너가 아님을 의미합니다.  
  
 다음 예제는 <xref:System.Windows.Controls.Menu> 수가 <xref:System.Windows.Controls.MenuItem> 개체입니다.  합니다 <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> 연결된 속성이로 설정 된 <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> 에 <xref:System.Windows.Controls.Menu>합니다.  <xref:System.Windows.Controls.Menu>의 탭 키를 사용하여 포커스가 변경되면 포커스가 각 요소에서 이동하고 마지막 요소에 도달하면 포커스가 첫 번째 요소로 돌아갑니다.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>포커스를 프로그래밍 방식으로 탐색  
 포커스로 작업할 추가 <xref:System.Windows.UIElement.MoveFocus%2A> <xref:System.Windows.UIElement.PredictFocus%2A>API는 및 .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>변경 내용은 응용 프로그램의 다음 요소에 초점을 맞춥니다.  A는 <xref:System.Windows.Input.TraversalRequest> 방향을 지정하는 데 사용됩니다.   <xref:System.Windows.Input.FocusNavigationDirection> 전달된 <xref:System.Windows.UIElement.MoveFocus%2A> 다른 방향 <xref:System.Windows.Input.FocusNavigationDirection.First>포커스를 지정하여 을 <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> 이와 <xref:System.Windows.Input.FocusNavigationDirection.Down>같이 이동할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.MoveFocus%2A> 포커스가 있는 요소를 변경하는 데 사용합니다.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>포커스를 변경하면 포커스를 받을 개체를 반환합니다.  현재 는 <xref:System.Windows.Input.FocusNavigationDirection.Up> <xref:System.Windows.Input.FocusNavigationDirection.Down>에서만 을 <xref:System.Windows.Input.FocusNavigationDirection.Left>지원하며 <xref:System.Windows.Input.FocusNavigationDirection.Right> 에서 <xref:System.Windows.FrameworkElement.PredictFocus%2A>지원됩니다.  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>포커스 이벤트  
 키보드 포커스와 관련된 <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>이벤트는 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>및 <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>은  이벤트는 <xref:System.Windows.Input.Keyboard> 클래스에서 연결된 이벤트로 정의되지만 기본 요소 클래스에서 동일한 라우트된 이벤트로 더 쉽게 액세스할 수 있습니다.  이벤트에 대한 자세한 내용은 [라우트된 이벤트 개요](routed-events-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>요소는 키보드 포커스를 얻을 때 발생합니다.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>요소가 키보드 포커스를 잃으면 발생합니다.  <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> 이벤트 또는 <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> 이벤트가 처리되고 <xref:System.Windows.RoutedEventArgs.Handled%2A> `true`로 설정된 경우 포커스는 변경되지 않습니다.  
  
 다음 예제는 <xref:System.Windows.UIElement.GotKeyboardFocus> <xref:System.Windows.UIElement.LostKeyboardFocus> <xref:System.Windows.Controls.TextBox>에 및 이벤트 처리기를 연결합니다.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 키보드 <xref:System.Windows.Controls.TextBox> 포커스를 가져오면 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.TextBox> 속성이 로 <xref:System.Windows.Media.Brushes.LightBlue%2A>변경됩니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 키보드 <xref:System.Windows.Controls.TextBox> 포커스를 잃으면 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.TextBox> 속성이 다시 흰색으로 변경됩니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 논리적 포커스와 관련된 <xref:System.Windows.UIElement.GotFocus> 이벤트는 <xref:System.Windows.UIElement.LostFocus>및 .  이러한 이벤트는 연결된 <xref:System.Windows.Input.FocusManager> 이벤트로 정의되지만 <xref:System.Windows.Input.FocusManager> CLR 이벤트 래퍼를 노출하지 는 않습니다.  <xref:System.Windows.UIElement>이러한 <xref:System.Windows.ContentElement> 이벤트를 보다 편리하게 노출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [입력 개요](input-overview.md)
- [기본 요소 개요](base-elements-overview.md)
