---
title: Menu 개요
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124652"
---
# <a name="menu-overview"></a>Menu 개요
<xref:System.Windows.Controls.Menu> 클래스를 사용 하면 명령 및 이벤트 처리기와 연결 된 요소를 계층적 순서로 구성할 수 있습니다. 각 <xref:System.Windows.Controls.Menu> 요소는 <xref:System.Windows.Controls.MenuItem> 요소의 컬렉션을 포함 합니다.  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu 컨트롤  
 <xref:System.Windows.Controls.Menu> 컨트롤에 명령 또는 애플리케이션에 대 한 옵션을 지정 하는 항목의 목록을 제공 합니다. 일반적으로 <xref:System.Windows.Controls.MenuItem> 클릭 하면 하위 메뉴가 열리거나 응용 프로그램에서 명령을 실행 합니다.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>메뉴 만들기  
 다음 예에서는 <xref:System.Windows.Controls.TextBox>텍스트를 조작 하는 <xref:System.Windows.Controls.Menu>을 만듭니다. <xref:System.Windows.Controls.Menu>에는 <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>및 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성과 <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>및 <xref:System.Windows.Controls.MenuItem.Click> 이벤트를 사용 하는 <xref:System.Windows.Controls.MenuItem> 개체가 포함 되어 있습니다.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>바로 가기 키가 있는 MenuItem  
 바로 가기 키는 키보드를 사용 하 여 <xref:System.Windows.Controls.Menu> 명령을 호출할 수 있는 문자 조합입니다. 예를 들어 **복사**의 바로 가기는 Ctrl+C입니다. 키보드 바로 가기 키와 메뉴 항목에 사용할 수 있는 두 가지 속성은<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 또는 <xref:System.Windows.Controls.MenuItem.Command%2A>입니다.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 다음 예제에서는 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.MenuItem> 컨트롤에 바로 가기 키 텍스트를 할당 하는 방법을 보여 줍니다. 이렇게 해야만 메뉴 항목에 바로 가기 키가 배치됩니다.  명령은 <xref:System.Windows.Controls.MenuItem>와 연결 되지 않습니다. 애플리케이션은 사용자 입력을 처리하여 작업을 수행해야 합니다.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>명령  
 다음 예제에서는 <xref:System.Windows.Controls.MenuItem.Command%2A> 속성을 사용 하 여 **열기** 및 **저장** 명령을 <xref:System.Windows.Controls.MenuItem> 컨트롤과 연결 하는 방법을 보여 줍니다. Command 속성은 명령을 <xref:System.Windows.Controls.MenuItem>와 연결 하는 것 뿐만 아니라 바로 가기로 사용할 입력 제스처 텍스트를 제공 합니다.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem> 클래스에는 명령이 발생 하는 요소를 지정 하는 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 속성도 있습니다. <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>를 설정 하지 않으면 키보드 포커스가 있는 요소가 명령을 수신 합니다. 명령에 대한 자세한 내용은 [명령 개요](../advanced/commanding-overview.md)를 참조하세요.  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>메뉴 스타일 설정  
 컨트롤 스타일을 사용 하면 사용자 지정 컨트롤을 작성 하지 않고도 <xref:System.Windows.Controls.Menu> 컨트롤의 모양과 동작을 크게 변경할 수 있습니다. 시각적 속성을 설정 하는 것 외에도, 컨트롤의 개별 부분에 <xref:System.Windows.Style>를 적용 하거나, 속성을 통해 컨트롤의 일부에 대 한 동작을 변경 하거나, 추가 파트를 추가 하거나 컨트롤의 레이아웃을 변경할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Controls.Menu> 컨트롤에 <xref:System.Windows.Style>를 추가 하는 여러 가지 방법을 보여 줍니다.  
  
 첫 번째 코드 예제에서는 스타일에서 현재 시스템 설정을 사용 하는 방법을 보여 주는 `Simple` 이라는 <xref:System.Windows.Style>를 정의 합니다. 코드에서는 `MenuHighlightBrush`의 색을 메뉴의 배경색으로 할당하고 `MenuTextBrush`를 메뉴의 전경색으로 할당합니다. 리소스 키를 사용하여 브러시를 할당하게 됩니다.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 다음 샘플에서는 <xref:System.Windows.Trigger> 요소를 사용 하 여 <xref:System.Windows.Controls.Menu>에서 발생 하는 이벤트에 대 한 응답으로 <xref:System.Windows.Controls.MenuItem>의 모양을 변경할 수 있습니다. <xref:System.Windows.Controls.Menu>위로 마우스를 이동 하면 메뉴 항목의 전경색과 글꼴 특성이 변경 됩니다.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>참고 항목

- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)(WPF 컨트롤 갤러리 샘플)
