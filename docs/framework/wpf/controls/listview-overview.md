---
title: ListView 개요
description: 여러 레이아웃이 나 뷰로 데이터 항목을 표시 하는 인프라를 제공 하는 Windows Presentation Foundation ListView 컨트롤에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 419c6216f0af696ec71e7607c79c2db637caa785
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164557"
---
# <a name="listview-overview"></a>ListView 개요
<xref:System.Windows.Controls.ListView>컨트롤은 여러 레이아웃 또는 뷰에서 데이터 항목 집합을 표시 하는 인프라를 제공 합니다. 예를 들어 사용자가 데이터 항목을 표에 표시하고 해당 열을 정렬해야 할 수도 있습니다.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>ListView란?  
 <xref:System.Windows.Controls.ListView>컨트롤은에서 파생 되는입니다 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox> . 일반적으로 해당 항목은 데이터 컬렉션의 멤버 이며 개체로 표현 됩니다 <xref:System.Windows.Controls.ListViewItem> . 는 이며 <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.Controls.ContentControl> 단일 자식 요소만 포함할 수 있습니다. 하지만 자식 요소는 모든 시각적 요소가 될 수 있습니다.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>ListView의 뷰 모드 정의  
 컨트롤의 내용에 대 한 보기 모드를 지정 하려면 <xref:System.Windows.Controls.ListView> 속성을 설정 <xref:System.Windows.Controls.ListView.View%2A> 합니다. 에서 제공 하는 뷰 모드 중 하나 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 는 <xref:System.Windows.Controls.GridView> 사용자 지정 가능한 열이 있는 테이블의 데이터 항목 컬렉션을 표시 하는입니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView> 직원 정보를 표시 하는 컨트롤에 대해를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림에서는 이전 예제의 데이터가 표시되는 방법을 보여 줍니다.  
  
 ![GridView를 출력 하는 ListView를 보여 주는 스크린샷](./media/gridview-overview/listview-gridview-output.jpg)  
  
 클래스에서 상속 되는 클래스를 정의 하 여 사용자 지정 보기 모드를 만들 수 있습니다 <xref:System.Windows.Controls.ViewBase> . <xref:System.Windows.Controls.ViewBase>클래스는 사용자 지정 뷰를 만드는 데 필요한 인프라를 제공 합니다. 사용자 지정 뷰를 만드는 방법에 대한 자세한 내용은 [ListView의 사용자 지정 뷰 모드 만들기](how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하세요.  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>ListView에 데이터 바인딩  
 <xref:System.Windows.Controls.ItemsControl.Items%2A>및 속성을 사용 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 하 여 컨트롤에 대 한 항목을 지정 <xref:System.Windows.Controls.ListView> 합니다. 다음 예제에서는 속성을 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 호출 되는 데이터 컬렉션으로 설정 합니다 `EmployeeInfoDataSource` .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 에서 <xref:System.Windows.Controls.GridView> 개체는 <xref:System.Windows.Controls.GridViewColumn> 지정 된 데이터 필드에 바인딩됩니다. 다음 예제에서는 <xref:System.Windows.Controls.GridViewColumn> 속성에 대해를 지정 하 여 개체를 데이터 필드에 바인딩합니다 <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> .  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 <xref:System.Windows.Data.Binding> <xref:System.Windows.DataTemplate> 열에서 셀의 스타일을 지정 하는 데 사용 하는 정의의 일부로를 지정할 수도 있습니다. 다음 예제에서 <xref:System.Windows.DataTemplate> 로 식별 되는는에 <xref:System.Windows.ResourceKey> 대 한를 설정 합니다 <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.GridViewColumn> . 이 예제에서는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 로 지정 된 바인딩을 재정의 하므로를 정의 하지 않습니다 <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>GridView를 구현하는 ListView에 스타일 지정  
 <xref:System.Windows.Controls.ListView>컨트롤에는 <xref:System.Windows.Controls.ListViewItem> 표시 되는 데이터 항목을 나타내는 개체가 포함 되어 있습니다. 다음 속성을 사용하여 데이터 항목의 콘텐츠 및 스타일을 정의할 수 있습니다.  
  
- 컨트롤에서 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , 및 속성을 사용 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 합니다.  
  
- 컨트롤에서 <xref:System.Windows.Controls.ListViewItem> 및 속성을 사용 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 합니다.  
  
 의 셀 간에 맞춤 문제가 발생 하지 않도록 하려면를 <xref:System.Windows.Controls.GridView> 사용 하 여 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 속성을 설정 하거나의 항목 너비에 영향을 주는 내용을 추가 하지 마십시오 <xref:System.Windows.Controls.ListView> . 예를 들어에서 속성을 설정 하면 맞춤 문제가 발생할 수 있습니다 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . 의 항목 너비에 영향을 주는 속성을 지정 하거나 콘텐츠를 정의 하려면 <xref:System.Windows.Controls.GridView> 클래스의 속성과와 <xref:System.Windows.Controls.GridView> 같은 관련 클래스를 사용 <xref:System.Windows.Controls.GridViewColumn> 합니다.  
  
 및 해당 지원 클래스를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.Controls.GridView> [GridView 개요](gridview-overview.md)를 참조 하세요.  
  
 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>컨트롤에 대해를 정의 <xref:System.Windows.Controls.ListView> 하 고도 정의 하는 경우이 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 제대로 작동 하려면 스타일에를 포함 해야 합니다.  
  
 사용 하지 마십시오는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성에 대 한 <xref:System.Windows.Controls.ListView> 사용 하 여 표시 되는 콘텐츠를 <xref:System.Windows.Controls.GridView>입니다. 열에서 콘텐츠의 맞춤을 지정 하는 <xref:System.Windows.Controls.GridView>, 정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>합니다.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>같은 뷰 모드 공유  
 두 컨트롤은 동시에 <xref:System.Windows.Controls.ListView> 같은 뷰 모드를 공유할 수 없습니다. 둘 이상의 컨트롤과 함께 동일한 뷰 모드를 사용 하려고 하면 <xref:System.Windows.Controls.ListView> 예외가 발생 합니다.  
  
 둘 이상에서 동시에 사용할 수 있는 보기 모드를 지정 하려면 <xref:System.Windows.Controls.ListView> 템플릿 또는 스타일을 사용 합니다.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>사용자 지정 보기 모드 만들기  
 와 같은 사용자 지정 뷰는 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ViewBase> 개체로 표시 되는 데이터 항목을 표시 하는 도구를 제공 하는 추상 클래스에서 파생 됩니다 <xref:System.Windows.Controls.ListViewItem> .
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [GridView 개요](gridview-overview.md)
- [방법 항목](listview-how-to-topics.md)
- [컨트롤](../advanced/optimizing-performance-controls.md)
