---
title: '&amp;&amp; 하거나 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198043"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="cb8f2-102">&amp;&amp; 하거나 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cb8f2-102">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="cb8f2-103">두 식이 `true` 이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb8f2-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="cb8f2-105">또는</span><span class="sxs-lookup"><span data-stu-id="cb8f2-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb8f2-106">인수</span><span class="sxs-lookup"><span data-stu-id="cb8f2-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="cb8f2-107">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb8f2-108">설명</span><span class="sxs-lookup"><span data-stu-id="cb8f2-108">Remarks</span></span>  

 <span data-ttu-id="cb8f2-109">이중 앰퍼샌드(&&)는 AND 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="cb8f2-110">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="cb8f2-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-111">TRUE</span></span>|<span data-ttu-id="cb8f2-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-112">FALSE</span></span>|<span data-ttu-id="cb8f2-113">NULL</span><span class="sxs-lookup"><span data-stu-id="cb8f2-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="cb8f2-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-114">FALSE</span></span>|<span data-ttu-id="cb8f2-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-115">FALSE</span></span>|<span data-ttu-id="cb8f2-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="cb8f2-117">NULL</span><span class="sxs-lookup"><span data-stu-id="cb8f2-117">NULL</span></span>|<span data-ttu-id="cb8f2-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="cb8f2-118">FALSE</span></span>|<span data-ttu-id="cb8f2-119">NULL</span><span class="sxs-lookup"><span data-stu-id="cb8f2-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb8f2-120">예제</span><span class="sxs-lookup"><span data-stu-id="cb8f2-120">Example</span></span>  

 <span data-ttu-id="cb8f2-121">다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="cb8f2-122">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cb8f2-123">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cb8f2-124">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cb8f2-125">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f2-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="cb8f2-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb8f2-126">See also</span></span>

- [<span data-ttu-id="cb8f2-127">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cb8f2-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
