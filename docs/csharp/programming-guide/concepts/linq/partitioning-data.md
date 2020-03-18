---
title: 데이터 분할(C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: d9330e9973b2f25903e1f81a7296362e2a7c756b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591585"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="73c83-102">데이터 분할(C#)</span><span class="sxs-lookup"><span data-stu-id="73c83-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="73c83-103">LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="73c83-104">다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="73c83-105">첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="73c83-106">두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="73c83-107">세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![세 개의 LINQ 분할 작업을 보여주는 그림.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="73c83-109">시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="73c83-110">연산자</span><span class="sxs-lookup"><span data-stu-id="73c83-110">Operators</span></span>  
  
|<span data-ttu-id="73c83-111">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="73c83-111">Operator Name</span></span>|<span data-ttu-id="73c83-112">설명</span><span class="sxs-lookup"><span data-stu-id="73c83-112">Description</span></span>|<span data-ttu-id="73c83-113">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="73c83-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="73c83-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="73c83-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="73c83-115">Skip</span><span class="sxs-lookup"><span data-stu-id="73c83-115">Skip</span></span>|<span data-ttu-id="73c83-116">시퀀스에서 지정한 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="73c83-117">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="73c83-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="73c83-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="73c83-118">SkipWhile</span></span>|<span data-ttu-id="73c83-119">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="73c83-120">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="73c83-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="73c83-121">Take</span><span class="sxs-lookup"><span data-stu-id="73c83-121">Take</span></span>|<span data-ttu-id="73c83-122">시퀀스에서 지정된 위치까지 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="73c83-123">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="73c83-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="73c83-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="73c83-124">TakeWhile</span></span>|<span data-ttu-id="73c83-125">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73c83-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="73c83-126">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="73c83-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="73c83-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73c83-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="73c83-128">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="73c83-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
