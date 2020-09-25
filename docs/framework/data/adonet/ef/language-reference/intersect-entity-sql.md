---
title: INTERSECT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 217cd9b2a428c890d83d2b55d45321a04488398e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203646"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="5f2d1-102">INTERSECT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f2d1-102">INTERSECT (Entity SQL)</span></span>

<span data-ttu-id="5f2d1-103">INTERSECT 피연산자의 왼쪽과 오른쪽에 있는 두 쿼리 식에서 반환된 고유한 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="5f2d1-104">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f2d1-105">Syntax</span></span>  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f2d1-106">인수</span><span class="sxs-lookup"><span data-stu-id="5f2d1-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="5f2d1-107">다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f2d1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5f2d1-108">Return Value</span></span>  

 <span data-ttu-id="5f2d1-109">형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f2d1-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f2d1-110">Remarks</span></span>  

 <span data-ttu-id="5f2d1-111">INTERSECT는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5f2d1-112">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5f2d1-113">집합 연산자의 우선 순위에 대 한 자세한 내용은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [EXCEPT](except-entity-sql.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f2d1-114">예제</span><span class="sxs-lookup"><span data-stu-id="5f2d1-114">Example</span></span>  

 <span data-ttu-id="5f2d1-115">다음 Entity SQL 쿼리에서는 INTERSECT 연산자를 사용하여 INTERSECT 피연산자의 왼쪽과 오른쪽에 있는 두 쿼리 식에서 반환된 고유한 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="5f2d1-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5f2d1-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5f2d1-118">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5f2d1-119">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2d1-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="5f2d1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f2d1-120">See also</span></span>

- [<span data-ttu-id="5f2d1-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="5f2d1-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
