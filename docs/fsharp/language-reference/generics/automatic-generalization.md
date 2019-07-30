---
title: 자동 일반화
description: 가능 하면 F# 여러 형식에서 작동 하도록 함수 인수 및 형식을 자동으로 일반화 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630630"
---
# <a name="automatic-generalization"></a><span data-ttu-id="40931-103">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="40931-103">Automatic Generalization</span></span>

<span data-ttu-id="40931-104">F#에서는 형식 유추를 사용 하 여 함수 및 식의 형식을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="40931-105">이 항목에서는 가능한 F# 경우 여러 형식에서 작동 하도록 함수 인수 및 형식을 자동으로 일반화 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="40931-106">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="40931-106">Automatic Generalization</span></span>

<span data-ttu-id="40931-107">컴파일러 F# 는 함수에서 형식 유추를 수행 하는 경우 지정 된 매개 변수가 제네릭일 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="40931-108">컴파일러는 각 매개 변수를 검사 하 고 함수에 해당 매개 변수의 특정 형식에 대 한 종속성이 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="40931-109">그렇지 않으면 형식이 제네릭인 것으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40931-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="40931-110">다음 코드 예제에서는 컴파일러가 제네릭으로 유추 하는 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40931-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="40931-111">형식은로 `'a -> 'a -> 'a`유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40931-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="40931-112">형식은 동일한 알 수 없는 형식의 두 인수를 사용 하 고 동일한 형식의 값을 반환 하는 함수 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40931-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="40931-113">이전 함수를 제네릭일 수 있는 이유 중 하나는 보다 큼 연산자 (`>`)는 제네릭 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="40931-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="40931-114">보다 큼 연산자에는 시그니처가 `'a -> 'a -> bool`있습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="40931-115">모든 연산자가 제네릭이 아니라 함수의 코드에서 제네릭이 아닌 함수 또는 연산자와 함께 매개 변수 형식을 사용 하는 경우 해당 매개 변수 형식은 일반화 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="40931-116">는 `max` 제네릭 이기 때문에 다음 예제와 같이 `int`, `float`등의 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="40931-117">그러나 두 인수는 동일한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="40931-118">서명은이 아니라 `'a -> 'a -> 'a` `'a -> 'b -> 'a`입니다.</span><span class="sxs-lookup"><span data-stu-id="40931-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="40931-119">따라서 다음 코드는 형식이 일치 하지 않기 때문에 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="40931-120">함수 `max` 는 보다 큼 연산자를 지 원하는 모든 형식 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="40931-121">따라서 다음 코드와 같이 문자열에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="40931-122">값 제한</span><span class="sxs-lookup"><span data-stu-id="40931-122">Value Restriction</span></span>

<span data-ttu-id="40931-123">컴파일러는 명시적 인수를 포함 하는 완전 한 함수 정의 및 변경 불가능 한 단순 값에 대해서만 자동 일반화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="40931-124">즉, 특정 형식으로 충분히 제한 되지 않는 코드를 컴파일하려고 시도 하는 경우 컴파일러에서 오류가 발생 하지만 일반화할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="40931-125">이 문제에 대 한 오류 메시지는 값 *제한*값에 대 한 자동 일반화의 이러한 제한을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40931-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="40931-126">일반적으로 구문을 제네릭으로 하려고 하지만 컴파일러에 일반화를 위한 정보가 부족 하거나, 제네릭이 아닌 구문에서 적절 한 형식 정보를 실수로 생략 하는 경우에는 값 제한 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="40931-127">값 제한 오류에 대 한 해결 방법은 다음 방법 중 하나로 형식 유추 문제를 보다 완전 하 게 제한 하는 보다 명시적인 정보를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40931-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="40931-128">명시적 형식 주석을 값 또는 매개 변수에 추가 하 여 형식을 제네릭이 아닌 형식으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="40931-129">함수 컴퍼지션 또는 불완전 하 게 적용 된 커리 된 함수 인수와 같은 제네릭 함수를 정의 하는 데 nongeneralizable 구문을 사용 하는 경우에는 함수를 일반적인 함수 정의로 다시 작성 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="40931-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="40931-130">일반화 하기에 너무 복잡 한 식인 문제인 경우 사용 하지 않는 불필요 한 매개 변수를 추가 하 여 함수로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40931-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="40931-131">명시적 제네릭 형식 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="40931-132">이 옵션은 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-132">This option is rarely used.</span></span>

- <span data-ttu-id="40931-133">다음 코드 예제에서는 이러한 각 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40931-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="40931-134">사례 1: 식이 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="40931-135">이 예제에서 목록은 `counter` 이 고 변경할 수 `int option ref`없는 단순한 값으로 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40931-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="40931-136">사례 2: Nongeneralizable 구문을 사용 하 여 제네릭 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="40931-137">이 예제에서 구문은 함수 인수의 부분 적용을 포함 하기 때문에 nongeneralizable입니다.</span><span class="sxs-lookup"><span data-stu-id="40931-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="40931-138">사례 3: 사용 되지 않는 불필요 한 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="40931-139">이 식은 일반화에 충분 하지 않으므로 컴파일러에서 값 제한 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="40931-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="40931-140">사례 4: 형식 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40931-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="40931-141">마지막 경우에 값은 다음과 같이 다양 한 형식의 값을 만드는 데 사용할 수 있는 형식 함수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40931-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="40931-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="40931-142">See also</span></span>

- [<span data-ttu-id="40931-143">형식 유추</span><span class="sxs-lookup"><span data-stu-id="40931-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="40931-144">제네릭</span><span class="sxs-lookup"><span data-stu-id="40931-144">Generics</span></span>](index.md)
- [<span data-ttu-id="40931-145">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="40931-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="40931-146">제약 조건</span><span class="sxs-lookup"><span data-stu-id="40931-146">Constraints</span></span>](constraints.md)
