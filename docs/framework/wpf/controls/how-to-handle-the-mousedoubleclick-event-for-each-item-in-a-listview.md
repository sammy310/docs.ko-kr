---
title: '방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460222"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리
<xref:System.Windows.Controls.ListView>항목에 대 한 이벤트를 처리 하려면 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가 해야 합니다. <xref:System.Windows.Controls.ListView> 데이터 소스에 바인딩된 경우에는 <xref:System.Windows.Controls.ListViewItem>를 명시적으로 만들지 않지만 <xref:System.Windows.Controls.ListViewItem>스타일에 <xref:System.Windows.EventSetter>를 추가 하 여 각 항목에 대 한 이벤트를 처리할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터 바인딩된 <xref:System.Windows.Controls.ListView>를 만들고 <xref:System.Windows.Style>를 만들어 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가 합니다.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트를 처리 합니다.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <xref:System.Windows.Controls.ListView>를 데이터 소스에 바인딩하는 것이 가장 일반적 이지만 스타일을 사용 하 여 명시적으로 <xref:System.Windows.Controls.ListViewItem>를 만들지 여부와 관계 없이 데이터 바인딩되지 않은 <xref:System.Windows.Controls.ListView>의 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가할 수 있습니다.  명시적 및 암시적으로 생성 되는 <xref:System.Windows.Controls.ListViewItem> 컨트롤에 대 한 자세한 내용은 <xref:System.Windows.Controls.ItemsControl>을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Xml.XmlElement>
- [데이터 바인딩 개요](../data/data-binding-overview.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 개요](listview-overview.md)
