---
description: '자세한 정보: DataView를 사용 하 여 정렬 (LINQ to DataSet)'
title: DataView로 정렬(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: ac07e5bc2c74a5724a4497d630d7352694ac9a7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718683"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a><span data-ttu-id="9766f-103">DataView로 정렬(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9766f-103">Sorting with DataView (LINQ to DataSet)</span></span>

<span data-ttu-id="9766f-104">특정 조건을 기준으로 데이터를 정렬한 다음 UI 컨트롤을 통해 클라이언트에 데이터를 제공하는 기능은 데이터 바인딩의 중요한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-104">The ability to sort data based on specific criteria and then present the data to a client through a UI control is an important aspect of data binding.</span></span> <span data-ttu-id="9766f-105"><xref:System.Data.DataView>에서는 데이터를 정렬하여 특정 정렬 기준에 따라 정렬된 데이터 행을 반환하는 여러 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-105"><xref:System.Data.DataView> provides several ways to sort data and return data rows ordered by specific ordering criteria.</span></span> <span data-ttu-id="9766f-106">문자열 기반 정렬 기능 외에 <xref:System.Data.DataView> 도를 사용 하 여 정렬 기준으로 LINQ (Language-Integrated Query) 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-106">In addition to its string-based sorting capabilities, <xref:System.Data.DataView> also enables you to use Language-Integrated Query (LINQ) expressions for the sorting criteria.</span></span> <span data-ttu-id="9766f-107">LINQ 식을 사용 하면 문자열 기반 정렬에 비해 더 복잡 하 고 강력한 정렬 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-107">LINQ expressions allow for much more complex and powerful sorting operations than string-based sorting.</span></span> <span data-ttu-id="9766f-108">이 항목에서는 <xref:System.Data.DataView>를 사용하여 정렬하는 두 가지 방법을 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-108">This topic describes both approaches to sorting using <xref:System.Data.DataView>.</span></span>  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a><span data-ttu-id="9766f-109">정렬 정보가 있는 쿼리에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="9766f-109">Creating DataView from a Query with Sorting Information</span></span>  

 <span data-ttu-id="9766f-110"><xref:System.Data.DataView>LINQ to DataSet 쿼리에서 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-110">A <xref:System.Data.DataView> object can be created from a LINQ to DataSet query.</span></span> <span data-ttu-id="9766f-111">해당 쿼리에 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A> 또는 <xref:System.Linq.Enumerable.ThenByDescending%2A> 절이 있는 경우 이러한 절의 식은 <xref:System.Data.DataView>의 데이터를 정렬하기 위한 기본 요소로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-111">If that query contains an <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>, or <xref:System.Linq.Enumerable.ThenByDescending%2A> clause the expressions in these clauses are used as the basis for sorting the data in the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="9766f-112">예를 들어 쿼리에 `Order By…` 및 `Then By…` 절이 있는 경우 결과 <xref:System.Data.DataView>는 지정된 두 열을 기준으로 데이터를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-112">For example, if the query contains the `Order By…`and `Then By…` clauses, the resulting <xref:System.Data.DataView> would order the data by both columns specified.</span></span>  
  
 <span data-ttu-id="9766f-113">식 기반 정렬은 간단한 문자열 기반 정렬에 비해 강력하고 복잡한 정렬 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-113">Expression-based sorting offers more powerful and complex sorting than the simpler string-based sorting.</span></span> <span data-ttu-id="9766f-114">문자열 기반 정렬 및 식 기반 정렬은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-114">Note that string-based and expression-based sorting are mutually exclusive.</span></span> <span data-ttu-id="9766f-115">쿼리에서 <xref:System.Data.DataView.Sort%2A>를 만든 후에 문자열 기반 <xref:System.Data.DataView>를 설정하면 쿼리에서 유추된 식 기반 필터가 지워지며, 이 필터는 재설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-115">If the string-based <xref:System.Data.DataView.Sort%2A> is set after a <xref:System.Data.DataView> is created from a query, the expression-based filter inferred from the query is cleared and cannot be reset.</span></span>  
  
 <span data-ttu-id="9766f-116"><xref:System.Data.DataView>의 인덱스는 <xref:System.Data.DataView>가 만들어지거나 정렬 또는 필터링 정보가 수정될 때 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-116">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="9766f-117">를 만든 LINQ to DataSet 쿼리에서 정렬 기준을 제공 하 <xref:System.Data.DataView> 고 나중에 정렬 정보를 수정 하지 않는 것이 가장 좋은 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-117">You get the best performance by supplying sorting criteria in the LINQ to DataSet query that the <xref:System.Data.DataView> is created from and not modifying the sorting information, later.</span></span> <span data-ttu-id="9766f-118">자세한 내용은 [DataView 성능](dataview-performance.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9766f-118">For more information, see [DataView Performance](dataview-performance.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9766f-119">대부분의 경우 정렬에 사용되는 식은 파생 효과가 없어야 하고 명확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-119">In most cases, the expressions used for sorting should not have side effects and must be deterministic.</span></span> <span data-ttu-id="9766f-120">또한 정렬 작업이 여러 번 실행될 수 있으므로 이러한 식에는 실행 집합 번호에 따라 달라지는 논리가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-120">Also, the expressions should not contain any logic that depends on a set number of executions, because the sorting operations might be executed any number of times.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9766f-121">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-121">Example</span></span>  

 <span data-ttu-id="9766f-122">다음 예제에서는 SalesOrderHeader 테이블을 쿼리하여 반환된 행을 주문 날짜를 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-122">The following example queries the SalesOrderHeader table and orders the returned rows by the order date; creates a <xref:System.Data.DataView> from that query; and binds the <xref:System.Data.DataView> to a <xref:System.Windows.Forms.BindingSource>.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a><span data-ttu-id="9766f-123">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-123">Example</span></span>  

 <span data-ttu-id="9766f-124">다음 예제에서는 SalesOrderHeader 테이블을 쿼리하여 반환된 행을 합계 금액을 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-124">The following example queries the SalesOrderHeader table and orders the returned row by total amount due; creates a <xref:System.Data.DataView> from that query; and binds the <xref:System.Data.DataView> to a <xref:System.Windows.Forms.BindingSource>.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a><span data-ttu-id="9766f-125">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-125">Example</span></span>  

 <span data-ttu-id="9766f-126">다음 예제에서는 SalesOrderDetail 테이블을 쿼리하여 반환된 행을 주문 수량과 판매 주문 ID를 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-126">The following example queries the SalesOrderDetail table and orders the returned rows by order quantity and then by sales order ID; creates a <xref:System.Data.DataView> from that query; and binds the <xref:System.Data.DataView> to a <xref:System.Windows.Forms.BindingSource>.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a><span data-ttu-id="9766f-127">문자열 기반 정렬 속성 사용</span><span class="sxs-lookup"><span data-stu-id="9766f-127">Using the String-Based Sort Property</span></span>  

 <span data-ttu-id="9766f-128">의 문자열 기반 정렬 기능은 <xref:System.Data.DataView> 여전히 LINQ to DataSet와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-128">The string-based sorting functionality of <xref:System.Data.DataView> still works with LINQ to DataSet.</span></span> <span data-ttu-id="9766f-129">LINQ to DataSet 쿼리에서를 만든 후에는 <xref:System.Data.DataView> 속성을 사용 하 여에 대 한 <xref:System.Data.DataView.Sort%2A> 정렬을 설정할 수 있습니다 <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="9766f-129">After a <xref:System.Data.DataView> has been created from a LINQ to DataSet query, you can use the <xref:System.Data.DataView.Sort%2A> property to set the sorting on the <xref:System.Data.DataView>.</span></span>  
  
 <span data-ttu-id="9766f-130">문자열 기반 정렬 및 식 기반 정렬 기능은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-130">The string-based and expression-based sorting functionality are mutually exclusive.</span></span> <span data-ttu-id="9766f-131"><xref:System.Data.DataView.Sort%2A> 속성을 설정하면 <xref:System.Data.DataView>가 만들어진 쿼리에서 상속된 식 기반 정렬이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-131">Setting the <xref:System.Data.DataView.Sort%2A> property will clear the expression-based sort inherited from the query that the <xref:System.Data.DataView> was created from.</span></span>  
  
 <span data-ttu-id="9766f-132">문자열 기반 필터링에 대 한 자세한 내용은 <xref:System.Data.DataView.Sort%2A> [데이터 정렬 및 필터링](./dataset-datatable-dataview/sorting-and-filtering-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9766f-132">For more information about string-based <xref:System.Data.DataView.Sort%2A> filtering, see [Sorting and Filtering Data](./dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="9766f-133">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-133">Example</span></span>  

 <span data-ttu-id="9766f-134">다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 내림차순으로 행을 정렬하고, 이름을 기준으로 오름차순으로 행을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-134">The follow example creates a <xref:System.Data.DataView> from the Contact table and sorts the rows by last name in descending order, then first name in ascending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a><span data-ttu-id="9766f-135">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-135">Example</span></span>  

 <span data-ttu-id="9766f-136">다음 예제에서는 Contact 테이블에 대해 &quot;S&quot;로 시작하는 성을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-136">The following example queries the Contact table for last names that start with the letter "S".</span></span>  <span data-ttu-id="9766f-137">해당 쿼리에서 <xref:System.Data.DataView>가 만들어지고 <xref:System.Windows.Forms.BindingSource> 개체에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-137">A <xref:System.Data.DataView> is created from that query and bound to a <xref:System.Windows.Forms.BindingSource> object.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a><span data-ttu-id="9766f-138">정렬 지우기</span><span class="sxs-lookup"><span data-stu-id="9766f-138">Clearing the Sort</span></span>  

 <span data-ttu-id="9766f-139"><xref:System.Data.DataView>의 정렬 정보는 설정된 후에 <xref:System.Data.DataView.Sort%2A> 속성을 사용하여 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-139">The sorting information on a <xref:System.Data.DataView> can be cleared after it has been set using the <xref:System.Data.DataView.Sort%2A> property.</span></span> <span data-ttu-id="9766f-140">두 가지 방법으로 <xref:System.Data.DataView>의 정렬 정보를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-140">There are two ways to clear the sorting information in <xref:System.Data.DataView>:</span></span>  
  
- <span data-ttu-id="9766f-141"><xref:System.Data.DataView.Sort%2A> 속성을 `null`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-141">Set the <xref:System.Data.DataView.Sort%2A> property to `null`.</span></span>  
  
- <span data-ttu-id="9766f-142"><xref:System.Data.DataView.Sort%2A> 속성을 빈 문자열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-142">Set the <xref:System.Data.DataView.Sort%2A> property to an empty string.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9766f-143">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-143">Example</span></span>  

 <span data-ttu-id="9766f-144">다음 예제에서는 쿼리에서 <xref:System.Data.DataView>를 만든 다음 <xref:System.Data.DataView.Sort%2A> 속성을 빈 문자열로 설정하여 정렬을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-144">The following example creates a <xref:System.Data.DataView> from a query and clears the sorting by setting the <xref:System.Data.DataView.Sort%2A> property to an empty string:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a><span data-ttu-id="9766f-145">예제</span><span class="sxs-lookup"><span data-stu-id="9766f-145">Example</span></span>  

 <span data-ttu-id="9766f-146">다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 내림차순으로 정렬하도록 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-146">The following example creates a <xref:System.Data.DataView> from the Contact table and sets the <xref:System.Data.DataView.Sort%2A> property to sort by last name in descending order.</span></span> <span data-ttu-id="9766f-147">그런 다음 <xref:System.Data.DataView.Sort%2A> 속성을 `null`로 설정하여 정렬 정보를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9766f-147">The sorting information is then cleared by setting the <xref:System.Data.DataView.Sort%2A> property to `null`:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a><span data-ttu-id="9766f-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9766f-148">See also</span></span>

- [<span data-ttu-id="9766f-149">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9766f-149">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
- [<span data-ttu-id="9766f-150">DataView로 필터링</span><span class="sxs-lookup"><span data-stu-id="9766f-150">Filtering with DataView</span></span>](filtering-with-dataview-linq-to-dataset.md)
- <span data-ttu-id="9766f-151">[데이터 정렬](/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9766f-151">[Sorting Data](/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))</span></span>
