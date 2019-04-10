---
title: BETWEEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: eae4387bcd5cbaf381ebf7169b6bc54d60328377
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309305"
---
# <a name="between-entity-sql"></a><span data-ttu-id="e7666-102">BETWEEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7666-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="e7666-103">식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e7666-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN 식의 기능은 Transact-SQL BETWEEN 식의 기능과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7666-105">구문</span><span class="sxs-lookup"><span data-stu-id="e7666-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="e7666-106">인수</span><span class="sxs-lookup"><span data-stu-id="e7666-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e7666-107">`begin_expression`과 `end_expression`으로 정의된 범위 내에서 테스트할 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> `expression` <span data-ttu-id="e7666-108">두 가지 모두 동일한 형식 이어야 합니다 `begin_expression` 고 `end_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-108">must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="e7666-109">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-109">Any valid expression.</span></span> `begin_expression` <span data-ttu-id="e7666-110">두 가지 모두 동일한 형식 이어야 합니다 `expression` 고 `end_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-110">must be the same type as both `expression` and `end_expression`.</span></span> `begin_expression` <span data-ttu-id="e7666-111">해야 미만 `end_expression`, 그렇지 않으면 반환 값이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-111">should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="e7666-112">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-112">Any valid expression.</span></span> `end_expression` <span data-ttu-id="e7666-113">두 가지 모두 동일한 형식 이어야 합니다 `expression` 고 `begin_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-113">must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="e7666-114">NOT</span><span class="sxs-lookup"><span data-stu-id="e7666-114">NOT</span></span>  
 <span data-ttu-id="e7666-115">BETWEEN의 결과를 무효화하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="e7666-116">AND</span><span class="sxs-lookup"><span data-stu-id="e7666-116">AND</span></span>  
 <span data-ttu-id="e7666-117">`expression`이 `begin_expression`과 `end_expression` 범위 내에 있어야 함을 나타내는 자리 표시자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7666-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="e7666-118">Return Value</span></span>  
 `true` <span data-ttu-id="e7666-119">하는 경우 `expression` 범위 사이 `begin_expression` 하 고 `end_expression`이 고, 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-119">if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> `null` <span data-ttu-id="e7666-120">경우에 반환 됩니다 `expression` 됩니다 `null` 이거나 `begin_expression` 또는 `end_expression` 는 `null`.</span><span class="sxs-lookup"><span data-stu-id="e7666-120">will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7666-121">설명</span><span class="sxs-lookup"><span data-stu-id="e7666-121">Remarks</span></span>  
 <span data-ttu-id="e7666-122">배타적 범위를 지정 하려면 BETWEEN 대신 보다 큼 (>) 및 미만 (<) 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7666-123">예제</span><span class="sxs-lookup"><span data-stu-id="e7666-123">Example</span></span>  
 <span data-ttu-id="e7666-124">다음 Entity SQL 쿼리에서는 BETWEEN 연산자를 사용하여 식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e7666-125">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e7666-126">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e7666-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e7666-127">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e7666-128">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e7666-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="e7666-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7666-129">See also</span></span>

- [<span data-ttu-id="e7666-130">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e7666-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
