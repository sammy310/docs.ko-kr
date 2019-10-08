---
title: Group Join 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 184077f2689eb64e4373d407913eefcc03b795c2
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005726"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="ed0d6-102">Group Join 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed0d6-102">Group Join Clause (Visual Basic)</span></span>
<span data-ttu-id="ed0d6-103">두 컬렉션을 단일 계층 구조 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-103">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="ed0d6-104">조인 작업은 일치 하는 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-104">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed0d6-105">Syntax</span></span>  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="ed0d6-106">요소</span><span class="sxs-lookup"><span data-stu-id="ed0d6-106">Parts</span></span>  
  
|<span data-ttu-id="ed0d6-107">용어</span><span class="sxs-lookup"><span data-stu-id="ed0d6-107">Term</span></span>|<span data-ttu-id="ed0d6-108">정의</span><span class="sxs-lookup"><span data-stu-id="ed0d6-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="ed0d6-109">필수.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-109">Required.</span></span> <span data-ttu-id="ed0d6-110">조인 되는 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-110">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="ed0d6-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ed0d6-111">Optional.</span></span> <span data-ttu-id="ed0d6-112">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-112">The type of `element`.</span></span> <span data-ttu-id="ed0d6-113">@No__t-0이 지정 되지 않은 경우 `element`의 형식은 `collection`에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-113">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="ed0d6-114">필수.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-114">Required.</span></span> <span data-ttu-id="ed0d6-115">@No__t-0 연산자의 왼쪽에 있는 컬렉션과 결합할 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-115">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="ed0d6-116">@No__t-1 절 또는 다른 `Group Join` 절에 `Group Join` 절을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-116">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="ed0d6-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="ed0d6-117">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="ed0d6-118">필수.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-118">Required.</span></span> <span data-ttu-id="ed0d6-119">조인 되는 컬렉션의 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="ed0d6-120">조인 되는 컬렉션의 키를 비교 하려면 `Equals` 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="ed0d6-121">@No__t-0 연산자를 사용 하 여 여러 키를 식별 하는 조인 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="ed0d6-122">@No__t-0 매개 변수는 `Join` 연산자의 좌 변에 있는 컬렉션에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-122">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="ed0d6-123">@No__t-0 매개 변수는 `Join` 연산자의 오른쪽에 있는 컬렉션에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-123">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="ed0d6-124">조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="ed0d6-125">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-125">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="ed0d6-126">필수.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-126">Required.</span></span> <span data-ttu-id="ed0d6-127">컬렉션의 요소 그룹을 집계 하는 방법을 식별 하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-127">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="ed0d6-128">그룹화 된 결과의 멤버 이름을 식별 하려면 `Group` 키워드 (`<alias> = Group`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-128">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="ed0d6-129">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-129">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed0d6-130">설명</span><span class="sxs-lookup"><span data-stu-id="ed0d6-130">Remarks</span></span>  
 <span data-ttu-id="ed0d6-131">@No__t-0 절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-131">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="ed0d6-132">결과 컬렉션에는 첫 번째 컬렉션의 키 값과 일치 하는 두 번째 컬렉션의 요소 컬렉션을 참조 하는 멤버가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-132">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="ed0d6-133">또한 두 번째 컬렉션에서 그룹화 된 요소에 적용할 집계 함수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-133">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="ed0d6-134">집계 함수에 대 한 자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-134">For information about aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="ed0d6-135">예를 들어 관리자 컬렉션 및 직원 컬렉션을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-135">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="ed0d6-136">두 컬렉션의 요소에는 특정 관리자에 게 보고 하는 직원을 식별 하는 ManagerID 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-136">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="ed0d6-137">조인 작업의 결과에는 일치 하는 ManagerID 값이 있는 각 관리자 및 직원의 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-137">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="ed0d6-138">@No__t-0 작업의 결과에는 관리자의 전체 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-138">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="ed0d6-139">각 관리자 결과에는 특정 관리자와 일치 하는 직원 목록을 참조 하는 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-139">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="ed0d6-140">@No__t-0 작업의 결과로 생성 되는 컬렉션에는 `From` 절에서 식별 된 컬렉션의 값과 `Group Join` 절의 `Into` 절에서 식별 된 식의 모든 조합이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-140">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="ed0d6-141">@No__t-0 절의 유효한 식에 대 한 자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-141">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="ed0d6-142">@No__t-0 연산은 `Group Join` 연산자의 왼쪽에서 식별 된 컬렉션의 모든 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-142">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="ed0d6-143">조인 되는 컬렉션에 일치 하는 항목이 없는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-143">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="ed0d6-144">이는 SQL의 `LEFT OUTER JOIN`과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-144">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="ed0d6-145">@No__t-0 절을 사용 하 여 컬렉션을 단일 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-145">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="ed0d6-146">이는 SQL의 `INNER JOIN`과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-146">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed0d6-147">예제</span><span class="sxs-lookup"><span data-stu-id="ed0d6-147">Example</span></span>  
 <span data-ttu-id="ed0d6-148">다음 코드 예제에서는 `Group Join` 절을 사용 하 여 두 컬렉션을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-148">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="ed0d6-149">참조</span><span class="sxs-lookup"><span data-stu-id="ed0d6-149">See also</span></span>

- [<span data-ttu-id="ed0d6-150">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="ed0d6-150">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ed0d6-151">쿼리</span><span class="sxs-lookup"><span data-stu-id="ed0d6-151">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ed0d6-152">Select 절</span><span class="sxs-lookup"><span data-stu-id="ed0d6-152">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="ed0d6-153">From 절</span><span class="sxs-lookup"><span data-stu-id="ed0d6-153">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="ed0d6-154">Join 절</span><span class="sxs-lookup"><span data-stu-id="ed0d6-154">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="ed0d6-155">Where 절</span><span class="sxs-lookup"><span data-stu-id="ed0d6-155">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="ed0d6-156">Group By 절</span><span class="sxs-lookup"><span data-stu-id="ed0d6-156">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
