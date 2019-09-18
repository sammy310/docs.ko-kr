---
title: '조건식: if ... 그런 다음 ... 사람이'
description: 에서 F# 조건 식을 작성 하 여 다른 코드 분기를 실행 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083028"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="76c7a-103">조건식:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="76c7a-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="76c7a-104">`if...then...else` 식은 다른 코드 분기를 실행 하 고 지정 된 부울 식에 따라 다른 값으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="76c7a-105">구문</span><span class="sxs-lookup"><span data-stu-id="76c7a-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="76c7a-106">설명</span><span class="sxs-lookup"><span data-stu-id="76c7a-106">Remarks</span></span>

<span data-ttu-id="76c7a-107">이전 구문에서 *expression1* 는 부울 식이로 `true`계산 될 때 실행 되 고, 그렇지 않으면 *식* 1이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="76c7a-108">다른 언어 `if...then...else` 와 달리 구문은 문이 아니라 식입니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="76c7a-109">즉,를 실행 하는 분기의 마지막 식 값인 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="76c7a-110">각 분기에서 생성 되는 값의 형식은 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="76c7a-111">명시적 `else` 분기가 없는 경우 해당 `unit`형식은입니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="76c7a-112">따라서 `then` 분기의 형식이가 아닌 `unit`다른 형식인 경우 반환 형식이 같은 `else` 분기가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="76c7a-113">식을 함께 연결 하는 경우 대신 `else if`키워드 `elif` 를 사용할 수 있습니다. `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="76c7a-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="76c7a-114">예제</span><span class="sxs-lookup"><span data-stu-id="76c7a-114">Example</span></span>

<span data-ttu-id="76c7a-115">다음 예에서는 `if...then...else` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76c7a-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="76c7a-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="76c7a-116">See also</span></span>

- [<span data-ttu-id="76c7a-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="76c7a-117">F# Language Reference</span></span>](index.md)
