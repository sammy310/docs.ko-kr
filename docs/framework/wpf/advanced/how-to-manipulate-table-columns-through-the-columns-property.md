---
title: '방법: Columns 속성을 통해 테이블의 열 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: d379d1a98bff614ff9e16cdd340bb69644988743
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078423"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>방법: Columns 속성을 통해 테이블의 열 조작
이 예제에서는 테이블의 열을 통해 수행할 수 있는 보다 일반적인 작업 중 일부는 <xref:System.Windows.Documents.Table.Columns%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 테이블을 만들고 사용 하 여는 <xref:System.Windows.Documents.TableColumnCollection.Add%2A> 테이블의 열을 추가 하는 방법 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션입니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 삽입 <xref:System.Windows.Documents.TableColumn>합니다.  새 열은 테이블의 첫 번째 새 열을 만드는 인덱스 위치 0에 삽입 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableColumnCollection> 컬렉션 표준 인덱스를 사용 합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>예제  
 열에 대 한 일부 임의 속성을 액세스 하는 다음 예제는 <xref:System.Windows.Documents.TableColumnCollection> 컬렉션, 특정 열에 인덱스를 참조 합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>예제  
 다음 예에서는 현재 테이블에서 호스트 되는 열의 수를 가져옵니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 참조 하 여 특정 열을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>예제  
 다음 예에서는 인덱스에서 특정 열을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>예제  
 다음 예에서는 테이블의 열 컬렉션에서 모든 열을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>참고자료

- [테이블 개요](table-overview.md)
- [XAML을 사용하여 테이블 정의](how-to-define-a-table-with-xaml.md)
- [프로그래밍 방식으로 테이블 작성](how-to-build-a-table-programmatically.md)
- [RowGroups 속성을 통해 테이블의 행 그룹 조작](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Blocks 속성을 통해 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [RowGroups 속성을 통해 테이블의 행 그룹 조작](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
