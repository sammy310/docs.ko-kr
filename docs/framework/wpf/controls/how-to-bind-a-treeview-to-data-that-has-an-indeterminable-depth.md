---
title: '방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458621"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩
깊이를 알 수 없는 데이터 원본에 <xref:System.Windows.Controls.TreeView>을 바인딩하려는 경우가 있을 수 있습니다.  이러한 문제는 데이터가 재귀적으로 수행 되는 경우에 발생할 수 있습니다. 여기에는 폴더에 폴더를 포함할 수 있는 파일 시스템 또는 회사의 조직 구조 (직원 들이 직접 보고서 인 경우)가 있습니다.  
  
 데이터 원본에는 계층적 개체 모델이 있어야 합니다. 예를 들어 `Employee` 클래스에는 직원의 직속 보고서 인 Employee 개체의 컬렉션이 포함 될 수 있습니다. 데이터가 계층적이 아닌 방식으로 표현 되는 경우 데이터의 계층적 표현을 빌드해야 합니다.  
  
 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> 속성을 설정 하 고 <xref:System.Windows.Controls.ItemsControl>에서 각 자식 항목에 대해 <xref:System.Windows.Controls.ItemsControl>을 생성 하는 경우 자식 <xref:System.Windows.Controls.ItemsControl>는 부모와 동일한 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>를 사용 합니다. 예를 들어 데이터 바인딩된 <xref:System.Windows.Controls.TreeView>에서 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성을 설정 하는 경우 생성 되는 각 <xref:System.Windows.Controls.TreeViewItem>는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>의 <xref:System.Windows.Controls.TreeView>속성에 할당 된 <xref:System.Windows.DataTemplate>를 사용 합니다.  
  
 <xref:System.Windows.HierarchicalDataTemplate>를 사용 하 여 데이터 템플릿에서 <xref:System.Windows.Controls.TreeViewItem>또는 <xref:System.Windows.Controls.HeaderedItemsControl>에 대 한 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 지정할 수 있습니다. <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> 속성을 설정 하는 경우 <xref:System.Windows.HierarchicalDataTemplate> 적용 될 때 해당 값이 사용 됩니다. <xref:System.Windows.HierarchicalDataTemplate>를 사용 하 여 <xref:System.Windows.Controls.TreeView>의 각 <xref:System.Windows.Controls.TreeViewItem>에 대 한 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 재귀적으로 설정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Controls.TreeView>를 계층적 데이터에 바인딩하고 <xref:System.Windows.HierarchicalDataTemplate>를 사용 하 여 각 <xref:System.Windows.Controls.TreeViewItem>에 대 한 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 지정 하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.TreeView>는 회사의 직원을 나타내는 XML 데이터에 바인딩합니다.  각 `Employee` 요소는 다른 `Employee` 요소를 포함 하 여 누가 누구에 게 보고서를 표시할 수 있습니다. 데이터가 재귀적 이므로 <xref:System.Windows.HierarchicalDataTemplate> 각 수준에 적용할 수 있습니다.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
