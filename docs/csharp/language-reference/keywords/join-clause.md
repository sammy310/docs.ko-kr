---
title: join 절 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- join
- join_CSharpKeyword
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
ms.openlocfilehash: 8e52e9db241392b67818b7316767dd97bd38432a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713399"
---
# <a name="join-clause-c-reference"></a><span data-ttu-id="814bb-102">join 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="814bb-102">join clause (C# Reference)</span></span>

<span data-ttu-id="814bb-103">`join` 절은 개체 모델에서 직접적인 관계가 없는 서로 다른 소스 시퀀스의 요소를 연결하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-103">The `join` clause is useful for associating elements from different source sequences that have no direct relationship in the object model.</span></span> <span data-ttu-id="814bb-104">각 소스의 요소가 같은지 비교할 수 있는 일부 값을 공유하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-104">The only requirement is that the elements in each source share some value that can be compared for equality.</span></span> <span data-ttu-id="814bb-105">예를 들어 식품 유통업체에는 특정 제품의 공급업체 목록과 구매자 목록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-105">For example, a food distributor might have a list of suppliers of a certain product, and a list of buyers.</span></span> <span data-ttu-id="814bb-106">예를 들어 `join` 절은 모두 동일한 지역에 있는, 해당 제품의 공급업체 및 구매자 목록을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-106">A `join` clause can be used, for example, to create a list of the suppliers and buyers of that product who are all in the same specified region.</span></span>

<span data-ttu-id="814bb-107">`join` 절은 두 개의 소스 시퀀스를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-107">A `join` clause takes two source sequences as input.</span></span> <span data-ttu-id="814bb-108">각 시퀀스의 요소는 다른 시퀀스의 속성과 비교할 수 있는 속성이거나 해당 속성을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-108">The elements in each sequence must either be or contain a property that can be compared to a corresponding property in the other sequence.</span></span> <span data-ttu-id="814bb-109">`join` 절은 특수한 `equals` 키워드를 사용하여 지정된 키가 같은지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-109">The `join` clause compares the specified keys for equality by using the special `equals` keyword.</span></span> <span data-ttu-id="814bb-110">`join` 절로 수행된 모든 조인은 동등 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-110">All joins performed by the `join` clause are equijoins.</span></span> <span data-ttu-id="814bb-111">`join` 절의 출력 형태는 수행하는 조인의 특정 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-111">The shape of the output of a `join` clause depends on the specific type of join you are performing.</span></span> <span data-ttu-id="814bb-112">다음은 세 가지 가장 일반적인 조인 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-112">The following are three most common join types:</span></span>

- <span data-ttu-id="814bb-113">내부 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-113">Inner join</span></span>

- <span data-ttu-id="814bb-114">그룹 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-114">Group join</span></span>

- <span data-ttu-id="814bb-115">왼쪽 우선 외부 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-115">Left outer join</span></span>

## <a name="inner-join"></a><span data-ttu-id="814bb-116">내부 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-116">Inner join</span></span>

<span data-ttu-id="814bb-117">다음 예제에서는 간단한 내부 동등 조인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-117">The following example shows a simple inner equijoin.</span></span> <span data-ttu-id="814bb-118">이 쿼리는 "제품 이름/범주" 쌍의 기본 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-118">This query produces a flat sequence of "product name / category" pairs.</span></span> <span data-ttu-id="814bb-119">동일한 범주 문자열이 여러 요소에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-119">The same category string will appear in multiple elements.</span></span> <span data-ttu-id="814bb-120">`categories`의 요소에 일치하는 `products`가 없는 경우 해당 범주는 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-120">If an element from `categories` has no matching `products`, that category will not appear in the results.</span></span>

[!code-csharp[cscsrefQueryKeywords#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#24)]

<span data-ttu-id="814bb-121">자세한 내용은 [내부 조인 수행](../../linq/perform-inner-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-121">For more information, see [Perform inner joins](../../linq/perform-inner-joins.md).</span></span>

## <a name="group-join"></a><span data-ttu-id="814bb-122">그룹 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-122">Group join</span></span>

<span data-ttu-id="814bb-123">`into` 식을 포함한 `join` 절을 그룹 조인이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-123">A `join` clause with an `into` expression is called a group join.</span></span>

[!code-csharp[cscsrefQueryKeywords#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#25)]

<span data-ttu-id="814bb-124">그룹 조인은 왼쪽 소스 시퀀스의 요소를 오른쪽 소스 시퀀스에서 일치하는 하나 이상의 요소와 연결하는 계층적 결과 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-124">A group join produces a hierarchical result sequence, which associates elements in the left source sequence with one or more matching elements in the right side source sequence.</span></span> <span data-ttu-id="814bb-125">관계적인 측면에서 그룹 조인에는 해당 항목이 없으며, 그룹 조인은 기본적으로 개체 배열의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-125">A group join has no equivalent in relational terms; it is essentially a sequence of object arrays.</span></span>

<span data-ttu-id="814bb-126">왼쪽 소스의 요소와 일치하는 오른쪽 소스 시퀀스의 요소가 없을 경우 `join` 절은 해당 항목에 대해 빈 배열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-126">If no elements from the right source sequence are found to match an element in the left source, the `join` clause will produce an empty array for that item.</span></span> <span data-ttu-id="814bb-127">따라서 결과 시퀀스가 그룹으로 구성된다는 점을 제외하면 그룹 조인은 기본적으로 내부 동등 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-127">Therefore, the group join is still basically an inner-equijoin except that the result sequence is organized into groups.</span></span>

<span data-ttu-id="814bb-128">그룹 조인의 결과를 선택하는 경우 항목에 액세스할 수 있지만 항목이 일치되는 키를 식별할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-128">If you just select the results of a group join, you can access the items, but you cannot identify the key that they match on.</span></span> <span data-ttu-id="814bb-129">따라서 이전 예제와 같이 키 이름도 포함하는 새로운 유형으로 그룹 조인의 결과를 선택하는 것이 일반적으로 더 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-129">Therefore, it is generally more useful to select the results of the group join into a new type that also has the key name, as shown in the previous example.</span></span>

<span data-ttu-id="814bb-130">또한 그룹 조인의 결과를 또 다른 하위 쿼리의 생성기로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-130">You can also, of course, use the result of a group join as the generator of another subquery:</span></span>

[!code-csharp[cscsrefQueryKeywords#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#26)]

<span data-ttu-id="814bb-131">자세한 내용은 [그룹화 조인 수행](../../linq/perform-grouped-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-131">For more information, see [Perform grouped joins](../../linq/perform-grouped-joins.md).</span></span>

## <a name="left-outer-join"></a><span data-ttu-id="814bb-132">왼쪽 우선 외부 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-132">Left outer join</span></span>

<span data-ttu-id="814bb-133">왼쪽 우선 외부 조인에서는 오른쪽 시퀀스에 일치하는 요소가 없는 경우에도 왼쪽 소스 시퀀스의 모든 요소가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-133">In a left outer join, all the elements in the left source sequence are returned, even if no matching elements are in the right sequence.</span></span> <span data-ttu-id="814bb-134">LINQ에서 왼쪽 우선 외부 조인을 수행하려면 그룹 조인과 함께 `DefaultIfEmpty` 메서드를 사용하여 왼쪽 요소에 일치하는 요소가 없을 경우 생성할 기본 오른쪽 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-134">To perform a left outer join in LINQ, use the `DefaultIfEmpty` method in combination with a group join to specify a default right-side element to produce if a left-side element has no matches.</span></span> <span data-ttu-id="814bb-135">`null`을 모든 참조 형식의 기본값으로 사용하거나 사용자 정의 기본 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-135">You can use `null` as the default value for any reference type, or you can specify a user-defined default type.</span></span> <span data-ttu-id="814bb-136">다음 예제에서는 사용자 정의 기본 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-136">In the following example, a user-defined default type is shown:</span></span>

[!code-csharp[cscsrefQueryKeywords#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#27)]

<span data-ttu-id="814bb-137">자세한 내용은 [왼쪽 우선 외부 조인 수행](../../linq/perform-left-outer-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-137">For more information, see [Perform left outer joins](../../linq/perform-left-outer-joins.md).</span></span>

## <a name="the-equals-operator"></a><span data-ttu-id="814bb-138">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="814bb-138">The equals operator</span></span>

<span data-ttu-id="814bb-139">`join` 절은 동등 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-139">A `join` clause performs an equijoin.</span></span> <span data-ttu-id="814bb-140">즉, 일치 항목만을 기준으로 두 키가 같은지 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-140">In other words, you can only base matches on the equality of two keys.</span></span> <span data-ttu-id="814bb-141">"보다 큼"이나 "같지 않음"과 같은 다른 유형의 비교는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-141">Other types of comparisons such as "greater than" or "not equals" are not supported.</span></span> <span data-ttu-id="814bb-142">모든 조인이 동등 조인인지 확인하기 위해 `join` 절은 `==` 연산자 대신 `equals` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-142">To make clear that all joins are equijoins, the `join` clause uses the `equals` keyword instead of the `==` operator.</span></span> <span data-ttu-id="814bb-143">`equals` 키워드는 `join` 절에서만 사용할 수 있으며 한 가지 중요한 측면에서 `==` 연산자와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-143">The `equals` keyword can only be used in a `join` clause and it differs from the `==` operator in one important way.</span></span> <span data-ttu-id="814bb-144">`equals`를 사용할 경우 왼쪽 키는 외부 소스 시퀀스를 사용하고 오른쪽 키는 내부 소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-144">With `equals`, the left key consumes the outer source sequence, and the right key consumes the inner source.</span></span> <span data-ttu-id="814bb-145">외부 소스는 `equals`의 왼쪽 범위에만 있고 내부 소스 시퀀스는 오른쪽 범위에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-145">The outer source is only in scope on the left side of `equals` and the inner source sequence is only in scope on the right side.</span></span>

## <a name="non-equijoins"></a><span data-ttu-id="814bb-146">비동등 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-146">Non-equijoins</span></span>

<span data-ttu-id="814bb-147">여러 개의 `from` 절을 사용하여 비동등 조인, 크로스 조인 및 기타 사용자 지정 조인 작업을 수행하면 새 시퀀스를 독립적으로 쿼리에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-147">You can perform non-equijoins, cross joins, and other custom join operations by using multiple `from` clauses to introduce new sequences independently into a query.</span></span> <span data-ttu-id="814bb-148">자세한 내용은 [사용자 지정 조인 작업 수행](../../linq/perform-custom-join-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-148">For more information, see [Perform custom join operations](../../linq/perform-custom-join-operations.md).</span></span>

## <a name="joins-on-object-collections-vs-relational-tables"></a><span data-ttu-id="814bb-149">개체 컬렉션 및 관계형 테이블에서 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-149">Joins on object collections vs. relational tables</span></span>

<span data-ttu-id="814bb-150">LINQ 쿼리 식에서 조인 작업은 개체 컬렉션에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-150">In a LINQ query expression, join operations are performed on object collections.</span></span> <span data-ttu-id="814bb-151">개체 컬렉션은 두 개의 관계형 테이블과 정확히 동일한 방식으로 "조인"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-151">Object collections cannot be "joined" in exactly the same way as two relational tables.</span></span> <span data-ttu-id="814bb-152">LINQ에서는 두 소스 시퀀스가 관계로 연결되지 않는 경우에만 명시적 `join` 절이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-152">In LINQ, explicit `join` clauses are only required when two source sequences are not tied by any relationship.</span></span> <span data-ttu-id="814bb-153">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]로 작업할 때 외래 키 테이블은 기본 테이블의 속성으로 개체 모델에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-153">When working with [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], foreign key tables are represented in the object model as properties of the primary table.</span></span> <span data-ttu-id="814bb-154">예를 들어 Northwind 데이터베이스에서 Customer 테이블은 Orders 테이블과 외래 키 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-154">For example, in the Northwind database, the Customer table has a foreign key relationship with the Orders table.</span></span> <span data-ttu-id="814bb-155">테이블을 개체 모델에 매핑하면 Customer 클래스는 해당 Customer와 연결된 Orders 컬렉션을 포함하는 Orders 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-155">When you map the tables to the object model, the Customer class has an Orders property that contains the collection of Orders associated with that Customer.</span></span> <span data-ttu-id="814bb-156">사실상 조인은 이미 수행된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-156">In effect, the join has already been done for you.</span></span>

<span data-ttu-id="814bb-157">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 컨텍스트에서 관련 테이블을 쿼리하는 방법에 대한 자세한 내용은 [방법: 데이터베이스 관계 매핑](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-157">For more information about querying across related tables in the context of [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], see [How to: Map Database Relationships](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md).</span></span>

## <a name="composite-keys"></a><span data-ttu-id="814bb-158">복합 키</span><span class="sxs-lookup"><span data-stu-id="814bb-158">Composite keys</span></span>

<span data-ttu-id="814bb-159">복합 키를 사용하여 여러 값이 같은지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-159">You can test for equality of multiple values by using a composite key.</span></span> <span data-ttu-id="814bb-160">자세한 내용은 [복합 키를 사용하여 조인](../../linq/join-by-using-composite-keys.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="814bb-160">For more information, see [Join by using composite keys](../../linq/join-by-using-composite-keys.md).</span></span> <span data-ttu-id="814bb-161">복합 키는 `group` 절에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-161">Composite keys can be also used in a `group` clause.</span></span>

## <a name="example"></a><span data-ttu-id="814bb-162">예제</span><span class="sxs-lookup"><span data-stu-id="814bb-162">Example</span></span>

<span data-ttu-id="814bb-163">다음 예제에서는 동일한 데이터 소스에서 동일한 일치하는 키를 사용하여 내부 조인, 그룹 조인 및 왼쪽 우선 외부 조인의 결과를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-163">The following example compares the results of an inner join, a group join, and a left outer join on the same data sources by using the same matching keys.</span></span> <span data-ttu-id="814bb-164">콘솔 디스플레이에 결과를 명확하게 나타내기 위해 이러한 예제에 몇 가지 추가 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-164">Some extra code is added to these examples to clarify the results in the console display.</span></span>

[!code-csharp[cscsrefQueryKeywords#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#23)]

## <a name="remarks"></a><span data-ttu-id="814bb-165">설명</span><span class="sxs-lookup"><span data-stu-id="814bb-165">Remarks</span></span>

<span data-ttu-id="814bb-166">뒤에 `into`가 오지 않는 `join` 절은 <xref:System.Linq.Enumerable.Join%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-166">A `join` clause that is not followed by `into` is translated into a <xref:System.Linq.Enumerable.Join%2A> method call.</span></span> <span data-ttu-id="814bb-167">뒤에 `into`가 오는 `join` 절은 <xref:System.Linq.Enumerable.GroupJoin%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="814bb-167">A `join` clause that is followed by `into` is translated to a <xref:System.Linq.Enumerable.GroupJoin%2A> method call.</span></span>

## <a name="see-also"></a><span data-ttu-id="814bb-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="814bb-168">See also</span></span>

- [<span data-ttu-id="814bb-169">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="814bb-169">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="814bb-170">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="814bb-170">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="814bb-171">조인 작업</span><span class="sxs-lookup"><span data-stu-id="814bb-171">Join Operations</span></span>](../../programming-guide/concepts/linq/join-operations.md)
- [<span data-ttu-id="814bb-172">group 절</span><span class="sxs-lookup"><span data-stu-id="814bb-172">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="814bb-173">왼쪽 우선 외부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="814bb-173">Perform left outer joins</span></span>](../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="814bb-174">내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="814bb-174">Perform inner joins</span></span>](../../linq/perform-inner-joins.md)
- [<span data-ttu-id="814bb-175">그룹화 조인 수행</span><span class="sxs-lookup"><span data-stu-id="814bb-175">Perform grouped joins</span></span>](../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="814bb-176">Join 절 결과를 서순대로 정렬</span><span class="sxs-lookup"><span data-stu-id="814bb-176">Order the results of a join clause</span></span>](../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="814bb-177">복합 키를 사용하여 조인</span><span class="sxs-lookup"><span data-stu-id="814bb-177">Join by using composite keys</span></span>](../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="814bb-178">Visual Studio용 호환 데이터베이스 시스템</span><span class="sxs-lookup"><span data-stu-id="814bb-178">Compatible database systems for Visual Studio</span></span>](/visualstudio/data-tools/installing-database-systems-tools-and-samples)
