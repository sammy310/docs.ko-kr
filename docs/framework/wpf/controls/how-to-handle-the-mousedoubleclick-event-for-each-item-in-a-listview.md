---
title: '방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646102"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>방법: ListView의 각 항목에 대한 MouseDoubleClick 이벤트 처리
<xref:System.Windows.Controls.ListView>에서 항목에 대한 이벤트를 처리하려면 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가해야 합니다. a가 <xref:System.Windows.Controls.ListView> 데이터 원본에 바인딩된 경우 <xref:System.Windows.Controls.ListViewItem>을 명시적으로 만들지 않지만 <xref:System.Windows.EventSetter> <xref:System.Windows.Controls.ListViewItem>의 스타일에 를 추가하여 각 항목에 대한 이벤트를 처리할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 데이터 바인딩을 <xref:System.Windows.Controls.ListView> 만들고 <xref:System.Windows.Style> 각 <xref:System.Windows.Controls.ListViewItem>에 이벤트 처리기를 추가할 a를 만듭니다.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 처리 된 <xref:System.Windows.Controls.Control.MouseDoubleClick> 이벤트입니다.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> 데이터 <xref:System.Windows.Controls.ListView> 원본에 바인딩하는 것이 가장 일반적이지만 스타일을 사용하여 <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListViewItem>을 명시적으로 만들지 여부에 관계없이 데이터 바인딩되지 않은 각 데이터 바인딩의 각 처리기를 추가할 수 있습니다.  명시적 및 암시적으로 생성된 <xref:System.Windows.Controls.ListViewItem> 컨트롤에 <xref:System.Windows.Controls.ItemsControl>대한 자세한 내용은 을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.XmlElement>
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 개요](listview-overview.md)
