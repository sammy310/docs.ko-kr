---
title: TreeView 개요
description: 간단한 예제를 포함 하 여 노드를 사용 하 여 Windows Presentation Foundation TreeView 컨트롤에서 계층 구조로 정보를 표시 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 6ef77febdd3facb7c7e1af566841c2a1aeaff810
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164538"
---
# <a name="treeview-overview"></a>TreeView 개요
<xref:System.Windows.Controls.TreeView>컨트롤은 축소 가능한 노드를 사용 하 여 계층 구조로 정보를 표시 하는 방법을 제공 합니다. 이 항목에서는 <xref:System.Windows.Controls.TreeView> 및 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 소개 하 고이를 사용 하는 간단한 예제를 제공 합니다.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>TreeView란?  
 <xref:System.Windows.Controls.TreeView>는 <xref:System.Windows.Controls.ItemsControl> 컨트롤을 사용 하 여 항목을 중첩 하는입니다 <xref:System.Windows.Controls.TreeViewItem> . 다음 예제에서는 <xref:System.Windows.Controls.TreeView>합니다.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>TreeView 만들기  
 <xref:System.Windows.Controls.TreeView>컨트롤은 컨트롤의 계층 구조를 포함 합니다 <xref:System.Windows.Controls.TreeViewItem> . <xref:System.Windows.Controls.TreeViewItem>컨트롤은 <xref:System.Windows.Controls.HeaderedItemsControl> 및 컬렉션을 포함 하는입니다 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.ItemsControl.Items%2A> .  
  
 를 사용 하 여을 정의 하는 경우 <xref:System.Windows.Controls.TreeView> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 컨트롤의 내용과 <xref:System.Windows.Controls.TreeViewItem> 해당 컬렉션을 구성 하는 항목을 명시적으로 정의할 수 있습니다. 위의 그림에서는 이 메서드를 보여 줍니다.  
  
 를 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 데이터 원본으로 지정한 다음 및을 지정 하 여 콘텐츠를 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> 정의할 수도 있습니다 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.TreeViewItem> .  
  
 컨트롤의 레이아웃을 정의 하려면 <xref:System.Windows.Controls.TreeViewItem> 개체를 사용할 수도 있습니다 <xref:System.Windows.HierarchicalDataTemplate> . 자세한 내용 및 예제는 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 항목이 컨트롤이 아니면 컨트롤이 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeViewItem> 표시 될 때 컨트롤에 의해 자동으로 포함 됩니다 <xref:System.Windows.Controls.TreeView> .  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>TreeViewItem 확장 및 축소  
 사용자가를 확장 하면 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성이로 설정 됩니다 `true` . 또한 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성을 `true` (확장) 또는 `false` (축소)로 설정 하 여 직접 사용자 작업 없이을 확장 하거나 축소할 수 있습니다. 이 속성이 변경 되 면 <xref:System.Windows.Controls.TreeViewItem.Expanded> 또는 <xref:System.Windows.Controls.TreeViewItem.Collapsed> 이벤트가 발생 합니다.  
  
 <xref:System.Windows.FrameworkElement.BringIntoView%2A>컨트롤에 대해 메서드를 호출 하면 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeViewItem> 및 해당 부모 <xref:System.Windows.Controls.TreeViewItem> 컨트롤이 확장 됩니다. <xref:System.Windows.Controls.TreeViewItem>이 표시 되거나 부분적으로 표시 되지 않으면가 <xref:System.Windows.Controls.TreeView> 표시 되도록 스크롤합니다.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>TreeViewItem 선택  
 사용자가 컨트롤을 클릭 <xref:System.Windows.Controls.TreeViewItem> 하 여 선택 하면 <xref:System.Windows.Controls.TreeViewItem.Selected> 이벤트가 발생 하 고 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이로 설정 됩니다 `true` . <xref:System.Windows.Controls.TreeViewItem>또한는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 컨트롤의가 됩니다 <xref:System.Windows.Controls.TreeView> . 반대로, 컨트롤에서 선택이 변경 되 면 <xref:System.Windows.Controls.TreeViewItem> 해당 <xref:System.Windows.Controls.TreeViewItem.Unselected> 이벤트가 발생 하 고 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이로 설정 됩니다 `false` .  
  
 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>컨트롤의 속성은 <xref:System.Windows.Controls.TreeView> 읽기 전용 속성 이므로 명시적으로 설정할 수 없습니다. <xref:System.Windows.Controls.TreeView.SelectedItem%2A>속성은 사용자가 컨트롤을 클릭 <xref:System.Windows.Controls.TreeViewItem> 하거나 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 컨트롤에서 속성이로 설정 된 경우에 설정 됩니다 `true` <xref:System.Windows.Controls.TreeViewItem> .  
  
 속성을 사용 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 하 여의를 지정 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 합니다. 자세한 내용은 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 이벤트에 대 한 이벤트 처리기를 등록 <xref:System.Windows.Controls.TreeView.SelectedItemChanged> 하 여 선택한이 변경 되는 시기를 확인할 수 있습니다 <xref:System.Windows.Controls.TreeViewItem> . <xref:System.Windows.RoutedPropertyChangedEventArgs%601>이벤트 처리기에 제공 되는은 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> 이전 선택 항목인를 지정 하 고 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> 현재 선택 항목인를 지정 합니다. 애플리케이션 또는 사용자가 이전 또는 현재에 선택한 항목이 없는 경우 두 값은 `null`이 될 수 있습니다.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>TreeView 스타일  
 컨트롤의 기본 스타일은 <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.StackPanel> 컨트롤을 포함 하는 개체 내에 배치 합니다 <xref:System.Windows.Controls.ScrollViewer> . <xref:System.Windows.FrameworkElement.Width%2A>에 대해 및 속성을 설정 하면 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.TreeView> 이러한 값이를 <xref:System.Windows.Controls.StackPanel> 표시 하는 개체의 크기를 조정 하는 데 사용 됩니다 <xref:System.Windows.Controls.TreeView> . 표시할 콘텐츠가 표시 영역 보다 큰 경우 <xref:System.Windows.Controls.ScrollViewer> 사용자가 콘텐츠를 스크롤할 수 있도록가 자동으로 표시 됩니다 <xref:System.Windows.Controls.TreeView> .  
  
 컨트롤의 모양을 사용자 지정 하려면 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.FrameworkElement.Style%2A> 속성을 사용자 지정으로 설정 <xref:System.Windows.Style> 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> 를 사용 하 여 컨트롤에 대 한 및 속성 값을 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.FrameworkElement.Style%2A> .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>TreeView 항목에 이미지 및 기타 콘텐츠 추가  
 의 내용에 둘 이상의 개체를 포함할 수 있습니다 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> . 내용에 여러 개체를 포함 하려면 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 또는와 같은 레이아웃 컨트롤 내에 개체를 묶습니다 <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.StackPanel> .  
  
 다음 예제에서는의를로 정의 하 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.CheckBox> 고 <xref:System.Windows.Controls.TextBlock> 컨트롤에 모두 포함 <xref:System.Windows.Controls.DockPanel> 하는 방법을 보여 줍니다.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 다음 예제에서는 <xref:System.Windows.DataTemplate> 컨트롤에 포함 된 및를 포함 하는를 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel> . 을 사용 하 여에 <xref:System.Windows.DataTemplate> 대해 또는를 설정할 수 있습니다 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.TreeViewItem> .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [방법 항목](treeview-how-to-topics.md)
- [WPF 콘텐츠 모델](wpf-content-model.md)
