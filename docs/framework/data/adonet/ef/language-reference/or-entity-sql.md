---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 89c0a92030f2f067d5e5d45b58d475414a224ce4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150806"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="1ba9e-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1ba9e-102">|| (OR) (Entity SQL)</span></span>

<span data-ttu-id="1ba9e-103">두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ba9e-104">Syntax</span></span>  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ba9e-105">인수</span><span class="sxs-lookup"><span data-stu-id="1ba9e-105">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="1ba9e-106">`Boolean`을 반환하는 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ba9e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ba9e-107">Return Value</span></span>  

 <span data-ttu-id="1ba9e-108">조건 중 하나가`true` 이면 `true`이고 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ba9e-109">설명</span><span class="sxs-lookup"><span data-stu-id="1ba9e-109">Remarks</span></span>  

 <span data-ttu-id="1ba9e-110">OR는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 논리 연산자로</span><span class="sxs-lookup"><span data-stu-id="1ba9e-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="1ba9e-111">두 조건을 결합할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-111">It is used to combine two conditions.</span></span> <span data-ttu-id="1ba9e-112">문에 두 개 이상의 논리 연산자가 사용될 경우 AND 연산자가 먼저 계산된 다음 OR 연산자가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="1ba9e-113">그러나 괄호를 사용하면 계산 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="1ba9e-114">이중 세로 막대 (&#124;&#124;)에는 OR 연산자와 동일한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="1ba9e-115">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="1ba9e-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-116">TRUE</span></span>|<span data-ttu-id="1ba9e-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-117">TRUE</span></span>|<span data-ttu-id="1ba9e-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="1ba9e-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-119">TRUE</span></span>|<span data-ttu-id="1ba9e-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-120">FALSE</span></span>|<span data-ttu-id="1ba9e-121">NULL</span><span class="sxs-lookup"><span data-stu-id="1ba9e-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="1ba9e-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="1ba9e-122">TRUE</span></span>|<span data-ttu-id="1ba9e-123">NULL</span><span class="sxs-lookup"><span data-stu-id="1ba9e-123">NULL</span></span>|<span data-ttu-id="1ba9e-124">NULL</span><span class="sxs-lookup"><span data-stu-id="1ba9e-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ba9e-125">예제</span><span class="sxs-lookup"><span data-stu-id="1ba9e-125">Example</span></span>  

 <span data-ttu-id="1ba9e-126">다음 Entity SQL 쿼리에서는 OR 연산자를 사용하여 두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="1ba9e-127">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1ba9e-128">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1ba9e-129">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1ba9e-130">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba9e-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a><span data-ttu-id="1ba9e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ba9e-131">See also</span></span>

- [<span data-ttu-id="1ba9e-132">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="1ba9e-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
