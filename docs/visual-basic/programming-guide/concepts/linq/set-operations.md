---
description: '자세한 정보: Set 작업 (Visual Basic)'
title: 집합 작업
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 9c75c9e029ba260917f59c7d2ea0341c157bf406
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471671"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="44999-103">Set 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44999-103">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="44999-104">LINQ의 집합 작업은 동일 컬렉션이나 별개 컬렉션(또는 집합)에 동등한 요소가 있는지 여부에 따라 결과 집합을 생성하는 쿼리 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="44999-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="44999-105">다음 섹션에는 집합 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44999-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="44999-106">메서드</span><span class="sxs-lookup"><span data-stu-id="44999-106">Methods</span></span>

|<span data-ttu-id="44999-107">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="44999-107">Method Name</span></span>|<span data-ttu-id="44999-108">설명</span><span class="sxs-lookup"><span data-stu-id="44999-108">Description</span></span>|<span data-ttu-id="44999-109">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="44999-109">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="44999-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="44999-110">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="44999-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="44999-111">Distinct</span></span>|<span data-ttu-id="44999-112">컬렉션에서 중복 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="44999-112">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="44999-113">Except</span><span class="sxs-lookup"><span data-stu-id="44999-113">Except</span></span>|<span data-ttu-id="44999-114">두 번째 컬렉션에 표시되지 않는 한 컬렉션의 요소를 의미하는 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44999-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="44999-115">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="44999-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="44999-116">Intersect</span><span class="sxs-lookup"><span data-stu-id="44999-116">Intersect</span></span>|<span data-ttu-id="44999-117">두 컬렉션에 각각 표시되는 요소를 의미하는 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44999-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="44999-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="44999-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="44999-119">Union</span><span class="sxs-lookup"><span data-stu-id="44999-119">Union</span></span>|<span data-ttu-id="44999-120">두 컬렉션 중 하나에 표시되는 고유한 요소를 의미하는 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44999-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="44999-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="44999-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="44999-122">집합 작업 비교</span><span class="sxs-lookup"><span data-stu-id="44999-122">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="44999-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="44999-123">Distinct</span></span>

<span data-ttu-id="44999-124">다음 그림에서는 문자 시퀀스에 대한 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 메서드의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44999-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="44999-125">반환된 시퀀스에는 입력 시퀀스의 고유한 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44999-125">The returned sequence contains the unique elements from the input sequence.</span></span>

![Distinct()의 동작을 보여주는 그래픽](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="44999-127">Except</span><span class="sxs-lookup"><span data-stu-id="44999-127">Except</span></span>

<span data-ttu-id="44999-128">다음 그림에서는 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44999-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44999-129">반환된 시퀀스에는 두 번째 입력 시퀀스에 없는 첫 번째 입력 시퀀스의 요소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44999-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="44999-130">![Except&#40;&#41;의 동작을 보여 주는 그래픽.](./media/set-operations/except-behavior-graphic.png "Except의 동작을 보여 줍니다.")</span><span class="sxs-lookup"><span data-stu-id="44999-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="44999-131">Intersect</span><span class="sxs-lookup"><span data-stu-id="44999-131">Intersect</span></span>

<span data-ttu-id="44999-132">다음 그림에서는 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44999-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44999-133">반환된 시퀀스에는 입력 시퀀스 둘 다에 공통적으로 있는 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44999-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![두 시퀀스의 교집합을 보여주는 그래픽](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="44999-135">Union</span><span class="sxs-lookup"><span data-stu-id="44999-135">Union</span></span>

<span data-ttu-id="44999-136">다음 그림은 두 개의 문자 시퀀스에 대한 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44999-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="44999-137">반환된 시퀀스에는 두 입력 시퀀스의 고유한 요소가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44999-137">The returned sequence contains the unique elements from both input sequences.</span></span>

![두 시퀀스의 결합을 보여주는 그래픽](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="44999-139">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="44999-139">Query Expression Syntax Example</span></span>

<span data-ttu-id="44999-140">다음 예제에서는 LINQ 쿼리에 절을 사용 하 여 `Distinct` 정수 목록에서 고유 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44999-140">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="44999-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="44999-141">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="44999-142">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44999-142">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="44999-143">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="44999-143">Distinct Clause</span></span>](../../../language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="44999-144">방법: 문자열 컬렉션 결합 및 비교 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44999-144">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="44999-145">방법: 두 목록 간의 차집합을 설정 찾기 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44999-145">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)
