---
title: 데이터 분할(C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: b857c8c6e6b56a7263e6725a747e98ccfe4ff4fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832465"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="f4e60-102">데이터 분할(C#)</span><span class="sxs-lookup"><span data-stu-id="f4e60-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="f4e60-103">LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="f4e60-104">다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="f4e60-105">첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="f4e60-106">두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="f4e60-107">세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![세 개의 LINQ 분할 작업을 보여주는 그림.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="f4e60-109">시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="f4e60-110">연산자</span><span class="sxs-lookup"><span data-stu-id="f4e60-110">Operators</span></span>  
  
|<span data-ttu-id="f4e60-111">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="f4e60-111">Operator Name</span></span>|<span data-ttu-id="f4e60-112">설명</span><span class="sxs-lookup"><span data-stu-id="f4e60-112">Description</span></span>|<span data-ttu-id="f4e60-113">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="f4e60-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="f4e60-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f4e60-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f4e60-115">Skip</span><span class="sxs-lookup"><span data-stu-id="f4e60-115">Skip</span></span>|<span data-ttu-id="f4e60-116">시퀀스에서 지정한 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="f4e60-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f4e60-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f4e60-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="f4e60-118">SkipWhile</span></span>|<span data-ttu-id="f4e60-119">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="f4e60-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f4e60-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f4e60-121">Take</span><span class="sxs-lookup"><span data-stu-id="f4e60-121">Take</span></span>|<span data-ttu-id="f4e60-122">시퀀스에서 지정된 위치까지 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="f4e60-123">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f4e60-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f4e60-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="f4e60-124">TakeWhile</span></span>|<span data-ttu-id="f4e60-125">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e60-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="f4e60-126">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f4e60-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="f4e60-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4e60-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f4e60-128">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="f4e60-128">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
