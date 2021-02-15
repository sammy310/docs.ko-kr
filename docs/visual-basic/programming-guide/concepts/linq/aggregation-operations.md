---
description: '자세한 정보: 집계 작업 (Visual Basic)'
title: 집계 작업
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 2ef41faf03100814e062ec98afb8fe17b1ef64bc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462167"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="57ede-103">집계 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ede-103">Aggregation Operations (Visual Basic)</span></span>

<span data-ttu-id="57ede-104">집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-104">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="57ede-105">예를 들어 1달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-105">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="57ede-106">다음 그림은 숫자 시퀀스에 대한 두 가지 집계 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-106">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="57ede-107">첫 번째 작업은 숫자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-107">The first operation sums the numbers.</span></span> <span data-ttu-id="57ede-108">두 번째 작업은 시퀀스의 최대 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-108">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![LINQ 집계 작업을 보여주는 그림](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="57ede-110">다음 섹션에는 집계 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-110">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57ede-111">메서드</span><span class="sxs-lookup"><span data-stu-id="57ede-111">Methods</span></span>  
  
|<span data-ttu-id="57ede-112">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="57ede-112">Method Name</span></span>|<span data-ttu-id="57ede-113">설명</span><span class="sxs-lookup"><span data-stu-id="57ede-113">Description</span></span>|<span data-ttu-id="57ede-114">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="57ede-114">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="57ede-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="57ede-115">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="57ede-116">Aggregate</span><span class="sxs-lookup"><span data-stu-id="57ede-116">Aggregate</span></span>|<span data-ttu-id="57ede-117">컬렉션 값에 대해 사용자 지정 집계 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-117">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="57ede-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="57ede-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-119">평균</span><span class="sxs-lookup"><span data-stu-id="57ede-119">Average</span></span>|<span data-ttu-id="57ede-120">값 컬렉션의 평균 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-120">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-121">개수</span><span class="sxs-lookup"><span data-stu-id="57ede-121">Count</span></span>|<span data-ttu-id="57ede-122">컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-123">LongCount</span><span class="sxs-lookup"><span data-stu-id="57ede-123">LongCount</span></span>|<span data-ttu-id="57ede-124">큰 컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-124">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-125">최대</span><span class="sxs-lookup"><span data-stu-id="57ede-125">Max</span></span>|<span data-ttu-id="57ede-126">컬렉션의 최대값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-126">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-127">최소</span><span class="sxs-lookup"><span data-stu-id="57ede-127">Min</span></span>|<span data-ttu-id="57ede-128">컬렉션의 최소값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-128">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57ede-129">Sum</span><span class="sxs-lookup"><span data-stu-id="57ede-129">Sum</span></span>|<span data-ttu-id="57ede-130">컬렉션에 있는 값의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-130">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="57ede-131">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="57ede-131">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="57ede-132">평균</span><span class="sxs-lookup"><span data-stu-id="57ede-132">Average</span></span>  

 <span data-ttu-id="57ede-133">다음 코드 예제에서는 Visual Basic의 절을 사용 하 여 `Aggregate Into Average` 온도를 나타내는 숫자 배열의 평균 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-133">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="57ede-134">개수</span><span class="sxs-lookup"><span data-stu-id="57ede-134">Count</span></span>  

 <span data-ttu-id="57ede-135">다음 코드 예제에서는 `Aggregate Into Count` Visual Basic 절을 사용 하 여 배열에서 80 보다 크거나 같은 값의 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-135">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="57ede-136">LongCount</span><span class="sxs-lookup"><span data-stu-id="57ede-136">LongCount</span></span>  

 <span data-ttu-id="57ede-137">다음 코드 예제에서는 절을 사용 `Aggregate Into LongCount` 하 여 배열에 있는 값의 개수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-137">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="57ede-138">Max</span><span class="sxs-lookup"><span data-stu-id="57ede-138">Max</span></span>  

 <span data-ttu-id="57ede-139">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Max` 온도를 나타내는 숫자 배열의 최대 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-139">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="57ede-140">최소값</span><span class="sxs-lookup"><span data-stu-id="57ede-140">Min</span></span>  

 <span data-ttu-id="57ede-141">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Min` 온도를 나타내는 숫자 배열의 최소 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-141">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="57ede-142">합계</span><span class="sxs-lookup"><span data-stu-id="57ede-142">Sum</span></span>  

 <span data-ttu-id="57ede-143">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Sum` 비용을 나타내는 값 배열의 총 비용을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ede-143">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="57ede-144">추가 정보</span><span class="sxs-lookup"><span data-stu-id="57ede-144">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="57ede-145">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ede-145">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="57ede-146">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="57ede-146">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="57ede-147">방법: CSV 텍스트 파일의 열 값 계산 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ede-147">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="57ede-148">방법: 데이터 개수, 합 또는 평균 계산</span><span class="sxs-lookup"><span data-stu-id="57ede-148">How to: Count, Sum, or Average Data</span></span>](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="57ede-149">방법: 쿼리 결과의 최소값 또는 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="57ede-149">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="57ede-150">방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ede-150">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="57ede-151">방법: 폴더 집합의 총 바이트 수 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ede-151">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
