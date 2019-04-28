---
title: '! (NOT)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 51d3bdbc4adb0b5fd6275629219698dd9b42fa86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760379"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="a16a4-103">!</span><span class="sxs-lookup"><span data-stu-id="a16a4-103">!</span></span> <span data-ttu-id="a16a4-104">(NOT)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a16a4-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="a16a4-105">`Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16a4-106">구문</span><span class="sxs-lookup"><span data-stu-id="a16a4-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a16a4-107">인수</span><span class="sxs-lookup"><span data-stu-id="a16a4-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="a16a4-108">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a16a4-109">설명</span><span class="sxs-lookup"><span data-stu-id="a16a4-109">Remarks</span></span>  
 <span data-ttu-id="a16a4-110">느낌표(!)는 NOT 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a16a4-111">예제</span><span class="sxs-lookup"><span data-stu-id="a16a4-111">Example</span></span>  
 <span data-ttu-id="a16a4-112">다음 Entity SQL 쿼리에서는 NOT 연산자를 사용하여 `Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="a16a4-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a16a4-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="a16a4-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a16a4-115">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a16a4-116">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a16a4-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="a16a4-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="a16a4-117">See also</span></span>

- [<span data-ttu-id="a16a4-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a16a4-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
