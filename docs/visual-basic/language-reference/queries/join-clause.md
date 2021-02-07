---
description: '자세한 정보: Join 절 (Visual Basic)'
title: Join 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 69d808e68a32b3f8799dabbbc8abc53acae42b57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700444"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="de6f6-103">Join 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de6f6-103">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="de6f6-104">두 컬렉션을 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-104">Combines two collections into a single collection.</span></span> <span data-ttu-id="de6f6-105">조인 작업은 일치 하는 키를 기반으로 하며 연산자를 사용 합니다 `Equals` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-105">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="de6f6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="de6f6-106">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="de6f6-107">부분</span><span class="sxs-lookup"><span data-stu-id="de6f6-107">Parts</span></span>

<span data-ttu-id="de6f6-108">`element` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-108">`element` Required.</span></span> <span data-ttu-id="de6f6-109">조인 되는 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-109">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="de6f6-110">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-110">Required.</span></span> <span data-ttu-id="de6f6-111">연산자의 좌 변에 있는 컬렉션과 결합할 컬렉션 `Join` 입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-111">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="de6f6-112">`Join`절은 다른 `Join` 절 또는 절에 중첩 될 수 있습니다 `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-112">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="de6f6-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-113">Optional.</span></span> <span data-ttu-id="de6f6-114">`Join`쿼리를 추가로 구체화 하는 하나 이상의 추가 절입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-114">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="de6f6-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-115">Optional.</span></span> <span data-ttu-id="de6f6-116">`Group Join`쿼리를 추가로 구체화 하는 하나 이상의 추가 절입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-116">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="de6f6-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="de6f6-117">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="de6f6-118">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-118">Required.</span></span> <span data-ttu-id="de6f6-119">조인 되는 컬렉션의 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="de6f6-120">`Equals`조인 되는 컬렉션의 키를 비교 하려면 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="de6f6-121">연산자를 사용 하 여 `And` 여러 키를 식별 하 여 조인 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="de6f6-122">`key1` 연산자의 좌 변에 있는 컬렉션에서 가져와야 합니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-122">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="de6f6-123">`key2` 연산자의 우변에 있는 컬렉션에서 가져와야 합니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-123">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="de6f6-124">조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="de6f6-125">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-125">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="de6f6-126">설명</span><span class="sxs-lookup"><span data-stu-id="de6f6-126">Remarks</span></span>

<span data-ttu-id="de6f6-127">`Join`절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-127">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="de6f6-128">결과 컬렉션에는 연산자의 왼쪽에서 식별 된 컬렉션의 모든 값 조합 `Join` 및 절에서 식별 된 컬렉션이 포함 될 수 있습니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-128">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="de6f6-129">이 쿼리는 연산자에 의해 지정 된 조건이 충족 되는 결과만 반환 합니다 `Equals` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-129">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="de6f6-130">이는 `INNER JOIN` SQL의와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-130">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="de6f6-131">`Join`쿼리에서 여러 절을 사용 하 여 둘 이상의 컬렉션을 단일 컬렉션으로 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-131">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="de6f6-132">절이 없으면 암시적 조인을 수행 하 여 컬렉션을 결합할 수 있습니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-132">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="de6f6-133">이렇게 하려면 `In` 절에 여러 절을 포함 하 `From` 고 `Where` 조인에 사용할 키를 식별 하는 절을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-133">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="de6f6-134">절을 사용 `Group Join` 하 여 컬렉션을 단일 계층 구조 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-134">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="de6f6-135">이는 `LEFT OUTER JOIN` SQL의와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-135">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="de6f6-136">예제</span><span class="sxs-lookup"><span data-stu-id="de6f6-136">Example</span></span>

<span data-ttu-id="de6f6-137">다음 코드 예제에서는 암시적 조인을 수행 하 여 고객 목록을 주문과 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-137">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="de6f6-138">예제</span><span class="sxs-lookup"><span data-stu-id="de6f6-138">Example</span></span>

<span data-ttu-id="de6f6-139">다음 코드 예제에서는 절을 사용 하 여 두 컬렉션을 조인 합니다 `Join` .</span><span class="sxs-lookup"><span data-stu-id="de6f6-139">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="de6f6-140">이 예제는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-140">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="de6f6-141">예제</span><span class="sxs-lookup"><span data-stu-id="de6f6-141">Example</span></span>

<span data-ttu-id="de6f6-142">다음 코드 예제에서는 `Join` 두 개의 키 열이 있는 절을 사용 하 여 두 컬렉션을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-142">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="de6f6-143">예제는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6f6-143">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="de6f6-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de6f6-144">See also</span></span>

- [<span data-ttu-id="de6f6-145">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="de6f6-145">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="de6f6-146">쿼리</span><span class="sxs-lookup"><span data-stu-id="de6f6-146">Queries</span></span>](index.md)
- [<span data-ttu-id="de6f6-147">Select 절</span><span class="sxs-lookup"><span data-stu-id="de6f6-147">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="de6f6-148">From 절</span><span class="sxs-lookup"><span data-stu-id="de6f6-148">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="de6f6-149">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="de6f6-149">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="de6f6-150">Where 절</span><span class="sxs-lookup"><span data-stu-id="de6f6-150">Where Clause</span></span>](where-clause.md)
