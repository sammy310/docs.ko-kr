---
description: '자세한 정보: 연산자 우선 순위 (Entity SQL)'
title: 연산자 우선 순위(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 72cfdecf7dfe4ce590d99e866429e771f9ede231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739328"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="8a544-103">연산자 우선 순위(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8a544-103">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="8a544-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]쿼리에 여러 개의 연산자가 있는 경우 연산자 우선 순위에 따라 연산이 수행 되는 순서가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-104">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="8a544-105">실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-105">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="8a544-106">다음 표에서는 연산자 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-106">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="8a544-107">높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-107">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="8a544-108">Level</span><span class="sxs-lookup"><span data-stu-id="8a544-108">Level</span></span>|<span data-ttu-id="8a544-109">작업 유형</span><span class="sxs-lookup"><span data-stu-id="8a544-109">Operation type</span></span>|<span data-ttu-id="8a544-110">연산자</span><span class="sxs-lookup"><span data-stu-id="8a544-110">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="8a544-111">1</span><span class="sxs-lookup"><span data-stu-id="8a544-111">1</span></span>|<span data-ttu-id="8a544-112">기본</span><span class="sxs-lookup"><span data-stu-id="8a544-112">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="8a544-113">2</span><span class="sxs-lookup"><span data-stu-id="8a544-113">2</span></span>|<span data-ttu-id="8a544-114">단항</span><span class="sxs-lookup"><span data-stu-id="8a544-114">Unary</span></span>|`! not`|  
|<span data-ttu-id="8a544-115">3</span><span class="sxs-lookup"><span data-stu-id="8a544-115">3</span></span>|<span data-ttu-id="8a544-116">곱하기</span><span class="sxs-lookup"><span data-stu-id="8a544-116">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="8a544-117">4</span><span class="sxs-lookup"><span data-stu-id="8a544-117">4</span></span>|<span data-ttu-id="8a544-118">더하기</span><span class="sxs-lookup"><span data-stu-id="8a544-118">Additive</span></span>|`+ -`|  
|<span data-ttu-id="8a544-119">5</span><span class="sxs-lookup"><span data-stu-id="8a544-119">5</span></span>|<span data-ttu-id="8a544-120">순서 지정</span><span class="sxs-lookup"><span data-stu-id="8a544-120">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="8a544-121">6</span><span class="sxs-lookup"><span data-stu-id="8a544-121">6</span></span>|<span data-ttu-id="8a544-122">같음</span><span class="sxs-lookup"><span data-stu-id="8a544-122">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="8a544-123">7</span><span class="sxs-lookup"><span data-stu-id="8a544-123">7</span></span>|<span data-ttu-id="8a544-124">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="8a544-124">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="8a544-125">8</span><span class="sxs-lookup"><span data-stu-id="8a544-125">8</span></span>|<span data-ttu-id="8a544-126">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="8a544-126">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="8a544-127">식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-127">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="8a544-128">예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-128">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="8a544-129">괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-129">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="8a544-130">괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a544-130">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="8a544-131">예를 들어,은를 `x+y*z` 곱한 `y` 다음를 `z` 추가 `x` 하지만 `(x+y)*z` 는를 `x` 에 추가한 다음 결과를에 `y` 곱합니다 `z` .</span><span class="sxs-lookup"><span data-stu-id="8a544-131">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a544-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a544-132">See also</span></span>

- [<span data-ttu-id="8a544-133">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="8a544-133">Entity SQL Overview</span></span>](entity-sql-overview.md)
