---
title: 테이블 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187268"
---
# <a name="table-overview"></a>테이블 개요
<xref:System.Windows.Documents.Table>은 Flow 문서 콘텐츠의 그리드 기반 프레젠테이션을 지원하는 블록 수준 요소입니다. 이 요소의 유연성 덕분에 이 요소는 매우 유용하지만 이해하고 제대로 사용하기가 더 복잡합니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
- [테이블 기본 사항](#table_basics)  
  
- [Table은 Grid와 어떻게 다를까요?](#table_vs_Grid)  
  
- [기본 테이블 구조](#basic_table_structure)  
  
- [테이블 포함](#table_containment)  
  
- [행 그룹](#row_groupings)  
  
- [백그라운드 렌더링 우선 순위](#rendering_precedence)  
  
- [행 및 열 확장](#spanning_rows_or_columns)  
  
- [코드로 테이블 빌드](#building_a_table_with_code)  
  
- [관련 항목]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>테이블 기본 사항  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>Table은 Grid와 어떻게 다를까요?  
 <xref:System.Windows.Documents.Table>몇 <xref:System.Windows.Controls.Grid> 가지 일반적인 기능을 공유하지만 각 기능은 서로 다른 시나리오에 가장 적합합니다. A는 <xref:System.Windows.Documents.Table> 흐름 콘텐츠 내에서 사용하도록 설계되었습니다(흐름 내용에 대한 자세한 내용은 [흐름 문서 개요](flow-document-overview.md) 참조). 그리드는 폼 내부에서 사용하는 것이 적합합니다(기본적으로 유동 콘텐츠 외부의 모든 위치). 에서 <xref:System.Windows.Documents.FlowDocument>는 <xref:System.Windows.Documents.Table> 페이지 조정, 열 리플로우 및 콘텐츠 선택과 <xref:System.Windows.Controls.Grid> 같은 흐름 콘텐츠 동작을 지원하지 않지만 그렇지 않습니다. 반면에 <xref:System.Windows.Controls.Grid> A는 행 및 열 <xref:System.Windows.Documents.FlowDocument> 인덱스를 <xref:System.Windows.Controls.Grid> 기반으로 요소를 추가하는 등 여러 <xref:System.Windows.Documents.Table> 가지 이유로 외부에서 사용하는 것이 가장 좋습니다. 이 <xref:System.Windows.Controls.Grid> 요소는 자식 콘텐츠를 계층화하여 단일 "셀" 내에 두 개 이상의 요소가 존재할 수 있도록 합니다. <xref:System.Windows.Documents.Table> 레이어를 지원 하지 않습니다. a의 <xref:System.Windows.Controls.Grid> 자식 요소는 "셀" 경계의 면적을 기준으로 절대적으로 배치될 수 있습니다. <xref:System.Windows.Documents.Table> 이 기능을 지원 하지 않습니다. 마지막으로, <xref:System.Windows.Controls.Grid> 더 적은 리소스가 <xref:System.Windows.Documents.Table> 필요하므로 <xref:System.Windows.Controls.Grid> 성능을 향상시키기 위해 a를 사용하는 것이 좋습니다.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>기본 테이블 구조  
 <xref:System.Windows.Documents.Table>는 열(요소로 표시) 및 행(요소로 <xref:System.Windows.Documents.TableColumn> 표시)으로 <xref:System.Windows.Documents.TableRow> 구성된 그리드 기반 프레젠테이션을 제공합니다. <xref:System.Windows.Documents.TableColumn>요소는 콘텐츠를 호스팅하지 않습니다. 단순히 열의 열과 특성을 정의합니다. <xref:System.Windows.Documents.TableRow>요소는 테이블에 대한 <xref:System.Windows.Documents.TableRowGroup> 행 그룹을 정의하는 요소에서 호스팅되어야 합니다. <xref:System.Windows.Documents.TableCell>테이블에서 제시할 실제 콘텐츠를 포함하는 요소는 <xref:System.Windows.Documents.TableRow> 요소에서 호스트되어야 합니다. <xref:System.Windows.Documents.TableCell><xref:System.Windows.Documents.Block>에서 파생되는 요소만 포함될 수 있습니다.  포함에 <xref:System.Windows.Documents.TableCell> 대한 유효한 자식 요소입니다.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>요소는 텍스트 콘텐츠를 직접 호스트할 수 없습니다. 와 같은 <xref:System.Windows.Documents.TableCell>흐름 콘텐츠 요소에 대한 제약 규칙에 대한 자세한 내용은 [흐름 문서 개요를](flow-document-overview.md)참조하십시오.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table> 비슷합니다는 <xref:System.Windows.Controls.Grid> 요소 하지만 더 많은 기능을 큰 리소스 오버 헤드가 필요 합니다.  
  
 다음 예제는 XAML을 가진 간단한 2 x 3 테이블을 정의합니다.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![기본 테이블이 렌더링되는 방식을 보여 주는 스크린샷입니다.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>테이블 포함  
 <xref:System.Windows.Documents.Table><xref:System.Windows.Documents.Block> 레벨 요소에 대한 <xref:System.Windows.Documents.Block> 공통 규칙을 준수합니다.  <xref:System.Windows.Documents.Table> 다음 요소 중 하나에서 요소를 포함 될 수 있습니다.  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>행 그룹  
 요소는 <xref:System.Windows.Documents.TableRowGroup> 테이블 내에서 임의로 행을 그룹화하는 방법을 제공합니다. 테이블의 모든 행은 행 그룹화에 속해야 합니다.  행 그룹 내의 행은 보통 공통 의도를 공유하고 그룹으로 스타일을 지정할 수 있습니다.  행 그룹은 공통적으로 제목, 헤더 및 바닥글 행과 같은 특수 용도 행을 테이블에 포함된 기본 콘텐츠에서 구분하는 데 사용됩니다.  
  
 다음 예제에서는 XAML을 사용하여 스타일이 지정된 헤더 및 바닥글 행이 있는 테이블을 정의합니다.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 표 행 그룹](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>백그라운드 렌더링 우선 순위  
 테이블 요소는 다음 순서로 렌더링됩니다(최저부터 최고까지 z 순서). 이 순서는 변경할 수 없습니다. 예를 들어 설정된 순서를 재정의하는 데 사용할 수 있는 다음 요소에 대한 "Z 순서" 속성은 없습니다.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 테이블에서 이러한 각 요소의 배경색을 정의하는 다음 예제를 살펴보겠습니다.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 다음 그림은 이 예제가 렌더링되는 방법을 보여 줍니다(배경색만 표시).  
  
 ![스크린샷: 표 z&#45;순서](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>행 및 열 확장  
 테이블 셀은 각각 <xref:System.Windows.Documents.TableCell.RowSpan%2A> 또는 <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> 특성을 사용하여 여러 행 또는 컬럼에 걸쳐 있도록 구성될 수 있다.  
  
 셀이 세 개의 열에 걸쳐 있는 다음 예제를 살펴보겠습니다.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 세 열에 걸친 셀](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>코드로 테이블 빌드  
 다음 예제에서는 프로그래밍 방식으로 를 <xref:System.Windows.Documents.Table> 만들고 콘텐츠로 채우는 방법을 보여 주습니다. 테이블의 내용은 5개의 <xref:System.Windows.Documents.TableRow> <xref:System.Windows.Documents.Table.RowGroups%2A> 행(개체에 포함된 개체로 표시됨)과 6개의 열(개체로 표시됨)으로 <xref:System.Windows.Documents.TableColumn> 배분됩니다. 행은 전체 테이블의 제목을 지정하는 제목 행, 테이블의 데이터 열을 설명하는 헤더 행 및 요약 정보가 포함된 바닥글 행 등의 여러 다른 프레젠테이션 용도로 사용됩니다.  “제목”, “헤더” 및 “바닥글” 행의 개념은 테이블에 고유한 것이 아니며, 여러 다른 특성이 있는 행일 뿐입니다. 테이블 셀에는 텍스트, 이미지 또는 거의 모든 다른 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소로 구성될 수 있는 실제 콘텐츠가 포함되어 있습니다.  
  
 먼저 를 <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Documents.Table>호스트하기 위해 a가 <xref:System.Windows.Documents.Table> 만들어지고 새 가 만들어지고 <xref:System.Windows.Documents.FlowDocument>의 내용에 추가됩니다.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 다음으로 6개의 <xref:System.Windows.Documents.TableColumn> 개체가 만들어지고 테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션에 추가되고 일부 서식이 적용됩니다.  
  
> [!NOTE]
> 테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션은 표준 제로 기반 인덱싱을 사용합니다.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 다음으로 제목 행을 만들어 서식이 적용된 테이블에 추가합니다.  제목 행은 테이블의 6개 열에 모두 걸친 단일 셀을 포함하게 됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 다음으로 헤더 행을 만들어 테이블에 추가하고, 헤더 행의 셀을 만들어 콘텐츠로 채웁니다.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 다음으로 데이터 행을 만들어 테이블에 추가하고, 이 행의 셀을 만들어 콘텐츠로 채웁니다.  이 행을 작성하는 것은 헤더 행을 작성하는 것과 비슷합니다. 단, 약간 다른 서식이 지정됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 마지막으로 바닥글 행을 만들어 추가하고 서식을 지정합니다.  제목 행과 마찬가지로 바닥글에는 테이블의 6개 열에 모두 걸친 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>참고 항목

- [유동 문서 개요](flow-document-overview.md)
- [XAML로 테이블 정의](how-to-define-a-table-with-xaml.md)
- [WPF의 문서](documents-in-wpf.md)
- [유동 콘텐츠 요소 사용](how-to-use-flow-content-elements.md)
