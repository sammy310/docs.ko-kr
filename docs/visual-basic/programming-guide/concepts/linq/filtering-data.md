---
title: 데이터 필터링
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383419"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="32061-102">데이터 필터링 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32061-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="32061-103">필터링은 지정된 조건을 충족하는 요소만 포함하도록 결과 집합을 제한하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="32061-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="32061-104">필터링은 선택이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="32061-104">It is also known as selection.</span></span>

<span data-ttu-id="32061-105">다음 그림에서는 문자 시퀀스를 필터링한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32061-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="32061-106">필터링 작업에 대한 조건자는 문자가 'A'가 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32061-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![LINQ 필터링 작업을 보여주는 다이어그램](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="32061-108">선택을 수행하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="32061-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="32061-109">메서드</span><span class="sxs-lookup"><span data-stu-id="32061-109">Methods</span></span>

|<span data-ttu-id="32061-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="32061-110">Method Name</span></span>|<span data-ttu-id="32061-111">설명</span><span class="sxs-lookup"><span data-stu-id="32061-111">Description</span></span>|<span data-ttu-id="32061-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="32061-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="32061-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="32061-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="32061-114">OfType</span><span class="sxs-lookup"><span data-stu-id="32061-114">OfType</span></span>|<span data-ttu-id="32061-115">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32061-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="32061-116">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="32061-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="32061-117">Where</span><span class="sxs-lookup"><span data-stu-id="32061-117">Where</span></span>|<span data-ttu-id="32061-118">조건자 함수를 기반으로 하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32061-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="32061-119">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="32061-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="32061-120">다음 예제에서는를 사용 하 여 `Where` 특정 길이가 지정 된 문자열을 배열에서 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="32061-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="32061-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32061-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="32061-122">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32061-122">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="32061-123">Where 절</span><span class="sxs-lookup"><span data-stu-id="32061-123">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="32061-124">방법: 쿼리 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="32061-124">How to: Filter Query Results</span></span>](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="32061-125">방법: 리플렉션을 사용 하 여 어셈블리의 메타 데이터 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32061-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="32061-126">방법: 지정 된 특성 또는 이름으로 파일 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32061-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="32061-127">방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32061-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
