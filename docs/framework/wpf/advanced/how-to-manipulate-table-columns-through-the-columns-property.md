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
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913599"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="2c339-102">방법: Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="2c339-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="2c339-103">이 예에서는 <xref:System.Windows.Documents.Table.Columns%2A> 속성을 통해 테이블의 열에 대해 수행할 수 있는 몇 가지 일반적인 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c339-104">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-104">Example</span></span>  
 <span data-ttu-id="2c339-105">다음 예에서는 새 테이블을 만든 다음 <xref:System.Windows.Documents.TableColumnCollection.Add%2A> 메서드를 사용 하 여 테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션에 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="2c339-106">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-106">Example</span></span>  
 <span data-ttu-id="2c339-107">다음 예에서는 새 <xref:System.Windows.Documents.TableColumn>을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="2c339-108">새 열이 인덱스 위치 0에 삽입 되어 테이블의 새 첫 번째 열로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c339-109">컬렉션 <xref:System.Windows.Documents.TableColumnCollection> 은 0부터 시작 하는 표준 인덱싱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="2c339-110">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-110">Example</span></span>  
 <span data-ttu-id="2c339-111">다음 예에서는 인덱스 별로 특정 열을 참조 하 여 <xref:System.Windows.Documents.TableColumnCollection> 컬렉션의 열에 있는 임의 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="2c339-112">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-112">Example</span></span>  
 <span data-ttu-id="2c339-113">다음 예에서는 테이블에서 현재 호스팅하는 열의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="2c339-114">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-114">Example</span></span>  
 <span data-ttu-id="2c339-115">다음 예에서는 참조로 특정 열을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="2c339-116">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-116">Example</span></span>  
 <span data-ttu-id="2c339-117">다음 예에서는 인덱스 별로 특정 열을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="2c339-118">예제</span><span class="sxs-lookup"><span data-stu-id="2c339-118">Example</span></span>  
 <span data-ttu-id="2c339-119">다음 예에서는 테이블의 columns 컬렉션에서 모든 열을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c339-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="2c339-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c339-120">See also</span></span>

- [<span data-ttu-id="2c339-121">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="2c339-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="2c339-122">XAML로 테이블 정의</span><span class="sxs-lookup"><span data-stu-id="2c339-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="2c339-123">프로그래밍 방식으로 표 작성</span><span class="sxs-lookup"><span data-stu-id="2c339-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="2c339-124">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="2c339-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="2c339-125">Blocks 속성을 통한 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="2c339-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="2c339-126">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="2c339-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
