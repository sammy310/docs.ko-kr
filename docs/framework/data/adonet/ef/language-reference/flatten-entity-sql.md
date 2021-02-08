---
description: '자세한 정보: 평면화 (Entity SQL)'
title: FLATTEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 3701fbdf481024c799b4cdc6f109bae9fc226609
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786357"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="7479e-103">FLATTEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7479e-103">FLATTEN (Entity SQL)</span></span>

<span data-ttu-id="7479e-104">여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-104">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="7479e-105">새 컬렉션에는 기존 컬렉션과 동일한 요소가 모두 포함되지만 중첩 구조는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-105">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7479e-106">구문</span><span class="sxs-lookup"><span data-stu-id="7479e-106">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="7479e-107">인수</span><span class="sxs-lookup"><span data-stu-id="7479e-107">Arguments</span></span>  

 `collection`  
 <span data-ttu-id="7479e-108">하나의 컬렉션으로 결합할 여러 값 컬렉션의 컬렉션을 반환하는 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-108">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7479e-109">설명</span><span class="sxs-lookup"><span data-stu-id="7479e-109">Remarks</span></span>  

 <span data-ttu-id="7479e-110">`FLATTEN` 는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-110">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="7479e-111">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-111">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="7479e-112">집합 연산자의 우선 순위 정보는 [EXCEPT](except-entity-sql.md) 를 참조 하십시오 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7479e-112">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7479e-113">예제</span><span class="sxs-lookup"><span data-stu-id="7479e-113">Example</span></span>  

 <span data-ttu-id="7479e-114">다음 Entity SQL 쿼리에서는 `FLATTEN` 연산자를 사용하여 여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-114">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="7479e-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7479e-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7479e-116">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7479e-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7479e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="7479e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7479e-118">See also</span></span>

- [<span data-ttu-id="7479e-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7479e-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
