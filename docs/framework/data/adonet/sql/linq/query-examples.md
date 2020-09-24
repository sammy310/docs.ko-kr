---
title: 쿼리 예제
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: f3f135850fb5f40b3b8882f72f5cc24512f21084
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147556"
---
# <a name="query-examples"></a><span data-ttu-id="03e8e-102">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="03e8e-102">Query Examples</span></span>

<span data-ttu-id="03e8e-103">이 섹션에서는 일반적인 쿼리의 Visual Basic 및 c # 예제를 제공 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="03e8e-104">Visual Studio를 사용 하는 개발자는 샘플 섹션에서 제공 하는 샘플 솔루션에서 더 많은 예제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="03e8e-105">자세한 내용은 [샘플](samples.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03e8e-105">For more information, see [Samples](samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="03e8e-106">*db* 는 설명서의 코드 예제에서 자주 사용 됩니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03e8e-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="03e8e-107">*db* 는에서 상속 되는 *Northwind* 클래스의 인스턴스로 간주 됩니다 <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="03e8e-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03e8e-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="03e8e-108">In This Section</span></span>  

 [<span data-ttu-id="03e8e-109">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="03e8e-109">Aggregate Queries</span></span>](aggregate-queries.md)  
 <span data-ttu-id="03e8e-110"><xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> 등의 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="03e8e-111">시퀀스의 첫 번째 요소 반환</span><span class="sxs-lookup"><span data-stu-id="03e8e-111">Return the First Element in a Sequence</span></span>](return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="03e8e-112"><xref:System.Linq.Enumerable.First%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-113">시퀀스에서 요소 반환 또는 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="03e8e-113">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="03e8e-114"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-115">시퀀스의 요소 정렬</span><span class="sxs-lookup"><span data-stu-id="03e8e-115">Sort Elements in a Sequence</span></span>](sort-elements-in-a-sequence.md)  
 <span data-ttu-id="03e8e-116"><xref:System.Linq.Enumerable.OrderBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-117">시퀀스의 요소 그룹화</span><span class="sxs-lookup"><span data-stu-id="03e8e-117">Group Elements in a Sequence</span></span>](group-elements-in-a-sequence.md)  
 <span data-ttu-id="03e8e-118"><xref:System.Linq.Enumerable.GroupBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-119">시퀀스에서 중복 요소 제거</span><span class="sxs-lookup"><span data-stu-id="03e8e-119">Eliminate Duplicate Elements from a Sequence</span></span>](eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="03e8e-120"><xref:System.Linq.Enumerable.Distinct%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-121">시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="03e8e-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="03e8e-122"><xref:System.Linq.Enumerable.All%2A> 및 <xref:System.Linq.Enumerable.Any%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-123">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="03e8e-123">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)  
 <span data-ttu-id="03e8e-124"><xref:System.Linq.Enumerable.Concat%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-125">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="03e8e-125">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="03e8e-126"><xref:System.Linq.Enumerable.Except%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-127">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="03e8e-127">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="03e8e-128"><xref:System.Linq.Enumerable.Intersect%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-129">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="03e8e-129">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="03e8e-130"><xref:System.Linq.Enumerable.Union%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-131">시퀀스를 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="03e8e-131">Convert a Sequence to an Array</span></span>](convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="03e8e-132"><xref:System.Linq.Enumerable.ToArray%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-133">제네릭 목록으로 시퀀스 변환</span><span class="sxs-lookup"><span data-stu-id="03e8e-133">Convert a Sequence to a Generic List</span></span>](convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="03e8e-134"><xref:System.Linq.Enumerable.ToList%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-135">제네릭 IEnumerable로 형식 변환</span><span class="sxs-lookup"><span data-stu-id="03e8e-135">Convert a Type to a Generic IEnumerable</span></span>](convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="03e8e-136"><xref:System.Linq.Enumerable.AsEnumerable%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="03e8e-137">방법: 조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="03e8e-137">Formulate Joins and Cross-Product Queries</span></span>](formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="03e8e-138">`from`, `where` 및 `select` 절에서 외래 키 탐색 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="03e8e-139">프로젝션 작성</span><span class="sxs-lookup"><span data-stu-id="03e8e-139">Formulate Projections</span></span>](formulate-projections.md)  
 <span data-ttu-id="03e8e-140">`select`다른 기능 (예: *익명 형식*)을 결합 하 여 쿼리 프로젝션을 구성 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="03e8e-141">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="03e8e-141">Related Sections</span></span>  

 [<span data-ttu-id="03e8e-142">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="03e8e-142">Standard Query Operators Overview (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="03e8e-143">C #을 사용 하는 표준 쿼리 연산자의 개념에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-143">Explains the concept of standard query operators using C#.</span></span>  
  
 [<span data-ttu-id="03e8e-144">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03e8e-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="03e8e-145">Visual Basic 사용 하는 표준 쿼리 연산자의 개념에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-145">Explains the concept of standard query operators using Visual Basic.</span></span>  
  
 [<span data-ttu-id="03e8e-146">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="03e8e-146">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="03e8e-147">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 개념이 쿼리에 어떻게 적용되는지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-147">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="03e8e-148">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="03e8e-148">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="03e8e-149">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 관련 프로그래밍 개념을 설명하는 항목에 대한 포털을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8e-149">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
