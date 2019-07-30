---
title: Lazy 식
description: 지연 식 F# 으로 앱과 라이브러리의 성능을 향상 시킬 수 있는 방법을 알아봅니다.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630745"
---
# <a name="lazy-expressions"></a><span data-ttu-id="e3f18-103">Lazy 식</span><span class="sxs-lookup"><span data-stu-id="e3f18-103">Lazy Expressions</span></span>

<span data-ttu-id="e3f18-104">*지연 식은* 즉시 계산 되지 않고 결과가 필요할 때 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="e3f18-105">이를 통해 코드의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3f18-106">구문</span><span class="sxs-lookup"><span data-stu-id="e3f18-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="e3f18-107">설명</span><span class="sxs-lookup"><span data-stu-id="e3f18-107">Remarks</span></span>

<span data-ttu-id="e3f18-108">이전 구문에서 *expression* 은 결과가 필요한 경우에만 평가 되는 코드이 고, *identifier* 는 결과를 저장 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="e3f18-109">값은 형식 [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)입니다. 여기서에 `'T` 사용 되는 실제 형식은 식의 결과에서 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="e3f18-110">지연 식은 결과가 필요한 상황 으로만 식의 실행을 제한 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="e3f18-111">식을 강제로 수행 하려면 메서드 `Force`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="e3f18-112">`Force`실행이 한 번만 수행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="e3f18-113">에 대 한 `Force` 후속 호출은 동일한 결과를 반환 하지만 코드를 실행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="e3f18-114">다음 코드는 지연 식의 사용 및 사용 `Force`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="e3f18-115">이 `result` 코드에서의 형식은이 `Lazy<int>` `Force` 고, 메서드는을 반환 합니다.`int`</span><span class="sxs-lookup"><span data-stu-id="e3f18-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="e3f18-116">지연 계산은 `Lazy` 형식이 아니라 시퀀스에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f18-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="e3f18-117">자세한 내용은 [시퀀스](sequences.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f18-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3f18-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3f18-118">See also</span></span>

- [<span data-ttu-id="e3f18-119">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="e3f18-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e3f18-120">Lazyextensions.createfromvalue 모듈</span><span class="sxs-lookup"><span data-stu-id="e3f18-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
