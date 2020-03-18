---
title: 데이터 그룹화(C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 7ef3d3c9097d7a9478605565518ac8975feb9fe2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635745"
---
# <a name="grouping-data-c"></a><span data-ttu-id="da1be-102">데이터 그룹화(C#)</span><span class="sxs-lookup"><span data-stu-id="da1be-102">Grouping Data (C#)</span></span>
<span data-ttu-id="da1be-103">그룹화는 데이터를 그룹에 넣어 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="da1be-104">다음 그림은 문자 시퀀스를 그룹화한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="da1be-105">각 그룹에 대한 키는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-105">The key for each group is the character.</span></span>  
  
 ![LINQ 그룹화 작업을 보여주는 다이어그램.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="da1be-107">데이터 요소를 그룹화하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da1be-108">메서드</span><span class="sxs-lookup"><span data-stu-id="da1be-108">Methods</span></span>  
  
|<span data-ttu-id="da1be-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="da1be-109">Method Name</span></span>|<span data-ttu-id="da1be-110">설명</span><span class="sxs-lookup"><span data-stu-id="da1be-110">Description</span></span>|<span data-ttu-id="da1be-111">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="da1be-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="da1be-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="da1be-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="da1be-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="da1be-113">GroupBy</span></span>|<span data-ttu-id="da1be-114">공통 특성을 공유하는 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="da1be-115">각 그룹은 <xref:System.Linq.IGrouping%602> 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="da1be-116">또는</span><span class="sxs-lookup"><span data-stu-id="da1be-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="da1be-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="da1be-117">ToLookup</span></span>|<span data-ttu-id="da1be-118">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일대다 사전)에 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="da1be-119">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="da1be-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="da1be-120">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da1be-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="da1be-121">다음 코드 예제에서는 `group by` 절을 사용하여 짝수 또는 홀수인지에 따라 목록에서 정수를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="da1be-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da1be-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da1be-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="da1be-123">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="da1be-123">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="da1be-124">group 절</span><span class="sxs-lookup"><span data-stu-id="da1be-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="da1be-125">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="da1be-125">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="da1be-126">확장명에 따라 파일을 그룹화하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="da1be-126">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="da1be-127">쿼리 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="da1be-127">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="da1be-128">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="da1be-128">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="da1be-129">그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="da1be-129">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
