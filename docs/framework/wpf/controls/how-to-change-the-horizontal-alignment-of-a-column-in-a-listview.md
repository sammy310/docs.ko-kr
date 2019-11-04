---
title: '방법: ListView에 있는 열의 가로 맞춤 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458598"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>방법: ListView에 있는 열의 가로 맞춤 변경
기본적으로 <xref:System.Windows.Controls.ListViewItem>의 각 열에 대 한 내용은 왼쪽에 맞춰집니다. <xref:System.Windows.DataTemplate>를 제공 하 고 <xref:System.Windows.DataTemplate>내의 요소에서 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 설정 하 여 각 열의 맞춤을 변경할 수 있습니다. 이 항목에서는 <xref:System.Windows.Controls.ListView>에서 기본적으로 콘텐츠를 정렬 하는 방법과 <xref:System.Windows.Controls.ListView>한 열의 맞춤을 변경 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Title` 및 `ISBN` 열의 데이터를 왼쪽에 맞춥니다.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 `ISBN` 열의 맞춤을 변경 하려면 각 <xref:System.Windows.Controls.ListViewItem>의 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 속성이 <xref:System.Windows.HorizontalAlignment.Stretch>되도록 지정 하 여 각 <xref:System.Windows.Controls.ListViewItem>의 요소가 각 열의 전체 너비를 따라 확장 되거나 배치 될 수 있도록 지정 해야 합니다. <xref:System.Windows.Controls.ListView> 데이터 원본에 바인딩되므로 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>를 설정 하는 스타일을 만들어야 합니다. 다음으로 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성을 사용 하는 대신 <xref:System.Windows.DataTemplate>를 사용 하 여 콘텐츠를 표시 해야 합니다. 각 템플릿의 `ISBN`를 표시 하기 위해 <xref:System.Windows.DataTemplate>는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성이 <xref:System.Windows.HorizontalAlignment.Right>로 설정 된 <xref:System.Windows.Controls.TextBlock>만 포함할 수 있습니다.  
  
 다음 예제에서는 `ISBN` 열을 오른쪽에 맞추도록 설정 하 고 <xref:System.Windows.DataTemplate>를 참조 하도록 <xref:System.Windows.Controls.GridViewColumn>를 변경 하는 데 필요한 스타일과 <xref:System.Windows.DataTemplate>를 정의 합니다.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 개요](listview-overview.md)
