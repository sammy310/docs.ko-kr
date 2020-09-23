---
title: 집계 작업
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 1cf82d8acfdb1f8b0fc33c324064574b0dd01f4a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078400"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="003e5-102">집계 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e5-102">Aggregation Operations (Visual Basic)</span></span>

<span data-ttu-id="003e5-103">집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="003e5-104">예를 들어 1달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="003e5-105">다음 그림은 숫자 시퀀스에 대한 두 가지 집계 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="003e5-106">첫 번째 작업은 숫자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-106">The first operation sums the numbers.</span></span> <span data-ttu-id="003e5-107">두 번째 작업은 시퀀스의 최대 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![LINQ 집계 작업을 보여주는 그림](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="003e5-109">다음 섹션에는 집계 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="003e5-110">메서드</span><span class="sxs-lookup"><span data-stu-id="003e5-110">Methods</span></span>  
  
|<span data-ttu-id="003e5-111">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="003e5-111">Method Name</span></span>|<span data-ttu-id="003e5-112">설명</span><span class="sxs-lookup"><span data-stu-id="003e5-112">Description</span></span>|<span data-ttu-id="003e5-113">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="003e5-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="003e5-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="003e5-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="003e5-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="003e5-115">Aggregate</span></span>|<span data-ttu-id="003e5-116">컬렉션 값에 대해 사용자 지정 집계 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="003e5-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="003e5-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-118">평균</span><span class="sxs-lookup"><span data-stu-id="003e5-118">Average</span></span>|<span data-ttu-id="003e5-119">값 컬렉션의 평균 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-120">개수</span><span class="sxs-lookup"><span data-stu-id="003e5-120">Count</span></span>|<span data-ttu-id="003e5-121">컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="003e5-122">LongCount</span></span>|<span data-ttu-id="003e5-123">큰 컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-124">최대</span><span class="sxs-lookup"><span data-stu-id="003e5-124">Max</span></span>|<span data-ttu-id="003e5-125">컬렉션의 최대값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-126">최소</span><span class="sxs-lookup"><span data-stu-id="003e5-126">Min</span></span>|<span data-ttu-id="003e5-127">컬렉션의 최소값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="003e5-128">Sum</span><span class="sxs-lookup"><span data-stu-id="003e5-128">Sum</span></span>|<span data-ttu-id="003e5-129">컬렉션에 있는 값의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="003e5-130">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="003e5-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="003e5-131">평균</span><span class="sxs-lookup"><span data-stu-id="003e5-131">Average</span></span>  

 <span data-ttu-id="003e5-132">다음 코드 예제에서는 Visual Basic의 절을 사용 하 여 `Aggregate Into Average` 온도를 나타내는 숫자 배열의 평균 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="003e5-133">개수</span><span class="sxs-lookup"><span data-stu-id="003e5-133">Count</span></span>  

 <span data-ttu-id="003e5-134">다음 코드 예제에서는 `Aggregate Into Count` Visual Basic 절을 사용 하 여 배열에서 80 보다 크거나 같은 값의 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="003e5-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="003e5-135">LongCount</span></span>  

 <span data-ttu-id="003e5-136">다음 코드 예제에서는 절을 사용 `Aggregate Into LongCount` 하 여 배열에 있는 값의 개수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="003e5-137">최대</span><span class="sxs-lookup"><span data-stu-id="003e5-137">Max</span></span>  

 <span data-ttu-id="003e5-138">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Max` 온도를 나타내는 숫자 배열의 최대 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="003e5-139">최소값</span><span class="sxs-lookup"><span data-stu-id="003e5-139">Min</span></span>  

 <span data-ttu-id="003e5-140">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Min` 온도를 나타내는 숫자 배열의 최소 온도를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="003e5-141">합계</span><span class="sxs-lookup"><span data-stu-id="003e5-141">Sum</span></span>  

 <span data-ttu-id="003e5-142">다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Sum` 비용을 나타내는 값 배열의 총 비용을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="003e5-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="003e5-143">참조</span><span class="sxs-lookup"><span data-stu-id="003e5-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="003e5-144">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e5-144">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="003e5-145">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="003e5-145">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="003e5-146">방법: CSV 텍스트 파일의 열 값 계산 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e5-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="003e5-147">방법: 데이터 개수, 합 또는 평균 계산</span><span class="sxs-lookup"><span data-stu-id="003e5-147">How to: Count, Sum, or Average Data</span></span>](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="003e5-148">방법: 쿼리 결과의 최소값 또는 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="003e5-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="003e5-149">방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e5-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="003e5-150">방법: 폴더 집합의 총 바이트 수 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e5-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
