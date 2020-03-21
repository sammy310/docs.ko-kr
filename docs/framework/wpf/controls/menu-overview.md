---
title: Menu 개요
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186969"
---
# <a name="menu-overview"></a>Menu 개요
클래스를 <xref:System.Windows.Controls.Menu> 사용하면 명령 및 이벤트 처리기와 관련된 요소를 계층 적 순서로 구성할 수 있습니다. 각 <xref:System.Windows.Controls.Menu> 요소에는 <xref:System.Windows.Controls.MenuItem> 요소 컬렉션이 포함되어 있습니다.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Menu 컨트롤  
 <xref:System.Windows.Controls.Menu> 컨트롤에 명령 또는 애플리케이션에 대 한 옵션을 지정 하는 항목의 목록을 제공 합니다. 일반적으로 를 <xref:System.Windows.Controls.MenuItem> 클릭하면 하위 메뉴가 열리거나 응용 프로그램이 명령을 수행하게 됩니다.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>메뉴 만들기  
 다음 예제에서는 <xref:System.Windows.Controls.Menu> 에서 텍스트를 조작하는 <xref:System.Windows.Controls.TextBox>a를 만듭니다. 에는 <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.MenuItem.Command%2A> <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>에서 및 속성 및 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.MenuItem.Checked>및 <xref:System.Windows.Controls.MenuItem.Unchecked> <xref:System.Windows.Controls.MenuItem.Click> 의 이벤트를 사용하는 개체가 포함됩니다.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>바로 가기 키가 있는 MenuItem  
 키보드 단축키는 <xref:System.Windows.Controls.Menu> 명령을 호출하기 위해 키보드와 함께 입력할 수 있는 문자 조합입니다. 예를 들어 **복사**의 바로 가기는 Ctrl+C입니다. 키보드 단축키 및 메뉴 항목과<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 함께 사용할 <xref:System.Windows.Controls.MenuItem.Command%2A>수 있는 속성은 두 가지가 있습니다.  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 다음 예제에서는 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 속성을 사용하여 컨트롤에 키보드 단축구 <xref:System.Windows.Controls.MenuItem> 텍스트를 할당하는 방법을 보여 주습니다. 이렇게 해야만 메뉴 항목에 바로 가기 키가 배치됩니다.  명령을 <xref:System.Windows.Controls.MenuItem>에 연결하지 않습니다. 애플리케이션은 사용자 입력을 처리하여 작업을 수행해야 합니다.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>명령  
 <xref:System.Windows.Controls.MenuItem.Command%2A> 다음 예제에서는 속성을 사용하여 **열기** 및 **저장** 명령을 <xref:System.Windows.Controls.MenuItem> 컨트롤과 연결하는 방법을 보여 주십습니다. 명령 속성은 명령을 <xref:System.Windows.Controls.MenuItem>에 연결할 뿐만 아니라 바로 가기로 사용할 입력 제스처 텍스트도 제공합니다.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem> 클래스에는 명령이 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 발생하는 요소를 지정하는 속성도 있습니다. 설정되지 않은 경우 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 키보드 포커스가 있는 요소가 명령을 받습니다. 명령에 대한 자세한 내용은 [명령 개요](../advanced/commanding-overview.md)를 참조하세요.  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>메뉴 스타일 설정  
 컨트롤 스타일을 사용하면 사용자 지정 컨트롤을 작성하지 않고도 컨트롤의 <xref:System.Windows.Controls.Menu> 모양과 동작을 크게 변경할 수 있습니다. 시각적 속성을 설정하는 것 외에도 컨트롤의 <xref:System.Windows.Style> 개별 부분에 를 적용하거나, 속성을 통해 컨트롤 부품의 동작을 변경하거나, 추가 부품을 추가하거나 컨트롤의 레이아웃을 변경할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Style> <xref:System.Windows.Controls.Menu> 컨트롤에 a를 추가하는 몇 가지 방법을 보여 줍니다.  
  
 첫 번째 코드 예제에서는 사용자 스타일에서 현재 시스템 설정을 사용하는 방법을 보여 주는 <xref:System.Windows.Style> 호출을 `Simple` 정의합니다. 코드에서는 `MenuHighlightBrush`의 색을 메뉴의 배경색으로 할당하고 `MenuTextBrush`를 메뉴의 전경색으로 할당합니다. 리소스 키를 사용하여 브러시를 할당하게 됩니다.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 다음 샘플에서는 <xref:System.Windows.Trigger> <xref:System.Windows.Controls.Menu>에서 발생하는 이벤트에 대한 응답으로 <xref:System.Windows.Controls.MenuItem> 의 모양을 변경할 수 있는 요소를 사용합니다. 마우스를 <xref:System.Windows.Controls.Menu>[의 전경 색 과 메뉴 항목의 글꼴 특성)을 통해 이동하면 변경됩니다.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>참고 항목

- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)(WPF 컨트롤 갤러리 샘플)
