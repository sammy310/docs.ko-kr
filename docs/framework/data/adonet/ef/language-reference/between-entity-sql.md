---
title: BETWEEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 41036e629837bd5861368df545bed9423eac5b23
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251287"
---
# <a name="between-entity-sql"></a><span data-ttu-id="b2377-102">BETWEEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b2377-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="b2377-103">식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="b2377-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN 식의 기능은 Transact-SQL BETWEEN 식의 기능과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2377-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2377-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="b2377-106">인수</span><span class="sxs-lookup"><span data-stu-id="b2377-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b2377-107">`begin_expression`과 `end_expression`으로 정의된 범위 내에서 테스트할 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="b2377-108">`expression`의 형식은 `begin_expression`과 `end_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="b2377-109">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-109">Any valid expression.</span></span> <span data-ttu-id="b2377-110">`begin_expression`의 형식은 `expression`과 `end_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="b2377-111">`begin_expression`은 `end_expression`보다 작아야 합니다. 그렇지 않으면 반환 값이 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="b2377-112">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-112">Any valid expression.</span></span> <span data-ttu-id="b2377-113">`end_expression`의 형식은 `expression`과 `begin_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="b2377-114">NOT</span><span class="sxs-lookup"><span data-stu-id="b2377-114">NOT</span></span>  
 <span data-ttu-id="b2377-115">BETWEEN의 결과를 무효화하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="b2377-116">AND</span><span class="sxs-lookup"><span data-stu-id="b2377-116">AND</span></span>  
 <span data-ttu-id="b2377-117">`expression`이 `begin_expression`과 `end_expression` 범위 내에 있어야 함을 나타내는 자리 표시자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2377-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2377-118">Return Value</span></span>  
 <span data-ttu-id="b2377-119">`true`이 `expression`과 `begin_expression`이 가리키는 범위에 있으면 `end_expression`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="b2377-120">`null`이 `expression`이거나 `null` 또는 `begin_expression`이 `end_expression`이면 `null`이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2377-121">설명</span><span class="sxs-lookup"><span data-stu-id="b2377-121">Remarks</span></span>  
 <span data-ttu-id="b2377-122">제외 범위를 지정 하려면 보다 큼 (>) 및 보다 작음 (<) 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2377-123">예제</span><span class="sxs-lookup"><span data-stu-id="b2377-123">Example</span></span>  
 <span data-ttu-id="b2377-124">다음 Entity SQL 쿼리에서는 BETWEEN 연산자를 사용하여 식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="b2377-125">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b2377-126">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b2377-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b2377-127">[방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b2377-128">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b2377-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="b2377-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2377-129">See also</span></span>

- [<span data-ttu-id="b2377-130">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="b2377-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
