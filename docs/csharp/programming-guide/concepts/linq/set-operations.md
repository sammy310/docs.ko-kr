---
title: 집합 작업(C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 9e507bbaa39bf040a8ce1564630fb5fbb8c0dbe4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408914"
---
# <a name="set-operations-c"></a><span data-ttu-id="742ed-102">집합 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="742ed-102">Set Operations (C#)</span></span>
<span data-ttu-id="742ed-103">LINQ의 집합 작업은 동일 컬렉션이나 별개 컬렉션(또는 집합)에 동등한 요소가 있는지 여부에 따라 결과 집합을 생성하는 쿼리 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="742ed-104">다음 섹션에는 집합 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="742ed-105">메서드</span><span class="sxs-lookup"><span data-stu-id="742ed-105">Methods</span></span>  
  
|<span data-ttu-id="742ed-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="742ed-106">Method Name</span></span>|<span data-ttu-id="742ed-107">설명</span><span class="sxs-lookup"><span data-stu-id="742ed-107">Description</span></span>|<span data-ttu-id="742ed-108">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="742ed-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="742ed-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="742ed-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="742ed-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="742ed-110">Distinct</span></span>|<span data-ttu-id="742ed-111">컬렉션에서 중복 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="742ed-112">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="742ed-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="742ed-113">Except</span><span class="sxs-lookup"><span data-stu-id="742ed-113">Except</span></span>|<span data-ttu-id="742ed-114">두 번째 컬렉션에 표시되지 않는 한 컬렉션의 요소를 의미하는 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="742ed-115">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="742ed-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="742ed-116">Intersect</span><span class="sxs-lookup"><span data-stu-id="742ed-116">Intersect</span></span>|<span data-ttu-id="742ed-117">두 컬렉션에 각각 표시되는 요소를 의미하는 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="742ed-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="742ed-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="742ed-119">Union</span><span class="sxs-lookup"><span data-stu-id="742ed-119">Union</span></span>|<span data-ttu-id="742ed-120">두 컬렉션 중 하나에 표시되는 고유한 요소를 의미하는 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="742ed-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="742ed-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="742ed-122">집합 작업 비교</span><span class="sxs-lookup"><span data-stu-id="742ed-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="742ed-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="742ed-123">Distinct</span></span>  
 <span data-ttu-id="742ed-124">다음 그림에서는 문자 시퀀스에 대한 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 메서드의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="742ed-125">반환된 시퀀스에는 입력 시퀀스의 고유한 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Distinct()의 동작을 보여주는 그래픽](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="742ed-127">Except</span><span class="sxs-lookup"><span data-stu-id="742ed-127">Except</span></span>  
 <span data-ttu-id="742ed-128">다음 그림에서는 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="742ed-129">반환된 시퀀스에는 두 번째 입력 시퀀스에 없는 첫 번째 입력 시퀀스의 요소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="742ed-130">![Except&#40;&#41;의 작업을 보여 주는 그래픽](./media/set-operations/except-behavior-graphic.png "Except의 동작을 보여 줍니다.")</span><span class="sxs-lookup"><span data-stu-id="742ed-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="742ed-131">Intersect</span><span class="sxs-lookup"><span data-stu-id="742ed-131">Intersect</span></span>  
 <span data-ttu-id="742ed-132">다음 그림에서는 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="742ed-133">반환된 시퀀스에는 입력 시퀀스 둘 다에 공통적으로 있는 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![두 시퀀스의 교집합을 보여주는 그래픽](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a><span data-ttu-id="742ed-135">Union</span><span class="sxs-lookup"><span data-stu-id="742ed-135">Union</span></span>  
 <span data-ttu-id="742ed-136">다음 그림은 두 개의 문자 시퀀스에 대한 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="742ed-137">반환된 시퀀스에는 두 입력 시퀀스의 고유한 요소가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="742ed-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![두 시퀀스의 결합을 보여주는 그래픽](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a><span data-ttu-id="742ed-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="742ed-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="742ed-140">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="742ed-140">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="742ed-141">방법: 문자열 컬렉션 결합 및 비교(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="742ed-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="742ed-142">방법: 두 목록 간의 차집합 구하기(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="742ed-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
