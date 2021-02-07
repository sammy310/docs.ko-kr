---
description: '자세한 정보: DataView 개체 만들기 (LINQ to DataSet)'
title: DataView 개체 만들기(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: 4261e4bf55616a56652cb111d3660210dc3f96f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663822"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a><span data-ttu-id="165ac-103">DataView 개체 만들기(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="165ac-103">Creating a DataView Object (LINQ to DataSet)</span></span>

<span data-ttu-id="165ac-104">LINQ to DataSet 컨텍스트에서를 만드는 방법에는 두 가지가 있습니다 <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="165ac-104">There are two ways to create a <xref:System.Data.DataView> in the LINQ to DataSet context.</span></span> <span data-ttu-id="165ac-105"><xref:System.Data.DataView>에 대 한 LINQ to DataSet 쿼리에서를 만들거나 형식화 <xref:System.Data.DataTable> 되거나 형식화 되지 않은에서 만들 수 있습니다 <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="165ac-105">You can create a <xref:System.Data.DataView> from a LINQ to DataSet query over a <xref:System.Data.DataTable>, or you can create it from a typed or un-typed <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="165ac-106">두 경우 모두 <xref:System.Data.DataView> 확장 메서드 중 하나를 사용 하 여를 만듭니다 <xref:System.Data.DataTableExtensions.AsDataView%2A> . <xref:System.Data.DataView> 는 LINQ to DataSet 컨텍스트에서 직접 생성 가능 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-106">In both cases, you create the <xref:System.Data.DataView> by using one of the <xref:System.Data.DataTableExtensions.AsDataView%2A> extension methods; <xref:System.Data.DataView> is not directly constructible in the LINQ to DataSet context.</span></span>  
  
 <span data-ttu-id="165ac-107"><xref:System.Data.DataView>를 만든 후에 Windows Forms 애플리케이션 또는 ASP.NET 애플리케이션의 UI 컨트롤에 바인딩하거나 필터링 및 정렬 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-107">After the <xref:System.Data.DataView> has been created, you can bind it to a UI control in a Windows forms application or an ASP.NET application, or change the filtering and sorting settings.</span></span>  
  
 <span data-ttu-id="165ac-108"><xref:System.Data.DataView>에서 만든 인덱스는 필터링 및 정렬과 같이 인덱스를 사용할 수 있는 작업의 성능을 크게 높여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-108"><xref:System.Data.DataView> constructs an index, which significantly increases the performance of operations that can use the index, such as filtering and sorting.</span></span> <span data-ttu-id="165ac-109"><xref:System.Data.DataView>의 인덱스는 <xref:System.Data.DataView>가 만들어지거나 정렬 또는 필터링 정보가 수정될 때 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="165ac-110"><xref:System.Data.DataView>를 만든 다음 정렬 또는 필터링 정보를 설정하면 <xref:System.Data.DataView>가 만들어질 때와 정렬 또는 필터 속성이 수정될 때 각각 한 번씩 인덱스가 작성되므로 적어도 두 개의 인덱스가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="165ac-111">을 사용 하 여 필터링 하 고 정렬 하는 방법에 대 한 자세한 내용은 <xref:System.Data.DataView> [dataview를 사용 하 여 필터링](filtering-with-dataview-linq-to-dataset.md) 및 [dataview로 정렬](sorting-with-dataview-linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="165ac-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a><span data-ttu-id="165ac-112">LINQ to DataSet 쿼리에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="165ac-112">Creating DataView from a LINQ to DataSet Query</span></span>  

 <span data-ttu-id="165ac-113"><xref:System.Data.DataView>LINQ to DataSet 쿼리의 결과에서 개체를 만들 수 있습니다. 여기서 결과는 개체의 프로젝션 <xref:System.Data.DataRow> 입니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-113">A <xref:System.Data.DataView> object can be created from the results of a LINQ to DataSet query, where the results are a projection of <xref:System.Data.DataRow> objects.</span></span> <span data-ttu-id="165ac-114">새로 만들어진 <xref:System.Data.DataView>는 자신을 만든 쿼리의 필터링 및 정렬 정보를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-114">The newly created <xref:System.Data.DataView> inherits the filtering and sorting information from the query it is created from.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="165ac-115">대부분의 경우 필터링 및 정렬에 사용되는 식은 파생 효과가 없어야 하고 명확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-115">In most cases, the expressions used for filtering and sorting should not have side effects and must be deterministic.</span></span> <span data-ttu-id="165ac-116">또한 정렬 및 필터링 작업이 여러 번 실행될 수 있으므로 이러한 식에는 실행 집합 번호에 따라 달라지는 논리가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-116">Also, the expressions should not contain any logic that depend on a set number of executions, as the sorting and filtering operations may be executed any number of times.</span></span>  
  
 <span data-ttu-id="165ac-117">익명 형식을 반환하는 쿼리 또는 조인 연산을 수행하는 쿼리에서는 <xref:System.Data.DataView>를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-117">Creating a <xref:System.Data.DataView> from a query that returns anonymous types or queries that perform join operations is not supported.</span></span>  
  
 <span data-ttu-id="165ac-118"><xref:System.Data.DataView>를 만드는 데 사용하는 쿼리에서는 다음과 같은 쿼리 연산자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-118">Only the following query operators are supported in a query used to create <xref:System.Data.DataView>:</span></span>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 <span data-ttu-id="165ac-119"><xref:System.Data.DataView>LINQ to DataSet 쿼리에서을 만드는 경우 <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> 메서드는 쿼리에서 호출 된 마지막 메서드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-119">Note that when a <xref:System.Data.DataView> is created from a LINQ to DataSet query the <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> method must be the final method called in the query.</span></span> <span data-ttu-id="165ac-120">다음 예제에서는이를 보여 줍니다. 다음 예제에서는 온라인 주문 합계를 기준으로 정렬 된를 만듭니다 <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="165ac-120">This is shown in the following example, which creates a <xref:System.Data.DataView> of online orders sorted by total due:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 <span data-ttu-id="165ac-121">문자열 기반 및 속성을 사용 하 여 <xref:System.Data.DataView.RowFilter%2A> <xref:System.Data.DataView.Sort%2A> 쿼리를 만든 후에 필터링 하 고 정렬할 수도 있습니다 <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="165ac-121">You can also use the string-based <xref:System.Data.DataView.RowFilter%2A> and <xref:System.Data.DataView.Sort%2A> properties to filter and sort a <xref:System.Data.DataView> after it has been created from a query.</span></span> <span data-ttu-id="165ac-122">이렇게 하면 쿼리에서 상속된 정렬 및 필터링 정보가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-122">Note that this will clear the sorting and filtering information inherited from the query.</span></span> <span data-ttu-id="165ac-123">다음 예에서는 <xref:System.Data.DataView> ' '로 시작 하는 성을 기준으로 필터링 하는 LINQ to DataSet 쿼리에서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-123">The following example creates a <xref:System.Data.DataView> from a LINQ to DataSet query that filters by last names that start with 'S'.</span></span> <span data-ttu-id="165ac-124">성을 기준으로 오름차순으로 정렬한 다음 이름을 기준으로 내림차순으로 정렬하도록 문자열 기반 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-124">The string-based <xref:System.Data.DataView.Sort%2A> property is set to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a><span data-ttu-id="165ac-125">DataTable에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="165ac-125">Creating a DataView from a DataTable</span></span>  

 <span data-ttu-id="165ac-126">LINQ to DataSet 쿼리에서 만드는 것 외에도 <xref:System.Data.DataView> <xref:System.Data.DataTable> 메서드를 사용 하 여에서 개체를 만들 수 있습니다 <xref:System.Data.DataTableExtensions.AsDataView%2A> .</span><span class="sxs-lookup"><span data-stu-id="165ac-126">In addition to being created from a LINQ to DataSet query, a <xref:System.Data.DataView> object can be created from a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTableExtensions.AsDataView%2A> method.</span></span>  
  
 <span data-ttu-id="165ac-127">다음 예제에서는 SalesOrderDetail 테이블에서 <xref:System.Data.DataView>를 만든 다음 <xref:System.Windows.Forms.BindingSource> 개체의 데이터 소스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-127">The following example creates a <xref:System.Data.DataView> from the SalesOrderDetail table and sets it as the data source of a <xref:System.Windows.Forms.BindingSource> object.</span></span> <span data-ttu-id="165ac-128">이 개체는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 프록시 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-128">This object acts as a proxy for a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 <span data-ttu-id="165ac-129">에서 만든 후에 필터링 및 정렬을 설정할 수 있습니다 <xref:System.Data.DataView> <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="165ac-129">Filtering and sorting can be set on the <xref:System.Data.DataView> after it has been created from a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="165ac-130">다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 오름차순으로 정렬하고, 이름을 기준으로 내림차순으로 정렬하도록 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-130">The following example creates a <xref:System.Data.DataView> from the Contact table and sets the <xref:System.Data.DataView.Sort%2A> property to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 <span data-ttu-id="165ac-131">그러나 쿼리에서 <xref:System.Data.DataView.RowFilter%2A>를 만든 후에 <xref:System.Data.DataView.Sort%2A> 또는 <xref:System.Data.DataView> 속성을 설정하면 필터링 및 정렬 작업을 지원하기 위해 <xref:System.Data.DataView>에서 인덱스가 생성되므로 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-131">However, there is a performance loss that comes with setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property after the <xref:System.Data.DataView> has been created from a query, because <xref:System.Data.DataView> constructs an index to support filtering and sorting operations.</span></span> <span data-ttu-id="165ac-132"><xref:System.Data.DataView.RowFilter%2A> 또는 <xref:System.Data.DataView.Sort%2A> 속성을 설정하면 데이터에 대한 인덱스가 다시 작성되므로 애플리케이션에 오버헤드가 발생하여 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-132">Setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="165ac-133">가능하면 <xref:System.Data.DataView>를 처음 만들 때 필터링 및 정렬 정보를 지정하고 이후에는 수정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="165ac-133">When possible, it is better to specify the filtering and sorting information when you first create the <xref:System.Data.DataView> and avoid modifying it afterwards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165ac-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="165ac-134">See also</span></span>

- [<span data-ttu-id="165ac-135">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="165ac-135">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
- [<span data-ttu-id="165ac-136">DataView로 필터링</span><span class="sxs-lookup"><span data-stu-id="165ac-136">Filtering with DataView</span></span>](filtering-with-dataview-linq-to-dataset.md)
- [<span data-ttu-id="165ac-137">DataView로 정렬</span><span class="sxs-lookup"><span data-stu-id="165ac-137">Sorting with DataView</span></span>](sorting-with-dataview-linq-to-dataset.md)
