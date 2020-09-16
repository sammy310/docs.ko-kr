---
title: 컴파일된 쿼리(LINQ to Entities)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
ms.openlocfilehash: f3270147f0cf38a646efac603f058173daa78547
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541137"
---
# <a name="compiled-queries--linq-to-entities"></a><span data-ttu-id="6bd24-102">컴파일된 쿼리 (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="6bd24-102">Compiled queries  (LINQ to Entities)</span></span>

<span data-ttu-id="6bd24-103">구조적으로 비슷한 쿼리를 Entity Framework에서 여러 차례 실행하는 애플리케이션이 있는 경우, 쿼리를 한 번 컴파일한 후 매개 변수를 다르게 하여 여러 차례 실행하는 방법을 통해 성능을 높일 수 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-103">When you have an application that executes structurally similar queries many times in the Entity Framework, you can frequently increase performance by compiling the query one time and executing it several times with different parameters.</span></span> <span data-ttu-id="6bd24-104">예를 들어, 애플리케이션에서 특정 도시의 모든 고객을 검색해야 하며 사용자가 런타임에 양식에서 도시를 지정하는 경우를 생각해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-104">For example, an application might have to retrieve all the customers in a particular city; the city is specified at runtime by the user in a form.</span></span> <span data-ttu-id="6bd24-105">LINQ to Entities에서는 컴파일된 쿼리를 이 용도로 사용할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-105">LINQ to Entities supports using compiled queries for this purpose.</span></span>  
  
 <span data-ttu-id="6bd24-106">.NET Framework 4.5부터 LINQ 쿼리가 자동으로 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-106">Starting with .NET Framework 4.5, LINQ queries are cached automatically.</span></span> <span data-ttu-id="6bd24-107">그러나, 여전히 컴파일된 LINQ 쿼리를 사용하여 나중에 실행할 때 이러한 비용을 줄일 수 있으며 컴파일된 쿼리는 자동으로 캐시되는 LINQ 쿼리에서보다 효율적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-107">However, you can still use compiled LINQ queries to reduce this cost in later executions and compiled queries can be more efficient than LINQ queries that are automatically cached.</span></span> <span data-ttu-id="6bd24-108">메모리 내 컬렉션에 연산자를 적용 하는 LINQ to Entities 쿼리 `Enumerable.Contains` 는 자동으로 캐시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-108">LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="6bd24-109">또한 컴파일된 LINQ 쿼리에서 메모리 내 컬렉션을 매개 변수화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-109">Also, parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
 <span data-ttu-id="6bd24-110"><xref:System.Data.Objects.CompiledQuery> 클래스는 쿼리를 재사용할 수 있도록 컴파일하고 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-110">The <xref:System.Data.Objects.CompiledQuery> class provides compilation and caching of queries for reuse.</span></span> <span data-ttu-id="6bd24-111">개념상 이 클래스에는 다수의 오버로드가 있는 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-111">Conceptually, this class contains a <xref:System.Data.Objects.CompiledQuery>'s `Compile` method with several overloads.</span></span> <span data-ttu-id="6bd24-112">이 `Compile` 메서드를 호출하여 컴파일된 쿼리를 나타내는 새 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-112">Call the `Compile` method to create a new delegate to represent the compiled query.</span></span> <span data-ttu-id="6bd24-113">`Compile` 및 매개 변수 값과 함께 제공된 <xref:System.Data.Objects.ObjectContext> 메서드는 <xref:System.Linq.IQueryable%601> 인스턴스와 같이 결과를 생성하는 대리자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-113">The `Compile` methods, provided with a <xref:System.Data.Objects.ObjectContext> and parameter values, return a delegate that produces some result (such as an <xref:System.Linq.IQueryable%601> instance).</span></span> <span data-ttu-id="6bd24-114">쿼리는 첫 번째 실행 중에만 한 번 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-114">The query compiles once during only the first execution.</span></span> <span data-ttu-id="6bd24-115">컴파일 시에 쿼리에 대해 설정된 병합 옵션은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-115">The merge options set for the query at the time of the compilation cannot be changed later.</span></span> <span data-ttu-id="6bd24-116">쿼리가 컴파일되면 기본 형식의 매개 변수만 제공할 수 있지만 생성 된 SQL을 변경 하는 쿼리의 일부는 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-116">Once the query is compiled, you can only supply parameters of primitive type but you cannot replace parts of the query that would change the generated SQL.</span></span> <span data-ttu-id="6bd24-117">자세한 내용은 [EF Merge 옵션 및 컴파일된 쿼리](/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bd24-117">For more information, see [EF Merge Options and Compiled Queries](/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries).</span></span>
  
 <span data-ttu-id="6bd24-118">의 메서드가 컴파일하는 LINQ to Entities 쿼리 <xref:System.Data.Objects.CompiledQuery> 식은 `Compile` 와 같은 제네릭 대리자 중 하나로 표시 됩니다 `Func` <xref:System.Func%605> .</span><span class="sxs-lookup"><span data-stu-id="6bd24-118">The LINQ to Entities query expression that the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method compiles is represented by one of the generic `Func` delegates, such as <xref:System.Func%605>.</span></span> <span data-ttu-id="6bd24-119">쿼리 식은 최대로 `ObjectContext` 매개 변수 1개, 반환 매개 변수 1개 및 쿼리 매개 변수 16개를 캡슐화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-119">At most, the query expression can encapsulate an `ObjectContext` parameter, a return parameter, and 16 query parameters.</span></span> <span data-ttu-id="6bd24-120">쿼리 매개 변수가 17개 이상 필요한 경우 속성으로 쿼리 매개 변수를 나타내는 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-120">If more than 16 query parameters are required, you can create a structure whose properties represent query parameters.</span></span> <span data-ttu-id="6bd24-121">속성을 설정한 후 쿼리 식에서 구조의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-121">You can then use the properties on the structure in the query expression after you set the properties.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="6bd24-122">예 1</span><span class="sxs-lookup"><span data-stu-id="6bd24-122">Example 1</span></span>  
 <span data-ttu-id="6bd24-123">다음 예제에서는 <xref:System.Decimal> 입력 매개 변수를 허용 하 고 total이 $200.00 보다 크거나 같은 일련의 주문을 반환 하는 쿼리를 컴파일한 다음 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-123">The following example compiles and then invokes a query that accepts a <xref:System.Decimal> input parameter and returns a sequence of orders where the total due is greater than or equal to $200.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query 2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples - compiled query2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## <a name="example-2"></a><span data-ttu-id="6bd24-124">예제 2</span><span class="sxs-lookup"><span data-stu-id="6bd24-124">Example 2</span></span>  
 <span data-ttu-id="6bd24-125">다음 예에서는 인스턴스를 반환 하는 쿼리를 컴파일한 다음 호출 합니다 <xref:System.Data.Objects.ObjectQuery%601> .</span><span class="sxs-lookup"><span data-stu-id="6bd24-125">The following example compiles and then invokes a query that returns an <xref:System.Data.Objects.ObjectQuery%601> instance:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## <a name="example-3"></a><span data-ttu-id="6bd24-126">예제 3</span><span class="sxs-lookup"><span data-stu-id="6bd24-126">Example 3</span></span>  
 <span data-ttu-id="6bd24-127">다음 예제에서는 제품 가격의 평균을 <xref:System.Decimal> 값 형태로 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-127">The following example compiles and then invokes a query that returns the average of the product list prices as a <xref:System.Decimal> value:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## <a name="example-4"></a><span data-ttu-id="6bd24-128">예제 4</span><span class="sxs-lookup"><span data-stu-id="6bd24-128">Example 4</span></span>  
 <span data-ttu-id="6bd24-129">다음 예제에서는 입력 매개 변수를 수락 하 고 해당 <xref:System.String> `Contact` 전자 메일 주소가 지정 된 문자열로 시작 하는을 반환 하는 쿼리를 컴파일한 다음 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-129">The following example compiles and then invokes a query that accepts a <xref:System.String> input parameter and then returns a `Contact` whose email address starts with the specified string:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## <a name="example-5"></a><span data-ttu-id="6bd24-130">예제 5</span><span class="sxs-lookup"><span data-stu-id="6bd24-130">Example 5</span></span>  
 <span data-ttu-id="6bd24-131">다음 예제에서는 <xref:System.DateTime> 및 <xref:System.Decimal> 입력 매개 변수를 사용하고 주문 날짜가 2003년 3월 8일 이후이고 합계 $300 미만인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-131">The following example compiles and then invokes a query that accepts <xref:System.DateTime> and <xref:System.Decimal> input parameters and returns a sequence of orders where the order date is later than March 8, 2003, and the total due is less than $300.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples - compiled query5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## <a name="example-6"></a><span data-ttu-id="6bd24-132">예제 6</span><span class="sxs-lookup"><span data-stu-id="6bd24-132">Example 6</span></span>  
 <span data-ttu-id="6bd24-133">다음 예제에서는 <xref:System.DateTime> 입력 매개 변수를 사용하고 주문 날짜가 2004년 3월 8일 이후인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-133">The following example compiles and then invokes a query that accepts a <xref:System.DateTime> input parameter and returns a sequence of orders where the order date is later than March 8, 2004.</span></span> <span data-ttu-id="6bd24-134">이 쿼리는 주문 정보를 일련의 익명 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-134">This query returns the order information as a sequence of anonymous types.</span></span> <span data-ttu-id="6bd24-135">익명 형식은 컴파일러에서 유추됩니다. 따라서 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드에서 형식 매개 변수를 지정할 수 없으며, 형식은 쿼리 자체에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-135">Anonymous types are inferred by the compiler, so you cannot specify type parameters in the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method and the type is defined in the query itself.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples - compiled query6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## <a name="example-7"></a><span data-ttu-id="6bd24-136">예제 7</span><span class="sxs-lookup"><span data-stu-id="6bd24-136">Example 7</span></span>  
 <span data-ttu-id="6bd24-137">다음 예제에서는 사용자 정의 구조 입력 매개 변수를 사용하고 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-137">The following example compiles and then invokes a query that accepts a user-defined structure input parameter and returns a sequence of orders.</span></span> <span data-ttu-id="6bd24-138">이 구조는 시작 날짜, 종료 날짜 및 수수료 합계 쿼리 매개 변수를 정의하고, 2003년 3월 3일에서 3월 8일 사이에 배송되었으며 수수료 합계가 $700.00보다 큰 주문을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-138">The structure defines start date, end date, and total due query parameters, and the query returns orders shipped between March 3 and March 8, 2003 with a total due greater than $700.00.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples - compiled query7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 <span data-ttu-id="6bd24-139">쿼리 매개 변수를 정의하는 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd24-139">The structure that defines the query parameters:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples - MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples - MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## <a name="see-also"></a><span data-ttu-id="6bd24-140">참조</span><span class="sxs-lookup"><span data-stu-id="6bd24-140">See also</span></span>

- [<span data-ttu-id="6bd24-141">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6bd24-141">ADO.NET Entity Framework</span></span>](../index.md)
- [<span data-ttu-id="6bd24-142">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6bd24-142">LINQ to Entities</span></span>](linq-to-entities.md)
- [<span data-ttu-id="6bd24-143">EF 병합 옵션 및 컴파일된 쿼리</span><span class="sxs-lookup"><span data-stu-id="6bd24-143">EF Merge Options and Compiled Queries</span></span>](/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries)
