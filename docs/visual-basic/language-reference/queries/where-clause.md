---
title: Where 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 60b7ebe96ce0c4580c36675b2e4aa5f9888732c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349622"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="8ab2c-102">Where 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ab2c-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="8ab2c-103">쿼리의 필터링 조건을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ab2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ab2c-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="8ab2c-105">요소</span><span class="sxs-lookup"><span data-stu-id="8ab2c-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="8ab2c-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-106">Required.</span></span> <span data-ttu-id="8ab2c-107">컬렉션의 현재 항목에 대 한 값이 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="8ab2c-108">식은 `Boolean` 값 또는 `Boolean` 값에 해당 하는 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="8ab2c-109">조건이 `True`로 확인 되 면 요소가 쿼리 결과에 포함 됩니다. 그렇지 않으면 요소가 쿼리 결과에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ab2c-110">주의</span><span class="sxs-lookup"><span data-stu-id="8ab2c-110">Remarks</span></span>  
 <span data-ttu-id="8ab2c-111">`Where` 절을 사용 하면 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="8ab2c-112">`Where` `True` 절이 쿼리 결과에 포함 되도록 하는 값을 갖는 요소입니다. 다른 요소는 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="8ab2c-113">`Where` 절에 사용 되는 식은 `Boolean` 또는 해당 값이 0 일 때 `False`를 계산 하는 정수와 같은 `Boolean`으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="8ab2c-114">`And`, `Or`, `AndAlso`, `OrElse`, `Is`, `IsNot`등의 논리 연산자를 사용 하 여 `Where` 절에서 여러 식을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="8ab2c-115">기본적으로 쿼리 식은 액세스 될 때까지 계산 되지 않습니다. 예를 들어, 데이터 바인딩된 경우에는 `For` 루프에서 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="8ab2c-116">따라서 쿼리를 액세스할 때까지 `Where` 절이 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="8ab2c-117">`Where` 절에서 사용 되는 쿼리 외부 값이 있는 경우 쿼리가 실행 될 때 `Where` 절에서 적절 한 값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="8ab2c-118">쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="8ab2c-119">`Where` 절 내에서 함수를 호출 하 여 컬렉션의 현재 요소에서 값에 대 한 계산 또는 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="8ab2c-120">`Where` 절에서 함수를 호출 하면 쿼리가 액세스 될 때가 아니라 정의 될 때 쿼리를 즉시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="8ab2c-121">쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ab2c-122">예제</span><span class="sxs-lookup"><span data-stu-id="8ab2c-122">Example</span></span>  
 <span data-ttu-id="8ab2c-123">다음 쿼리 식은 `From` 절을 사용 하 여 `customers` 컬렉션의 각 `Customer` 개체에 대해 범위 변수 `cust`를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="8ab2c-124">`Where` 절은 범위 변수를 사용 하 여 지정 된 지역의 고객에 대 한 출력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="8ab2c-125">`For Each` 루프는 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="8ab2c-126">예제</span><span class="sxs-lookup"><span data-stu-id="8ab2c-126">Example</span></span>  
 <span data-ttu-id="8ab2c-127">다음 예에서는 `Where` 절에 `And` 및 `Or` 논리 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab2c-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="8ab2c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ab2c-128">See also</span></span>

- [<span data-ttu-id="8ab2c-129">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="8ab2c-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8ab2c-130">쿼리</span><span class="sxs-lookup"><span data-stu-id="8ab2c-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8ab2c-131">From 절</span><span class="sxs-lookup"><span data-stu-id="8ab2c-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8ab2c-132">Select 절</span><span class="sxs-lookup"><span data-stu-id="8ab2c-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8ab2c-133">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="8ab2c-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
