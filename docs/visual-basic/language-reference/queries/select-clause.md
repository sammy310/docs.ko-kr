---
description: '자세한 정보: Select 절 (Visual Basic)'
title: Select 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 029778ce8262a93eee9a69843579523e8434eb01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653578"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="cd48c-103">Select 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd48c-103">Select Clause (Visual Basic)</span></span>

<span data-ttu-id="cd48c-104">쿼리 결과를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-104">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd48c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd48c-105">Syntax</span></span>  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="cd48c-106">부분</span><span class="sxs-lookup"><span data-stu-id="cd48c-106">Parts</span></span>  

 `var1`  
 <span data-ttu-id="cd48c-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-107">Optional.</span></span> <span data-ttu-id="cd48c-108">열 식의 결과를 참조 하는 데 사용할 수 있는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-108">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="cd48c-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-109">Required.</span></span> <span data-ttu-id="cd48c-110">쿼리 결과에 반환할 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-110">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd48c-111">설명</span><span class="sxs-lookup"><span data-stu-id="cd48c-111">Remarks</span></span>  

 <span data-ttu-id="cd48c-112">절을 사용 `Select` 하 여 쿼리에서 반환 되는 결과를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-112">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="cd48c-113">이렇게 하면 쿼리로 생성 된 새 익명 형식의 멤버를 정의 하거나 쿼리에서 반환 되는 명명 된 형식의 멤버를 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-113">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="cd48c-114">`Select`쿼리에는 절이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-114">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="cd48c-115">절을 `Select` 지정 하지 않으면 쿼리는 현재 범위에 대해 식별 된 범위 변수의 모든 멤버를 기반으로 하는 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-115">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="cd48c-116">자세한 내용은 [무명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd48c-116">For more information, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="cd48c-117">쿼리에서 명명 된 형식을 만들면 형식의 결과가 반환 됩니다 <xref:System.Collections.Generic.IEnumerable%601> `T` . 여기서는 생성 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-117">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="cd48c-118">`Select`절은 현재 범위에 있는 모든 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-118">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="cd48c-119">여기에는 절 또는 절에서 식별 된 범위 변수가 포함 됩니다 `From` `From` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-119">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="cd48c-120">또한,, 또는 절을 사용 하 여 별칭으로 만든 새 변수 `Aggregate` `Let` `Group By` `Group Join` 또는 `Select` 쿼리 식에 있는 이전 절의 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-120">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="cd48c-121">절에는 `Select` 정적 값이 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-121">The `Select` clause can also include static values.</span></span> <span data-ttu-id="cd48c-122">예를 들어 다음 코드 예제에서는 `Select` 절이 쿼리 결과를 4 개의 멤버 `ProductName` ,, `Price` `Discount` 및로 정의 하는 새 무명 형식으로 정의 하는 쿼리 식을 보여 `DiscountedPrice` 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-122">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="cd48c-123">`ProductName`및 `Price` 멤버 값은 절에 정의 된 product range 변수에서 가져옵니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-123">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="cd48c-124">`DiscountedPrice`멤버 값은 절에서 계산 됩니다 `Let` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-124">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="cd48c-125">`Discount`멤버가 정적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-125">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 <span data-ttu-id="cd48c-126">`Select`절은 후속 쿼리 절에 대해 새로운 범위 변수 집합을 도입 하 고 이전 범위 변수는 더 이상 범위에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-126">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="cd48c-127">`Select`쿼리 식의 마지막 절은 쿼리의 반환 값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-127">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="cd48c-128">예를 들어 다음 쿼리는 합계가 500를 초과 하는 모든 고객 주문에 대 한 회사 이름 및 주문 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-128">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="cd48c-129">첫 번째 `Select` 절은 `Where` 절과 두 번째 절에 대 한 범위 변수를 식별 합니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-129">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="cd48c-130">두 번째 `Select` 절은 쿼리에서 반환 되는 값을 새 익명 형식으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-130">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 <span data-ttu-id="cd48c-131">절이 `Select` 반환할 단일 항목을 식별 하는 경우 쿼리 식은 해당 단일 항목 형식의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-131">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="cd48c-132">절이 `Select` 반환할 여러 항목을 식별 하는 경우 쿼리 식은 선택한 항목을 기반으로 새 익명 형식의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-132">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="cd48c-133">예를 들어 다음 두 쿼리는 절을 기반으로 서로 다른 두 형식의 컬렉션을 반환 합니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-133">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="cd48c-134">첫 번째 쿼리는 회사 이름 컬렉션을 문자열로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-134">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="cd48c-135">두 번째 쿼리는 `Customer` 회사 이름 및 주소 정보로 채워진 개체의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-135">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="cd48c-136">예제</span><span class="sxs-lookup"><span data-stu-id="cd48c-136">Example</span></span>  

 <span data-ttu-id="cd48c-137">다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션에 대 한 범위 변수를 선언 합니다 `customers` .</span><span class="sxs-lookup"><span data-stu-id="cd48c-137">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="cd48c-138">`Select`절은 고객 이름 및 ID 값을 선택 하 고 `CompanyName` `CustomerID` 새 범위 변수의 및 열을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-138">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="cd48c-139">`For Each`문은 반환 된 각 개체를 반복 하 고 `CompanyName` `CustomerID` 각 레코드의 및 열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd48c-139">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="cd48c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd48c-140">See also</span></span>

- [<span data-ttu-id="cd48c-141">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="cd48c-141">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="cd48c-142">쿼리</span><span class="sxs-lookup"><span data-stu-id="cd48c-142">Queries</span></span>](index.md)
- [<span data-ttu-id="cd48c-143">From 절</span><span class="sxs-lookup"><span data-stu-id="cd48c-143">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="cd48c-144">Where 절</span><span class="sxs-lookup"><span data-stu-id="cd48c-144">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="cd48c-145">Order By 절</span><span class="sxs-lookup"><span data-stu-id="cd48c-145">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="cd48c-146">익명 형식</span><span class="sxs-lookup"><span data-stu-id="cd48c-146">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
