---
title: CASE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 58b21d3be8e13a0a2204a4fd6d355f734207c509
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150469"
---
# <a name="case-entity-sql"></a><span data-ttu-id="c9407-102">CASE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c9407-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="c9407-103">`Boolean` 식 집합을 계산하여 결과를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9407-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9407-104">Syntax</span></span>  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9407-105">인수</span><span class="sxs-lookup"><span data-stu-id="c9407-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="c9407-106">여러 WHEN `Boolean_expression` THEN `result_expression` 절을 사용할 수 있음을 나타내는 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="c9407-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="c9407-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="c9407-108">`Boolean_expression` 이 `true`인 경우에 반환되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="c9407-109">`result expression` 은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="c9407-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="c9407-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="c9407-111">`true`인 비교 연산이 없는 경우 반환되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="c9407-112">이 인수가 생략되고 `true`인 비교 연산이 없는 경우 CASE는 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="c9407-113">`else_result_expression` 은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="c9407-114">`else_result_expression` 과 `result_expression` 의 데이터 형식은 동일하거나 암시적으로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="c9407-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="c9407-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="c9407-116">검색된 CASE 형식을 사용할 때 계산되는 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="c9407-117">`Boolean_expression` 은 유효한 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9407-118">Return Value</span><span class="sxs-lookup"><span data-stu-id="c9407-118">Return Value</span></span>  
 <span data-ttu-id="c9407-119">`result_expression` 과 선택적 요소인 `else_result_expression`의 형식 집합에서 우선 순위가 가장 높은 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9407-120">설명</span><span class="sxs-lookup"><span data-stu-id="c9407-120">Remarks</span></span>  
 <span data-ttu-id="c9407-121">대/소문자 식은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Transact-SQL 대/소문자 식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the Transact-SQL case expression.</span></span> <span data-ttu-id="c9407-122">CASE 식을 사용하면 적절한 결과를 생성하는 식을 결정하는 일련의 조건 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="c9407-123">이러한 CASE 식 형식은 하나 이상으로 구성된 일련의 `Boolean` 식에 적용되어 올바른 결과 식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="c9407-124">CASE 함수는 지정된 순서대로 각 WHEN 절에 대해 `Boolean_expression` 을 계산한 다음 `result_expression` 인 첫 번째 `Boolean_expression` 의 `true`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="c9407-125">나머지 식은 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="c9407-126">`Boolean_expression` 인 `true`이 없으면 ELSE 절이 지정된 경우 데이터베이스 엔진에서 `else_result_expression` 을 반환하고 ELSE 절이 지정되지 않은 경우 null 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="c9407-127">CASE 문은 multiset을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9407-128">예제</span><span class="sxs-lookup"><span data-stu-id="c9407-128">Example</span></span>  
 <span data-ttu-id="c9407-129">다음 Entity SQL 쿼리에서는 결과를 결정하기 위해 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="c9407-130">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c9407-131">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c9407-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c9407-132">[방법: PrimitiveType 결과를 반환하는 쿼리 실행의 절차를 따릅니다.](../how-to-execute-a-query-that-returns-primitivetype-results.md)</span><span class="sxs-lookup"><span data-stu-id="c9407-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="c9407-133">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c9407-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="c9407-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9407-134">See also</span></span>

- [<span data-ttu-id="c9407-135">THEN</span><span class="sxs-lookup"><span data-stu-id="c9407-135">THEN</span></span>](then-entity-sql.md)
- [<span data-ttu-id="c9407-136">선택</span><span class="sxs-lookup"><span data-stu-id="c9407-136">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="c9407-137">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c9407-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
