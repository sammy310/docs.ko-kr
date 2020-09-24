---
title: THEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: f038f242bc0873df3d72700aa05fca2f76f777ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161674"
---
# <a name="then-entity-sql"></a><span data-ttu-id="96741-102">THEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="96741-102">THEN (Entity SQL)</span></span>

<span data-ttu-id="96741-103">WHEN 절이 `true`로 계산될 때의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="96741-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96741-104">구문</span><span class="sxs-lookup"><span data-stu-id="96741-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="96741-105">인수</span><span class="sxs-lookup"><span data-stu-id="96741-105">Arguments</span></span>  

 `when_expression`  
 <span data-ttu-id="96741-106">모든 유효한 부울 식입니다.</span><span class="sxs-lookup"><span data-stu-id="96741-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="96741-107">컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="96741-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96741-108">설명</span><span class="sxs-lookup"><span data-stu-id="96741-108">Remarks</span></span>  

 <span data-ttu-id="96741-109">`when_expression` 이 `true`값으로 계산되면 결과는 해당 `then-expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="96741-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="96741-110">만족되는 WHEN 조건이 없으면 `else-expression` 이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="96741-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="96741-111">하지만 `else-expression`이 없으면 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="96741-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="96741-112">예제는 [CASE](case-entity-sql.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96741-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96741-113">예제</span><span class="sxs-lookup"><span data-stu-id="96741-113">Example</span></span>  

 <span data-ttu-id="96741-114">다음 Entity SQL 쿼리에서는 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="96741-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="96741-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96741-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="96741-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="96741-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="96741-117">[방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="96741-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="96741-118">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96741-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="96741-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96741-119">See also</span></span>

- [<span data-ttu-id="96741-120">CASE</span><span class="sxs-lookup"><span data-stu-id="96741-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="96741-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="96741-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
