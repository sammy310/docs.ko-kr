---
title: '재귀 함수: Rec 키워드'
description: "' Rec ' F# 키워드를 ' let ' 키워드와 함께 사용 하 여 재귀 함수를 정의 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630658"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="b627c-103">재귀 함수: Rec 키워드</span><span class="sxs-lookup"><span data-stu-id="b627c-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="b627c-104">키워드는 `let` 키워드와 함께 사용 되어 재귀 함수를 정의 합니다. `rec`</span><span class="sxs-lookup"><span data-stu-id="b627c-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="b627c-105">구문</span><span class="sxs-lookup"><span data-stu-id="b627c-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="b627c-106">설명</span><span class="sxs-lookup"><span data-stu-id="b627c-106">Remarks</span></span>

<span data-ttu-id="b627c-107">재귀 함수는 자신을 호출 하는 함수는 F# 언어에서 명시적으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="b627c-108">이렇게 하면 함수 범위에서 정의 되는 식별자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="b627c-109">다음 코드에서는 *n*<sup>번째</sup> 피보나치 수를 계산 하는 재귀 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="b627c-110">실제로 위와 같은 코드는 이전에 계산 된 값의 다시 계산 기능을 포함 하기 때문에 메모리 및 프로세서 시간에 대 한 불필요 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="b627c-111">메서드는 형식 내에서 암시적으로 재귀적입니다. `rec` 키워드를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="b627c-112">클래스 내의 바인딩이 암시적으로 재귀적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="b627c-113">상호 재귀 함수</span><span class="sxs-lookup"><span data-stu-id="b627c-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="b627c-114">경우에 따라 함수는 서로 *재귀적*으로 사용 됩니다. 즉, 한 함수가 다른 함수를 호출 하는 원을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="b627c-115">키워드`and` 를 사용 하 여 함께 연결 하려면 하나의 `let` 바인딩에서 이러한 함수를 함께 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="b627c-116">다음 예에서는 두 개의 상호 재귀 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="b627c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b627c-117">See also</span></span>

- [<span data-ttu-id="b627c-118">함수</span><span class="sxs-lookup"><span data-stu-id="b627c-118">Functions</span></span>](index.md)
