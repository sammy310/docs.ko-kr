---
title: '조건식: if... then... else'
description: 조건 식에서 작성 하는 방법을 알아봅니다 F# 코드의 다른 분기를 실행 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: eade8c20c1b62a2e9a54700550d832798308f368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766041"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="40f85-103">조건식: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="40f85-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="40f85-104">`if...then...else` 식 코드의 다른 분기를 실행 하 고 지정 된 부울 식에 따라 다른 값으로 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="40f85-105">구문</span><span class="sxs-lookup"><span data-stu-id="40f85-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="40f85-106">설명</span><span class="sxs-lookup"><span data-stu-id="40f85-106">Remarks</span></span>

<span data-ttu-id="40f85-107">이전 구문에서 *expression1* 부울 식으로 평가 되 면 실행 `true`이 고, 그렇지 않으면 *expression2* 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="40f85-108">달리 다른 언어로 된 `if...then...else` 구문은 문이 아닌 식입니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="40f85-109">즉, 실행 하는 분기의 마지막 식의 값을 생성 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="40f85-110">각 분기에서 생성 된 값의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="40f85-111">없으면 더 명시적 `else` 분기에 해당 형식이 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="40f85-112">따라서 경우 형식의 합니다 `then` 아닌 다른 분기는 모든 형식 `unit`, 있어야는 `else` 동일한 반환 형식 사용 하 여 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="40f85-113">연결 하는 경우 `if...then...else` 식을 그룹화 키워드를 사용할 수 있습니다 `elif` 대신 `else if`; 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="40f85-114">예제</span><span class="sxs-lookup"><span data-stu-id="40f85-114">Example</span></span>

<span data-ttu-id="40f85-115">다음 예제를 사용 하는 방법의 `if...then...else` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="40f85-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="40f85-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="40f85-116">See also</span></span>

- [<span data-ttu-id="40f85-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="40f85-117">F# Language Reference</span></span>](index.md)