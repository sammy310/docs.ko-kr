---
description: '자세히 알아보기: 겹치기 (Entity SQL)'
title: OVERLAPS(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: dd2f4a0925c57edcc3dd2d1264d00921b092525a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791909"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="404bf-103">OVERLAPS(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="404bf-103">OVERLAPS (Entity SQL)</span></span>

<span data-ttu-id="404bf-104">두 컬렉션에 공통 요소가 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-104">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404bf-105">구문</span><span class="sxs-lookup"><span data-stu-id="404bf-105">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="404bf-106">인수</span><span class="sxs-lookup"><span data-stu-id="404bf-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="404bf-107">다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="404bf-108">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-108">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="404bf-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="404bf-109">Return Value</span></span>  

 <span data-ttu-id="404bf-110">두 컬렉션에 공통 요소가 있으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-110">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="404bf-111">설명</span><span class="sxs-lookup"><span data-stu-id="404bf-111">Remarks</span></span>  

 <span data-ttu-id="404bf-112">겹치기는 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-112">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="404bf-113">OVERLAPS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-113">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="404bf-114">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-114">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="404bf-115">집합 연산자의 우선 순위에 대 한 자세한 내용은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [EXCEPT](except-entity-sql.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="404bf-115">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="404bf-116">예제</span><span class="sxs-lookup"><span data-stu-id="404bf-116">Example</span></span>  

 <span data-ttu-id="404bf-117">다음 Entity SQL 쿼리에서는 OVERLAPS 연산자를 사용하여 두 컬렉션에 공통 값이 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-117">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="404bf-118">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="404bf-119">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="404bf-119">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="404bf-120">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="404bf-121">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="404bf-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="404bf-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="404bf-122">See also</span></span>

- [<span data-ttu-id="404bf-123">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="404bf-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
