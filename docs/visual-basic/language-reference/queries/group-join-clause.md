---
description: '자세히 알아보기: Group Join 절 (Visual Basic)'
title: Group Join 절
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
ms.openlocfilehash: 177dc2b41c923bc8c1ae0477c3905e8adad36fbe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700483"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="663f5-103">Group Join 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="663f5-103">Group Join Clause (Visual Basic)</span></span>

<span data-ttu-id="663f5-104">두 컬렉션을 단일 계층 구조 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-104">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="663f5-105">조인 작업은 일치 하는 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-105">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663f5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="663f5-106">Syntax</span></span>  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="663f5-107">부분</span><span class="sxs-lookup"><span data-stu-id="663f5-107">Parts</span></span>  
  
|<span data-ttu-id="663f5-108">용어</span><span class="sxs-lookup"><span data-stu-id="663f5-108">Term</span></span>|<span data-ttu-id="663f5-109">정의</span><span class="sxs-lookup"><span data-stu-id="663f5-109">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="663f5-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="663f5-110">Required.</span></span> <span data-ttu-id="663f5-111">조인 되는 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-111">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="663f5-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-112">Optional.</span></span> <span data-ttu-id="663f5-113">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-113">The type of `element`.</span></span> <span data-ttu-id="663f5-114">을 지정 하지 않으면 `type` 의 형식이 `element` 에서 유추 됩니다 `collection` .</span><span class="sxs-lookup"><span data-stu-id="663f5-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="663f5-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-115">Required.</span></span> <span data-ttu-id="663f5-116">연산자의 좌 변에 있는 컬렉션과 결합할 컬렉션입니다 `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-116">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="663f5-117">절은 `Group Join` `Join` 절 이나 다른 절에 중첩 될 수 있습니다 `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-117">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="663f5-118">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="663f5-118">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="663f5-119">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-119">Required.</span></span> <span data-ttu-id="663f5-120">조인 되는 컬렉션의 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-120">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="663f5-121">`Equals`조인 되는 컬렉션의 키를 비교 하려면 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-121">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="663f5-122">연산자를 사용 하 여 `And` 여러 키를 식별 하 여 조인 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-122">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="663f5-123">`key1`매개 변수는 연산자의 좌 변에 있는 컬렉션에서 가져와야 합니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-123">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="663f5-124">`key2`매개 변수는 연산자의 우변에 있는 컬렉션에서 가져와야 합니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-124">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="663f5-125">조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-125">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="663f5-126">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-126">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="663f5-127">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-127">Required.</span></span> <span data-ttu-id="663f5-128">컬렉션의 요소 그룹을 집계 하는 방법을 식별 하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-128">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="663f5-129">그룹화 된 결과의 멤버 이름을 식별 하려면 `Group` 키워드 ()를 사용 `<alias> = Group` 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-129">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="663f5-130">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-130">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="663f5-131">설명</span><span class="sxs-lookup"><span data-stu-id="663f5-131">Remarks</span></span>  

 <span data-ttu-id="663f5-132">`Group Join`절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-132">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="663f5-133">결과 컬렉션에는 첫 번째 컬렉션의 키 값과 일치 하는 두 번째 컬렉션의 요소 컬렉션을 참조 하는 멤버가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-133">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="663f5-134">또한 두 번째 컬렉션에서 그룹화 된 요소에 적용할 집계 함수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-134">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="663f5-135">집계 함수에 대 한 자세한 내용은 [Aggregate 절](aggregate-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="663f5-135">For information about aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="663f5-136">예를 들어 관리자 컬렉션 및 직원 컬렉션을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-136">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="663f5-137">두 컬렉션의 요소에는 특정 관리자에 게 보고 하는 직원을 식별 하는 ManagerID 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-137">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="663f5-138">조인 작업의 결과에는 일치 하는 ManagerID 값이 있는 각 관리자 및 직원의 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-138">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="663f5-139">작업 결과에는 `Group Join` 관리자의 전체 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-139">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="663f5-140">각 관리자 결과에는 특정 관리자와 일치 하는 직원 목록을 참조 하는 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-140">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="663f5-141">작업으로 인해 발생 하는 컬렉션에는 절의 절에서 식별 된 `Group Join` 컬렉션의 값 조합 `From` 및 절의 절에서 식별 된 식이 포함 될 수 있습니다 `Into` `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-141">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="663f5-142">절의 유효한 식에 대 한 자세한 내용은 `Into` [Aggregate 절](aggregate-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="663f5-142">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="663f5-143">`Group Join`작업은 연산자의 좌 변에 식별 된 컬렉션의 모든 결과를 반환 합니다 `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-143">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="663f5-144">조인 되는 컬렉션에 일치 하는 항목이 없는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-144">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="663f5-145">이는 `LEFT OUTER JOIN` SQL의와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-145">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="663f5-146">절을 사용 `Join` 하 여 컬렉션을 단일 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-146">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="663f5-147">이는 `INNER JOIN` SQL의와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="663f5-147">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="663f5-148">예제</span><span class="sxs-lookup"><span data-stu-id="663f5-148">Example</span></span>  

 <span data-ttu-id="663f5-149">다음 코드 예제에서는 절을 사용 하 여 두 컬렉션을 조인 합니다 `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="663f5-149">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="663f5-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="663f5-150">See also</span></span>

- [<span data-ttu-id="663f5-151">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="663f5-151">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="663f5-152">쿼리</span><span class="sxs-lookup"><span data-stu-id="663f5-152">Queries</span></span>](index.md)
- [<span data-ttu-id="663f5-153">Select 절</span><span class="sxs-lookup"><span data-stu-id="663f5-153">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="663f5-154">From 절</span><span class="sxs-lookup"><span data-stu-id="663f5-154">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="663f5-155">Join 절</span><span class="sxs-lookup"><span data-stu-id="663f5-155">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="663f5-156">Where 절</span><span class="sxs-lookup"><span data-stu-id="663f5-156">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="663f5-157">Group By 절</span><span class="sxs-lookup"><span data-stu-id="663f5-157">Group By Clause</span></span>](group-by-clause.md)
