---
title: 데이터 그룹화
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: 9a4011b77f91ff241d23f7aeca95925a1e170483
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266822"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="e3632-102">데이터 그룹화(시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="e3632-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="e3632-103">그룹화는 데이터를 그룹에 넣어 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="e3632-104">다음 그림은 문자 시퀀스를 그룹화한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="e3632-105">각 그룹에 대한 키는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-105">The key for each group is the character.</span></span>  
  
 ![LINQ 그룹화 작업을 보여주는 다이어그램.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="e3632-107">데이터 요소를 그룹화하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3632-108">메서드</span><span class="sxs-lookup"><span data-stu-id="e3632-108">Methods</span></span>  
  
|<span data-ttu-id="e3632-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="e3632-109">Method Name</span></span>|<span data-ttu-id="e3632-110">설명</span><span class="sxs-lookup"><span data-stu-id="e3632-110">Description</span></span>|<span data-ttu-id="e3632-111">시각적 기본 쿼리 표현식 구문</span><span class="sxs-lookup"><span data-stu-id="e3632-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e3632-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e3632-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e3632-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="e3632-113">GroupBy</span></span>|<span data-ttu-id="e3632-114">공통 특성을 공유하는 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="e3632-115">각 그룹은 <xref:System.Linq.IGrouping%602> 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e3632-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="e3632-116">ToLookup</span></span>|<span data-ttu-id="e3632-117">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일대다 사전)에 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="e3632-118">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="e3632-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="e3632-119">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="e3632-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="e3632-120">다음 코드 예제에서는 `Group By` 절을 사용하여 짝수 또는 홀수인지에 따라 목록에서 정수를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e3632-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3632-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3632-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e3632-122">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3632-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e3632-123">그룹별 절</span><span class="sxs-lookup"><span data-stu-id="e3632-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="e3632-124">방법: 확장자별 파일 그룹화(LINQ) (시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="e3632-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="e3632-125">방법: 그룹(LINQ)(시각적 기본)을 사용하여 파일을 여러 파일로 분할</span><span class="sxs-lookup"><span data-stu-id="e3632-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
