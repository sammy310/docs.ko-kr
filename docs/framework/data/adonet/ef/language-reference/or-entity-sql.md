---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: c88e041638fbe6f32717ce9c4f9c2ff6fb56d803
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249767"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="7dcfc-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7dcfc-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="7dcfc-103">두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dcfc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7dcfc-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dcfc-105">인수</span><span class="sxs-lookup"><span data-stu-id="7dcfc-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="7dcfc-106">`Boolean`을 반환하는 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dcfc-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7dcfc-107">Return Value</span></span>  
 <span data-ttu-id="7dcfc-108">조건 중 하나가`true` 이면 `true`이고 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dcfc-109">설명</span><span class="sxs-lookup"><span data-stu-id="7dcfc-109">Remarks</span></span>  
 <span data-ttu-id="7dcfc-110">OR는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 논리 연산자로</span><span class="sxs-lookup"><span data-stu-id="7dcfc-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="7dcfc-111">두 조건을 결합할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-111">It is used to combine two conditions.</span></span> <span data-ttu-id="7dcfc-112">한 문에 논리 연산자를 둘 이상 사용하는 경우 OR 연산자가 AND 연산자 다음에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="7dcfc-113">그러나 괄호를 사용하면 계산 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="7dcfc-114">이중 세로 막대 (&#124;&#124;)에는 OR 연산자와 동일한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="7dcfc-115">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="7dcfc-116">true</span><span class="sxs-lookup"><span data-stu-id="7dcfc-116">TRUE</span></span>|<span data-ttu-id="7dcfc-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dcfc-117">TRUE</span></span>|<span data-ttu-id="7dcfc-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dcfc-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="7dcfc-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dcfc-119">TRUE</span></span>|<span data-ttu-id="7dcfc-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="7dcfc-120">FALSE</span></span>|<span data-ttu-id="7dcfc-121">NULL</span><span class="sxs-lookup"><span data-stu-id="7dcfc-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="7dcfc-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dcfc-122">TRUE</span></span>|<span data-ttu-id="7dcfc-123">NULL</span><span class="sxs-lookup"><span data-stu-id="7dcfc-123">NULL</span></span>|<span data-ttu-id="7dcfc-124">NULL</span><span class="sxs-lookup"><span data-stu-id="7dcfc-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dcfc-125">예제</span><span class="sxs-lookup"><span data-stu-id="7dcfc-125">Example</span></span>  
 <span data-ttu-id="7dcfc-126">다음 Entity SQL 쿼리에서는 OR 연산자를 사용하여 두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="7dcfc-127">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7dcfc-128">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7dcfc-129">[방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7dcfc-130">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="7dcfc-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="7dcfc-131">See also</span></span>

- [<span data-ttu-id="7dcfc-132">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7dcfc-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
