---
description: '자세한 정보: Aggregate 절 (Visual Basic)'
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 404cb4091bc11132450cf0d8d001ce426439ece7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700665"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="5a633-103">Aggregate 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a633-103">Aggregate Clause (Visual Basic)</span></span>

<span data-ttu-id="5a633-104">하나 이상의 집계 함수를 컬렉션에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-104">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a633-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a633-105">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="5a633-106">부분</span><span class="sxs-lookup"><span data-stu-id="5a633-106">Parts</span></span>  
  
|<span data-ttu-id="5a633-107">용어</span><span class="sxs-lookup"><span data-stu-id="5a633-107">Term</span></span>|<span data-ttu-id="5a633-108">정의</span><span class="sxs-lookup"><span data-stu-id="5a633-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="5a633-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5a633-109">Required.</span></span> <span data-ttu-id="5a633-110">컬렉션의 요소를 반복 하는 데 사용 되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-110">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="5a633-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-111">Optional.</span></span> <span data-ttu-id="5a633-112">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-112">The type of `element`.</span></span> <span data-ttu-id="5a633-113">형식이 지정 되지 않은 경우의 형식은 `element` 에서 유추 됩니다 `collection` .</span><span class="sxs-lookup"><span data-stu-id="5a633-113">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="5a633-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-114">Required.</span></span> <span data-ttu-id="5a633-115">작업할 컬렉션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-115">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="5a633-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-116">Optional.</span></span> <span data-ttu-id="5a633-117">`Where`집계 절 또는 절을에 적용 하는 쿼리 결과를 구체화 하는 절과 같은 하나 이상의 쿼리 절입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-117">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="5a633-118">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-118">Required.</span></span> <span data-ttu-id="5a633-119">컬렉션에 적용할 집계 함수를 식별 하는 쉼표로 구분 된 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-119">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="5a633-120">집계 함수에 별칭을 적용 하 여 쿼리 결과의 멤버 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-120">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="5a633-121">별칭을 제공 하지 않으면 집계 함수의 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-121">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="5a633-122">예제는이 항목의 뒷부분에 나오는 집계 함수에 대 한 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a633-122">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a633-123">설명</span><span class="sxs-lookup"><span data-stu-id="5a633-123">Remarks</span></span>  

 <span data-ttu-id="5a633-124">`Aggregate`절은 쿼리에 집계 함수를 포함 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-124">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="5a633-125">집계 함수는 값 집합에 대 한 검사 및 계산을 수행 하 고 단일 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-125">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="5a633-126">쿼리 결과 형식의 멤버를 사용 하 여 계산 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-126">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="5a633-127">사용할 수 있는 표준 집계 함수는,,,,,, `All` `Any` `Average` `Count` `LongCount` `Max` `Min` 및 `Sum` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-127">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="5a633-128">이러한 함수는 SQL의 집계에 대해 잘 알고 있는 개발자에 게 친숙 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-128">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="5a633-129">이러한 내용은이 항목의 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-129">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="5a633-130">집계 함수의 결과는 쿼리 결과 형식의 필드로 쿼리 결과에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-130">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="5a633-131">집계 함수 결과에 대 한 별칭을 제공 하 여 집계 값을 포함 하는 쿼리 결과 형식의 멤버 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-131">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="5a633-132">별칭을 제공 하지 않으면 집계 함수의 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-132">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="5a633-133">`Aggregate`절은 쿼리를 시작 하거나 쿼리에 추가 절로 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-133">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="5a633-134">`Aggregate`절이 쿼리를 시작 하는 경우 결과는 절에 지정 된 집계 함수의 결과인 단일 값입니다 `Into` .</span><span class="sxs-lookup"><span data-stu-id="5a633-134">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="5a633-135">절에 둘 이상의 집계 함수가 지정 된 경우 `Into` 쿼리에서는 절에 있는 각 집계 함수의 결과를 참조 하는 개별 속성이 있는 단일 형식을 반환 합니다 `Into` .</span><span class="sxs-lookup"><span data-stu-id="5a633-135">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="5a633-136">`Aggregate`절이 쿼리에 추가 절로 포함 된 경우 쿼리 컬렉션에서 반환 되는 형식에는 절의 각 집계 함수에 대 한 결과를 참조 하는 별도의 속성이 포함 됩니다 `Into` .</span><span class="sxs-lookup"><span data-stu-id="5a633-136">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="5a633-137">집계 함수</span><span class="sxs-lookup"><span data-stu-id="5a633-137">Aggregate Functions</span></span>

<span data-ttu-id="5a633-138">다음은 절에서 사용할 수 있는 표준 집계 함수입니다 `Aggregate` .</span><span class="sxs-lookup"><span data-stu-id="5a633-138">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="5a633-139">모두</span><span class="sxs-lookup"><span data-stu-id="5a633-139">All</span></span>

<span data-ttu-id="5a633-140">`true`컬렉션의 모든 요소가 지정 된 조건을 만족 하면를 반환 하 고, 그렇지 않으면 `false` 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-140">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="5a633-141">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-141">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="5a633-142">임의</span><span class="sxs-lookup"><span data-stu-id="5a633-142">Any</span></span>

<span data-ttu-id="5a633-143">`true`지정 된 조건을 만족 하는 컬렉션의 요소가 있으면를 반환 하 고, 그렇지 않으면 `false` 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-143">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="5a633-144">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-144">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="5a633-145">평균</span><span class="sxs-lookup"><span data-stu-id="5a633-145">Average</span></span>

<span data-ttu-id="5a633-146">컬렉션의 모든 요소에 대 한 평균을 계산 하거나 컬렉션의 모든 요소에 대해 제공 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-146">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="5a633-147">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-147">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="5a633-148">개수</span><span class="sxs-lookup"><span data-stu-id="5a633-148">Count</span></span>

<span data-ttu-id="5a633-149">컬렉션의 요소 수를 셉니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-149">Counts the number of elements in the collection.</span></span> <span data-ttu-id="5a633-150">`Boolean`컬렉션에서 조건에 맞는 요소 수만 계산 하는 선택적 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-150">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="5a633-151">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-151">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="5a633-152">그룹</span><span class="sxs-lookup"><span data-stu-id="5a633-152">Group</span></span>

<span data-ttu-id="5a633-153">Or 절의 결과로 그룹화 되는 쿼리 결과를 나타냅니다 `Group By` `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="5a633-153">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="5a633-154">`Group`함수는 또는 절의 절에만 사용할 수 `Into` `Group By` `Group Join` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-154">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="5a633-155">자세한 내용 및 예제는 [Group By 절](group-by-clause.md) 및 [group Join 절](group-join-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a633-155">For more information and examples, see [Group By Clause](group-by-clause.md) and [Group Join Clause](group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="5a633-156">LongCount</span><span class="sxs-lookup"><span data-stu-id="5a633-156">LongCount</span></span>

<span data-ttu-id="5a633-157">컬렉션의 요소 수를 셉니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-157">Counts the number of elements in the collection.</span></span> <span data-ttu-id="5a633-158">`Boolean`컬렉션에서 조건에 맞는 요소 수만 계산 하는 선택적 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-158">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="5a633-159">결과를로 반환 합니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="5a633-159">Returns the result as a `Long`.</span></span> <span data-ttu-id="5a633-160">예를 들어 집계 함수를 참조 하세요 `Count` .</span><span class="sxs-lookup"><span data-stu-id="5a633-160">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="5a633-161">Max</span><span class="sxs-lookup"><span data-stu-id="5a633-161">Max</span></span>

<span data-ttu-id="5a633-162">컬렉션에서 최 댓 값을 계산 하거나 컬렉션의 모든 요소에 대해 제공 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-162">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="5a633-163">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-163">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="5a633-164">최소값</span><span class="sxs-lookup"><span data-stu-id="5a633-164">Min</span></span>

<span data-ttu-id="5a633-165">컬렉션의 최소값을 계산 하거나 컬렉션의 모든 요소에 대해 제공 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-165">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="5a633-166">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-166">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="5a633-167">합계</span><span class="sxs-lookup"><span data-stu-id="5a633-167">Sum</span></span>

<span data-ttu-id="5a633-168">컬렉션에 있는 모든 요소의 합계를 계산 하거나 컬렉션의 모든 요소에 대해 제공 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-168">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="5a633-169">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-169">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="5a633-170">예제</span><span class="sxs-lookup"><span data-stu-id="5a633-170">Example</span></span>  

<span data-ttu-id="5a633-171">다음 예에서는 절을 사용 하 여 `Aggregate` 쿼리 결과에 집계 함수를 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-171">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="5a633-172">User-Defined 집계 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="5a633-172">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="5a633-173">형식에 확장 메서드를 추가 하 여 쿼리 식에 사용자 지정 집계 함수를 포함할 수 있습니다 <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="5a633-173">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="5a633-174">그런 다음 사용자 지정 메서드는 집계 함수를 참조 하는 열거 가능한 컬렉션에 대해 계산 또는 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-174">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="5a633-175">확장 메서드에 대한 자세한 내용은 [확장 메서드](../../programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a633-175">For more information about extension methods, see [Extension Methods](../../programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="5a633-176">예를 들어 다음 예제에서는 숫자 컬렉션의 중앙값을 계산 하는 사용자 지정 집계 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-176">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="5a633-177">확장 메서드에는 두 개의 오버 로드가 있습니다 `Median` .</span><span class="sxs-lookup"><span data-stu-id="5a633-177">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="5a633-178">첫 번째 오버 로드는 형식의 컬렉션인를 입력으로 받아들입니다 `IEnumerable(Of Double)` .</span><span class="sxs-lookup"><span data-stu-id="5a633-178">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="5a633-179">`Median`형식의 쿼리 필드에 대해 집계 함수를 호출 하면 `Double` 이 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-179">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="5a633-180">메서드의 두 번째 오버 로드는 `Median` 모든 제네릭 형식으로 전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a633-180">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="5a633-181">메서드의 제네릭 오버 로드는 `Median` 람다 식을 참조 하는 두 번째 매개 변수를 사용 `Func(Of T, Double)` 하 여 컬렉션에서 형식의 값을 해당 형식의 값으로 프로젝션 합니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="5a633-181">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="5a633-182">그런 다음 중앙값의 계산을 메서드의 다른 오버 로드에 위임 합니다 `Median` .</span><span class="sxs-lookup"><span data-stu-id="5a633-182">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="5a633-183">람다 식에 대 한 자세한 내용은 [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a633-183">For more information about lambda expressions, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="5a633-184">다음 예제에서는 `Median` 형식의 컬렉션 및 형식의 컬렉션에서 집계 함수를 호출 하는 샘플 쿼리를 보여 줍니다 `Integer` `Double` .</span><span class="sxs-lookup"><span data-stu-id="5a633-184">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="5a633-185">형식의 컬렉션에서 집계 함수를 호출 하는 쿼리는 입력 `Median` `Double` `Median` 으로 형식의 컬렉션을 허용 하는 메서드의 오버 로드를 호출 합니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="5a633-185">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="5a633-186">`Median`형식의 컬렉션에 대 한 집계 함수를 호출 하는 쿼리는 `Integer` 메서드의 제네릭 오버 로드를 호출 합니다 `Median` .</span><span class="sxs-lookup"><span data-stu-id="5a633-186">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="5a633-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a633-187">See also</span></span>

- [<span data-ttu-id="5a633-188">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="5a633-188">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5a633-189">쿼리</span><span class="sxs-lookup"><span data-stu-id="5a633-189">Queries</span></span>](index.md)
- [<span data-ttu-id="5a633-190">Select 절</span><span class="sxs-lookup"><span data-stu-id="5a633-190">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="5a633-191">From 절</span><span class="sxs-lookup"><span data-stu-id="5a633-191">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="5a633-192">Where 절</span><span class="sxs-lookup"><span data-stu-id="5a633-192">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="5a633-193">Group By 절</span><span class="sxs-lookup"><span data-stu-id="5a633-193">Group By Clause</span></span>](group-by-clause.md)
