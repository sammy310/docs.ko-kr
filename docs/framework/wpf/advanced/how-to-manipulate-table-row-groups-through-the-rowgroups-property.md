---
title: '방법: RowGroups 속성을 통한 표의 행 그룹 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: e456aab0d36ae611f3bfe4974aa3603efff27379
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351972"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a>방법: RowGroups 속성을 통한 표의 행 그룹 조작
이 예제에서는 테이블의 행 그룹을 통해 수행할 수 있는 보다 일반적인 작업 중 일부는 <xref:System.Windows.Documents.Table.RowGroups%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 테이블을 만들고 사용 하 여는 <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> 테이블의 열을 추가 하는 방법 <xref:System.Windows.Documents.Table.RowGroups%2A> 컬렉션입니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 삽입 <xref:System.Windows.Documents.TableRowGroup>합니다.  새 열의 인덱스 위치 0 새 첫 번째 행에 삽입 하는 테이블의 그룹입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableRowGroupCollection> 컬렉션 표준 인덱스를 사용 합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 특정 행이 여러 개 추가 <xref:System.Windows.Documents.TableRowGroup> (인덱스로 지정 됨) 테이블에 있습니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a>예제  
 다음 예에서는 테이블에 있는 첫 번째 행 그룹의 행에서 일부 임의 속성에 액세스합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 특정 여러 셀 추가 <xref:System.Windows.Documents.TableRow> (인덱스로 지정 된) 테이블의 합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 일부 임의 메서드 및 속성의 첫 번째 행 그룹에서 첫 번째 행의 셀에 액세스 합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 수를 반환 합니다. <xref:System.Windows.Documents.TableRowGroup> 테이블에 호스트 되는 요소입니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 참조로 특정 행 그룹을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a>예제  
 다음 예에서는 인덱스에서 특정 행 그룹을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a>예제  
 다음 예에서는 테이블의 행 그룹 컬렉션에서 모든 행 그룹을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a>참고자료
- [방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Blocks 속성을 통한 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Columns 속성을 통해 테이블의 열 조작](how-to-manipulate-table-columns-through-the-columns-property.md)
