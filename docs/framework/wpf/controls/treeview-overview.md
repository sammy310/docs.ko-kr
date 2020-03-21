---
title: TreeView 개요
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187377"
---
# <a name="treeview-overview"></a>TreeView 개요
컨트롤은 <xref:System.Windows.Controls.TreeView> 축소 가능한 노드를 사용하여 계층 구조에 정보를 표시하는 방법을 제공합니다. 이 항목에서는 <xref:System.Windows.Controls.TreeView> 및 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 소개하고 사용의 간단한 예제를 제공합니다.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>TreeView란?  
 <xref:System.Windows.Controls.TreeView><xref:System.Windows.Controls.ItemsControl> 은 컨트롤을 사용하여 <xref:System.Windows.Controls.TreeViewItem> 항목을 중첩하는 것입니다. 다음 예제에서는 <xref:System.Windows.Controls.TreeView>합니다.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>TreeView 만들기  
 컨트롤에는 <xref:System.Windows.Controls.TreeView> 컨트롤 계층이 <xref:System.Windows.Controls.TreeViewItem> 포함되어 있습니다. <xref:System.Windows.Controls.TreeViewItem> 컨트롤은 <xref:System.Windows.Controls.HeaderedItemsControl> a와 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 컬렉션이 있는 컨트롤입니다. <xref:System.Windows.Controls.ItemsControl.Items%2A>  
  
 을 <xref:System.Windows.Controls.TreeView> 사용하여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]정의하는 경우 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 내용과 해당 컬렉션을 구성하는 항목을 명시적으로 정의할 수 있습니다. 위의 그림에서는 이 메서드를 보여 줍니다.  
  
 또한 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 를 데이터 원본으로 지정한 다음 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 을 지정하고 콘텐츠를 정의할 수도 있습니다. <xref:System.Windows.Controls.TreeViewItem>  
  
 컨트롤의 레이아웃을 <xref:System.Windows.Controls.TreeViewItem> 정의하려면 개체를 <xref:System.Windows.HierarchicalDataTemplate> 사용할 수도 있습니다. 자세한 내용 및 예제는 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 항목이 컨트롤이 <xref:System.Windows.Controls.TreeViewItem> 아닌 경우 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeView> 컨트롤이 표시될 때 컨트롤에 의해 자동으로 동봉됩니다.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>TreeViewItem 확장 및 축소  
 사용자가 <xref:System.Windows.Controls.TreeViewItem>을 확장하는 경우 <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성이 로 `true`설정됩니다. 또한 속성을 (확장) <xref:System.Windows.Controls.TreeViewItem> 또는 (축소)로 설정하여 `true` 직접 적인 `false` 사용자 작업없이 를 확장하거나 축소할 수도 있습니다. <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 이 속성이 변경되면 <xref:System.Windows.Controls.TreeViewItem.Collapsed> 또는 <xref:System.Windows.Controls.TreeViewItem.Expanded> 이벤트가 발생합니다.  
  
 컨트롤에서 <xref:System.Windows.FrameworkElement.BringIntoView%2A> 메서드를 호출하면 해당 <xref:System.Windows.Controls.TreeViewItem> 상위 <xref:System.Windows.Controls.TreeViewItem> 컨트롤이 확장됩니다. <xref:System.Windows.Controls.TreeViewItem> a가 <xref:System.Windows.Controls.TreeViewItem> 보이지 않거나 부분적으로 표시되지 <xref:System.Windows.Controls.TreeView> 않으면 스크롤하여 표시되도록 합니다.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>TreeViewItem 선택  
 <xref:System.Windows.Controls.TreeViewItem> 사용자가 컨트롤을 클릭하여 <xref:System.Windows.Controls.TreeViewItem.Selected> 선택하면 이벤트가 발생하고 해당 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이 `true`로 설정됩니다. <xref:System.Windows.Controls.TreeViewItem> 또한 컨트롤의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> 가됩니다. 반대로 선택 <xref:System.Windows.Controls.TreeViewItem> 영역이 컨트롤에서 변경되면 <xref:System.Windows.Controls.TreeViewItem.Unselected> 해당 이벤트가 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 발생하고 해당 `false`속성이 로 설정됩니다.  
  
 컨트롤의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> 속성은 읽기 전용 속성입니다. 따라서 명시적으로 설정할 수 없습니다. 사용자가 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 클릭하거나 속성이 컨트롤에 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 설정된 `true` 경우 속성이 <xref:System.Windows.Controls.TreeViewItem> 설정됩니다.  
  
 속성을 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 사용하여 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A>를 지정합니다. 자세한 내용은 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 선택한 <xref:System.Windows.Controls.TreeViewItem> 변경 시기를 결정하기 <xref:System.Windows.Controls.TreeView.SelectedItemChanged> 위해 이벤트에 이벤트 처리기를 등록할 수 있습니다. 이벤트 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> 처리기에 제공되는 내용은 이전 선택 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>영역이고 의 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>는 현재 선택 영역인 을 지정합니다. 애플리케이션 또는 사용자가 이전 또는 현재에 선택한 항목이 없는 경우 두 값은 `null`이 될 수 있습니다.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>TreeView 스타일  
 컨트롤의 기본 <xref:System.Windows.Controls.TreeView> 스타일은 컨트롤이 <xref:System.Windows.Controls.StackPanel> 포함된 개체 <xref:System.Windows.Controls.ScrollViewer> 내부에 배치됩니다. <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.TreeView>에 대한 속성을 설정하면 이러한 값은 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TreeView>을 표시하는 개체의 크기를 조정하는 데 사용됩니다. 표시할 콘텐츠가 표시 영역보다 큰 <xref:System.Windows.Controls.ScrollViewer> 경우 사용자가 <xref:System.Windows.Controls.TreeView> 콘텐츠를 스크롤할 수 있도록 자동으로 표시됩니다.  
  
 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 모양을 사용자 지정하려면 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 사용자 지정 <xref:System.Windows.Style>으로 설정합니다.  
  
 다음 <xref:System.Windows.Controls.Control.Foreground%2A> 예제에서는 <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.FrameworkElement.Style%2A>을 사용하여 컨트롤에 대한 및 속성 값을 설정하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>TreeView 항목에 이미지 및 기타 콘텐츠 추가  
 의 콘텐츠에 두 개 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 이상의 개체를 포함할 수 있습니다. <xref:System.Windows.Controls.TreeViewItem> 컨텐츠에 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 여러 객체를 포함하려면 <xref:System.Windows.Controls.Panel> 또는 와 <xref:System.Windows.Controls.StackPanel>같은 레이아웃 컨트롤 내부의 객체를 둘러싸는 다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel> a를 컨트롤에 동봉된 a를 정의하는 방법을 보여 주며 둘 다 로 둘러싸여 있습니다.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 다음 <xref:System.Windows.DataTemplate> 예제에서는 <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel> 컨트롤에 둘러싸인 a와 를 포함하는 a를 정의하는 방법을 보여 주습니다. 을 <xref:System.Windows.DataTemplate> 사용하여 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> 또는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.TreeViewItem>에 대해 설정할 수 있습니다.  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [방법 주제](treeview-how-to-topics.md)
- [WPF 콘텐츠 모델](wpf-content-model.md)
