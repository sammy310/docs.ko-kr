---
title: '방법: TreeView에서 TreeViewItem 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: c90db5312d58cfba18910f299386e2884fb36ce6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360232"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>방법: TreeView에서 TreeViewItem 찾기
<xref:System.Windows.Controls.TreeView> 컨트롤은 계층적 데이터를 표시 하는 편리한 방법을 제공 합니다. 경우에 <xref:System.Windows.Controls.TreeView> 데이터 원본에 바인딩되는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에는 신속 하 게 선택한 데이터 개체를 검색할 수 있는 편리한 방법을 제공 합니다. 내부 데이터 개체를 사용 하려면 일반적으로 적합 하지만 프로그래밍 방식으로 포함 하는 데이터를 조작 해야 하는 경우에 따라 <xref:System.Windows.Controls.TreeViewItem>합니다. 프로그래밍 방식으로 확장 해야 하는 예를 들어 합니다 <xref:System.Windows.Controls.TreeViewItem>에서 다른 항목을 선택 하거나를 <xref:System.Windows.Controls.TreeView>입니다.  
  
 찾을 수를 <xref:System.Windows.Controls.TreeViewItem> 특정 데이터 개체를 포함 하는, 각 수준의 트래버스해야 합니다 <xref:System.Windows.Controls.TreeView>합니다. 항목을 <xref:System.Windows.Controls.TreeView> 성능 향상을 위해 가상화 할 수도 있습니다. 항목을 가상화 할 경우에도 해야 알게는 <xref:System.Windows.Controls.TreeViewItem> 데이터 개체를 포함 하는지 여부를 확인 합니다.  
  
## <a name="example"></a>예제  
  
## <a name="description"></a>설명  
 다음 예제에서는 검색을 <xref:System.Windows.Controls.TreeView> 특정 개체를 포함 하는 개체의 반환 <xref:System.Windows.Controls.TreeViewItem>합니다. 이 예제에서는 각 하면 <xref:System.Windows.Controls.TreeViewItem> 해당 자식 항목을 검색할 수 있도록 인스턴스화됩니다. 이 예제는 경우에 작동 합니다 <xref:System.Windows.Controls.TreeView> 가상화 된 항목을 사용 하지 않습니다.  
  
> [!NOTE]
>  다음 예제에 대 한 작동 <xref:System.Windows.Controls.TreeView>기본 데이터 모델 및 검색 하는 지와 관계 없이 모든 <xref:System.Windows.Controls.TreeViewItem> 개체를 찾을 때까지 합니다. 성능을 향상 시키는 또 다른 방법은 지정된 된 개체에 대 한 데이터 모델을 검색, 데이터 계층 내 위치로 기록해 및 해당 찾을 것 <xref:System.Windows.Controls.TreeViewItem> 에 <xref:System.Windows.Controls.TreeView>합니다. 그러나 성능을 향상 시키는 방법을 데이터 모델에 대 한 지식이 필요 하 고 지정 된 모든 일반화 될 수 없습니다 <xref:System.Windows.Controls.TreeView>합니다.  
  
## <a name="code"></a>코드  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 이전 코드는 사용자 지정 의존 <xref:System.Windows.Controls.VirtualizingStackPanel> 이라는 메서드를 노출 하는 `BringIntoView`합니다. 다음 코드는 사용자 지정 정의 <xref:System.Windows.Controls.VirtualizingStackPanel>합니다.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 다음 XAML 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.TreeView> 사용자 지정을 사용 하는 <xref:System.Windows.Controls.VirtualizingStackPanel>합니다.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>참고자료
- [TreeView의 성능 개선](how-to-improve-the-performance-of-a-treeview.md)
