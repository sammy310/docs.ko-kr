---
title: '람다 식: 흥미로운 키워드'
description: F# ' 재미 ' 키워드를 사용 하 여 익명 함수인 람다 식을 정의 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630670"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="bf0de-103">람다 식: 흥미로운 키워드 (F#)</span><span class="sxs-lookup"><span data-stu-id="bf0de-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="bf0de-104">`fun` 키워드는 람다 식, 즉 익명 함수를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf0de-105">구문</span><span class="sxs-lookup"><span data-stu-id="bf0de-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="bf0de-106">설명</span><span class="sxs-lookup"><span data-stu-id="bf0de-106">Remarks</span></span>

<span data-ttu-id="bf0de-107">*매개 변수 목록은* 일반적으로 이름 및 매개 변수의 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="bf0de-108">일반적으로 *매개 변수 목록은* 모든 F# 패턴으로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="bf0de-109">가능한 패턴의 전체 목록은 [패턴 일치](../pattern-matching.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf0de-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="bf0de-110">유효한 매개 변수 목록에는 다음 예제가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="bf0de-111">*식은* 함수의 본문 이며,의 마지막 식은 반환 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="bf0de-112">유효한 람다 식의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="bf0de-113">람다 식 사용</span><span class="sxs-lookup"><span data-stu-id="bf0de-113">Using Lambda Expressions</span></span>

<span data-ttu-id="bf0de-114">람다 식은 목록 또는 다른 컬렉션에 대 한 작업을 수행 하 고 함수를 정의 하는 추가 작업을 방지 하려는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="bf0de-115">많은 F# 라이브러리 함수는 함수 값을 인수로 사용 하 고, 이러한 경우에는 람다 식을 사용 하는 것이 특히 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="bf0de-116">다음 코드는 목록 요소에 람다 식을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="bf0de-117">이 경우 익명 함수는 목록의 모든 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0de-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="bf0de-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf0de-118">See also</span></span>

- [<span data-ttu-id="bf0de-119">함수</span><span class="sxs-lookup"><span data-stu-id="bf0de-119">Functions</span></span>](index.md)
