---
title: EXCEPT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 32b5148e43a38e5cf8dcce0ae16260d7a6b6a018
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341220"
---
# <a name="except-entity-sql"></a><span data-ttu-id="a9583-102">EXCEPT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a9583-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="a9583-103">EXCEPT 피연산자 오른쪽 쿼리 식에서 반환되지 않은 모든 고유한 값 컬렉션을 EXCEPT 피연산자 왼쪽에 있는 쿼리 식에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="a9583-104">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9583-105">구문</span><span class="sxs-lookup"><span data-stu-id="a9583-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9583-106">인수</span><span class="sxs-lookup"><span data-stu-id="a9583-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a9583-107">다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9583-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a9583-108">Return Value</span></span>  
 <span data-ttu-id="a9583-109">형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9583-110">설명</span><span class="sxs-lookup"><span data-stu-id="a9583-110">Remarks</span></span>  
 <span data-ttu-id="a9583-111">EXCEPT는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="a9583-112">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="a9583-113">다음 표에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="a9583-114">우선 순위</span><span class="sxs-lookup"><span data-stu-id="a9583-114">Precedence</span></span>|<span data-ttu-id="a9583-115">연산자</span><span class="sxs-lookup"><span data-stu-id="a9583-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="a9583-116">가장 높음</span><span class="sxs-lookup"><span data-stu-id="a9583-116">Highest</span></span>|<span data-ttu-id="a9583-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="a9583-117">INTERSECT</span></span>|  
||<span data-ttu-id="a9583-118">UNION</span><span class="sxs-lookup"><span data-stu-id="a9583-118">UNION</span></span><br /><br /> <span data-ttu-id="a9583-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="a9583-119">UNION ALL</span></span>|  
||<span data-ttu-id="a9583-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="a9583-120">EXCEPT</span></span>|  
|<span data-ttu-id="a9583-121">가장 낮음</span><span class="sxs-lookup"><span data-stu-id="a9583-121">Lowest</span></span>|<span data-ttu-id="a9583-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="a9583-122">EXISTS</span></span><br /><br /> <span data-ttu-id="a9583-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="a9583-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="a9583-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="a9583-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="a9583-125">SET</span><span class="sxs-lookup"><span data-stu-id="a9583-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9583-126">예제</span><span class="sxs-lookup"><span data-stu-id="a9583-126">Example</span></span>  
 <span data-ttu-id="a9583-127">다음 Entity SQL 쿼리에서는 EXCEPT 연산자를 사용하여 두 쿼리 식에서 모든 고유한 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="a9583-128">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a9583-129">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="a9583-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a9583-130">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a9583-131">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a9583-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="a9583-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9583-132">See also</span></span>

- [<span data-ttu-id="a9583-133">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a9583-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
