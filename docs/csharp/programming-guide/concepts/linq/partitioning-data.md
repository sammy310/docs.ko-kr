---
title: 데이터 분할(C#)
description: LINQ에서 데이터를 분할하는 방법을 알아봅니다. 분할 작업의 결과를 보여 주는 그림을 봅니다.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 3c85eaec2dc01b683234a27714750354982be440
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302609"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="39683-104">데이터 분할(C#)</span><span class="sxs-lookup"><span data-stu-id="39683-104">Partitioning Data (C#)</span></span>
<span data-ttu-id="39683-105">LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="39683-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="39683-106">다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39683-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="39683-107">첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39683-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="39683-108">두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39683-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="39683-109">세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39683-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![세 개의 LINQ 분할 작업을 보여주는 그림.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="39683-111">시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39683-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="39683-112">연산자</span><span class="sxs-lookup"><span data-stu-id="39683-112">Operators</span></span>  
  
|<span data-ttu-id="39683-113">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="39683-113">Operator Name</span></span>|<span data-ttu-id="39683-114">설명</span><span class="sxs-lookup"><span data-stu-id="39683-114">Description</span></span>|<span data-ttu-id="39683-115">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="39683-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="39683-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="39683-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="39683-117">Skip</span><span class="sxs-lookup"><span data-stu-id="39683-117">Skip</span></span>|<span data-ttu-id="39683-118">시퀀스에서 지정한 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="39683-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="39683-119">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="39683-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="39683-120">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="39683-120">SkipWhile</span></span>|<span data-ttu-id="39683-121">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="39683-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="39683-122">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="39683-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="39683-123">Take</span><span class="sxs-lookup"><span data-stu-id="39683-123">Take</span></span>|<span data-ttu-id="39683-124">시퀀스에서 지정된 위치까지 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39683-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="39683-125">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="39683-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="39683-126">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="39683-126">TakeWhile</span></span>|<span data-ttu-id="39683-127">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39683-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="39683-128">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="39683-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="39683-129">참조</span><span class="sxs-lookup"><span data-stu-id="39683-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="39683-130">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="39683-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
