---
title: '방법: Columns 속성을 통해 표의 열 조작'
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
ms.openlocfilehash: e7b2c1923f7262417f44cb5ac2ea057ef6c83690
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358511"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="b6908-102">방법: Columns 속성을 통해 표의 열 조작</span><span class="sxs-lookup"><span data-stu-id="b6908-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="b6908-103">이 예제에서는 테이블의 열을 통해 수행할 수 있는 보다 일반적인 작업 중 일부는 <xref:System.Windows.Documents.Table.Columns%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6908-104">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-104">Example</span></span>  
 <span data-ttu-id="b6908-105">다음 예제에서는 새 테이블을 만들고 사용 하 여는 <xref:System.Windows.Documents.TableColumnCollection.Add%2A> 테이블의 열을 추가 하는 방법 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="b6908-106">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-106">Example</span></span>  
 <span data-ttu-id="b6908-107">다음 예제에서는 새 삽입 <xref:System.Windows.Documents.TableColumn>합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="b6908-108">새 열은 테이블의 첫 번째 새 열을 만드는 인덱스 위치 0에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6908-109"><xref:System.Windows.Documents.TableColumnCollection> 컬렉션 표준 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="b6908-110">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-110">Example</span></span>  
 <span data-ttu-id="b6908-111">열에 대 한 일부 임의 속성을 액세스 하는 다음 예제는 <xref:System.Windows.Documents.TableColumnCollection> 컬렉션, 특정 열에 인덱스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="b6908-112">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-112">Example</span></span>  
 <span data-ttu-id="b6908-113">다음 예에서는 현재 테이블에서 호스트 되는 열의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="b6908-114">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-114">Example</span></span>  
 <span data-ttu-id="b6908-115">다음 예제에서는 참조 하 여 특정 열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="b6908-116">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-116">Example</span></span>  
 <span data-ttu-id="b6908-117">다음 예에서는 인덱스에서 특정 열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="b6908-118">예제</span><span class="sxs-lookup"><span data-stu-id="b6908-118">Example</span></span>  
 <span data-ttu-id="b6908-119">다음 예에서는 테이블의 열 컬렉션에서 모든 열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b6908-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="b6908-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6908-120">See also</span></span>
- [<span data-ttu-id="b6908-121">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="b6908-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="b6908-122">XAML로 테이블 정의</span><span class="sxs-lookup"><span data-stu-id="b6908-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="b6908-123">프로그래밍 방식으로 표 작성</span><span class="sxs-lookup"><span data-stu-id="b6908-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="b6908-124">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="b6908-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="b6908-125">Blocks 속성을 통한 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="b6908-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="b6908-126">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="b6908-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
