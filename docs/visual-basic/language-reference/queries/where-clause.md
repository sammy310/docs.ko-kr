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
ms.openlocfilehash: 3a43554fb25592bf413525a2df109010e4868492
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869635"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="84b6d-102">Where 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b6d-102">Where Clause (Visual Basic)</span></span>

<span data-ttu-id="84b6d-103">쿼리의 필터링 조건을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="84b6d-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="84b6d-105">부분</span><span class="sxs-lookup"><span data-stu-id="84b6d-105">Parts</span></span>  

 `condition`  
 <span data-ttu-id="84b6d-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-106">Required.</span></span> <span data-ttu-id="84b6d-107">컬렉션의 현재 항목에 대 한 값이 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="84b6d-108">식은 값 또는 값에 해당 하는 값으로 계산 되어야 합니다 `Boolean` `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="84b6d-109">조건이로 평가 되 면 `True` 요소가 쿼리 결과에 포함 되 고, 그렇지 않으면 요소가 쿼리 결과에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b6d-110">설명</span><span class="sxs-lookup"><span data-stu-id="84b6d-110">Remarks</span></span>  

 <span data-ttu-id="84b6d-111">`Where`절을 사용 하면 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="84b6d-112">해당 값이 절을 `Where` 평가 하도록 하는 요소 `True` 는 쿼리 결과에 포함 되 고 다른 요소는 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="84b6d-113">절에 사용 되는 식은 `Where` `Boolean` `Boolean` 값이 0 인 경우로 계산 되는 정수와 같이 또는에 해당 하는로 계산 되어야 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="84b6d-114">,,,, `Where` 및와 같은 논리 연산자를 사용 하 여 절에서 여러 식을 조합할 수 있습니다 `And` `Or` `AndAlso` `OrElse` `Is` `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="84b6d-115">기본적으로 쿼리 식은 액세스할 때까지 계산 되지 않습니다. 예를 들어, 데이터 바인딩된 경우 나 루프에서 반복 될 때 쿼리 식은 계산 되지 않습니다 `For` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="84b6d-116">따라서 절은 쿼리를 `Where` 액세스할 때까지 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="84b6d-117">절에 사용 되는 쿼리 외부 값이 있는 경우 `Where` 쿼리 실행 시 절에서 적절 한 값이 사용 되는지 확인 `Where` 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="84b6d-118">쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84b6d-118">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="84b6d-119">절 내에서 함수를 호출 `Where` 하 여 컬렉션의 현재 요소에서 값에 대 한 계산 또는 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="84b6d-120">절에서 함수를 호출 하면 `Where` 쿼리가 액세스 될 때 대신 정의 될 때 쿼리를 즉시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="84b6d-121">쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84b6d-121">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84b6d-122">예제</span><span class="sxs-lookup"><span data-stu-id="84b6d-122">Example</span></span>  

 <span data-ttu-id="84b6d-123">다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션의 각 개체에 대해 범위 변수를 선언 합니다 `Customer` `customers` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="84b6d-124">`Where`절은 범위 변수를 사용 하 여 지정 된 지역의 고객에 대 한 출력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="84b6d-125">`For Each`루프는 쿼리 결과에 있는 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b6d-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="84b6d-126">예제</span><span class="sxs-lookup"><span data-stu-id="84b6d-126">Example</span></span>  

 <span data-ttu-id="84b6d-127">다음 예에서는 `And` `Or` 절에서 및 논리 연산자를 사용 합니다 `Where` .</span><span class="sxs-lookup"><span data-stu-id="84b6d-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="84b6d-128">참조</span><span class="sxs-lookup"><span data-stu-id="84b6d-128">See also</span></span>

- [<span data-ttu-id="84b6d-129">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="84b6d-129">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="84b6d-130">쿼리</span><span class="sxs-lookup"><span data-stu-id="84b6d-130">Queries</span></span>](index.md)
- [<span data-ttu-id="84b6d-131">From 절</span><span class="sxs-lookup"><span data-stu-id="84b6d-131">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="84b6d-132">Select 절</span><span class="sxs-lookup"><span data-stu-id="84b6d-132">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="84b6d-133">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="84b6d-133">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
