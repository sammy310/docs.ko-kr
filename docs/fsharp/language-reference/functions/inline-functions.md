---
title: 인라인 함수
description: 사용 하는 방법을 알아봅니다 F# 호출 코드에 직접 통합 되는 인라인 함수입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 12c175e3e46e12d978fe02d3e1fe83142e71a25d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966597"
---
# <a name="inline-functions"></a><span data-ttu-id="666a6-103">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="666a6-103">Inline Functions</span></span>

<span data-ttu-id="666a6-104">*인라인 함수* 는 호출 코드에 직접 통합 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="666a6-105">인라인 함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="666a6-105">Using Inline Functions</span></span>

<span data-ttu-id="666a6-106">정적 형식 매개 변수를 사용 하면 형식 매개 변수로 매개 변수화 되는 모든 함수는 인라인 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="666a6-107">이렇게 하면 컴파일러가 이러한 형식 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="666a6-108">일반적인 제네릭 형식 매개 변수를 사용 하는 경우에 이러한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="666a6-109">이외의 멤버 제약 조건 사용 하도록 설정, 인라인 함수 코드 최적화에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="666a6-110">그러나 인라인 함수 남용 되지 않도록 컴파일러 최적화 및 라이브러리 함수의 구현 형태가 변화에 덜 정보 훼손에 강하도록 코드를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="666a6-111">따라서 다른 모든 최적화 기술을 시도 하지 않는 한 최적화를 위해 인라인 함수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="666a6-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="666a6-112">함수 또는 메서드 인라인 만들기 성능이 향상 될 수 있습니다 하지만 하는 경우가 아니라면 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="666a6-113">따라서 특정된 함수를 인라인으로 만드는 긍정적인 영향을 미칠 실제로 확인 하려면 성능 측정을도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="666a6-114">`inline` 최상위 수준에서 모듈 수준에서 또는 클래스에서 메서드 수준에서 함수에 한정자를 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="666a6-115">다음 코드 예제에서는 최상위 수준, 인라인 인스턴스 메서드 및 인라인 정적 메서드는 인라인 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="666a6-116">인라인 함수 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="666a6-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="666a6-117">현재 상태 `inline` 형식 유추에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="666a6-118">반면 인라인이 아닌 함수에 사용할 수 없습니다 인라인 함수 수 있는 정적으로 확인 된 형식 매개 변수 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="666a6-119">경우 다음 코드 예제를 보여 줍니다 위치 `inline` 는 정적으로 확인 된 형식 매개 변수가 있는 함수를 사용 하 고 있으므로 유용 합니다 `float` 변환 연산자.</span><span class="sxs-lookup"><span data-stu-id="666a6-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="666a6-120">없이 합니다 `inline` 한정자를 형식 유추는 함수가 특정 형식,이 경우 강제로 `int`입니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="666a6-121">하지만 `inline` 한정자에 함수를 정적으로 확인 된 형식 매개 변수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="666a6-122">사용 하 여는 `inline` 다음 한정자를 형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="666a6-123">즉, 함수를 변환할 수 있는 모든 형식을 허용 하는지 **float**합니다.</span><span class="sxs-lookup"><span data-stu-id="666a6-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="666a6-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="666a6-124">See also</span></span>

- [<span data-ttu-id="666a6-125">함수</span><span class="sxs-lookup"><span data-stu-id="666a6-125">Functions</span></span>](index.md)
- [<span data-ttu-id="666a6-126">제약 조건</span><span class="sxs-lookup"><span data-stu-id="666a6-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="666a6-127">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="666a6-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)