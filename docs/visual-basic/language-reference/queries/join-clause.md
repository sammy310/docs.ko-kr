---
title: Join 절(Visual Basic)
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
ms.openlocfilehash: 8eab7db00515f55b086b5e1beddd149f966cb27a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72001928"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="bd39e-102">Join 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd39e-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="bd39e-103">두 컬렉션을 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="bd39e-104">조인 작업은 일치 하는 키를 기반으로 하며 `Equals` 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd39e-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd39e-105">Syntax</span></span>  
  
```vb  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bd39e-106">요소</span><span class="sxs-lookup"><span data-stu-id="bd39e-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="bd39e-107">필수.</span><span class="sxs-lookup"><span data-stu-id="bd39e-107">Required.</span></span> <span data-ttu-id="bd39e-108">조인 되는 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="bd39e-109">필수.</span><span class="sxs-lookup"><span data-stu-id="bd39e-109">Required.</span></span> <span data-ttu-id="bd39e-110">@No__t-0 연산자의 왼쪽에서 식별 된 컬렉션과 결합할 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="bd39e-111">@No__t-0 절은 다른 `Join` 절 또는 `Group Join` 절에 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="bd39e-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="bd39e-112">Optional.</span></span> <span data-ttu-id="bd39e-113">쿼리를 구체화 하는 하나 이상의 추가 `Join` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="bd39e-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="bd39e-114">Optional.</span></span> <span data-ttu-id="bd39e-115">쿼리를 구체화 하는 하나 이상의 추가 `Group Join` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="bd39e-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="bd39e-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="bd39e-117">필수.</span><span class="sxs-lookup"><span data-stu-id="bd39e-117">Required.</span></span> <span data-ttu-id="bd39e-118">조인 되는 컬렉션의 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="bd39e-119">조인 되는 컬렉션의 키를 비교 하려면 `Equals` 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="bd39e-120">@No__t-0 연산자를 사용 하 여 여러 키를 식별 하는 조인 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="bd39e-121">`key1`은 `Join` 연산자의 왼쪽에 있는 컬렉션에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="bd39e-122">`key2`은 `Join` 연산자의 오른쪽에 있는 컬렉션에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="bd39e-123">조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="bd39e-124">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd39e-125">설명</span><span class="sxs-lookup"><span data-stu-id="bd39e-125">Remarks</span></span>  
 <span data-ttu-id="bd39e-126">@No__t-0 절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="bd39e-127">결과 컬렉션은 `Join` 연산자의 왼쪽에서 식별 된 컬렉션의 모든 값 조합 및 `Join` 절에서 식별 된 컬렉션을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="bd39e-128">이 쿼리는 `Equals` 연산자로 지정 된 조건이 충족 되는 결과만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="bd39e-129">이는 SQL의 `INNER JOIN`과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="bd39e-130">쿼리에서 여러 `Join` 절을 사용 하 여 둘 이상의 컬렉션을 단일 컬렉션으로 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="bd39e-131">@No__t-0 절이 없으면 암시적 조인을 수행 하 여 컬렉션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="bd39e-132">이렇게 하려면 `From` 절에 여러 `In` 절을 포함 하 고 조인에 사용할 키를 식별 하는 `Where` 절을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="bd39e-133">@No__t-0 절을 사용 하 여 컬렉션을 단일 계층 구조 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="bd39e-134">이는 SQL의 `LEFT OUTER JOIN`과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd39e-135">예제</span><span class="sxs-lookup"><span data-stu-id="bd39e-135">Example</span></span>  
 <span data-ttu-id="bd39e-136">다음 코드 예제에서는 암시적 조인을 수행 하 여 고객 목록을 주문과 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="bd39e-137">예제</span><span class="sxs-lookup"><span data-stu-id="bd39e-137">Example</span></span>  
 <span data-ttu-id="bd39e-138">다음 코드 예제에서는 `Join` 절을 사용 하 여 두 컬렉션을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 <span data-ttu-id="bd39e-139">이 예제는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="bd39e-140">예제</span><span class="sxs-lookup"><span data-stu-id="bd39e-140">Example</span></span>  
 <span data-ttu-id="bd39e-141">다음 코드 예제에서는 두 개의 키 열이 있는 `Join` 절을 사용 하 여 두 컬렉션을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 <span data-ttu-id="bd39e-142">예제는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd39e-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="bd39e-143">참조</span><span class="sxs-lookup"><span data-stu-id="bd39e-143">See also</span></span>

- [<span data-ttu-id="bd39e-144">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="bd39e-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="bd39e-145">쿼리</span><span class="sxs-lookup"><span data-stu-id="bd39e-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="bd39e-146">Select 절</span><span class="sxs-lookup"><span data-stu-id="bd39e-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="bd39e-147">From 절</span><span class="sxs-lookup"><span data-stu-id="bd39e-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="bd39e-148">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="bd39e-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="bd39e-149">Where 절</span><span class="sxs-lookup"><span data-stu-id="bd39e-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
