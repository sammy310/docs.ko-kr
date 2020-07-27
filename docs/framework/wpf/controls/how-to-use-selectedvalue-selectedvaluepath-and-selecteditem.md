---
title: '방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용'
description: SelectedValue 및 SelectedValuePath 속성을 사용 하 여 Windows Presentation Foundation TreeView의 SelectedItem에 대 한 값을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166277"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용
이 예제에서는 및 속성을 사용 하 여 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 의에 대 한 값을 지정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>예제  
 속성은의에 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 대 한를 지정 하는 방법을 제공 합니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> . 는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 컬렉션의 개체를 나타내고 <xref:System.Windows.Controls.ItemsControl.Items%2A> 는 <xref:System.Windows.Controls.TreeView> 선택한 항목의 단일 속성 값을 표시 합니다. 속성은 속성 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 의 값을 결정 하는 데 사용 되는 속성의 경로를 지정 합니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> . 이 항목의 예제에서는 이러한 개념을 보여 줍니다.  
  
 다음 예제에서는 <xref:System.Windows.Data.XmlDataProvider> 직원 정보를 포함 하는을 보여 줍니다.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 다음 예제에서는 <xref:System.Windows.HierarchicalDataTemplate> 의 및를 표시 하는를 정의 합니다 `EmployeeName` `EmployeeWorkDay` `Employee` . 는 <xref:System.Windows.HierarchicalDataTemplate> 템플릿의 일부로를 지정 하지 않습니다 `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 다음 예제에서는 이전에 <xref:System.Windows.Controls.TreeView> 정의 된를 사용 하 <xref:System.Windows.HierarchicalDataTemplate> 고 속성을로 설정 하는을 보여 줍니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> `EmployeeNumber` . 에서을 선택 하면 `EmployeeName` <xref:System.Windows.Controls.TreeView> 속성이 선택 된에 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> `EmployeeInfo` 해당 하는 데이터 항목을 반환 합니다 `EmployeeName` . 그러나이의가로 설정 되어 있기 때문에는로 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> <xref:System.Windows.Controls.TreeView> `EmployeeNumber` <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 설정 됩니다 `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [TreeView 개요](treeview-overview.md)
- [방법 항목](treeview-how-to-topics.md)
