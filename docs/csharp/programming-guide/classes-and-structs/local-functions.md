---
title: 로컬 함수 - C# 프로그래밍 가이드
description: C#의 로컬 함수는 다른 멤버에 중첩되어 포함된 멤버에서 호출할 수 있는 전용 메서드입니다.
ms.date: 10/16/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 1c0cd1b8122f9069e5d6385d698f0ff8278912dd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103246"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="44d62-103">로컬 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="44d62-103">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="44d62-104">C# 7.0부터 C#에서는 *로컬 함수* 를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-104">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="44d62-105">로컬 함수는 다른 멤버에 중첩된 형식의 private 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-105">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="44d62-106">포함하는 멤버에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-106">They can only be called from their containing member.</span></span> <span data-ttu-id="44d62-107">로컬 함수는 다음에서 선언하고 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-107">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="44d62-108">메서드, 특히 반복기 메서드 및 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="44d62-108">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="44d62-109">생성자</span><span class="sxs-lookup"><span data-stu-id="44d62-109">Constructors</span></span>
- <span data-ttu-id="44d62-110">속성 접근자</span><span class="sxs-lookup"><span data-stu-id="44d62-110">Property accessors</span></span>
- <span data-ttu-id="44d62-111">이벤트 접근자</span><span class="sxs-lookup"><span data-stu-id="44d62-111">Event accessors</span></span>
- <span data-ttu-id="44d62-112">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="44d62-112">Anonymous methods</span></span>
- <span data-ttu-id="44d62-113">람다 식</span><span class="sxs-lookup"><span data-stu-id="44d62-113">Lambda expressions</span></span>
- <span data-ttu-id="44d62-114">종료자</span><span class="sxs-lookup"><span data-stu-id="44d62-114">Finalizers</span></span>
- <span data-ttu-id="44d62-115">다른 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="44d62-115">Other local functions</span></span>

<span data-ttu-id="44d62-116">그러나 식 본문 멤버 내에서는 로컬 함수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-116">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="44d62-117">로컬 함수에서도 지원하는 기능을 람다 식으로 구현할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-117">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="44d62-118">비교를 보려면 [로컬 함수 및 람다 식](#local-functions-vs-lambda-expressions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d62-118">For a comparison, see [Local functions vs. lambda expressions](#local-functions-vs-lambda-expressions).</span></span>

<span data-ttu-id="44d62-119">로컬 함수는 코드의 의도를 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-119">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="44d62-120">코드를 읽는 모든 사용자가 포함하는 메서드를 통해서만 메서드를 호출할 수 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-120">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="44d62-121">팀 프로젝트의 경우 로컬 함수를 사용하면 다른 개발자가 실수로 클래스 또는 구조체의 다른 곳에서 직접 메서드를 호출하는 경우를 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-121">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>

## <a name="local-function-syntax"></a><span data-ttu-id="44d62-122">로컬 함수 구문</span><span class="sxs-lookup"><span data-stu-id="44d62-122">Local function syntax</span></span>

<span data-ttu-id="44d62-123">로컬 함수는 포함하는 멤버 내의 중첩 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-123">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="44d62-124">해당 정의는 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-124">Its definition has the following syntax:</span></span>

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="44d62-125">로컬 함수에 다음 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-125">You can use the following modifiers with a local function:</span></span>

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- <span data-ttu-id="44d62-126">[`static`](../../language-reference/keywords/static.md)(C# 8.0 이상).</span><span class="sxs-lookup"><span data-stu-id="44d62-126">[`static`](../../language-reference/keywords/static.md) (in C# 8.0 and later).</span></span> <span data-ttu-id="44d62-127">정적 로컬 함수는 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-127">A static local function can't capture local variables or instance state.</span></span>
- <span data-ttu-id="44d62-128">[`extern`](../../language-reference/keywords/extern.md)(C# 9.0 이상).</span><span class="sxs-lookup"><span data-stu-id="44d62-128">[`extern`](../../language-reference/keywords/extern.md) (in C# 9.0 and later).</span></span> <span data-ttu-id="44d62-129">외부 로컬 함수는 `static`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-129">An external local function must be `static`.</span></span>

<span data-ttu-id="44d62-130">해당 메서드 매개 변수를 비롯하여 포함하는 멤버에 정의된 모든 지역 변수는 정적이지 않은 로컬 함수에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-130">All local variables that are defined in the containing member, including its method parameters, are accessible in a non-static local function.</span></span>

<span data-ttu-id="44d62-131">메서드 정의와 달리 로컬 함수 정의에는 멤버 액세스 한정자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-131">Unlike a method definition, a local function definition cannot include the member access modifier.</span></span> <span data-ttu-id="44d62-132">모든 로컬 함수는 private이므로 `private` 키워드 등의 액세스 한정자를 포함하면 컴파일러 오류 CS0106,“이 항목의 ‘private’ 한정자가 유효하지 않습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-132">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>

<span data-ttu-id="44d62-133">다음 예제에서는 `GetText` 메서드에 대해 private인 로컬 함수 `AppendPathSeparator`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-133">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="Basic" :::

<span data-ttu-id="44d62-134">C# 9.0부터 다음 예제와 같이 로컬 함수, 매개 변수, 형식 매개 변수에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-134">Beginning with C# 9.0, you can apply attributes to a local function, its parameters and type parameters, as the following example shows:</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="WithAttributes" :::

<span data-ttu-id="44d62-135">이전 예제에서는 [특수 특성](../../language-reference/attributes/nullable-analysis.md)을 사용하여 null 허용 컨텍스트에서 컴파일러의 정적 분석을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-135">The preceding example uses a [special attribute](../../language-reference/attributes/nullable-analysis.md) to assist the compiler in static analysis in a nullable context.</span></span>

## <a name="local-functions-and-exceptions"></a><span data-ttu-id="44d62-136">로컬 함수 및 예외</span><span class="sxs-lookup"><span data-stu-id="44d62-136">Local functions and exceptions</span></span>

<span data-ttu-id="44d62-137">로컬 함수의 유용한 기능 중 하나는 예외가 즉시 나타나도록 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-137">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="44d62-138">메서드 반복기의 경우 반환된 시퀀스가 열거된 경우에만 예외가 나타나고 반복기를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-138">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="44d62-139">비동기 메서드의 경우 비동기 메서드에서 throw된 예외는 반환된 작업을 대기할 때 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-139">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span>

<span data-ttu-id="44d62-140">다음 예제에서는 지정한 범위의 홀수를 열거하는 `OddSequence` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-140">The following example defines an `OddSequence` method that enumerates odd numbers in a specified range.</span></span> <span data-ttu-id="44d62-141">100보다 큰 숫자를 `OddSequence` 열거자 메서드에 전달하기 때문에 메서드가 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-141">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="44d62-142">예제의 출력에서 볼 수 있듯이 예외는 숫자를 반복하는 경우에만 나타나고 열거자를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-142">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

:::code language="csharp" source="snippets/local-functions/IteratorWithoutLocal.cs" :::

<span data-ttu-id="44d62-143">로컬 함수에 반복기 논리를 추가하는 경우 다음 예제와 같이 열거자를 검색할 때 인수 유효성 검사 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-143">If you put iterator logic into a local function, argument validation exceptions are thrown when you retrieve the enumerator, as the following example shows:</span></span>

:::code language="csharp" source="snippets/local-functions/IteratorWithLocal.cs" :::

## <a name="local-functions-vs-lambda-expressions"></a><span data-ttu-id="44d62-144">로컬 함수 및 람다 식</span><span class="sxs-lookup"><span data-stu-id="44d62-144">Local functions vs. lambda expressions</span></span>

<span data-ttu-id="44d62-145">얼핏 보기에 로컬 함수와 [람다 식](../../language-reference/operators/lambda-expressions.md)은 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-145">At first glance, local functions and [lambda expressions](../../language-reference/operators/lambda-expressions.md) are very similar.</span></span> <span data-ttu-id="44d62-146">대부분의 경우 람다 식과 로컬 함수 사용 간 선택은 스타일 및 개인 기본 설정의 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-146">In many cases, the choice between using lambda expressions and local functions is a matter of style and personal preference.</span></span> <span data-ttu-id="44d62-147">그러나 하나 또는 다른 것을 사용할 수 있는 것에 알고 있어야 하는 실제 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-147">However, there are real differences in where you can use one or the other that you should be aware of.</span></span>

<span data-ttu-id="44d62-148">계승 알고리즘의 로컬 함수 및 람다 식 구현 간의 차이점을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-148">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="44d62-149">로컬 함수를 사용하는 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-149">Here's the version using a local function:</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLocal" :::

<span data-ttu-id="44d62-150">이 버전은 람다 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-150">This version uses lambda expressions:</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLambda" :::

### <a name="naming"></a><span data-ttu-id="44d62-151">이름 지정</span><span class="sxs-lookup"><span data-stu-id="44d62-151">Naming</span></span>

<span data-ttu-id="44d62-152">로컬 함수는 메서드와 같이 명시적으로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-152">Local functions are explicitly named like methods.</span></span> <span data-ttu-id="44d62-153">람다 식은 무명 메서드이며 일반적으로 `Action` 또는 `Func` 형식인 `delegate` 형식의 변수에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-153">Lambda expressions are anonymous methods and need to be assigned to variables of a `delegate` type, typically either `Action` or `Func` types.</span></span> <span data-ttu-id="44d62-154">로컬 함수를 선언하는 경우 프로세스는 일반 메서드를 작성하는 것과 유사하며, 반환 형식 및 함수 시그니처를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-154">When you declare a local function, the process is like writing a normal method; you declare a return type and a function signature.</span></span>

### <a name="function-signatures-and-lambda-expression-types"></a><span data-ttu-id="44d62-155">함수 시그니처 및 람다 식 형식</span><span class="sxs-lookup"><span data-stu-id="44d62-155">Function signatures and lambda expression types</span></span>

<span data-ttu-id="44d62-156">람다 식은 인수 및 반환 형식을 결정하기 위해 할당되는 `Action`/`Func` 변수의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-156">Lambda expressions rely on the type of the `Action`/`Func` variable that they're assigned to determine the argument and return types.</span></span> <span data-ttu-id="44d62-157">로컬 함수에서 구문은 일반적인 메서드를 작성하는 것과 매우 유사하기 때문에 인수 형식 및 반환 형식이 이미 함수 선언에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-157">In local functions, since the syntax is much like writing a normal method, argument types and return type are already part of the function declaration.</span></span>

### <a name="definite-assignment"></a><span data-ttu-id="44d62-158">한정된 할당</span><span class="sxs-lookup"><span data-stu-id="44d62-158">Definite assignment</span></span>

<span data-ttu-id="44d62-159">람다 식은 런타임에 선언되고 할당되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-159">Lambda expressions are objects that are declared and assigned at runtime.</span></span> <span data-ttu-id="44d62-160">람다 식을 사용하려면 명확하게 할당해야 합니다. 할당될 `Action`/`Func` 변수를 선언하고 람다 식을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-160">In order for a lambda expression to be used, it needs to be definitely assigned: the `Action`/`Func` variable that it will be assigned to must be declared and the lambda expression assigned to it.</span></span> <span data-ttu-id="44d62-161">`LambdaFactorial`은 정의하기 전에 먼저 람다 식 `nthFactorial`을 선언하고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-161">Notice that `LambdaFactorial` must declare and initialize the lambda expression `nthFactorial` before defining it.</span></span> <span data-ttu-id="44d62-162">이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-162">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>

<span data-ttu-id="44d62-163">로컬 함수는 컴파일 시간에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-163">Local functions are defined at compile time.</span></span> <span data-ttu-id="44d62-164">변수에 할당되지 않기 때문에 **범위에 있는** 모든 코드 위치에서 참조할 수 있습니다. 첫 번째 예제 `LocalFunctionFactorial`에서는 `return` 문 위 또는 아래에 로컬 함수를 선언하고 컴파일러 오류를 트리거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-164">As they're not assigned to variables, they can be referenced from any code location **where it is in scope**; in our first example `LocalFunctionFactorial`, we could declare our local function either above or below the `return` statement and not trigger any compiler errors.</span></span>

<span data-ttu-id="44d62-165">이러한 차이점은 로컬 함수를 사용하여 재귀 알고리즘을 쉽게 만들 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-165">These differences mean that recursive algorithms are easier to create using local functions.</span></span> <span data-ttu-id="44d62-166">자신을 호출하는 로컬 함수를 선언하고 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-166">You can declare and define a local function that calls itself.</span></span> <span data-ttu-id="44d62-167">람다 식을 동일한 람다 식을 참조하는 본문에 다시 할당하려면 선언하고, 기본 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-167">Lambda expressions must be declared, and assigned a default value before they can be re-assigned to a body that references the same lambda expression.</span></span>

### <a name="implementation-as-a-delegate"></a><span data-ttu-id="44d62-168">대리자로 구현</span><span class="sxs-lookup"><span data-stu-id="44d62-168">Implementation as a delegate</span></span>

<span data-ttu-id="44d62-169">람다 식은 선언될 때 대리자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-169">Lambda expressions are converted to delegates when they're declared.</span></span> <span data-ttu-id="44d62-170">로컬 함수는 기존 메서드 ‘또는’ 대리자로 작성할 수 있다는 점에서 더욱 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-170">Local functions are more flexible in that they can be written like a traditional method *or* as a delegate.</span></span> <span data-ttu-id="44d62-171">로컬 함수는 대리자로 ***사용*** 되는 경우에만 대리자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-171">Local functions are only converted to delegates when ***used*** as a delegate.</span></span>

<span data-ttu-id="44d62-172">로컬 함수를 선언하고 메서드처럼 호출하여 참조하는 경우 대리자로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-172">If you declare a local function and only reference it by calling it like a method, it will not be converted to a delegate.</span></span>

### <a name="variable-capture"></a><span data-ttu-id="44d62-173">변수 캡처</span><span class="sxs-lookup"><span data-stu-id="44d62-173">Variable capture</span></span>

<span data-ttu-id="44d62-174">[한정된 할당](../../../../_csharplang/spec/variables.md#definite-assignment) 규칙은 로컬 함수 또는 람다 식에서 캡처되는 변수에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-174">The rules of [definite assignment](../../../../_csharplang/spec/variables.md#definite-assignment) also affect any variables that are captured by the local function or lambda expression.</span></span> <span data-ttu-id="44d62-175">컴파일러는 로컬 함수가 포함된 범위에서 캡처된 변수를 한정적으로 할당할 수 있도록 하는 정적 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-175">The compiler can perform static analysis that enables local functions to definitely assign captured variables in the enclosing scope.</span></span> <span data-ttu-id="44d62-176">다음 예제를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="44d62-176">Consider this example:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="44d62-177">컴파일러는 `LocalFunction`에서 호출될 때 `y`를 한정적으로 할당하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-177">The compiler can determine that `LocalFunction` definitely assigns `y` when called.</span></span> <span data-ttu-id="44d62-178">`LocalFunction`은 `return` 문 전에 호출되므로 `y`는 `return` 문에서 한정적으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-178">Because `LocalFunction` is called before the `return` statement, `y` is definitely assigned at the `return` statement.</span></span>

<span data-ttu-id="44d62-179">로컬 함수가 바깥쪽 범위에서 변수를 캡처하는 경우 로컬 함수는 대리자 형식으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-179">Note that when a local function captures variables in the enclosing scope, the local function is implemented as a delegate type.</span></span>

### <a name="heap-allocations"></a><span data-ttu-id="44d62-180">힙 할당</span><span class="sxs-lookup"><span data-stu-id="44d62-180">Heap allocations</span></span>

<span data-ttu-id="44d62-181">해당 용도에 따라 로컬 함수는 람다 식에 항상 필요한 힙 할당을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-181">Depending on their use, local functions can avoid heap allocations that are always necessary for lambda expressions.</span></span> <span data-ttu-id="44d62-182">로컬 함수가 대리자로 변환되지 않고 로컬 함수에 의해 캡처된 변수가 대리자로 변환된 다른 람다 식 또는 로컬 함수에 의해 캡처되지 않는 경우 컴파일러는 힙 할당을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-182">If a local function is never converted to a delegate, and none of the variables captured by the local function are captured by other lambdas or local functions that are converted to delegates, the compiler can avoid heap allocations.</span></span>

<span data-ttu-id="44d62-183">다음 비동기 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="44d62-183">Consider this async example:</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLambda" :::

<span data-ttu-id="44d62-184">이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-184">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="44d62-185">로컬 함수의 경우 클로저를 구현하는 개체는 `struct` 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-185">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="44d62-186">해당 구조체 형식은 로컬 함수에 참조로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-186">That struct type would be passed by reference to the local function.</span></span> <span data-ttu-id="44d62-187">구현에서 이러한 차이점은 할당에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-187">This difference in implementation would save on an allocation.</span></span>

<span data-ttu-id="44d62-188">람다 식에 필요한 인스턴스화는 추가 메모리 할당을 의미하며, 시간이 중요한 코드 경로에서 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-188">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time-critical code paths.</span></span> <span data-ttu-id="44d62-189">로컬 함수는 이러한 오버헤드를 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-189">Local functions do not incur this overhead.</span></span> <span data-ttu-id="44d62-190">위 예제에서 로컬 함수 버전은 람다 식 버전보다 할당 수가 2개 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-190">In the example above, the local functions version has two fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="44d62-191">로컬 함수가 대리자로 변환되지 않고 로컬 함수에 의해 캡처된 변수가 대리자로 변환된 다른 람다 또는 로컬 함수에 의해 캡처되지 않는 경우 로컬 함수를 `static` 로컬 함수로 선언하여 힙에 할당되지 않도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-191">If you know that your local function won't be converted to a delegate and none of the variables captured by it are captured by other lambdas or local functions that are converted to delegates, you can guarantee that your local function avoids being allocated on the heap by declaring it as a `static` local function.</span></span> <span data-ttu-id="44d62-192">이 기능은 C# 8.0 이상 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-192">Note that this feature is available in C# 8.0 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="44d62-193">이 메서드에 해당하는 로컬 함수는 클로저에 클래스도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-193">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="44d62-194">로컬 함수의 클로저가 `class` 또는 `struct`로 구현되는지 여부는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-194">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="44d62-195">로컬 함수는 `struct`를 사용할 수 있는 반면, 람다는 항상 `class`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-195">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLocal" :::

### <a name="usage-of-the-yield-keyword"></a><span data-ttu-id="44d62-196">`yield` 키워드 사용</span><span class="sxs-lookup"><span data-stu-id="44d62-196">Usage of the `yield` keyword</span></span>

<span data-ttu-id="44d62-197">이 샘플에서 설명하지 않은 한 가지 최종 장점은 `yield return` 구문을 사용해서 로컬 함수를 반복기로 구현하여 값 시퀀스를 생성할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-197">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

:::code language="csharp" source="snippets/local-functions/Program.cs" id="YieldReturn" :::

<span data-ttu-id="44d62-198">`yield return` 문은 람다 식에서 허용되지 않습니다. [컴파일러 오류 CS1621](../../misc/cs1621.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d62-198">The `yield return` statement is not allowed in lambda expressions, see [compiler error CS1621](../../misc/cs1621.md).</span></span>

<span data-ttu-id="44d62-199">로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-199">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span> <span data-ttu-id="44d62-200">로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="44d62-200">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

## <a name="see-also"></a><span data-ttu-id="44d62-201">참조</span><span class="sxs-lookup"><span data-stu-id="44d62-201">See also</span></span>

- [<span data-ttu-id="44d62-202">메서드</span><span class="sxs-lookup"><span data-stu-id="44d62-202">Methods</span></span>](methods.md)
