---
title: '방법: GridView를 구현하는 ListView 행의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733548"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>방법: GridView를 구현하는 ListView 행의 스타일 지정
이 예제에서는 <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> 모드를 구현 하는 <xref:System.Windows.Controls.ListView> 컨트롤에서 행의 스타일을 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.ListView> 컨트롤에서 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>를 설정 하 여 <xref:System.Windows.Controls.ListView> 컨트롤의 행에 스타일을 지정할 수 있습니다. <xref:System.Windows.Controls.ListViewItem> 개체로 표시 되는 항목에 대 한 스타일을 설정 합니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>은 행 내용을 표시 하는 데 사용 되는 <xref:System.Windows.Controls.ControlTemplate> 개체를 참조 합니다.  
  
 다음 예제가에서 추출 되는 전체 예제는 XML 데이터베이스에 저장 되는 노래 정보 컬렉션을 표시 합니다. 데이터베이스의 각 곡에는 순위 필드가 있으며 이 필드의 값은 곡 정보 행의 표시 방법을 지정합니다.  
  
 다음 예제에서는 song 컬렉션의 곡을 나타내는 <xref:System.Windows.Controls.ListViewItem> 개체에 대 한 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>를 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>는 노래 정보 행을 표시 하는 방법을 지정 하는 <xref:System.Windows.Controls.ControlTemplate> 개체를 참조 합니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 다음 예에서는 `"Strongly Recommended"` 텍스트 문자열을 행에 추가 하는 <xref:System.Windows.Controls.ControlTemplate>을 보여 줍니다. 이 템플릿은 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>에서 참조 되 고 곡의 등급 값이 5 (5) 인 경우 표시 됩니다. <xref:System.Windows.Controls.ControlTemplate>에는 <xref:System.Windows.Controls.GridView> 뷰 모드에서 정의한 대로 열에 행 내용을 배치 하는 <xref:System.Windows.Controls.GridViewRowPresenter> 개체가 포함 되어 있습니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 다음 예에서는 <xref:System.Windows.Controls.GridView>를 정의 합니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [방법 항목](listview-how-to-topics.md)
- [ListView 개요](listview-overview.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
