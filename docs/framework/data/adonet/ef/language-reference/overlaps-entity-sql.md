---
title: OVERLAPS(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 9d909fb7efbb29619351cfc866b0f84381d0b80b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319640"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="6e8ab-102">OVERLAPS(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6e8ab-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="6e8ab-103">두 컬렉션에 공통 요소가 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e8ab-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e8ab-105">인수</span><span class="sxs-lookup"><span data-stu-id="6e8ab-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6e8ab-106">다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="6e8ab-107">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e8ab-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6e8ab-108">Return Value</span></span>  
 <span data-ttu-id="6e8ab-109">두 컬렉션에 공통 요소가 있으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e8ab-110">설명</span><span class="sxs-lookup"><span data-stu-id="6e8ab-110">Remarks</span></span>  
 <span data-ttu-id="6e8ab-111">OVERLAPS 제공 기능적으로 다음에 해당을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="6e8ab-112">OVERLAPS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="6e8ab-113">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="6e8ab-114">우선 순위에 대 한 정보를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자를 참조 하십시오 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e8ab-115">예제</span><span class="sxs-lookup"><span data-stu-id="6e8ab-115">Example</span></span>  
 <span data-ttu-id="6e8ab-116">다음 Entity SQL 쿼리에서는 OVERLAPS 연산자를 사용하여 두 컬렉션에 공통 값이 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="6e8ab-117">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6e8ab-118">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="6e8ab-119">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6e8ab-120">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ab-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="6e8ab-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e8ab-121">See also</span></span>

- [<span data-ttu-id="6e8ab-122">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="6e8ab-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
