---
title: Aggregate 절(Visual Basic)
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
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712632"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="23c56-102">Aggregate 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c56-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="23c56-103">컬렉션에 하나 이상의 집계 함수를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c56-104">구문</span><span class="sxs-lookup"><span data-stu-id="23c56-104">Syntax</span></span>  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="23c56-105">요소</span><span class="sxs-lookup"><span data-stu-id="23c56-105">Parts</span></span>  
  
|<span data-ttu-id="23c56-106">용어</span><span class="sxs-lookup"><span data-stu-id="23c56-106">Term</span></span>|<span data-ttu-id="23c56-107">정의</span><span class="sxs-lookup"><span data-stu-id="23c56-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="23c56-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c56-108">Required.</span></span> <span data-ttu-id="23c56-109">컬렉션의 요소를 반복 하는 데 사용 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="23c56-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-110">Optional.</span></span> <span data-ttu-id="23c56-111">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-111">The type of `element`.</span></span> <span data-ttu-id="23c56-112">형식이 지정 되지 않은, 경우 유형의 `element` 에서 유추 됩니다 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="23c56-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c56-113">Required.</span></span> <span data-ttu-id="23c56-114">에 적용할 컬렉션을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="23c56-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-115">Optional.</span></span> <span data-ttu-id="23c56-116">하나 이상의 절 등 쿼리는 `Where` aggregate 절 또는 절을 적용 하 여 쿼리 결과를 구체화할 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="23c56-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23c56-117">Required.</span></span> <span data-ttu-id="23c56-118">하나 이상의 쉼표로 구분 된 식 컬렉션에 적용할 집계 함수를 식별 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="23c56-119">쿼리 결과에 멤버 이름을 지정 하는 집계 함수에 별칭을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="23c56-120">별칭 없음이 제공 하는 경우 집계 함수의 이름 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="23c56-121">예를 들어이 항목의 뒷부분에 나오는 집계 함수에 대 한 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c56-122">설명</span><span class="sxs-lookup"><span data-stu-id="23c56-122">Remarks</span></span>  
 <span data-ttu-id="23c56-123">`Aggregate` 쿼리에서 집계 함수를 포함 하려면 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="23c56-124">집계 함수는 값의 집합에 대해 검사 및 계산을 수행 하 고 단일 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="23c56-125">쿼리 결과 형식의 멤버를 사용 하 여 계산 된 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="23c56-126">사용할 수 있는 표준 집계 함수를 `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, 및 `Sum` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="23c56-127">이러한 함수는 sql에서 집계에 익숙한 개발자에 게 친숙 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="23c56-128">이 항목의 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="23c56-129">집계 함수의 결과 쿼리 결과 형식의 필드와 쿼리 결과에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="23c56-130">집계 값을 포함 하는 쿼리 결과 형식의 멤버의 이름을 지정 하는 집계 함수 결과 대 한 별칭을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="23c56-131">별칭 없음이 제공 하는 경우 집계 함수의 이름 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="23c56-132">`Aggregate` 절에 쿼리를 시작할 수 또는 추가 쿼리 절과 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="23c56-133">경우는 `Aggregate` 절에 쿼리 시작 되는 결과에 지정 된 집계 함수의 결과인 단일 값을 `Into` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="23c56-134">둘 이상의 집계 함수에 지정 된 경우는 `Into` 절 쿼리 결과의 각 집계 함수를 참조 하는 별도 속성을 사용 하 여 단일 형식을 반환 합니다.는 `Into` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="23c56-135">경우는 `Aggregate` 절 추가 쿼리 절과 포함 되는지, 쿼리 컬렉션에서 반환 되는 형식 결과의 각 집계 함수를 참조 하려면 별도 속성은는 `Into` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="23c56-136">집계 함수</span><span class="sxs-lookup"><span data-stu-id="23c56-136">Aggregate Functions</span></span>

<span data-ttu-id="23c56-137">다음은 사용할 수 있는 표준 집계 함수는 `Aggregate` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="23c56-138">모두</span><span class="sxs-lookup"><span data-stu-id="23c56-138">All</span></span>

<span data-ttu-id="23c56-139">반환 `true` 컬렉션의 모든 요소가 지정 된 조건을 충족 하는 경우 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="23c56-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="23c56-141">임의의 값</span><span class="sxs-lookup"><span data-stu-id="23c56-141">Any</span></span>

<span data-ttu-id="23c56-142">반환 `true` 컬렉션의 임의 요소가 지정 된 조건을 충족 하는 경우 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="23c56-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="23c56-144">평균</span><span class="sxs-lookup"><span data-stu-id="23c56-144">Average</span></span>

<span data-ttu-id="23c56-145">컬렉션에 있는 모든 요소의 평균을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="23c56-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="23c56-147">개수</span><span class="sxs-lookup"><span data-stu-id="23c56-147">Count</span></span>

<span data-ttu-id="23c56-148">컬렉션의 요소 수를 셉니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="23c56-149">선택적인 제공할 수 있습니다 `Boolean` 만 조건을 만족 하는 컬렉션의 요소 수를 계산 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="23c56-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="23c56-151">그룹화</span><span class="sxs-lookup"><span data-stu-id="23c56-151">Group</span></span>

<span data-ttu-id="23c56-152">참조의 결과로 그룹화 된 쿼리 결과 `Group By` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="23c56-153">합니다 `Group` 함수에만 유효 합니다 `Into` 절을 `Group By` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="23c56-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="23c56-154">자세한 내용 및 예제를 참조 하세요 [그룹 By 절](../../../visual-basic/language-reference/queries/group-by-clause.md) 하 고 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="23c56-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="23c56-155">LongCount</span></span>

<span data-ttu-id="23c56-156">컬렉션의 요소 수를 셉니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="23c56-157">선택적인 제공할 수 있습니다 `Boolean` 만 조건을 만족 하는 컬렉션의 요소 수를 계산 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="23c56-158">결과 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="23c56-159">예를 들어 참조는 `Count` 집계 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="23c56-160">최대</span><span class="sxs-lookup"><span data-stu-id="23c56-160">Max</span></span>

<span data-ttu-id="23c56-161">컬렉션에서 최대값을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="23c56-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="23c56-163">최소</span><span class="sxs-lookup"><span data-stu-id="23c56-163">Min</span></span>

<span data-ttu-id="23c56-164">컬렉션의 최소값을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="23c56-165">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="23c56-166">Sum</span><span class="sxs-lookup"><span data-stu-id="23c56-166">Sum</span></span>

<span data-ttu-id="23c56-167">컬렉션에 있는 모든 요소의 합계를 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="23c56-168">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="23c56-169">예제</span><span class="sxs-lookup"><span data-stu-id="23c56-169">Example</span></span>  

<span data-ttu-id="23c56-170">다음 예제에서는 사용 하는 방법을 보여 줍니다는 `Aggregate` 절에 집계 함수를 쿼리 결과에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="23c56-171">사용자 정의 집계 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="23c56-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="23c56-172">에 대 한 확장 메서드를 추가 하 여 쿼리 식에서 사용자 고유의 사용자 지정 집계 함수를 포함할 수 있습니다는 <xref:System.Collections.Generic.IEnumerable%601> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="23c56-173">사용자 지정 메서드가 계산 또는 집계 함수 참조는 열거 가능한 컬렉션에 대 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="23c56-174">확장 메서드에 대한 자세한 내용은 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23c56-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="23c56-175">예를 들어, 다음 예제에서는 숫자 컬렉션의 중앙값을 계산 하는 사용자 지정 집계 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="23c56-176">두 가지 오버 로드의는 `Median` 확장 메서드.</span><span class="sxs-lookup"><span data-stu-id="23c56-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="23c56-177">첫 번째 오버 로드를 입력으로 받아들입니다, 형식의 컬렉션인 `IEnumerable(Of Double)`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="23c56-178">경우는 `Median` 유형 쿼리 필드에 대 한 집계 함수가 호출 될 `Double`,이 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="23c56-179">두 번째 오버 로드는 `Median` 메서드는 제네릭 형식 전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="23c56-180">제네릭 오버 로드를 `Median` 메서드를 참조 하는 두 번째 매개 변수를 사용 합니다 `Func(Of T, Double)` 람다 식 (컬렉션)에서 형식에 대 한 값 형식의 해당 값으로 프로젝션 할 `Double`.</span><span class="sxs-lookup"><span data-stu-id="23c56-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="23c56-181">다음의 다른 오버 로드에 중간 값 계산에 위임 된 `Median` 메서드.</span><span class="sxs-lookup"><span data-stu-id="23c56-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="23c56-182">람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23c56-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="23c56-183">다음 예제에서는 호출 하는 샘플 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Integer`, 및 형식의 컬렉션인 `Double`.</span><span class="sxs-lookup"><span data-stu-id="23c56-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="23c56-184">호출 하는 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Double` 의 오버 로드를 호출 합니다 `Median` 형식의 컬렉션을 입력으로 허용 되는 방법 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="23c56-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="23c56-185">호출 하는 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Integer` 의 제네릭 오버 로드를 호출 합니다 `Median` 메서드.</span><span class="sxs-lookup"><span data-stu-id="23c56-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="23c56-186">참고자료</span><span class="sxs-lookup"><span data-stu-id="23c56-186">See also</span></span>

- [<span data-ttu-id="23c56-187">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="23c56-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="23c56-188">쿼리</span><span class="sxs-lookup"><span data-stu-id="23c56-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="23c56-189">Select 절</span><span class="sxs-lookup"><span data-stu-id="23c56-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="23c56-190">From 절</span><span class="sxs-lookup"><span data-stu-id="23c56-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="23c56-191">Where 절</span><span class="sxs-lookup"><span data-stu-id="23c56-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="23c56-192">Group By 절</span><span class="sxs-lookup"><span data-stu-id="23c56-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
