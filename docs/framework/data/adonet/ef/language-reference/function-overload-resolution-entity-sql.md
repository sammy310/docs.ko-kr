---
description: '자세한 정보: 함수 오버 로드 확인 (Entity SQL)'
title: 함수 오버로드 확인(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: 8fbe0b54ed559d1f962c3e916d25554e0de65737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786331"
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="eb381-103">함수 오버로드 확인(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eb381-103">Function Overload Resolution (Entity SQL)</span></span>

<span data-ttu-id="eb381-104">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 함수의 확인 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-104">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="eb381-105">함수의 서명이 고유하다면 함수 두 개 이상을 동일한 이름으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-105">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="eb381-106">이런 경우 특정 식이 어느 함수를 참조하는지 확인하려면 다음 기준을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-106">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="eb381-107">이 기준은 차례로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-107">These criteria are applied in sequence.</span></span> <span data-ttu-id="eb381-108">하나의 함수에만 적용되는 첫 번째 기준은 확인된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-108">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1. <span data-ttu-id="eb381-109">**매개 변수 번호** 입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-109">**Parameter number**.</span></span> <span data-ttu-id="eb381-110">함수의 매개 변수 개수가 식에 지정된 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-110">The function has the same number of parameters specified in the expression.</span></span>  
  
2. <span data-ttu-id="eb381-111">**형식과 정확히 일치** 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-111">**Exact match on type**.</span></span> <span data-ttu-id="eb381-112">함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 null 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-112">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3. <span data-ttu-id="eb381-113">**하위 형식에 대해 일치** 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-113">**Match on subtype**.</span></span> <span data-ttu-id="eb381-114">함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 그 형식의 하위 형식입니다. 또는 인수가 null 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-114">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="eb381-115">여러 함수가 필요한 하위 형식 변환의 개수에서만 차이가 나는 경우, 하위 형식 변환의 개수가 가장 적은 함수가 확인된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-115">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4. <span data-ttu-id="eb381-116">**하위 유형 또는 유형 승격을 찾습니다**.</span><span class="sxs-lookup"><span data-stu-id="eb381-116">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="eb381-117">함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 그 하위 형식이거나 그 형식으로 승격될 수 있습니다. 또는 인수가 null 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-117">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="eb381-118">여러 함수가 하위 형식 변환 및 승격의 개수에서만 차이가 나는 경우, 하위 형식 변환 및 승격의 개수가 가장 적은 함수가 확인된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-118">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="eb381-119">이 중 어느 기준을 통해서도 하나의 함수가 선택되지 않는다면 함수 호출 식이 모호한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-119">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="eb381-120">이러한 규칙을 사용하여 함수를 하나 추출할 수 있는 경우라도 인수가 매개 변수와 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-120">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="eb381-121">이런 경우에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-121">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="eb381-122">사용자 정의 함수의 경우에는 이 함수와 더 잘 일치하는 서명이 있는 모델 정의 함수가 있더라도 인라인 쿼리 함수 정의가 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb381-122">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb381-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb381-123">See also</span></span>

- [<span data-ttu-id="eb381-124">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="eb381-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="eb381-125">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="eb381-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="eb381-126">함수</span><span class="sxs-lookup"><span data-stu-id="eb381-126">Functions</span></span>](functions-entity-sql.md)
