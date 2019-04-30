---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 736b92f7aac89c309b37a8ac61a295c8d1495d6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034102"
---
# <a name="union-entity-sql"></a><span data-ttu-id="8e670-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8e670-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="8e670-103">두 개 이상의 쿼리 결과를 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e670-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e670-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e670-105">인수</span><span class="sxs-lookup"><span data-stu-id="8e670-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8e670-106">컬렉션과 결합할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="8e670-107">UNION</span><span class="sxs-lookup"><span data-stu-id="8e670-107">UNION</span></span>  
 <span data-ttu-id="8e670-108">여러 컬렉션을 결합하여 하나의 컬렉션으로 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="8e670-109">ALL</span><span class="sxs-lookup"><span data-stu-id="8e670-109">ALL</span></span>  
 <span data-ttu-id="8e670-110">여러 컬렉션을 결합하여 중복된 값이 포함된 하나의 컬렉션으로 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="8e670-111">지정하지 않을 경우 중복된 값은 결과 컬렉션에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e670-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="8e670-112">Return Value</span></span>  
 <span data-ttu-id="8e670-113">형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e670-114">설명</span><span class="sxs-lookup"><span data-stu-id="8e670-114">Remarks</span></span>  
 <span data-ttu-id="8e670-115">UNION은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="8e670-116">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="8e670-117">우선 순위에 대 한 정보를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자를 참조 하십시오 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e670-118">예제</span><span class="sxs-lookup"><span data-stu-id="8e670-118">Example</span></span>  
 <span data-ttu-id="8e670-119">다음 Entity SQL 쿼리에서는 UNION ALL 연산자를 사용하여 두 쿼리의 결과를 하나의 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="8e670-120">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8e670-121">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="8e670-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8e670-122">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8e670-123">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8e670-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="8e670-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e670-124">See also</span></span>

- [<span data-ttu-id="8e670-125">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="8e670-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
