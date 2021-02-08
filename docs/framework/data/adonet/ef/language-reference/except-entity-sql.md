---
description: '자세히 알아보기: EXCEPT (Entity SQL)'
title: EXCEPT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: fd66d8dc6e22a73afbfd27e6eb1fd6c8bb9d3475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786396"
---
# <a name="except-entity-sql"></a><span data-ttu-id="5beb7-103">EXCEPT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5beb7-103">EXCEPT (Entity SQL)</span></span>

<span data-ttu-id="5beb7-104">EXCEPT 피연산자 오른쪽 쿼리 식에서 반환되지 않은 모든 고유한 값 컬렉션을 EXCEPT 피연산자 왼쪽에 있는 쿼리 식에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-104">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="5beb7-105">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-105">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5beb7-106">구문</span><span class="sxs-lookup"><span data-stu-id="5beb7-106">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5beb7-107">인수</span><span class="sxs-lookup"><span data-stu-id="5beb7-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="5beb7-108">다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-108">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5beb7-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5beb7-109">Return Value</span></span>  

 <span data-ttu-id="5beb7-110">형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-110">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5beb7-111">설명</span><span class="sxs-lookup"><span data-stu-id="5beb7-111">Remarks</span></span>  

 <span data-ttu-id="5beb7-112">EXCEPT는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-112">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5beb7-113">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5beb7-114">다음 표에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-114">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="5beb7-115">우선 순위</span><span class="sxs-lookup"><span data-stu-id="5beb7-115">Precedence</span></span>|<span data-ttu-id="5beb7-116">연산자</span><span class="sxs-lookup"><span data-stu-id="5beb7-116">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="5beb7-117">가장 높음</span><span class="sxs-lookup"><span data-stu-id="5beb7-117">Highest</span></span>|<span data-ttu-id="5beb7-118">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="5beb7-118">INTERSECT</span></span>|  
||<span data-ttu-id="5beb7-119">UNION</span><span class="sxs-lookup"><span data-stu-id="5beb7-119">UNION</span></span><br /><br /> <span data-ttu-id="5beb7-120">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="5beb7-120">UNION ALL</span></span>|  
||<span data-ttu-id="5beb7-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="5beb7-121">EXCEPT</span></span>|  
|<span data-ttu-id="5beb7-122">가장 낮음</span><span class="sxs-lookup"><span data-stu-id="5beb7-122">Lowest</span></span>|<span data-ttu-id="5beb7-123">EXISTS</span><span class="sxs-lookup"><span data-stu-id="5beb7-123">EXISTS</span></span><br /><br /> <span data-ttu-id="5beb7-124">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="5beb7-124">OVERLAPS</span></span><br /><br /> <span data-ttu-id="5beb7-125">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="5beb7-125">FLATTEN</span></span><br /><br /> <span data-ttu-id="5beb7-126">SET</span><span class="sxs-lookup"><span data-stu-id="5beb7-126">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5beb7-127">예제</span><span class="sxs-lookup"><span data-stu-id="5beb7-127">Example</span></span>  

 <span data-ttu-id="5beb7-128">다음 Entity SQL 쿼리에서는 EXCEPT 연산자를 사용하여 두 쿼리 식에서 모든 고유한 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-128">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="5beb7-129">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5beb7-130">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="5beb7-130">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5beb7-131">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5beb7-132">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5beb7-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="5beb7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5beb7-133">See also</span></span>

- [<span data-ttu-id="5beb7-134">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="5beb7-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
