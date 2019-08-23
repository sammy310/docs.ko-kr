---
title: '방법: RowGroups 속성을 통해 테이블의 행 그룹 조작'
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
ms.openlocfilehash: 195920af64888bd3671b45befc0fe4cde463ae7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913550"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="ac5bc-102">방법: RowGroups 속성을 통해 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="ac5bc-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="ac5bc-103">이 예에서는 속성을 <xref:System.Windows.Documents.Table.RowGroups%2A> 통해 테이블의 행 그룹에 대해 수행할 수 있는 몇 가지 일반적인 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac5bc-104">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-104">Example</span></span>  
 <span data-ttu-id="ac5bc-105">다음 예에서는 새 테이블을 만든 다음 <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> 메서드를 사용 하 여 테이블의 <xref:System.Windows.Documents.Table.RowGroups%2A> 컬렉션에 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-106">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-106">Example</span></span>  
 <span data-ttu-id="ac5bc-107">다음 예에서는 새 <xref:System.Windows.Documents.TableRowGroup>을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="ac5bc-108">새 열이 인덱스 위치 0에 삽입 되어 테이블의 새 첫 번째 행 그룹으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac5bc-109">컬렉션 <xref:System.Windows.Documents.TableRowGroupCollection> 은 0부터 시작 하는 표준 인덱싱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-110">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-110">Example</span></span>  
 <span data-ttu-id="ac5bc-111">다음 예에서는 테이블의 특정 <xref:System.Windows.Documents.TableRowGroup> (인덱스에 의해 지정)에 여러 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-112">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-112">Example</span></span>  
 <span data-ttu-id="ac5bc-113">다음 예에서는 테이블의 첫 번째 행 그룹에 있는 행의 일부 임의 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-114">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-114">Example</span></span>  
 <span data-ttu-id="ac5bc-115">다음 예에서는 테이블의 특정 <xref:System.Windows.Documents.TableRow> (인덱스에 의해 지정)에 여러 셀을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-116">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-116">Example</span></span>  
 <span data-ttu-id="ac5bc-117">다음 예에서는 첫 번째 행 그룹의 첫 번째 행에 있는 셀의 임의 메서드 및 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-118">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-118">Example</span></span>  
 <span data-ttu-id="ac5bc-119">다음 예에서는 테이블에서 호스트 되 <xref:System.Windows.Documents.TableRowGroup> 는 요소의 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-120">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-120">Example</span></span>  
 <span data-ttu-id="ac5bc-121">다음 예에서는 참조로 특정 행 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-122">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-122">Example</span></span>  
 <span data-ttu-id="ac5bc-123">다음 예에서는 인덱스를 기준으로 특정 행 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="ac5bc-124">예제</span><span class="sxs-lookup"><span data-stu-id="ac5bc-124">Example</span></span>  
 <span data-ttu-id="ac5bc-125">다음 예에서는 테이블의 행 그룹 컬렉션에서 모든 행 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="ac5bc-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac5bc-126">See also</span></span>

- [<span data-ttu-id="ac5bc-127">방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작</span><span class="sxs-lookup"><span data-stu-id="ac5bc-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="ac5bc-128">Blocks 속성을 통한 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="ac5bc-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="ac5bc-129">Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="ac5bc-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
