---
title: 연산자 우선 순위(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 2d8c78f410708fd1aa843ee8f14f7243a9f686c0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249778"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="c7c10-102">연산자 우선 순위(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c7c10-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="c7c10-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 여러 개의 연산자가 있는 경우 연산자 우선 순위에 따라 연산이 수행 되는 순서가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="c7c10-104">실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="c7c10-105">다음 표에서는 연산자 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="c7c10-106">높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="c7c10-107">Level</span><span class="sxs-lookup"><span data-stu-id="c7c10-107">Level</span></span>|<span data-ttu-id="c7c10-108">연산 유형</span><span class="sxs-lookup"><span data-stu-id="c7c10-108">Operation type</span></span>|<span data-ttu-id="c7c10-109">연산자</span><span class="sxs-lookup"><span data-stu-id="c7c10-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="c7c10-110">1</span><span class="sxs-lookup"><span data-stu-id="c7c10-110">1</span></span>|<span data-ttu-id="c7c10-111">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="c7c10-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="c7c10-112">2</span><span class="sxs-lookup"><span data-stu-id="c7c10-112">2</span></span>|<span data-ttu-id="c7c10-113">단항</span><span class="sxs-lookup"><span data-stu-id="c7c10-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="c7c10-114">3</span><span class="sxs-lookup"><span data-stu-id="c7c10-114">3</span></span>|<span data-ttu-id="c7c10-115">곱하기</span><span class="sxs-lookup"><span data-stu-id="c7c10-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="c7c10-116">4</span><span class="sxs-lookup"><span data-stu-id="c7c10-116">4</span></span>|<span data-ttu-id="c7c10-117">더하기</span><span class="sxs-lookup"><span data-stu-id="c7c10-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="c7c10-118">5</span><span class="sxs-lookup"><span data-stu-id="c7c10-118">5</span></span>|<span data-ttu-id="c7c10-119">순서 지정</span><span class="sxs-lookup"><span data-stu-id="c7c10-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="c7c10-120">6</span><span class="sxs-lookup"><span data-stu-id="c7c10-120">6</span></span>|<span data-ttu-id="c7c10-121">같음</span><span class="sxs-lookup"><span data-stu-id="c7c10-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="c7c10-122">7</span><span class="sxs-lookup"><span data-stu-id="c7c10-122">7</span></span>|<span data-ttu-id="c7c10-123">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="c7c10-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="c7c10-124">8</span><span class="sxs-lookup"><span data-stu-id="c7c10-124">8</span></span>|<span data-ttu-id="c7c10-125">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="c7c10-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="c7c10-126">식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="c7c10-127">예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="c7c10-128">괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="c7c10-129">괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="c7c10-130">예를 들어 `x+y*z` , `y` 은 `z` 를 곱한 다음 `x`를 추가 `(x+y)*z` 하지만 `x` 는 `y` 를에 추가한 다음 결과 `z`를에 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c10-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c10-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="c7c10-131">See also</span></span>

- [<span data-ttu-id="c7c10-132">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="c7c10-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
