---
title: 연산자 우선 순위(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175644"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="d71f4-102">연산자 우선 순위(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d71f4-102">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="d71f4-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]쿼리에 여러 개의 연산자가 있는 경우 연산자 우선 순위에 따라 연산이 수행 되는 순서가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="d71f4-104">실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="d71f4-105">다음 표에서는 연산자 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="d71f4-106">높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="d71f4-107">Level</span><span class="sxs-lookup"><span data-stu-id="d71f4-107">Level</span></span>|<span data-ttu-id="d71f4-108">작업 유형</span><span class="sxs-lookup"><span data-stu-id="d71f4-108">Operation type</span></span>|<span data-ttu-id="d71f4-109">연산자</span><span class="sxs-lookup"><span data-stu-id="d71f4-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="d71f4-110">1</span><span class="sxs-lookup"><span data-stu-id="d71f4-110">1</span></span>|<span data-ttu-id="d71f4-111">기본</span><span class="sxs-lookup"><span data-stu-id="d71f4-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="d71f4-112">2</span><span class="sxs-lookup"><span data-stu-id="d71f4-112">2</span></span>|<span data-ttu-id="d71f4-113">단항</span><span class="sxs-lookup"><span data-stu-id="d71f4-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="d71f4-114">3</span><span class="sxs-lookup"><span data-stu-id="d71f4-114">3</span></span>|<span data-ttu-id="d71f4-115">곱하기</span><span class="sxs-lookup"><span data-stu-id="d71f4-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="d71f4-116">4</span><span class="sxs-lookup"><span data-stu-id="d71f4-116">4</span></span>|<span data-ttu-id="d71f4-117">더하기</span><span class="sxs-lookup"><span data-stu-id="d71f4-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="d71f4-118">5</span><span class="sxs-lookup"><span data-stu-id="d71f4-118">5</span></span>|<span data-ttu-id="d71f4-119">순서 지정</span><span class="sxs-lookup"><span data-stu-id="d71f4-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="d71f4-120">6</span><span class="sxs-lookup"><span data-stu-id="d71f4-120">6</span></span>|<span data-ttu-id="d71f4-121">등호</span><span class="sxs-lookup"><span data-stu-id="d71f4-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="d71f4-122">7</span><span class="sxs-lookup"><span data-stu-id="d71f4-122">7</span></span>|<span data-ttu-id="d71f4-123">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="d71f4-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="d71f4-124">8</span><span class="sxs-lookup"><span data-stu-id="d71f4-124">8</span></span>|<span data-ttu-id="d71f4-125">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="d71f4-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="d71f4-126">식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="d71f4-127">예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="d71f4-128">괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="d71f4-129">괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d71f4-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="d71f4-130">예를 들어,은를 `x+y*z` 곱한 `y` 다음를 `z` 추가 `x` 하지만 `(x+y)*z` 는를 `x` 에 추가한 다음 결과를에 `y` 곱합니다 `z` .</span><span class="sxs-lookup"><span data-stu-id="d71f4-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71f4-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d71f4-131">See also</span></span>

- [<span data-ttu-id="d71f4-132">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="d71f4-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
