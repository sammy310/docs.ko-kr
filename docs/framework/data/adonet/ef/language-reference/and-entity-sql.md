---
description: '자세히 알아보기: &amp; &amp; (및) (Entity SQL)'
title: '&amp;&amp; 하거나 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 14fc6bc3f58ac78cb9806a7f421db87bbad048ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697181"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="00ade-103">&amp;&amp; 하거나 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="00ade-103">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="00ade-104">두 식이 `true` 이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-104">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ade-105">구문</span><span class="sxs-lookup"><span data-stu-id="00ade-105">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="00ade-106">또는</span><span class="sxs-lookup"><span data-stu-id="00ade-106">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="00ade-107">인수</span><span class="sxs-lookup"><span data-stu-id="00ade-107">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="00ade-108">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00ade-109">설명</span><span class="sxs-lookup"><span data-stu-id="00ade-109">Remarks</span></span>  

 <span data-ttu-id="00ade-110">이중 앰퍼샌드(&&)는 AND 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-110">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="00ade-111">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-111">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="00ade-112">TRUE</span><span class="sxs-lookup"><span data-stu-id="00ade-112">TRUE</span></span>|<span data-ttu-id="00ade-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="00ade-113">FALSE</span></span>|<span data-ttu-id="00ade-114">NULL</span><span class="sxs-lookup"><span data-stu-id="00ade-114">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="00ade-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="00ade-115">FALSE</span></span>|<span data-ttu-id="00ade-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="00ade-116">FALSE</span></span>|<span data-ttu-id="00ade-117">FALSE</span><span class="sxs-lookup"><span data-stu-id="00ade-117">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="00ade-118">NULL</span><span class="sxs-lookup"><span data-stu-id="00ade-118">NULL</span></span>|<span data-ttu-id="00ade-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="00ade-119">FALSE</span></span>|<span data-ttu-id="00ade-120">NULL</span><span class="sxs-lookup"><span data-stu-id="00ade-120">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00ade-121">예제</span><span class="sxs-lookup"><span data-stu-id="00ade-121">Example</span></span>  

 <span data-ttu-id="00ade-122">다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-122">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="00ade-123">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="00ade-124">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="00ade-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="00ade-125">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="00ade-126">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="00ade-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="00ade-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00ade-127">See also</span></span>

- [<span data-ttu-id="00ade-128">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="00ade-128">Entity SQL Reference</span></span>](entity-sql-reference.md)
