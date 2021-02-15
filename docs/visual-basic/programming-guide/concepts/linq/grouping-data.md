---
description: '자세한 정보: 데이터 그룹화 (Visual Basic)'
title: 데이터 그룹화
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: fa6dbcc22c7d991d48775c3974cfc529840ef933
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469801"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="bb42a-103">데이터 그룹화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb42a-103">Grouping Data (Visual Basic)</span></span>

<span data-ttu-id="bb42a-104">그룹화는 데이터를 그룹에 넣어 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-104">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="bb42a-105">다음 그림은 문자 시퀀스를 그룹화한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-105">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="bb42a-106">각 그룹에 대한 키는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-106">The key for each group is the character.</span></span>  
  
 ![LINQ 그룹화 작업을 보여주는 다이어그램.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="bb42a-108">데이터 요소를 그룹화하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-108">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb42a-109">메서드</span><span class="sxs-lookup"><span data-stu-id="bb42a-109">Methods</span></span>  
  
|<span data-ttu-id="bb42a-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="bb42a-110">Method Name</span></span>|<span data-ttu-id="bb42a-111">설명</span><span class="sxs-lookup"><span data-stu-id="bb42a-111">Description</span></span>|<span data-ttu-id="bb42a-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="bb42a-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="bb42a-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="bb42a-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="bb42a-114">GroupBy</span><span class="sxs-lookup"><span data-stu-id="bb42a-114">GroupBy</span></span>|<span data-ttu-id="bb42a-115">공통 특성을 공유하는 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-115">Groups elements that share a common attribute.</span></span> <span data-ttu-id="bb42a-116">각 그룹은 <xref:System.Linq.IGrouping%602> 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-116">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bb42a-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="bb42a-117">ToLookup</span></span>|<span data-ttu-id="bb42a-118">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일대다 사전)에 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="bb42a-119">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="bb42a-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="bb42a-120">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="bb42a-120">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="bb42a-121">다음 코드 예제에서는 `Group By` 절을 사용하여 짝수 또는 홀수인지에 따라 목록에서 정수를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb42a-121">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb42a-122">참조</span><span class="sxs-lookup"><span data-stu-id="bb42a-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="bb42a-123">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb42a-123">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="bb42a-124">Group By 절</span><span class="sxs-lookup"><span data-stu-id="bb42a-124">Group By Clause</span></span>](../../../language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="bb42a-125">방법: 확장명에 따라 파일 그룹화 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb42a-125">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="bb42a-126">방법: 그룹을 사용 하 여 파일을 여러 파일로 분할 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb42a-126">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
