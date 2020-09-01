---
title: '방법: GridView를 사용 하는 ListView의 행 스타일'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271947"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>방법: GridView를 구현하는 ListView 행의 스타일 지정
이 예제에서는 <xref:System.Windows.Controls.ListView> 모드를 사용 하는 컨트롤에서 행의 스타일을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> .  
  
## <a name="example"></a>예  
 컨트롤 <xref:System.Windows.Controls.ListView> 에서을 설정 하 여 컨트롤의 행에 스타일을 지정할 수 있습니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListView> . 개체로 표시 되는 항목에 대 한 스타일을 설정 합니다 <xref:System.Windows.Controls.ListViewItem> . 는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ControlTemplate> 행 내용을 표시 하는 데 사용 되는 개체를 참조 합니다.  
  
 다음 예제가에서 추출 되는 전체 예제는 XML 데이터베이스에 저장 되는 노래 정보 컬렉션을 표시 합니다. 데이터베이스의 각 곡에는 순위 필드가 있으며 이 필드의 값은 곡 정보 행의 표시 방법을 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ListViewItem> song 컬렉션의 곡을 나타내는 개체에 대해를 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> <xref:System.Windows.Controls.ControlTemplate> 노래 정보 행을 표시 하는 방법을 지정 하는 참조 개체입니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 텍스트 문자열을 행에 추가 하는을 보여 줍니다 `"Strongly Recommended"` . 이 템플릿은에서 참조 되 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 고 곡의 등급 값이 5 (5) 인 경우를 표시 합니다. 에는 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.GridViewRowPresenter> 뷰 모드에 정의 된 대로 열에 행 내용을 배치 하는 개체가 포함 되어 있습니다 <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 다음 예에서는를 정의 <xref:System.Windows.Controls.GridView> 합니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [방법 도움말 항목](listview-how-to-topics.md)
- [ListView 개요](listview-overview.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
