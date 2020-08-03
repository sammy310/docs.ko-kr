---
title: 데이터 그룹화(C#)
description: 그룹화는 특성을 공유하는 요소의 그룹에 데이터를 넣는 것입니다. C#에서 데이터 요소를 그룹화하는 LINQ의 표준 쿼리 연산자 메서드에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 5e1bca1d360b0f44a081cf2770118a0551629b5b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103676"
---
# <a name="grouping-data-c"></a><span data-ttu-id="e5b82-104">데이터 그룹화(C#)</span><span class="sxs-lookup"><span data-stu-id="e5b82-104">Grouping Data (C#)</span></span>
<span data-ttu-id="e5b82-105">그룹화는 데이터를 그룹에 넣어 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="e5b82-106">다음 그림은 문자 시퀀스를 그룹화한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="e5b82-107">각 그룹에 대한 키는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-107">The key for each group is the character.</span></span>  
  
 ![LINQ 그룹화 작업을 보여주는 다이어그램.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="e5b82-109">데이터 요소를 그룹화하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5b82-110">메서드</span><span class="sxs-lookup"><span data-stu-id="e5b82-110">Methods</span></span>  
  
|<span data-ttu-id="e5b82-111">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="e5b82-111">Method Name</span></span>|<span data-ttu-id="e5b82-112">설명</span><span class="sxs-lookup"><span data-stu-id="e5b82-112">Description</span></span>|<span data-ttu-id="e5b82-113">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="e5b82-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="e5b82-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e5b82-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e5b82-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="e5b82-115">GroupBy</span></span>|<span data-ttu-id="e5b82-116">공통 특성을 공유하는 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="e5b82-117">각 그룹은 <xref:System.Linq.IGrouping%602> 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="e5b82-118">또는</span><span class="sxs-lookup"><span data-stu-id="e5b82-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e5b82-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="e5b82-119">ToLookup</span></span>|<span data-ttu-id="e5b82-120">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일대다 사전)에 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="e5b82-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="e5b82-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="e5b82-122">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="e5b82-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="e5b82-123">다음 코드 예제에서는 `group by` 절을 사용하여 짝수 또는 홀수인지에 따라 목록에서 정수를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b82-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5b82-124">참조</span><span class="sxs-lookup"><span data-stu-id="e5b82-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e5b82-125">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="e5b82-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="e5b82-126">group 절</span><span class="sxs-lookup"><span data-stu-id="e5b82-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="e5b82-127">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="e5b82-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="e5b82-128">확장명에 따라 파일을 그룹화하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="e5b82-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="e5b82-129">쿼리 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="e5b82-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="e5b82-130">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="e5b82-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="e5b82-131">그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="e5b82-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
