---
title: '루프: for...in 식'
description: F# 자세한 내용은 다음을 참조 하세요. 식 반복 구문은 열거 가능한 컬렉션에서 패턴의 일치 항목을 반복 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5a2ca59ca4199ece5d78010ff780e86ae2b25181
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216451"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="f54fb-103">루프: for...in 식</span><span class="sxs-lookup"><span data-stu-id="f54fb-103">Loops: for...in Expression</span></span>

<span data-ttu-id="f54fb-104">이 루핑 구문은 범위 식, 시퀀스, 목록, 배열 또는 열거를 지 원하는 기타 구문과 같은 열거 가능한 컬렉션에서 패턴의 일치를 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="f54fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="f54fb-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="f54fb-106">설명</span><span class="sxs-lookup"><span data-stu-id="f54fb-106">Remarks</span></span>

<span data-ttu-id="f54fb-107">식은 열거 가능한 컬렉션의 값을 `for each` 반복 하는 데 사용 되기 때문에 다른 .net 언어의 문과 비교할 수 있습니다. `for...in`</span><span class="sxs-lookup"><span data-stu-id="f54fb-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="f54fb-108">그러나는 `for...in` 전체 컬렉션을 반복 하는 대신 컬렉션에 대 한 패턴 일치도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="f54fb-109">열거 가능한 식은 열거 가능한 컬렉션으로 지정 하거나 `..` 연산자를 사용 하 여 정수 계열 형식에 대 한 범위로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="f54fb-110">열거 가능한 컬렉션에는 목록, 시퀀스, 배열, 집합, 맵 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="f54fb-111">을 구현 `System.Collections.IEnumerable` 하는 모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="f54fb-112">`..` 연산자를 사용 하 여 범위를 표현할 때 다음 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="f54fb-113">*시작* ..</span><span class="sxs-lookup"><span data-stu-id="f54fb-113">*start* ..</span></span> <span data-ttu-id="f54fb-114">*finish*</span><span class="sxs-lookup"><span data-stu-id="f54fb-114">*finish*</span></span>

<span data-ttu-id="f54fb-115">다음 코드와 같이, *skip*이라는 증분을 포함 하는 버전을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="f54fb-116">*시작* ..</span><span class="sxs-lookup"><span data-stu-id="f54fb-116">*start* ..</span></span> <span data-ttu-id="f54fb-117">*skip* .</span><span class="sxs-lookup"><span data-stu-id="f54fb-117">*skip* ..</span></span> <span data-ttu-id="f54fb-118">*finish*</span><span class="sxs-lookup"><span data-stu-id="f54fb-118">*finish*</span></span>

<span data-ttu-id="f54fb-119">정수 범위와 단순 카운터 변수를 패턴으로 사용 하는 경우 일반적인 동작은 각 반복에서 카운터 변수를 1 씩 증가 하는 것 이지만, 범위에 skip 값이 포함 된 경우에는 카운터가 skip 값으로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="f54fb-120">패턴에서 일치 하는 값은 본문 식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="f54fb-121">다음 코드 예에서는 `for...in` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="f54fb-122">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-122">The output is as follows.</span></span>

```console
1
5
100
450
788
```

<span data-ttu-id="f54fb-123">다음 예제에서는 시퀀스를 반복 하는 방법과 단순 변수 대신 튜플 패턴을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="f54fb-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-124">The output is as follows.</span></span>

```console
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="f54fb-125">다음 예제에서는 간단한 정수 범위에 대해 루프를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="f54fb-126">Function1의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-126">The output of function1 is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="f54fb-127">다음 예제에서는 범위의 다른 모든 요소를 포함 하는 2의 skip을 사용 하 여 범위를 반복 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="f54fb-128">의 `function2` 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-128">The output of `function2` is as follows.</span></span>

```console
1 3 5 7 9
```

<span data-ttu-id="f54fb-129">다음 예제에서는 문자 범위를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="f54fb-130">의 `function3` 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-130">The output of `function3` is as follows.</span></span>

```console
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="f54fb-131">다음 예제에서는 역방향 반복에 음수 skip 값을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="f54fb-132">의 `function4` 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-132">The output of `function4` is as follows.</span></span>

```console
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="f54fb-133">범위의 시작과 끝은 다음 코드와 같이 함수와 같은 식일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="f54fb-134">이 입력에 `function5` 대 한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-134">The output of `function5` with this input is as follows.</span></span>

```console
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="f54fb-135">다음 예제에서는 루프에 요소가 필요 하지 않은 경우 와일드\_카드 문자 ()를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="f54fb-136">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-136">The output is as follows.</span></span>

```console
Number of elements in list1: 5
```

<span data-ttu-id="f54fb-137">`Note`시퀀스 식과 `for...in` 기타 계산 식에를 사용할 수 있습니다 .이 경우 사용자 지정 된 버전 `for...in` 의 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f54fb-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="f54fb-138">자세한 내용은 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md)및 [계산 식](computation-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f54fb-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f54fb-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f54fb-139">See also</span></span>

- [<span data-ttu-id="f54fb-140">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f54fb-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f54fb-141">하며 `for...to`식</span><span class="sxs-lookup"><span data-stu-id="f54fb-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="f54fb-142">하며 `while...do`식</span><span class="sxs-lookup"><span data-stu-id="f54fb-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
