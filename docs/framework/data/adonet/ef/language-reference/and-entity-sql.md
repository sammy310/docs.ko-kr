---
title: '&amp;&amp;하거나 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 02e404b73e5a9a9c3963e2d2b58ab7592afabc13
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251311"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="7d732-102">&amp;&amp;하거나 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7d732-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="7d732-103">두 식이 `true` 이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d732-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d732-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d732-105">인수</span><span class="sxs-lookup"><span data-stu-id="7d732-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="7d732-106">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d732-107">설명</span><span class="sxs-lookup"><span data-stu-id="7d732-107">Remarks</span></span>  
 <span data-ttu-id="7d732-108">이중 앰퍼샌드(&&)는 AND 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="7d732-109">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="7d732-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="7d732-110">TRUE</span></span>|<span data-ttu-id="7d732-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="7d732-111">FALSE</span></span>|<span data-ttu-id="7d732-112">NULL</span><span class="sxs-lookup"><span data-stu-id="7d732-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="7d732-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="7d732-113">FALSE</span></span>|<span data-ttu-id="7d732-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="7d732-114">FALSE</span></span>|<span data-ttu-id="7d732-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="7d732-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="7d732-116">NULL</span><span class="sxs-lookup"><span data-stu-id="7d732-116">NULL</span></span>|<span data-ttu-id="7d732-117">false</span><span class="sxs-lookup"><span data-stu-id="7d732-117">FALSE</span></span>|<span data-ttu-id="7d732-118">NULL</span><span class="sxs-lookup"><span data-stu-id="7d732-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d732-119">예제</span><span class="sxs-lookup"><span data-stu-id="7d732-119">Example</span></span>  
 <span data-ttu-id="7d732-120">다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="7d732-121">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7d732-122">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7d732-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7d732-123">[방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7d732-124">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7d732-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="7d732-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d732-125">See also</span></span>

- [<span data-ttu-id="7d732-126">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7d732-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
