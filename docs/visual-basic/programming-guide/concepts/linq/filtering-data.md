---
title: 데이터 필터링
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 81e207e451055fb2952e4bf393db067f0851afb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353488"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="39cd7-102">Filtering Data (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd7-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="39cd7-103">필터링은 지정된 조건을 충족하는 요소만 포함하도록 결과 집합을 제한하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="39cd7-104">필터링은 선택이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-104">It is also known as selection.</span></span>

<span data-ttu-id="39cd7-105">다음 그림에서는 문자 시퀀스를 필터링한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="39cd7-106">필터링 작업에 대한 조건자는 문자가 'A'가 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![LINQ 필터링 작업을 보여주는 다이어그램](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="39cd7-108">선택을 수행하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="39cd7-109">메서드</span><span class="sxs-lookup"><span data-stu-id="39cd7-109">Methods</span></span>

|<span data-ttu-id="39cd7-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="39cd7-110">Method Name</span></span>|<span data-ttu-id="39cd7-111">설명</span><span class="sxs-lookup"><span data-stu-id="39cd7-111">Description</span></span>|<span data-ttu-id="39cd7-112">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="39cd7-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="39cd7-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="39cd7-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="39cd7-114">OfType</span><span class="sxs-lookup"><span data-stu-id="39cd7-114">OfType</span></span>|<span data-ttu-id="39cd7-115">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="39cd7-116">해당 없음.</span><span class="sxs-lookup"><span data-stu-id="39cd7-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="39cd7-117">Where</span><span class="sxs-lookup"><span data-stu-id="39cd7-117">Where</span></span>|<span data-ttu-id="39cd7-118">조건자 함수를 기반으로 하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39cd7-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="39cd7-119">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="39cd7-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="39cd7-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span><span class="sxs-lookup"><span data-stu-id="39cd7-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a><span data-ttu-id="39cd7-121">참조</span><span class="sxs-lookup"><span data-stu-id="39cd7-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="39cd7-122">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd7-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="39cd7-123">Where 절</span><span class="sxs-lookup"><span data-stu-id="39cd7-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="39cd7-124">방법: 쿼리 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="39cd7-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="39cd7-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd7-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="39cd7-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd7-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="39cd7-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd7-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
