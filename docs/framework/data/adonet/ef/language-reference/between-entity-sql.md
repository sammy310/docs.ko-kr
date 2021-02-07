---
description: '다음에 대 한 자세한 정보: BETWEEN (Entity SQL)'
title: BETWEEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 35ac16e94f2e55f6a0f76591daf0f91f9708aa53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697116"
---
# <a name="between-entity-sql"></a><span data-ttu-id="e2c46-103">BETWEEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2c46-103">BETWEEN (Entity SQL)</span></span>

<span data-ttu-id="e2c46-104">식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-104">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e2c46-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN 식의 기능은 Transact-SQL BETWEEN 식의 기능과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-105">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c46-106">구문</span><span class="sxs-lookup"><span data-stu-id="e2c46-106">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a><span data-ttu-id="e2c46-107">인수</span><span class="sxs-lookup"><span data-stu-id="e2c46-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="e2c46-108">`begin_expression`과 `end_expression`으로 정의된 범위 내에서 테스트할 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-108">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="e2c46-109">`expression`의 형식은 `begin_expression`과 `end_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-109">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="e2c46-110">유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-110">Any valid expression.</span></span> <span data-ttu-id="e2c46-111">`begin_expression`의 형식은 `expression`과 `end_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-111">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="e2c46-112">`begin_expression`은 `end_expression`보다 작아야 합니다. 그렇지 않으면 반환 값이 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-112">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="e2c46-113">유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-113">Any valid expression.</span></span> <span data-ttu-id="e2c46-114">`end_expression`의 형식은 `expression`과 `begin_expression` 두 가지 모두의 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-114">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="e2c46-115">NOT</span><span class="sxs-lookup"><span data-stu-id="e2c46-115">NOT</span></span>  
 <span data-ttu-id="e2c46-116">BETWEEN의 결과를 무효화하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-116">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="e2c46-117">AND</span><span class="sxs-lookup"><span data-stu-id="e2c46-117">AND</span></span>  
 <span data-ttu-id="e2c46-118">`expression`이 `begin_expression`과 `end_expression` 범위 내에 있어야 함을 나타내는 자리 표시자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-118">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2c46-119">Return Value</span><span class="sxs-lookup"><span data-stu-id="e2c46-119">Return Value</span></span>  

 <span data-ttu-id="e2c46-120">`true`이 `expression`과 `begin_expression`이 가리키는 범위에 있으면 `end_expression`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-120">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="e2c46-121">`null`이 `expression`이거나 `null` 또는 `begin_expression`이 `end_expression`이면 `null`이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-121">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2c46-122">설명</span><span class="sxs-lookup"><span data-stu-id="e2c46-122">Remarks</span></span>  

 <span data-ttu-id="e2c46-123">제외 범위를 지정 하려면 보다 큼 (>) 및 보다 작음 (<) 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-123">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2c46-124">예제</span><span class="sxs-lookup"><span data-stu-id="e2c46-124">Example</span></span>  

 <span data-ttu-id="e2c46-125">다음 Entity SQL 쿼리에서는 BETWEEN 연산자를 사용하여 식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-125">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e2c46-126">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-126">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e2c46-127">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e2c46-127">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e2c46-128">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-128">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e2c46-129">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c46-129">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="e2c46-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2c46-130">See also</span></span>

- [<span data-ttu-id="e2c46-131">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e2c46-131">Entity SQL Reference</span></span>](entity-sql-reference.md)
