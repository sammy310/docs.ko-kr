---
description: '자세한 정보: UNION (Entity SQL)'
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: f02b3d76d8c21848b7a1b7ef5e7bbf749aea5c0f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673312"
---
# <a name="union-entity-sql"></a><span data-ttu-id="150d2-103">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="150d2-103">UNION (Entity SQL)</span></span>

<span data-ttu-id="150d2-104">두 개 이상의 쿼리 결과를 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-104">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150d2-105">구문</span><span class="sxs-lookup"><span data-stu-id="150d2-105">Syntax</span></span>  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="150d2-106">인수</span><span class="sxs-lookup"><span data-stu-id="150d2-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="150d2-107">컬렉션과 결합할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-107">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="150d2-108">UNION</span><span class="sxs-lookup"><span data-stu-id="150d2-108">UNION</span></span>  
 <span data-ttu-id="150d2-109">여러 컬렉션을 결합하여 하나의 컬렉션으로 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-109">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="150d2-110">ALL</span><span class="sxs-lookup"><span data-stu-id="150d2-110">ALL</span></span>  
 <span data-ttu-id="150d2-111">여러 컬렉션을 결합하여 중복된 값이 포함된 하나의 컬렉션으로 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-111">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="150d2-112">지정하지 않을 경우 중복된 값은 결과 컬렉션에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-112">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="150d2-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="150d2-113">Return Value</span></span>  

 <span data-ttu-id="150d2-114">형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-114">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="150d2-115">설명</span><span class="sxs-lookup"><span data-stu-id="150d2-115">Remarks</span></span>  

 <span data-ttu-id="150d2-116">UNION은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-116">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="150d2-117">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-117">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="150d2-118">집합 연산자의 우선 순위에 대 한 자세한 내용은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [EXCEPT](except-entity-sql.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="150d2-118">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="150d2-119">예제</span><span class="sxs-lookup"><span data-stu-id="150d2-119">Example</span></span>  

 <span data-ttu-id="150d2-120">다음 Entity SQL 쿼리에서는 UNION ALL 연산자를 사용하여 두 쿼리의 결과를 하나의 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-120">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="150d2-121">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="150d2-122">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="150d2-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="150d2-123">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="150d2-124">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="150d2-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a><span data-ttu-id="150d2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="150d2-125">See also</span></span>

- [<span data-ttu-id="150d2-126">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="150d2-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
