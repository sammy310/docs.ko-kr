---
title: SET(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319350"
---
# <a name="set-entity-sql"></a><span data-ttu-id="96020-102">SET(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="96020-102">SET (Entity SQL)</span></span>
<span data-ttu-id="96020-103">SET 식은 중복 요소가 모두 제거된 새 컬렉션을 생성하여 개체 컬렉션을 집합으로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96020-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96020-104">구문</span><span class="sxs-lookup"><span data-stu-id="96020-104">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="96020-105">인수</span><span class="sxs-lookup"><span data-stu-id="96020-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="96020-106">컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="96020-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96020-107">주의</span><span class="sxs-lookup"><span data-stu-id="96020-107">Remarks</span></span>  
 <span data-ttu-id="96020-108">집합 식 `SET(c)` 는 다음 select 문과 논리적으로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96020-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="96020-109">`SET` 는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="96020-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="96020-110">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="96020-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="96020-111">@No__t_1 집합 연산자의 우선 순위 정보는 [예외](except-entity-sql.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96020-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96020-112">예제</span><span class="sxs-lookup"><span data-stu-id="96020-112">Example</span></span>  
 <span data-ttu-id="96020-113">다음 Entity SQL 쿼리에서는 SET 식을 사용하여 개체의 컬렉션을 집합으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96020-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="96020-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96020-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="96020-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="96020-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="96020-116">[방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="96020-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="96020-117">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96020-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="96020-118">참조</span><span class="sxs-lookup"><span data-stu-id="96020-118">See also</span></span>

- [<span data-ttu-id="96020-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="96020-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
