---
title: '람다 식: Fun 키워드'
description: 사용 하는 방법을 알아봅니다는 F# 는 익명 함수는 람다 식 정의에 '재미' 키워드입니다.
ms.date: 05/16/2016
ms.openlocfilehash: c59d32bd4226384213453f1a9d362209e68a6fb5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645386"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="144cc-103">람다 식: Fun 키워드 (F#)</span><span class="sxs-lookup"><span data-stu-id="144cc-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="144cc-104">`fun` 키워드 람다 식, 익명 함수를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="144cc-105">구문</span><span class="sxs-lookup"><span data-stu-id="144cc-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="144cc-106">설명</span><span class="sxs-lookup"><span data-stu-id="144cc-106">Remarks</span></span>

<span data-ttu-id="144cc-107">합니다 *매개 변수 목록을* 이름 및 필요에 따라 매개 변수의 형식이 일반적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="144cc-108">보다 일반적으로 *매개 변수 목록을* 모든 구성 될 수 있습니다 F# 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="144cc-109">가능한 패턴의 전체 목록을 참조 하세요 [패턴 일치](../pattern-matching.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="144cc-110">올바른 매개 변수 목록에는 다음 예제에서는 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="144cc-111">합니다 *식* 함수 반환 값을 생성 하는 마지막 식의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="144cc-112">유효한 람다 식의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="144cc-113">람다 식 사용</span><span class="sxs-lookup"><span data-stu-id="144cc-113">Using Lambda Expressions</span></span>

<span data-ttu-id="144cc-114">람다 식 목록 또는 다른 컬렉션에 대 한 작업을 수행 하 고 함수를 정의 하는 추가 작업을 방지 하려면 하려는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="144cc-115">많은 F# 인수로 함수 값을 사용 하는 라이브러리 함수 및 람다 식을 사용 하 여 이러한 경우에 특히 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="144cc-116">다음 코드에는 목록의 요소에 람다 식을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="144cc-117">이 경우 익명 함수 목록의 모든 요소에 1을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="144cc-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="144cc-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="144cc-118">See also</span></span>

- [<span data-ttu-id="144cc-119">함수</span><span class="sxs-lookup"><span data-stu-id="144cc-119">Functions</span></span>](index.md)
