---
title: 지연 식
description: 설명 하는 방법 F# 지연 식에는 앱 및 라이브러리의 성능을 향상 시킬 수 있습니다.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57853331"
---
# <a name="lazy-expressions"></a><span data-ttu-id="e1b58-103">지연 식</span><span class="sxs-lookup"><span data-stu-id="e1b58-103">Lazy Expressions</span></span>

<span data-ttu-id="e1b58-104">*지연 식이* 식이 즉시 평가 되지 않습니다 하지만 대신 결과 필요할 때 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="e1b58-105">이 코드의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1b58-106">구문</span><span class="sxs-lookup"><span data-stu-id="e1b58-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="e1b58-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1b58-107">Remarks</span></span>

<span data-ttu-id="e1b58-108">이전 구문에서 *식* 결과가 필요한 경우에 평가 되는 코드 및 *식별자* 결과 저장 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="e1b58-109">형식의 값이 [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)여기서는 실제 형식은는 `'T` 식의 결과에서 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="e1b58-110">지연 식이 사용 하면 결과가 필요할 때 해당 상황에는 식의 실행을 제한 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="e1b58-111">메서드를 호출 하면 수행할 식을 적용할 `Force`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="e1b58-112">`Force` 한 번만 수행 하 고 실행을 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="e1b58-113">에 대 한 후속 호출 `Force` 동일한 결과 실행 하지는 않습니다 모든 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="e1b58-114">다음 코드에서는 지연 식 사용 하 고 사용 `Force`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="e1b58-115">이 코드에서 형식의 `result` 됩니다 `Lazy<int>`, 및 `Force` 메서드가 반환 되는 `int`.</span><span class="sxs-lookup"><span data-stu-id="e1b58-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="e1b58-116">지연 계산 하지 않고는 `Lazy` 입력, 시퀀스에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="e1b58-117">자세한 내용은 [시퀀스](sequences.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b58-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1b58-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1b58-118">See also</span></span>

- [<span data-ttu-id="e1b58-119">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="e1b58-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e1b58-120">LazyExtensions 모듈</span><span class="sxs-lookup"><span data-stu-id="e1b58-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
