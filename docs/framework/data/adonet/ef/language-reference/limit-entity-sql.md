---
description: '자세히 알아보기: LIMIT (Entity SQL)'
title: LIMIT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 873f3fd5ed83d04313aff92bf1f97e07001c3f08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748208"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="8a38e-103">LIMIT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8a38e-103">LIMIT (Entity SQL)</span></span>

<span data-ttu-id="8a38e-104">ORDER BY 절에서 LIIMIT 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-104">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="8a38e-105">LIMIT 절은 ORDER BY 절과 별도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-105">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a38e-106">구문</span><span class="sxs-lookup"><span data-stu-id="8a38e-106">Syntax</span></span>  
  
```sql  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a38e-107">인수</span><span class="sxs-lookup"><span data-stu-id="8a38e-107">Arguments</span></span>  

 `n`  
 <span data-ttu-id="8a38e-108">선택할 항목의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-108">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="8a38e-109">LIMIT 식 하위 절이 ORDER BY 절에 있으면 쿼리는 정렬 지정에 따라 정렬되고 결과 행의 수는 LIMIT 식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-109">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="8a38e-110">예를 들어, LIMIT 5는 결과 집합을 다섯 개의 인스턴스 또는 행으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-110">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="8a38e-111">LIMIT는 ORDER BY 절이 반드시 있어야 한다는 점을 제외하고는 TOP와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-111">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="8a38e-112">SKIP 및 LIMIT 절은 각각 ORDER BY 절과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-112">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a38e-113">TOP 한정자와 SKIP 하위 절이 모두 같은 쿼리 식에 있는 경우 Entity SQL 쿼리는 유효하지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-113">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="8a38e-114">TOP 식을 변경하여 쿼리를 LIMIT 식에 다시 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-114">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a38e-115">예제</span><span class="sxs-lookup"><span data-stu-id="8a38e-115">Example</span></span>  

 <span data-ttu-id="8a38e-116">다음 Entity SQL 쿼리는 LIMIT와 함께 ORDER BY 연산자를 사용하여 SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-116">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="8a38e-117">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8a38e-118">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="8a38e-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8a38e-119">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8a38e-120">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8a38e-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIMIT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="8a38e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a38e-121">See also</span></span>

- [<span data-ttu-id="8a38e-122">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="8a38e-122">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="8a38e-123">[방법: 쿼리 결과를 통해 페이징](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8a38e-123">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="8a38e-124">페이징</span><span class="sxs-lookup"><span data-stu-id="8a38e-124">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="8a38e-125">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="8a38e-125">TOP</span></span>](top-entity-sql.md)
