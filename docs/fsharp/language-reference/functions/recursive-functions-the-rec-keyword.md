---
title: '재귀 함수: Rec 키워드'
description: 설명 하는 방법을 F# 'rec' 키워드는 'let' 키워드를 사용 하 여 재귀 함수를 정의 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 9f9c7e1a4468de9551b3852d0e7b4381025b2699
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941010"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="b04be-103">재귀 함수: Rec 키워드</span><span class="sxs-lookup"><span data-stu-id="b04be-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="b04be-104">`rec` 키워드와 함께 사용 되는 `let` 재귀 함수를 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="b04be-105">구문</span><span class="sxs-lookup"><span data-stu-id="b04be-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b04be-106">설명</span><span class="sxs-lookup"><span data-stu-id="b04be-106">Remarks</span></span>

<span data-ttu-id="b04be-107">재귀 함수를 직접 호출 하는 함수에서 명시적으로 식별 되는 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="b04be-108">이렇게 하면 함수의 범위에서 사용 가능한 정의 되는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="b04be-109">다음 코드에서는 계산 하는 재귀 함수는 *n*<sup>th</sup> 피보나치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="b04be-110">실제로 위의 코드는 이전에 계산 된 값의 다시 계산 기능을 포함 하기 때문에 메모리 및 프로세서 시간을 낭비 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="b04be-111">메서드는 암시적으로 형식 내에서 재귀 추가할 필요가 없습니다를 `rec` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="b04be-112">Let 바인딩 클래스 내는 암시적으로 재귀 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="b04be-113">상호 재귀 함수</span><span class="sxs-lookup"><span data-stu-id="b04be-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="b04be-114">함수는 때때로 *상호 재귀*, 호출 형성 원 하나의 함수만 호출 하는 경우에 여러 개의 호출을 사용 하 여 첫 번째를 호출 하는 다른 사이는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="b04be-115">에 이러한 함수를 함께 정의 해야 합니다 `let` 바인딩을 사용 하는 `and` 키워드를 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="b04be-116">다음 예와 두 상호 재귀 함수.</span><span class="sxs-lookup"><span data-stu-id="b04be-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="b04be-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b04be-117">See also</span></span>

- [<span data-ttu-id="b04be-118">함수</span><span class="sxs-lookup"><span data-stu-id="b04be-118">Functions</span></span>](index.md)