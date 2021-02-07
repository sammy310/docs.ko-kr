---
description: 자세히 알아보세요. (NOT)(Entity SQL)
title: '! (NOT)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 648cc4ff73769ae280570b2d42934b2001fa5182
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696453"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="e1856-105">!</span><span class="sxs-lookup"><span data-stu-id="e1856-105">!</span></span> <span data-ttu-id="e1856-106">(NOT)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e1856-106">(NOT) (Entity SQL)</span></span>

<span data-ttu-id="e1856-107">`Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-107">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1856-108">구문</span><span class="sxs-lookup"><span data-stu-id="e1856-108">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="e1856-109">인수</span><span class="sxs-lookup"><span data-stu-id="e1856-109">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="e1856-110">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-110">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1856-111">설명</span><span class="sxs-lookup"><span data-stu-id="e1856-111">Remarks</span></span>  

 <span data-ttu-id="e1856-112">느낌표(!)는 NOT 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-112">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1856-113">예제</span><span class="sxs-lookup"><span data-stu-id="e1856-113">Example</span></span>  

 <span data-ttu-id="e1856-114">다음 Entity SQL 쿼리에서는 NOT 연산자를 사용하여 `Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-114">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="e1856-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e1856-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e1856-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e1856-117">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e1856-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e1856-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="e1856-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1856-119">See also</span></span>

- [<span data-ttu-id="e1856-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e1856-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
