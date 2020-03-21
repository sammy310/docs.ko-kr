---
title: ListView 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187516"
---
# <a name="listview-overview"></a>ListView 개요
컨트롤은 <xref:System.Windows.Controls.ListView> 다양한 레이아웃 또는 뷰에서 데이터 항목 집합을 표시하는 인프라를 제공합니다. 예를 들어 사용자가 데이터 항목을 표에 표시하고 해당 열을 정렬해야 할 수도 있습니다.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>ListView란?  
 컨트롤은 <xref:System.Windows.Controls.ListView> 에서 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox>파생되는 컨트롤입니다. 일반적으로 해당 항목은 데이터 컬렉션의 멤버이며 <xref:System.Windows.Controls.ListViewItem> 개체로 표시됩니다. A는 <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.Controls.ContentControl> a이며 단일 자식 요소만 포함할 수 있습니다. 하지만 자식 요소는 모든 시각적 요소가 될 수 있습니다.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>ListView의 뷰 모드 정의  
 <xref:System.Windows.Controls.ListView> 컨트롤의 콘텐츠에 대한 보기 모드를 지정하려면 <xref:System.Windows.Controls.ListView.View%2A> 속성을 설정합니다. 제공하는 한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 가지 <xref:System.Windows.Controls.GridView>보기 모드는 사용자 지정 가능한 열이 있는 테이블에 데이터 항목의 컬렉션을 표시하는 것입니다.  
  
 다음 예제에서는 직원 정보를 <xref:System.Windows.Controls.GridView> 표시 <xref:System.Windows.Controls.ListView> 하는 컨트롤에 대 한 를 정의 하는 방법을 보여 주어 있습니다.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림에서는 이전 예제의 데이터가 표시되는 방법을 보여 줍니다.  
  
 ![GridView 출력이 있는 ListView를 보여 주는 스크린샷입니다.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 <xref:System.Windows.Controls.ViewBase> 클래스에서 상속하는 클래스를 정의하여 사용자 지정 보기 모드를 만들 수 있습니다. 클래스는 <xref:System.Windows.Controls.ViewBase> 사용자 지정 보기를 만드는 데 필요한 인프라를 제공합니다. 사용자 지정 뷰를 만드는 방법에 대한 자세한 내용은 [ListView의 사용자 지정 뷰 모드 만들기](how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하세요.  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>ListView에 데이터 바인딩  
 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 속성을 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 사용하여 컨트롤에 <xref:System.Windows.Controls.ListView> 대한 항목을 지정합니다. 다음 예제는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 을 호출하는 데이터 `EmployeeInfoDataSource`컬렉션으로 설정합니다.  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 에서 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn> 개체는 지정된 데이터 필드에 바인딩됩니다. 다음 예제는 속성에 대한 a를 <xref:System.Windows.Controls.GridViewColumn> <xref:System.Windows.Data.Binding> 지정하여 개체를 데이터 필드에 바인딩합니다. <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 열에서 셀의 <xref:System.Windows.Data.Binding> <xref:System.Windows.DataTemplate> 스타일을 지정하는 데 사용하는 정의의 일부로 를 지정할 수도 있습니다. 다음 <xref:System.Windows.DataTemplate> 예제에서는 에 <xref:System.Windows.ResourceKey> <xref:System.Windows.Data.Binding> 대한 <xref:System.Windows.Controls.GridViewColumn>집합으로 식별되는 . 이 예제는 에 의해 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.DataTemplate>지정된 바인딩을 재정의하기 때문에 을 정의하지 않습니다.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>GridView를 구현하는 ListView에 스타일 지정  
 컨트롤에는 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListViewItem> 표시되는 데이터 항목을 나타내는 개체가 포함되어 있습니다. 다음 속성을 사용하여 데이터 항목의 콘텐츠 및 스타일을 정의할 수 있습니다.  
  
- 컨트롤에서 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>에서 " <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>및 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 속성을 사용합니다.  
  
- 컨트롤에서 <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 속성을 사용합니다.  
  
 에서 <xref:System.Windows.Controls.GridView>셀 간의 정렬 문제를 방지하려면 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 을 사용하여 속성을 설정하거나 <xref:System.Windows.Controls.ListView>에서 항목의 너비에 영향을 주는 콘텐츠를 추가하지 마십시오. 예를 들어 에서 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 설정할 때 정렬 문제가 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>발생할 수 있습니다. 의 항목 너비에 <xref:System.Windows.Controls.GridView>영향을 주는 속성을 지정하거나 을 정의하려면 <xref:System.Windows.Controls.GridView> 클래스의 속성과 관련 <xref:System.Windows.Controls.GridViewColumn>클래스를 사용합니다.  
  
 사용 <xref:System.Windows.Controls.GridView> 방법 및 지원 클래스에 대한 자세한 내용은 [GridView 개요](gridview-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Controls.ListView> 컨트롤에 대한 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 을 정의하고 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>을 정의하는 경우 <xref:System.Windows.Controls.ContentPresenter> 을 올바르게 작동하려면 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 스타일에 a를 포함해야 합니다.  
  
 사용 하지 마십시오는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성에 대 한 <xref:System.Windows.Controls.ListView> 사용 하 여 표시 되는 콘텐츠를 <xref:System.Windows.Controls.GridView>입니다. 열에서 콘텐츠의 맞춤을 지정 하는 <xref:System.Windows.Controls.GridView>, 정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>합니다.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>같은 뷰 모드 공유  
 두 <xref:System.Windows.Controls.ListView> 컨트롤은 동일한 뷰 모드를 동시에 공유할 수 없습니다. 두 <xref:System.Windows.Controls.ListView> 개 이상의 컨트롤에서 동일한 뷰 모드를 사용하려고 하면 예외가 발생합니다.  
  
 두 <xref:System.Windows.Controls.ListView>개 이상의 사용자에서 동시에 사용할 수 있는 뷰 모드를 지정하려면 템플릿 또는 스타일을 사용합니다.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>사용자 지정 보기 모드 만들기  
 와 같은 <xref:System.Windows.Controls.GridView> 사용자 지정된 <xref:System.Windows.Controls.ViewBase> 뷰는 개체로 <xref:System.Windows.Controls.ListViewItem> 표시되는 데이터 항목을 표시하는 도구를 제공하는 추상 클래스에서 파생됩니다.
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [GridView 개요](gridview-overview.md)
- [방법 주제](listview-how-to-topics.md)
- [컨트롤](../advanced/optimizing-performance-controls.md)
