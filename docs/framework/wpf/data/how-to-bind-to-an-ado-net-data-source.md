---
title: '방법: ADO.NET 데이터 소스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 08933e67c2cc4b7ccfb6ae0c9dfde34f40e4e5f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465550"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>방법: ADO.NET 데이터 소스 바인딩

바인딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 컨트롤을 [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`합니다.

## <a name="example"></a>예제

이 예에서는 `OleDbConnection` 개체를 사용하여 연결 문자열에 지정된 `Access MDB` 파일인 데이터 소스에 연결합니다. 연결이 설정되고 나면 `OleDbDataAdapter` 개체가 생성됩니다. `OleDbDataAdapter` 개체는 select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 명령문을 실행하여 데이터베이스에서 레코드 집합을 검색합니다. [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 명령의 결과는 `OleDbDataAdapter`의 `Fill` 메서드를 호출하여 `DataSet`의 `DataTable`에 저장됩니다. 이 예에서 `DataTable`은 `BookTable`로 이름이 지정됩니다. 설정한 후는 <xref:System.Windows.FrameworkElement.DataContext%2A> 의 속성을 <xref:System.Windows.Controls.ListBox> 에 `DataSet` 개체.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

다음 바인딩할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 <xref:System.Windows.Controls.ListBox> 에 `BookTable` 의 `DataSet`:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` 가 <xref:System.Windows.DataTemplate> 데이터가 표시 되는 방식을 정의 하는:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter`는 `int`를 색상으로 변환합니다. 이 변환기를 사용 하 여는 <xref:System.Windows.Controls.TextBlock.Background%2A> 세 번째의 색 <xref:System.Windows.Controls.TextBlock> 녹색으로 표시 됩니다 하는 경우 값 `NumPages` 이며 미만 350 빨간색이 고, 그렇지 합니다. 변환기의 구현은 여기에 표시되지 않습니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.BindingListCollectionView>
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
