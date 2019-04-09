---
title: FLATTEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 76fba91f27479df19bbc4ac6e120d615a16f1d42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115117"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="80485-102">FLATTEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80485-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="80485-103">여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="80485-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="80485-104">새 컬렉션에는 기존 컬렉션과 동일한 요소가 모두 포함되지만 중첩 구조는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80485-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80485-105">구문</span><span class="sxs-lookup"><span data-stu-id="80485-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="80485-106">인수</span><span class="sxs-lookup"><span data-stu-id="80485-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="80485-107">하나의 컬렉션으로 결합할 여러 값 컬렉션의 컬렉션을 반환하는 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="80485-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80485-108">설명</span><span class="sxs-lookup"><span data-stu-id="80485-108">Remarks</span></span>  
 `FLATTEN` <span data-ttu-id="80485-109">중 하나인는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80485-109">is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="80485-110">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="80485-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="80485-111">참조 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 에 대 한 우선 순위 정보는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="80485-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80485-112">예제</span><span class="sxs-lookup"><span data-stu-id="80485-112">Example</span></span>  
 <span data-ttu-id="80485-113">다음 Entity SQL 쿼리에서는 `FLATTEN` 연산자를 사용하여 여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="80485-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="80485-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="80485-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="80485-115">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80485-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="80485-116">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="80485-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="80485-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="80485-117">See also</span></span>

- [<span data-ttu-id="80485-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="80485-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
