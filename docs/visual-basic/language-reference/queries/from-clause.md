---
title: From 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 33680f49247b3b2a6082b3a6b27ca64f8401e42d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396183"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="05a6e-102">From 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05a6e-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="05a6e-103">하나 이상의 범위 변수와 쿼리할 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05a6e-104">구문</span><span class="sxs-lookup"><span data-stu-id="05a6e-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="05a6e-105">부분</span><span class="sxs-lookup"><span data-stu-id="05a6e-105">Parts</span></span>  
  
|<span data-ttu-id="05a6e-106">용어</span><span class="sxs-lookup"><span data-stu-id="05a6e-106">Term</span></span>|<span data-ttu-id="05a6e-107">정의</span><span class="sxs-lookup"><span data-stu-id="05a6e-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="05a6e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="05a6e-108">Required.</span></span> <span data-ttu-id="05a6e-109">컬렉션의 요소를 반복 하는 데 사용 되는 *범위 변수* 입니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="05a6e-110">범위 변수는 `collection` 쿼리를 통해가 반복 될 때의 각 멤버를 참조 하는 데 사용 됩니다 `collection` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="05a6e-111">는 열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="05a6e-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-112">Optional.</span></span> <span data-ttu-id="05a6e-113">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-113">The type of `element`.</span></span> <span data-ttu-id="05a6e-114">을 지정 하지 않으면 `type` 의 형식이 `element` 에서 유추 됩니다 `collection` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="05a6e-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="05a6e-115">Required.</span></span> <span data-ttu-id="05a6e-116">쿼리할 컬렉션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="05a6e-117">는 열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05a6e-118">설명</span><span class="sxs-lookup"><span data-stu-id="05a6e-118">Remarks</span></span>  
 <span data-ttu-id="05a6e-119">`From`절은 쿼리의 소스 데이터와 소스 컬렉션의 요소를 참조 하는 데 사용 되는 변수를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="05a6e-120">이러한 변수를 *범위 변수*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-120">These variables are called *range variables*.</span></span> <span data-ttu-id="05a6e-121">절 `From` `Aggregate` 이 집계 된 결과만 반환 하는 쿼리를 식별 하는 데 사용 되는 경우를 제외 하 고는 쿼리에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="05a6e-122">자세한 내용은 [Aggregate 절](aggregate-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a6e-122">For more information, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="05a6e-123">쿼리에 여러 절을 지정 `From` 하 여 조인할 여러 컬렉션을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="05a6e-124">여러 컬렉션을 지정 하는 경우 이러한 컬렉션은 독립적으로 반복 되거나 관련 된 경우 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="05a6e-125">`Select`절을 사용 하거나 또는 절을 사용 하 여 명시적으로 컬렉션을 조인할 수 있습니다 `Join` `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="05a6e-126">또는 여러 범위 변수와 컬렉션을 단일 절에 지정할 수 있으며 `From` , 각 관련 범위 변수와 컬렉션은 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="05a6e-127">다음 코드 예에서는 절의 구문 옵션을 모두 보여 줍니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="05a6e-128">`From`절은 루프의 범위와 비슷한 쿼리의 범위를 정의 합니다 `For` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="05a6e-129">따라서 `element` 쿼리 범위의 각 범위 변수에는 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="05a6e-130">쿼리에 대해 절을 여러 개 지정할 수 있으므로 `From` 후속 `From` 절은 절의 범위 변수를 참조 `From` 하거나 이전 절의 범위 변수를 참조할 수 있습니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="05a6e-131">예를 들어 다음 예에서는 `From` 두 번째 절의 컬렉션이 첫 번째 절에 있는 범위 변수의 속성을 기반으로 하는 중첩 절을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="05a6e-132">각 `From` 절 뒤에는 쿼리를 구체화 하기 위한 추가 쿼리 절의 조합이 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="05a6e-133">다음과 같은 방법으로 쿼리를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="05a6e-134">또는 절을 사용 하 여 명시적으로 또는 절을 사용 하 여 여러 컬렉션을 암시적으로 결합 `From` `Select` `Join` `Group Join` 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="05a6e-135">절을 사용 `Where` 하 여 쿼리 결과를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="05a6e-136">절을 사용 하 여 결과를 정렬 합니다 `Order By` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="05a6e-137">절을 사용 하 여 비슷한 결과를 함께 그룹화 `Group By` 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="05a6e-138">`Aggregate`전체 쿼리 결과를 평가 하는 집계 함수를 식별 하려면 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="05a6e-139">절을 사용 `Let` 하 여 해당 값이 컬렉션이 아닌 식에 의해 결정 되는 반복 변수를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="05a6e-140">절을 사용 `Distinct` 하 여 중복 쿼리 결과를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="05a6e-141">,, 및 절을 사용 하 여 반환할 결과의 일부를 식별 `Skip` `Take` `Skip While` `Take While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a6e-142">예제</span><span class="sxs-lookup"><span data-stu-id="05a6e-142">Example</span></span>  
 <span data-ttu-id="05a6e-143">다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션의 각 개체에 대해 범위 변수를 선언 합니다 `Customer` `customers` .</span><span class="sxs-lookup"><span data-stu-id="05a6e-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="05a6e-144">`Where`절은 범위 변수를 사용 하 여 지정 된 지역의 고객에 대 한 출력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="05a6e-145">`For Each`루프는 쿼리 결과에 있는 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a6e-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="05a6e-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05a6e-146">See also</span></span>

- [<span data-ttu-id="05a6e-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="05a6e-147">Queries</span></span>](index.md)
- [<span data-ttu-id="05a6e-148">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="05a6e-148">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="05a6e-149">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="05a6e-149">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="05a6e-150">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="05a6e-150">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="05a6e-151">Select 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-151">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="05a6e-152">Where 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-152">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="05a6e-153">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="05a6e-153">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="05a6e-154">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-154">Distinct Clause</span></span>](distinct-clause.md)
- [<span data-ttu-id="05a6e-155">Join 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-155">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="05a6e-156">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-156">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="05a6e-157">Order By 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-157">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="05a6e-158">Let 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-158">Let Clause</span></span>](let-clause.md)
- [<span data-ttu-id="05a6e-159">Skip 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-159">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="05a6e-160">Take 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-160">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="05a6e-161">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-161">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="05a6e-162">Take While 절</span><span class="sxs-lookup"><span data-stu-id="05a6e-162">Take While Clause</span></span>](take-while-clause.md)
