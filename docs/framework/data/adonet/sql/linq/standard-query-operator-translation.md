---
description: '자세한 정보: 표준 쿼리 연산자 변환'
title: 표준 쿼리 연산자 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: e7e45e8f27f1e7d3c572f00ea014b4edb288b2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681528"
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="a57ae-103">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="a57ae-103">Standard Query Operator Translation</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-104">에서는 표준 쿼리 연산자를 SQL 명령으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-104">translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="a57ae-105">데이터베이스의 쿼리 프로세서는 SQL 변환에 대한 실행 의미 체계를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-105">The query processor of the database determines the execution semantics of SQL translation.</span></span>

<span data-ttu-id="a57ae-106">표준 쿼리 연산자는 *시퀀스* 에 대해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-106">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="a57ae-107">시퀀스는 *순서가 지정* 되며 시퀀스의 각 요소에 대 한 참조 id를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-107">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="a57ae-108">자세한 내용은 [표준 쿼리 연산자 개요 (c #)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) 또는 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-108">For more information, see [Standard Query Operators Overview (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

<span data-ttu-id="a57ae-109">SQL은 정렬 되지 않은 *값 집합* 을 주로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-109">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="a57ae-110">순서 지정은 일반적으로 명시적으로 지정되는 후처리 작업으로 쿼리의 중간 결과가 아닌 최종 결과에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-110">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="a57ae-111">ID는 값으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-111">Identity is defined by values.</span></span> <span data-ttu-id="a57ae-112">이러한 이유로 SQL 쿼리는 *집합* 대신 다중 집합 (*백*)를 처리 하는 것을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-112">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>

<span data-ttu-id="a57ae-113">다음 단락에서는 표준 쿼리 연산자와 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 SQL 서버 공급자에 대한 해당 SQL 변환 사이의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-113">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

## <a name="operator-support"></a><span data-ttu-id="a57ae-114">연산자 지원</span><span class="sxs-lookup"><span data-stu-id="a57ae-114">Operator Support</span></span>

### <a name="concat"></a><span data-ttu-id="a57ae-115">Concat</span><span class="sxs-lookup"><span data-stu-id="a57ae-115">Concat</span></span>

<span data-ttu-id="a57ae-116"><xref:System.Linq.Enumerable.Concat%2A> 메서드는 수신자 순서와 인수 순서가 동일한 순서 있는 다중 집합에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-116">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="a57ae-117"><xref:System.Linq.Enumerable.Concat%2A>는 공통 순서 이전에 다중 집합에 대해 `UNION ALL`로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-117"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>

<span data-ttu-id="a57ae-118">최종 단계는 결과가 생성되기 전에 SQL에서 순서를 지정하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-118">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="a57ae-119"><xref:System.Linq.Enumerable.Concat%2A>에서는 해당 인수의 순서를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-119"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="a57ae-120">순서가 적절하게 지정되게 하려면 <xref:System.Linq.Enumerable.Concat%2A>에 대한 결과의 순서를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-120">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>

### <a name="intersect-except-union"></a><span data-ttu-id="a57ae-121">Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="a57ae-121">Intersect, Except, Union</span></span>

<span data-ttu-id="a57ae-122"><xref:System.Linq.Enumerable.Intersect%2A> 및 <xref:System.Linq.Enumerable.Except%2A> 메서드는 집합에 대해서만 잘 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-122">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="a57ae-123">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-123">The semantics for multisets is undefined.</span></span>

<span data-ttu-id="a57ae-124"><xref:System.Linq.Enumerable.Union%2A> 메서드는 다중 집합에 대해 순서 없는 다중 집합의 연결로 정의됩니다(사실상 SQL UNION ALL 절의 결과와 같음).</span><span class="sxs-lookup"><span data-stu-id="a57ae-124">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>

### <a name="take-skip"></a><span data-ttu-id="a57ae-125">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="a57ae-125">Take, Skip</span></span>

<span data-ttu-id="a57ae-126"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 메서드는 *순서가 지정 된 집합* 에 대해서만 잘 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-126"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="a57ae-127">순서 없는 집합이나 다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-127">The semantics for unordered sets or multisets are undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="a57ae-128"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>에는 SQL Server 2000에 대한 쿼리에서 사용할 경우 몇 가지 제한이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-128"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="a57ae-129">자세한 내용은 [문제 해결](troubleshooting.md)에서 "SQL Server 2000의 Skip 및 Take 예외" 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-129">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

<span data-ttu-id="a57ae-130">SQL의 순서 지정에 대한 제한 사항 때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 이러한 메서드의 인수에 대한 순서 지정 작업을 메서드의 결과로 이동하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-130">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="a57ae-131">예를 들어 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-131">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

<span data-ttu-id="a57ae-132">이 코드에 대해 생성된 SQL은 다음과 같이 순서 지정 작업을 맨 뒤로 옮깁니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-132">The generated SQL for this code moves the ordering to the end, as follows:</span></span>

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

<span data-ttu-id="a57ae-133"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>을 연결할 때 지정한 모든 순서가 일치해야 함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-133">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="a57ae-134">그렇지 않으면 결과가 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-134">Otherwise, the results are undefined.</span></span>

<span data-ttu-id="a57ae-135"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>은 모두 표준 쿼리 연산자 사양을 기반으로 하는 음수가 아닌 정수 계열 상수 인수에 대해 잘 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-135">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>

### <a name="operators-with-no-translation"></a><span data-ttu-id="a57ae-136">변환이 없는 연산자</span><span class="sxs-lookup"><span data-stu-id="a57ae-136">Operators with No Translation</span></span>

<span data-ttu-id="a57ae-137">다음 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-137">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a57ae-138">가장 일반적인 이유는 순서 없는 다중 집합과 시퀀스 간의 차이 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-138">The most common reason is the difference between unordered multisets and sequences.</span></span>

|<span data-ttu-id="a57ae-139">연산자</span><span class="sxs-lookup"><span data-stu-id="a57ae-139">Operators</span></span>|<span data-ttu-id="a57ae-140">이유</span><span class="sxs-lookup"><span data-stu-id="a57ae-140">Rationale</span></span>|
|---------------|---------------|
|<span data-ttu-id="a57ae-141"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="a57ae-141"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="a57ae-142">SQL 쿼리는 다중 집합에 대해서는 작동하지만 시퀀스에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-142">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="a57ae-143">`ORDER BY`는 결과에 적용되는 마지막 절이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-143">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="a57ae-144">따라서 이러한 두 메서드에 대한 일반 용도 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-144">For this reason, there is no general-purpose translation for these two methods.</span></span>|
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="a57ae-145">순서 있는 집합에 대해 이 메서드의 변환이 가능하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 현재 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-145">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="a57ae-146"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="a57ae-146"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="a57ae-147">순서 있는 집합에 대해 이러한 메서드의 변환이 가능하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 현재 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-147">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="a57ae-148"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="a57ae-148"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="a57ae-149">SQL 쿼리는 다중 집합에 대해서는 작동하지만 인덱싱 가능한 시퀀스에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-149">SQL queries operate on multisets, not on indexable sequences.</span></span>|
|<span data-ttu-id="a57ae-150"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A>(기본 인수로 오버로드)</span><span class="sxs-lookup"><span data-stu-id="a57ae-150"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="a57ae-151">일반적으로 임의의 튜플에 대해 기본값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-151">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="a57ae-152">일부 경우 외부 조인을 통해 튜플에 null 값을 지정할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-152">Null values for tuples are possible in some cases through outer joins.</span></span>|

## <a name="expression-translation"></a><span data-ttu-id="a57ae-153">식 변환</span><span class="sxs-lookup"><span data-stu-id="a57ae-153">Expression Translation</span></span>

### <a name="null-semantics"></a><span data-ttu-id="a57ae-154">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="a57ae-154">Null semantics</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-155">에서는 null 비교 의미 체계를 SQL에 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-155">does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="a57ae-156">비교 연산자는 구문상 동등한 SQL 항목으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-156">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="a57ae-157">따라서 의미 체계에는 서버 또는 연결 설정에 따라 정의된 SQL 의미 체계가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-157">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="a57ae-158">예를 들어 기본 SQL Server 설정에서는 두 개의 null 값이 동일하지 않은 것으로 간주되지만 이 설정을 변경하여 의미 체계를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-158">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-159">에서는 쿼리를 변환할 때 서버 설정을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-159">does not consider server settings when it translates queries.</span></span>

<span data-ttu-id="a57ae-160">리터럴 null을 사용한 비교는 해당 SQL 버전(`is null` 또는 `is not null`)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-160">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="a57ae-161">데이터 정렬의 `null` 값은 SQL Server에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-161">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-162">에서는 데이터 정렬을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-162">does not change the collation.</span></span>

### <a name="aggregates"></a><span data-ttu-id="a57ae-163">집계</span><span class="sxs-lookup"><span data-stu-id="a57ae-163">Aggregates</span></span>

<span data-ttu-id="a57ae-164">표준 쿼리 연산자의 집계 메서드 <xref:System.Linq.Enumerable.Sum%2A>은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-164">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="a57ae-165">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 SQL의 의미 체계는 변경되지 않은 상태로 유지되고 <xref:System.Linq.Enumerable.Sum%2A>은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0이 아닌 `null`로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-165">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>

<span data-ttu-id="a57ae-166">중간 결과에 대한 SQL 제한은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 집계에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-166">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a57ae-167">32비트 정수 수량의 <xref:System.Linq.Enumerable.Sum%2A>은 64비트 결과를 사용하여 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-167">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="a57ae-168">표준 쿼리 연산자 구현이 메모리 내의 해당 시퀀스에 대해 오버플로를 발생시키지 않는 경우에도 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 <xref:System.Linq.Enumerable.Sum%2A> 변환에 대해 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-168">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>

<span data-ttu-id="a57ae-169">마찬가지로 정수 값의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 <xref:System.Linq.Enumerable.Average%2A> 변환은 `integer`이 아닌 `double`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-169">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>

### <a name="entity-arguments"></a><span data-ttu-id="a57ae-170">엔터티 인수</span><span class="sxs-lookup"><span data-stu-id="a57ae-170">Entity Arguments</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-171">에서는 엔터티 형식을 <xref:System.Linq.Enumerable.GroupBy%2A> 및 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-171">enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="a57ae-172">이러한 연산자 변환에서 형식 인수를 사용하는 것은 해당 형식의 모든 멤버를 지정하는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-172">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="a57ae-173">예를 들어 다음 코드는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-173">For example, the following code is equivalent:</span></span>

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a><span data-ttu-id="a57ae-174">같을 수 있는/비교 가능한 인수</span><span class="sxs-lookup"><span data-stu-id="a57ae-174">Equatable / Comparable Arguments</span></span>

<span data-ttu-id="a57ae-175">인수의 같음은 다음과 같은 메서드의 구현에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-175">Equality of arguments is required in the implementation of the following methods:</span></span>

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a57ae-176">는 *플랫* 인수에 대해 같음 및 비교를 지원 하지만 시퀀스를 포함 하거나 포함 하는 인수에 대해서는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-176">supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="a57ae-177">단순 인수는 SQL 행에 매핑될 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-177">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="a57ae-178">시퀀스를 포함하지 않는 것으로 정적으로 확인할 수 있는 하나 이상의 엔터티 형식에 대한 프로젝션은 단순 인수인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-178">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>

<span data-ttu-id="a57ae-179">다음은 플랫 인수의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-179">The following are examples of flat arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

<span data-ttu-id="a57ae-180">다음은 플랫 (계층)이 아닌 인수의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-180">The following are examples of non-flat (hierarchical) arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a><span data-ttu-id="a57ae-181">Visual Basic 함수 변환</span><span class="sxs-lookup"><span data-stu-id="a57ae-181">Visual Basic Function Translation</span></span>

<span data-ttu-id="a57ae-182">Visual Basic 컴파일러에서 사용하는 다음과 같은 도우미 함수는 해당하는 SQL 연산자 및 함수로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-182">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

<span data-ttu-id="a57ae-183">변환 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-183">Conversion methods:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="a57ae-184">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="a57ae-184">ToBoolean</span></span>|<span data-ttu-id="a57ae-185">ToSByte</span><span class="sxs-lookup"><span data-stu-id="a57ae-185">ToSByte</span></span>|<span data-ttu-id="a57ae-186">ToByte</span><span class="sxs-lookup"><span data-stu-id="a57ae-186">ToByte</span></span>|<span data-ttu-id="a57ae-187">ToChar</span><span class="sxs-lookup"><span data-stu-id="a57ae-187">ToChar</span></span>|
|<span data-ttu-id="a57ae-188">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="a57ae-188">ToCharArrayRankOne</span></span>|<span data-ttu-id="a57ae-189">ToDate</span><span class="sxs-lookup"><span data-stu-id="a57ae-189">ToDate</span></span>|<span data-ttu-id="a57ae-190">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="a57ae-190">ToDecimal</span></span>|<span data-ttu-id="a57ae-191">ToDouble</span><span class="sxs-lookup"><span data-stu-id="a57ae-191">ToDouble</span></span>|
|<span data-ttu-id="a57ae-192">ToInteger</span><span class="sxs-lookup"><span data-stu-id="a57ae-192">ToInteger</span></span>|<span data-ttu-id="a57ae-193">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="a57ae-193">ToUInteger</span></span>|<span data-ttu-id="a57ae-194">ToLong</span><span class="sxs-lookup"><span data-stu-id="a57ae-194">ToLong</span></span>|<span data-ttu-id="a57ae-195">ToULong</span><span class="sxs-lookup"><span data-stu-id="a57ae-195">ToULong</span></span>|
|<span data-ttu-id="a57ae-196">ToShort</span><span class="sxs-lookup"><span data-stu-id="a57ae-196">ToShort</span></span>|<span data-ttu-id="a57ae-197">ToUShort</span><span class="sxs-lookup"><span data-stu-id="a57ae-197">ToUShort</span></span>|<span data-ttu-id="a57ae-198">ToSingle</span><span class="sxs-lookup"><span data-stu-id="a57ae-198">ToSingle</span></span>|<span data-ttu-id="a57ae-199">ToString</span><span class="sxs-lookup"><span data-stu-id="a57ae-199">ToString</span></span>|

## <a name="inheritance-support"></a><span data-ttu-id="a57ae-200">상속 지원</span><span class="sxs-lookup"><span data-stu-id="a57ae-200">Inheritance Support</span></span>

### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="a57ae-201">상속 매핑 제한</span><span class="sxs-lookup"><span data-stu-id="a57ae-201">Inheritance Mapping Restrictions</span></span>

<span data-ttu-id="a57ae-202">자세한 내용은 [방법: 상속 계층 구조 매핑](how-to-map-inheritance-hierarchies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-202">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>

### <a name="inheritance-in-queries"></a><span data-ttu-id="a57ae-203">쿼리의 상속</span><span class="sxs-lookup"><span data-stu-id="a57ae-203">Inheritance in Queries</span></span>

<span data-ttu-id="a57ae-204">C# 캐스트는 프로젝션에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-204">C# casts are supported only in projection.</span></span> <span data-ttu-id="a57ae-205">다른 위치에 사용된 캐스트는 변환되지 않고 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-205">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="a57ae-206">SQL 함수 이름을 제외하고는 SQL에서는 사실상 CLR <xref:System.Convert>와 동일한 기능만 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-206">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="a57ae-207">즉, SQL에서는 한 형식의 값을 다른 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-207">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="a57ae-208">다른 형식과 동일한 비트를 재해석하는 개념이 없으므로 CLR 캐스트와 동일한 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-208">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="a57ae-209">이 때문에 C# 캐스트는 로컬에서만 작동하며</span><span class="sxs-lookup"><span data-stu-id="a57ae-209">That is why a C# cast works only locally.</span></span> <span data-ttu-id="a57ae-210">원격으로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-210">It is not remoted.</span></span>

<span data-ttu-id="a57ae-211">`is` 및 `as` 연산자와 `GetType` 메서드는 `Select` 연산자뿐 아니라</span><span class="sxs-lookup"><span data-stu-id="a57ae-211">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="a57ae-212">다른 쿼리 연산자에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-212">They can be used in other query operators also.</span></span>

## <a name="sql-server-2008-support"></a><span data-ttu-id="a57ae-213">SQL Server 2008 지원</span><span class="sxs-lookup"><span data-stu-id="a57ae-213">SQL Server 2008 Support</span></span>

<span data-ttu-id="a57ae-214">.NET Framework 3.5 SP1부터 LINQ to SQL에서는 SQL Server 2008에 새로 도입된 날짜 및 시간 형식에 대한 매핑이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-214">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="a57ae-215">그러나 이러한 새로운 형식에 매핑된 값에 대한 연산을 수행할 때는 LINQ to SQL 쿼리 연산자에 대해 몇 가지 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-215">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>

### <a name="unsupported-query-operators"></a><span data-ttu-id="a57ae-216">지원되지 않는 쿼리 연산자</span><span class="sxs-lookup"><span data-stu-id="a57ae-216">Unsupported Query Operators</span></span>

<span data-ttu-id="a57ae-217">다음 쿼리 연산자는 `DATETIME2`, `DATE`, `TIME` 및 `DATETIMEOFFSET` 등의 새로운 SQL Server 날짜 및 시간 형식에 매핑된 값에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-217">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

<span data-ttu-id="a57ae-218">이러한 SQL Server 날짜 및 시간 형식에 매핑하는 방법에 대 한 자세한 내용은 [SQL-CLR 형식 매핑](sql-clr-type-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-218">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>

## <a name="sql-server-2005-support"></a><span data-ttu-id="a57ae-219">SQL Server 2005 지원</span><span class="sxs-lookup"><span data-stu-id="a57ae-219">SQL Server 2005 Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-220">에서는 다음과 같은 SQL Server 2005 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-220">does not support the following SQL Server 2005 features:</span></span>

- <span data-ttu-id="a57ae-221">SQL CLR용으로 작성된 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="a57ae-221">Stored procedures written for SQL CLR.</span></span>

- <span data-ttu-id="a57ae-222">사용자 정의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-222">User-defined type.</span></span>

- <span data-ttu-id="a57ae-223">XML 쿼리 기능</span><span class="sxs-lookup"><span data-stu-id="a57ae-223">XML query features.</span></span>

## <a name="sql-server-2000-support"></a><span data-ttu-id="a57ae-224">SQL Server 2000 지원</span><span class="sxs-lookup"><span data-stu-id="a57ae-224">SQL Server 2000 Support</span></span>

<span data-ttu-id="a57ae-225">다음 SQL Server 2000 제한 (Microsoft SQL Server 2005과 비교)은 지원에 영향을 줍니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a57ae-225">The following SQL Server 2000 limitations (compared to Microsoft SQL Server 2005) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>

### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="a57ae-226">Cross Apply 및 Outer Apply 연산자</span><span class="sxs-lookup"><span data-stu-id="a57ae-226">Cross Apply and Outer Apply Operators</span></span>

<span data-ttu-id="a57ae-227">이러한 연산자는 SQL Server 2000에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-227">These operators are not available in SQL Server 2000.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a57ae-228">에서는 일련의 다시 쓰기를 시도하여 해당 연산자를 적절한 조인으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-228">tries a series of rewrites to replace them with appropriate joins.</span></span>

<span data-ttu-id="a57ae-229">`Cross Apply` 및 `Outer Apply`는 관계 탐색을 위해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-229">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="a57ae-230">이러한 다시 쓰기가 가능한 쿼리 집합은 잘 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-230">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="a57ae-231">이러한 이유로 SQL Server 2000에 대해 지원 되는 최소 쿼리 집합은 관계 탐색과 관련이 없는 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-231">For this reason, the minimal set of queries that is supported for SQL Server 2000 is the set that does not involve relationship navigation.</span></span>

### <a name="text--ntext"></a><span data-ttu-id="a57ae-232">text/ntext</span><span class="sxs-lookup"><span data-stu-id="a57ae-232">text / ntext</span></span>

<span data-ttu-id="a57ae-233">데이터 형식은 `text`  /  `ntext` `varchar(max)`  /  `nvarchar(max)` Microsoft SQL Server 2005에서 지원 되는에 대 한 특정 쿼리 작업에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-233">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by Microsoft SQL Server 2005.</span></span>

<span data-ttu-id="a57ae-234">이 제한에 대한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-234">No resolution is available for this limitation.</span></span> <span data-ttu-id="a57ae-235">특히 `Distinct()` 또는 `text` 열에 매핑된 멤버가 들어 있는 결과에서는 `ntext`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-235">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>

### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="a57ae-236">중첩된 쿼리에 의해 트리거되는 동작</span><span class="sxs-lookup"><span data-stu-id="a57ae-236">Behavior Triggered by Nested Queries</span></span>

<span data-ttu-id="a57ae-237">SQL Server 2000 (SP4) 바인더에는 중첩 된 쿼리에 의해 트리거되는 몇 가지 고유한 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-237">SQL Server 2000 (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="a57ae-238">이러한 고유한 특징을 트리거하는 SQL 쿼리 집합은 잘 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-238">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="a57ae-239">따라서 SQL Server 예외를 일으킬 수 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 집합을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-239">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>

### <a name="skip-and-take-operators"></a><span data-ttu-id="a57ae-240">Skip 및 Take 연산자</span><span class="sxs-lookup"><span data-stu-id="a57ae-240">Skip and Take Operators</span></span>

<span data-ttu-id="a57ae-241"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>에는 SQL Server 2000에 대한 쿼리에서 사용할 경우 몇 가지 제한이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-241"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="a57ae-242">자세한 내용은 [문제 해결](troubleshooting.md)에서 "SQL Server 2000의 Skip 및 Take 예외" 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a57ae-242">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="object-materialization"></a><span data-ttu-id="a57ae-243">개체 구체화</span><span class="sxs-lookup"><span data-stu-id="a57ae-243">Object Materialization</span></span>

<span data-ttu-id="a57ae-244">구체화에서는 하나 이상의 SQL 쿼리에서 반환한 행을 사용하여 CLR 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-244">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>

- <span data-ttu-id="a57ae-245">다음 호출은 구체화의 일부로 *로컬에서 실행* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-245">The following calls are *executed locally* as a part of materialization:</span></span>

  - <span data-ttu-id="a57ae-246">생성자</span><span class="sxs-lookup"><span data-stu-id="a57ae-246">Constructors</span></span>

  - <span data-ttu-id="a57ae-247">프로젝션의 `ToString` 메서드</span><span class="sxs-lookup"><span data-stu-id="a57ae-247">`ToString` methods in projections</span></span>

  - <span data-ttu-id="a57ae-248">프로젝션의 형식 캐스트</span><span class="sxs-lookup"><span data-stu-id="a57ae-248">Type casts in projections</span></span>

- <span data-ttu-id="a57ae-249">메서드 뒤에 오는 메서드는 <xref:System.Linq.Enumerable.AsEnumerable%2A> *로컬로 실행* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-249">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="a57ae-250">이 메서드는 즉시 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-250">This method does not cause immediate execution.</span></span>

- <span data-ttu-id="a57ae-251">`struct`를 쿼리 결과의 반환 형식이나 결과 형식의 멤버로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-251">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="a57ae-252">엔터티는 클래스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-252">Entities are required to be classes.</span></span> <span data-ttu-id="a57ae-253">익명 형식은 클래스 인스턴스로 구체화되지만 명명된 구조체(비엔터티)는 프로젝션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-253">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>

- <span data-ttu-id="a57ae-254">쿼리 결과에 대한 반환 형식의 멤버는 <xref:System.Linq.IQueryable%601> 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-254">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="a57ae-255">이 멤버는 로컬 컬렉션으로 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-255">It is materialized as a local collection.</span></span>

- <span data-ttu-id="a57ae-256">다음 메서드는 메서드가 적용 되는 시퀀스의 *즉시 구체화* 를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a57ae-256">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a><span data-ttu-id="a57ae-257">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a57ae-257">See also</span></span>

- [<span data-ttu-id="a57ae-258">참조</span><span class="sxs-lookup"><span data-stu-id="a57ae-258">Reference</span></span>](reference.md)
- [<span data-ttu-id="a57ae-259">시퀀스에서 요소 반환 또는 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="a57ae-259">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)
- [<span data-ttu-id="a57ae-260">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="a57ae-260">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)
- [<span data-ttu-id="a57ae-261">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="a57ae-261">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)
- [<span data-ttu-id="a57ae-262">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="a57ae-262">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)
- [<span data-ttu-id="a57ae-263">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="a57ae-263">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)
