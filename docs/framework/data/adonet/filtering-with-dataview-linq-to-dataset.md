---
description: '자세한 정보: DataView를 사용 하 여 필터링 (LINQ to DataSet)'
title: DataView로 필터링(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5632d74a-ff53-4ea7-9fe7-4a148eeb1c68
ms.openlocfilehash: 152b2e1d82cd5cf0eac24fd952de26d83fbffe58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724143"
---
# <a name="filtering-with-dataview-linq-to-dataset"></a><span data-ttu-id="9afd7-103">DataView로 필터링(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9afd7-103">Filtering with DataView (LINQ to DataSet)</span></span>

<span data-ttu-id="9afd7-104">특정 조건을 사용하여 데이터를 필터링한 다음 UI 컨트롤을 통해 클라이언트에 데이터를 제공하는 기능은 데이터 바인딩의 중요한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-104">The ability to filter data using specific criteria and then present the data to a client through a UI control is an important aspect of data binding.</span></span> <span data-ttu-id="9afd7-105"><xref:System.Data.DataView>에서는 데이터를 필터링하여 특정 필터 조건을 충족하는 데이터 행의 하위 집합을 반환하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-105"><xref:System.Data.DataView> provides several ways to filter data and return subsets of data rows meeting specific filter criteria.</span></span> <span data-ttu-id="9afd7-106">는 문자열 기반 필터링 기능 외에 <xref:System.Data.DataView> 도 필터링 조건에 LINQ 식을 사용 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-106">In addition to the string-based filtering capabilities, <xref:System.Data.DataView> also provides the ability to use LINQ expressions for the filtering criteria.</span></span> <span data-ttu-id="9afd7-107">LINQ 식을 사용 하면 문자열 기반 필터링에 비해 더 복잡 하 고 강력한 필터링 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-107">LINQ expressions allow for much more complex and powerful filtering operations than the string-based filtering.</span></span>  
  
 <span data-ttu-id="9afd7-108"><xref:System.Data.DataView>를 사용하여 데이터를 필터링하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-108">There are two ways to filter data using a <xref:System.Data.DataView>:</span></span>  
  
- <span data-ttu-id="9afd7-109"><xref:System.Data.DataView>Where 절을 사용 하 여 LINQ to DataSet 쿼리에서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-109">Create a <xref:System.Data.DataView> from a LINQ to DataSet query with a Where clause.</span></span>  
  
- <span data-ttu-id="9afd7-110"><xref:System.Data.DataView>의 기존 문자열 기반 필터링 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-110">Use the existing, string-based filtering capabilities of <xref:System.Data.DataView>.</span></span>  
  
## <a name="creating-dataview-from-a-query-with-filtering-information"></a><span data-ttu-id="9afd7-111">필터링 정보가 있는 쿼리에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="9afd7-111">Creating DataView from a Query with Filtering Information</span></span>  

 <span data-ttu-id="9afd7-112"><xref:System.Data.DataView>LINQ to DataSet 쿼리에서 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-112">A <xref:System.Data.DataView> object can be created from a LINQ to DataSet query.</span></span> <span data-ttu-id="9afd7-113">해당 쿼리에 `Where` 절이 있으면 쿼리의 필터링 정보를 사용하여 <xref:System.Data.DataView>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-113">If that query contains a `Where` clause, the <xref:System.Data.DataView> is created with the filtering information from the query.</span></span> <span data-ttu-id="9afd7-114">`Where` 절의 식은 <xref:System.Data.DataView>에 포함되는 데이터 행을 확인하는 데 사용되며 필터의 기본 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-114">The expression in the `Where` clause is used to determine which data rows will be included in the <xref:System.Data.DataView>, and is the basis for the filter.</span></span>  
  
 <span data-ttu-id="9afd7-115">식 기반 필터는 간단한 문자열 기반 필터에 비해 강력하고 복잡한 필터링 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-115">Expression-based filters offer more powerful and complex filtering than the simpler string-based filters.</span></span> <span data-ttu-id="9afd7-116">문자열 기반 필터와 식 기반 필터는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-116">The string-based and expression-based filters are mutually exclusive.</span></span> <span data-ttu-id="9afd7-117"><xref:System.Data.DataView.RowFilter%2A>를 쿼리에서 만든 후에 문자열 기반 <xref:System.Data.DataView>를 설정하면 쿼리에서 유추된 식 기반 필터가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-117">When the string-based <xref:System.Data.DataView.RowFilter%2A> is set after a <xref:System.Data.DataView> is created from a query, the expression based filter inferred from the query is cleared.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9afd7-118">대부분의 경우 필터링에 사용되는 식은 파생 작용이 없어야 하고 명확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-118">In most cases, the expressions used for filtering should not have side effects and must be deterministic.</span></span> <span data-ttu-id="9afd7-119">또한 필터링 작업이 여러 번 실행될 수 있으므로 식에는 실행 집합 번호에 따라 달라지는 논리가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-119">Also, the expressions should not contain any logic that depends on a set number of executions, because the filtering operations might be executed any number of times.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9afd7-120">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-120">Example</span></span>  

 <span data-ttu-id="9afd7-121">다음 예제에서는 SalesOrderDetail 테이블에 대해 수량이 2보다 크고 6보다 작은 주문을 쿼리한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-121">The following example queries the SalesOrderDetail table for orders with a quantity greater than 2 and less than 6; creates a <xref:System.Data.DataView> from that query; and binds the <xref:System.Data.DataView> to a <xref:System.Windows.Forms.BindingSource>:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere)]  
  
### <a name="example"></a><span data-ttu-id="9afd7-122">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-122">Example</span></span>  

 <span data-ttu-id="9afd7-123">다음 예제에서는 2001년 6월 6일 이후 주문에 대한 쿼리에서 <xref:System.Data.DataView>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-123">The following example creates a <xref:System.Data.DataView> from a query for orders placed after June 6, 2001:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere3)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere3)]  
  
### <a name="example"></a><span data-ttu-id="9afd7-124">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-124">Example</span></span>  

 <span data-ttu-id="9afd7-125">필터링을 정렬과 결합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-125">Filtering can also be combined with sorting.</span></span> <span data-ttu-id="9afd7-126">다음 예제에서는 성이 "S"로 시작하는 연락처를 성과 이름순으로 정렬하는 쿼리에서 <xref:System.Data.DataView>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-126">The following example creates a <xref:System.Data.DataView> from a query for contacts whose last name start with "S" and sorted by last name, then first name:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhereorderbythenby)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhereorderbythenby)]  
  
### <a name="example"></a><span data-ttu-id="9afd7-127">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-127">Example</span></span>  

 <span data-ttu-id="9afd7-128">다음 예제에서는 SoundEx 알고리즘을 사용하여 성이 "Zhu"와 비슷한 연락처를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-128">The following example uses the SoundEx algorithm to find contacts whose last name is similar to "Zhu".</span></span> <span data-ttu-id="9afd7-129">SoundEx 알고리즘은 SoundEx 메서드에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-129">The SoundEx algorithm is implemented in the SoundEx method.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvsoundexfilter)]
 [!code-vb[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvsoundexfilter)]  
  
 <span data-ttu-id="9afd7-130">U.S. Census Bureau에서 개발한 SoundEx는 영어 발음의 소리를 기준으로 이름을 인덱싱하는 데 사용되는 음성 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-130">SoundEx is a phonetic algorithm used for indexing names by sound, as they are pronounced in English, originally developed by the U.S. Census Bureau.</span></span> <span data-ttu-id="9afd7-131">SoundEx 메서드는 하나의 영어 문자 뒤에 숫자 3개가 있는 형식으로 구성된 이름에 대한 4문자 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-131">The SoundEx method returns a four character code for a name consisting of an English letter followed by three numbers.</span></span> <span data-ttu-id="9afd7-132">영어 문자는 이름의 첫 번째 문자이고 숫자는 이름의 나머지 자음을 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-132">The letter is the first letter of the name and the numbers encode the remaining consonants in the name.</span></span> <span data-ttu-id="9afd7-133">발음이 비슷한 이름은 같은 SoundEx 코드를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-133">Similar sounding names share the same SoundEx code.</span></span> <span data-ttu-id="9afd7-134">이전 예제의 SoundEx 메서드에 사용된 SoundEx 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-134">The SoundEx implementation used in the SoundEx method of the previous example is shown here:</span></span>  
  
 [!code-csharp[DP DataView Samples#SoundEx](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#soundex)]
 [!code-vb[DP DataView Samples#SoundEx](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#soundex)]  
  
## <a name="using-the-rowfilter-property"></a><span data-ttu-id="9afd7-135">RowFilter 속성 사용</span><span class="sxs-lookup"><span data-stu-id="9afd7-135">Using the RowFilter Property</span></span>  

 <span data-ttu-id="9afd7-136">의 기존 문자열 기반 필터링 기능은 <xref:System.Data.DataView> 여전히 LINQ to DataSet 컨텍스트에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-136">The existing string-based filtering functionality of <xref:System.Data.DataView> still works in the LINQ to DataSet context.</span></span> <span data-ttu-id="9afd7-137">문자열 기반 필터링에 대 한 자세한 내용은 <xref:System.Data.DataView.RowFilter%2A> [데이터 정렬 및 필터링](./dataset-datatable-dataview/sorting-and-filtering-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9afd7-137">For more information about string-based <xref:System.Data.DataView.RowFilter%2A> filtering, see [Sorting and Filtering Data](./dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="9afd7-138">다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 연락처의 성이 "Zhu"인 행을 반환하도록 <xref:System.Data.DataView.RowFilter%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-138">The following example creates a <xref:System.Data.DataView> from the Contact table and then sets the <xref:System.Data.DataView.RowFilter%2A> property to return rows where the contact's last name is "Zhu":</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvrowfilter)]
 [!code-vb[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvrowfilter)]  
  
 <span data-ttu-id="9afd7-139"><xref:System.Data.DataView>또는 LINQ to DataSet 쿼리에서를 만든 후에는 <xref:System.Data.DataTable> 속성을 사용 하 여 <xref:System.Data.DataView.RowFilter%2A> 열 값을 기준으로 행의 하위 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-139">After a <xref:System.Data.DataView> has been created from a <xref:System.Data.DataTable> or LINQ to DataSet query, you can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="9afd7-140">문자열 기반 필터와 식 기반 필터는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-140">The string-based and expression-based filters are mutually exclusive.</span></span> <span data-ttu-id="9afd7-141">속성을 설정 <xref:System.Data.DataView.RowFilter%2A> 하면 LINQ to DataSet 쿼리에서 유추 된 필터 식이 지워집니다. 필터 식은 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-141">Setting the <xref:System.Data.DataView.RowFilter%2A> property will clear the filter expression inferred from the LINQ to DataSet query, and the filter expression cannot be reset.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywheresetrowfilter)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywheresetrowfilter)]  
  
 <span data-ttu-id="9afd7-142">데이터의 하위 집합에 대한 동적 뷰를 제공하는 것과는 반대로 데이터에 대한 특정 쿼리 결과를 반환하려는 경우 <xref:System.Data.DataView.Find%2A> 속성을 설정하는 대신 <xref:System.Data.DataView.FindRows%2A>의 <xref:System.Data.DataView> 또는 <xref:System.Data.DataView.RowFilter%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-142">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="9afd7-143"><xref:System.Data.DataView.RowFilter%2A> 속성은 바인딩된 컨트롤이 필터링된 결과를 표시하는 데이터 바인딩된 애플리케이션에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-143">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="9afd7-144"><xref:System.Data.DataView.RowFilter%2A> 속성을 설정하면 데이터의 인덱스가 다시 작성되므로 애플리케이션에 오버헤드가 발생하여 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-144">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="9afd7-145"><xref:System.Data.DataView.Find%2A> 및 <xref:System.Data.DataView.FindRows%2A> 메서드는 인덱스를 다시 작성하지 않고 현재 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-145">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="9afd7-146"><xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A>를 한 번만 호출할 경우에는 기존 <xref:System.Data.DataView>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-146">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="9afd7-147"><xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A>를 여러 번 호출할 경우에는 새 <xref:System.Data.DataView>를 만들어서 검색하려는 열의 인덱스를 다시 작성한 다음 <xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-147">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="9afd7-148">및 메서드에 대 한 자세한 <xref:System.Data.DataView.Find%2A> 내용은 <xref:System.Data.DataView.FindRows%2A> [행](./dataset-datatable-dataview/finding-rows.md) 및 [DataView 성능](dataview-performance.md)찾기를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9afd7-148">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods see [Finding Rows](./dataset-datatable-dataview/finding-rows.md) and [DataView Performance](dataview-performance.md).</span></span>  
  
## <a name="clearing-the-filter"></a><span data-ttu-id="9afd7-149">필터 지우기</span><span class="sxs-lookup"><span data-stu-id="9afd7-149">Clearing the Filter</span></span>  

 <span data-ttu-id="9afd7-150">필터링이 설정된 후 <xref:System.Data.DataView> 속성을 사용하여 <xref:System.Data.DataView.RowFilter%2A>의 필터를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-150">The filter on a <xref:System.Data.DataView> can be cleared after filtering has been set using the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="9afd7-151"><xref:System.Data.DataView>의 필터는 두 가지 방법으로 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-151">The filter on a <xref:System.Data.DataView> can be cleared in two different ways:</span></span>  
  
- <span data-ttu-id="9afd7-152"><xref:System.Data.DataView.RowFilter%2A> 속성을 `null`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-152">Set the <xref:System.Data.DataView.RowFilter%2A> property to `null`.</span></span>  
  
- <span data-ttu-id="9afd7-153"><xref:System.Data.DataView.RowFilter%2A> 속성을 빈 문자열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-153">Set the <xref:System.Data.DataView.RowFilter%2A> property to an empty string.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9afd7-154">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-154">Example</span></span>  

 <span data-ttu-id="9afd7-155">다음 예제에서는 쿼리에서 <xref:System.Data.DataView>를 만든 다음 <xref:System.Data.DataView.RowFilter%2A> 속성을 `null`로 설정하여 필터를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-155">The following example creates a <xref:System.Data.DataView> from a query and then clears the filter by setting <xref:System.Data.DataView.RowFilter%2A> property to `null`:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter2)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter2)]  
  
### <a name="example"></a><span data-ttu-id="9afd7-156">예제</span><span class="sxs-lookup"><span data-stu-id="9afd7-156">Example</span></span>  

 <span data-ttu-id="9afd7-157">다음 예제에서는 테이블에서 <xref:System.Data.DataView>를 만들고, <xref:System.Data.DataView.RowFilter%2A> 속성을 설정한 다음 <xref:System.Data.DataView.RowFilter%2A> 속성을 빈 문자열로 설정하여 필터를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9afd7-157">The following example creates a <xref:System.Data.DataView> from a table sets the <xref:System.Data.DataView.RowFilter%2A> property, and then clears the filter by setting the <xref:System.Data.DataView.RowFilter%2A> property to an empty string:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter)]  
  
## <a name="see-also"></a><span data-ttu-id="9afd7-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9afd7-158">See also</span></span>

- [<span data-ttu-id="9afd7-159">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9afd7-159">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
- [<span data-ttu-id="9afd7-160">DataView로 정렬</span><span class="sxs-lookup"><span data-stu-id="9afd7-160">Sorting with DataView</span></span>](sorting-with-dataview-linq-to-dataset.md)
