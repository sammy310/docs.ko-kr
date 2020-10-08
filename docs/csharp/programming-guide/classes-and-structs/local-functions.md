---
title: 로컬 함수 - C# 프로그래밍 가이드
description: C#의 로컬 함수는 다른 멤버에 중첩되어 포함된 멤버에서 호출할 수 있는 전용 메서드입니다.
ms.date: 10/02/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: a91995757048c8c54253d7f4b923d5194f69bc7b
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654922"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="4c494-103">로컬 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4c494-103">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="4c494-104">C# 7.0부터 C#에서는 *로컬 함수*를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-104">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="4c494-105">로컬 함수는 다른 멤버에 중첩된 형식의 private 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-105">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="4c494-106">포함하는 멤버에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-106">They can only be called from their containing member.</span></span> <span data-ttu-id="4c494-107">로컬 함수는 다음에서 선언하고 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-107">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="4c494-108">메서드, 특히 반복기 메서드 및 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="4c494-108">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="4c494-109">생성자</span><span class="sxs-lookup"><span data-stu-id="4c494-109">Constructors</span></span>
- <span data-ttu-id="4c494-110">속성 접근자</span><span class="sxs-lookup"><span data-stu-id="4c494-110">Property accessors</span></span>
- <span data-ttu-id="4c494-111">이벤트 접근자</span><span class="sxs-lookup"><span data-stu-id="4c494-111">Event accessors</span></span>
- <span data-ttu-id="4c494-112">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="4c494-112">Anonymous methods</span></span>
- <span data-ttu-id="4c494-113">람다 식</span><span class="sxs-lookup"><span data-stu-id="4c494-113">Lambda expressions</span></span>
- <span data-ttu-id="4c494-114">종료자</span><span class="sxs-lookup"><span data-stu-id="4c494-114">Finalizers</span></span>
- <span data-ttu-id="4c494-115">다른 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="4c494-115">Other local functions</span></span>

<span data-ttu-id="4c494-116">그러나 식 본문 멤버 내에서는 로컬 함수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-116">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="4c494-117">로컬 함수에서도 지원하는 기능을 람다 식으로 구현할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-117">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="4c494-118">비교를 보려면 [로컬 함수 및 람다 식](#local-functions-vs-lambda-expressions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c494-118">For a comparison, see [Local functions vs. lambda expressions](#local-functions-vs-lambda-expressions).</span></span>

<span data-ttu-id="4c494-119">로컬 함수는 코드의 의도를 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-119">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="4c494-120">코드를 읽는 모든 사용자가 포함하는 메서드를 통해서만 메서드를 호출할 수 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-120">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="4c494-121">팀 프로젝트의 경우 로컬 함수를 사용하면 다른 개발자가 실수로 클래스 또는 구조체의 다른 곳에서 직접 메서드를 호출하는 경우를 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-121">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>

## <a name="local-function-syntax"></a><span data-ttu-id="4c494-122">로컬 함수 구문</span><span class="sxs-lookup"><span data-stu-id="4c494-122">Local function syntax</span></span>

<span data-ttu-id="4c494-123">로컬 함수는 포함하는 멤버 내의 중첩 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-123">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="4c494-124">해당 정의는 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-124">Its definition has the following syntax:</span></span>

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="4c494-125">로컬 함수에 다음 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-125">You can use the following modifiers with a local function:</span></span>

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- <span data-ttu-id="4c494-126">[`static`](../../language-reference/keywords/static.md)(C# 8.0 이상).</span><span class="sxs-lookup"><span data-stu-id="4c494-126">[`static`](../../language-reference/keywords/static.md) (in C# 8.0 and later).</span></span> <span data-ttu-id="4c494-127">정적 로컬 함수는 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-127">A static local function can't capture local variables or instance state.</span></span>
- <span data-ttu-id="4c494-128">[`extern`](../../language-reference/keywords/extern.md)(C# 9.0 이상).</span><span class="sxs-lookup"><span data-stu-id="4c494-128">[`extern`](../../language-reference/keywords/extern.md) (in C# 9.0 and later).</span></span> <span data-ttu-id="4c494-129">외부 로컬 함수는 `static`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-129">An external local function must be `static`.</span></span>

<span data-ttu-id="4c494-130">해당 메서드 매개 변수를 비롯하여 포함하는 멤버에 정의된 모든 지역 변수는 정적이지 않은 로컬 함수에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-130">All local variables that are defined in the containing member, including its method parameters, are accessible in a non-static local function.</span></span>

<span data-ttu-id="4c494-131">메서드 정의와 달리 로컬 함수 정의에는 멤버 액세스 한정자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-131">Unlike a method definition, a local function definition cannot include the member access modifier.</span></span> <span data-ttu-id="4c494-132">모든 로컬 함수는 private이므로 `private` 키워드 등의 액세스 한정자를 포함하면 컴파일러 오류 CS0106,“이 항목의 ‘private’ 한정자가 유효하지 않습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-132">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>

<span data-ttu-id="4c494-133">또한 로컬 함수나 해당 매개 변수 및 형식 매개 변수에는 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-133">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span>

<span data-ttu-id="4c494-134">다음 예제에서는 `GetText` 메서드에 대해 private인 로컬 함수 `AppendPathSeparator`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-134">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a><span data-ttu-id="4c494-135">로컬 함수 및 예외</span><span class="sxs-lookup"><span data-stu-id="4c494-135">Local functions and exceptions</span></span>

<span data-ttu-id="4c494-136">로컬 함수의 유용한 기능 중 하나는 예외가 즉시 나타나도록 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-136">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="4c494-137">메서드 반복기의 경우 반환된 시퀀스가 열거된 경우에만 예외가 나타나고 반복기를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-137">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="4c494-138">비동기 메서드의 경우 비동기 메서드에서 throw된 예외는 반환된 작업을 대기할 때 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-138">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span>

<span data-ttu-id="4c494-139">다음 예제에서는 지정된 범위 사이의 홀수를 열거하는 `OddSequence` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-139">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="4c494-140">100보다 큰 숫자를 `OddSequence` 열거자 메서드에 전달하기 때문에 메서드가 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-140">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="4c494-141">예제의 출력에서 볼 수 있듯이 예외는 숫자를 반복하는 경우에만 나타나고 열거자를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-141">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

<span data-ttu-id="4c494-142">대신, 다음 예제와 같이 로컬 함수에서 반복기를 반환하여 유효성 검사를 수행할 때, 반복기를 검색하기 전에 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-142">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="4c494-143">유사한 방식으로 로컬 함수를 사용하여 비동기 작업 외부에서 예외를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-143">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="4c494-144">일반적으로 비동기 메서드에서 throw된 예외의 경우 <xref:System.AggregateException>의 내부 예외를 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-144">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="4c494-145">로컬 함수를 사용하면 코드가 빨리 실패하여 예외가 throw되는 동시에 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-145">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="4c494-146">다음 예제에서는 `GetMultipleAsync`라는 비동기 메서드를 사용하여 지정된 시간(초) 동안 일시 중지하고 해당 시간(초)의 임의 배수인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-146">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="4c494-147">최대 지연 시간은 5초입니다. 값이 5보다 크면 <xref:System.ArgumentOutOfRangeException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-147">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="4c494-148">다음 예제와 같이 값 6이 `GetMultipleAsync` 메서드에 전달될 때 throw되는 예외는 `GetMultipleAsync` 메서드 실행이 시작된 후에 <xref:System.AggregateException>에 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-148">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

<span data-ttu-id="4c494-149">메서드 반복기와 마찬가지로, 이 예제의 코드를 리팩터링하여 비동기 메서드를 호출하기 전에 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-149">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="4c494-150">다음 예제의 출력에서 볼 수 있듯이, <xref:System.ArgumentOutOfRangeException>이 <xref:System.AggregateException>에 래핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-150">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a><span data-ttu-id="4c494-151">로컬 함수 및 람다 식</span><span class="sxs-lookup"><span data-stu-id="4c494-151">Local functions vs. lambda expressions</span></span>

<span data-ttu-id="4c494-152">얼핏 보기에 로컬 함수와 [람다 식](../../language-reference/operators/lambda-expressions.md)은 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-152">At first glance, local functions and [lambda expressions](../../language-reference/operators/lambda-expressions.md) are very similar.</span></span> <span data-ttu-id="4c494-153">대부분의 경우 람다 식과 로컬 함수 사용 간 선택은 스타일 및 개인 기본 설정의 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-153">In many cases, the choice between using lambda expressions and local functions is a matter of style and personal preference.</span></span> <span data-ttu-id="4c494-154">그러나 하나 또는 다른 것을 사용할 수 있는 것에 알고 있어야 하는 실제 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-154">However, there are real differences in where you can use one or the other that you should be aware of.</span></span>

<span data-ttu-id="4c494-155">계승 알고리즘의 로컬 함수 및 람다 식 구현 간의 차이점을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-155">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="4c494-156">먼저 로컬 함수를 사용하는 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-156">First the version using a local function:</span></span>

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

<span data-ttu-id="4c494-157">람다 식을 사용하는 버전과 해당 구현을 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4c494-157">Contrast that implementation with a version that uses lambda expressions:</span></span>

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

<span data-ttu-id="4c494-158">로컬 함수에는 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-158">The local functions have names.</span></span> <span data-ttu-id="4c494-159">람다 식은 `Func` 또는 `Action` 형식인 변수에 할당된 무명 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-159">The lambda expressions are anonymous methods that are assigned to variables that are `Func` or `Action` types.</span></span> <span data-ttu-id="4c494-160">로컬 함수를 선언하는 경우 인수 형식 및 반환 형식은 함수 선언의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-160">When you declare a local function, the argument types and return type are part of the function declaration.</span></span> <span data-ttu-id="4c494-161">람다 식 본문에 포함되는 대신 인수 형식 및 반환 형식은 람다 식의 변수 형식 선언의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-161">Instead of being part of the body of the lambda expression, the argument types and return type are part of the lambda expression's variable type declaration.</span></span> <span data-ttu-id="4c494-162">이러한 두 가지 차이점은 코드를 더 명확하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-162">Those two differences may result in clearer code.</span></span>

<span data-ttu-id="4c494-163">로컬 함수는 람다 식보다 한정된 할당에 대한 다양한 규칙을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-163">Local functions have different rules for definite assignment than lambda expressions.</span></span> <span data-ttu-id="4c494-164">로컬 함수 선언은 범위에 있는 모든 코드 위치에서 참조될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-164">A local function declaration can be referenced from any code location where it is in scope.</span></span> <span data-ttu-id="4c494-165">람다 식을 액세스하려면 대리자 변수에 할당해야 합니다(또는 람다 식을 참조하는 대리자를 통해 호출).</span><span class="sxs-lookup"><span data-stu-id="4c494-165">A lambda expression must be assigned to a delegate variable before it can be accessed (or called through the delegate referencing the lambda expression).</span></span> <span data-ttu-id="4c494-166">람다 식을 사용하는 버전은 람다 식 `nthFactorial`을 정의하기 전에 선언하고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-166">Notice that the version using the lambda expression must declare and initialize the lambda expression `nthFactorial` before defining it.</span></span> <span data-ttu-id="4c494-167">이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-167">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span> <span data-ttu-id="4c494-168">이러한 차이점은 로컬 함수를 사용하여 재귀 알고리즘을 쉽게 만들 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-168">These differences mean that recursive algorithms are easier to create using local functions.</span></span> <span data-ttu-id="4c494-169">자신을 호출하는 로컬 함수를 선언하고 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-169">You can declare and define a local function that calls itself.</span></span> <span data-ttu-id="4c494-170">람다 식을 동일한 람다 식을 참조하는 본문에 다시 할당하려면 선언하고, 기본 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-170">Lambda expressions must be declared, and assigned a default value before they can be re-assigned to a body that references the same lambda expression.</span></span>

<span data-ttu-id="4c494-171">한정된 할당 규칙은 로컬 함수 또는 람다 식에서 캡처되는 변수에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-171">Definite assignment rules also affect any variables that are captured by the local function or lambda expression.</span></span> <span data-ttu-id="4c494-172">로컬 함수와 람다 식 규칙 모두는 로컬 함수 또는 람다 식이 대리자로 변환되는 시점에 캡처된 변수를 한정적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-172">Both local functions and lambda expression rules demand that any captured variables are definitely assigned at the point when the local function or lambda expression is converted to a delegate.</span></span> <span data-ttu-id="4c494-173">차이점은 선언될 때 람다 식이 대리자로 변환된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-173">The difference is that lambda expressions are converted to delegates when they are declared.</span></span> <span data-ttu-id="4c494-174">로컬 함수는 대리자로 사용되는 경우에만 대리자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-174">Local functions are converted to delegates only when used as a delegate.</span></span> <span data-ttu-id="4c494-175">로컬 함수를 선언하고 메서드처럼 호출하여 참조하는 경우 대리자로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-175">If you declare a local function and only reference it by calling it like a method, it will not be converted to a delegate.</span></span> <span data-ttu-id="4c494-176">해당 규칙을 통해 포함된 범위 내의 모든 편리한 위치에서 로컬 함수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-176">That rule enables you to declare a local function at any convenient location in its enclosing scope.</span></span> <span data-ttu-id="4c494-177">모든 return 문 뒤의 부모 메서드 끝에 로컬 함수를 선언하는 것은 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-177">It's common to declare local functions at the end of the parent method, after any return statements.</span></span>

<span data-ttu-id="4c494-178">세 번째, 컴파일러는 로컬 함수가 포함된 범위에서 캡처된 변수를 한정적으로 할당할 수 있도록 하는 정적 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-178">Third, the compiler can perform static analysis that enables local functions to definitely assign captured variables in the enclosing scope.</span></span> <span data-ttu-id="4c494-179">다음 예제를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4c494-179">Consider this example:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="4c494-180">컴파일러는 `LocalFunction`에서 호출될 때 `y`를 한정적으로 할당하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-180">The compiler can determine that `LocalFunction` definitely assigns `y` when called.</span></span> <span data-ttu-id="4c494-181">`LocalFunction`은 `return` 문 전에 호출되므로 `y`는 `return` 문에서 한정적으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-181">Because `LocalFunction` is called before the `return` statement, `y` is definitely assigned at the `return` statement.</span></span>

<span data-ttu-id="4c494-182">예제 분석을 활성화하는 분석은 네 번째 차이점을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-182">The analysis that enables the example analysis enables the fourth difference.</span></span> <span data-ttu-id="4c494-183">해당 용도에 따라 로컬 함수는 람다 식에 항상 필요한 힙 할당을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-183">Depending on their use, local functions can avoid heap allocations that are always necessary for lambda expressions.</span></span> <span data-ttu-id="4c494-184">로컬 함수가 대리자로 변환되지 않고 로컬 함수에 의해 캡처된 변수가 대리자로 변환된 다른 람다 식 또는 로컬 함수에 의해 캡처되지 않는 경우 컴파일러는 힙 할당을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-184">If a local function is never converted to a delegate, and none of the variables captured by the local function is captured by other lambdas or local functions that are converted to delegates, the compiler can avoid heap allocations.</span></span>

<span data-ttu-id="4c494-185">다음 비동기 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="4c494-185">Consider this async example:</span></span>

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

<span data-ttu-id="4c494-186">이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-186">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="4c494-187">로컬 함수의 경우 클로저를 구현하는 개체는 `struct` 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-187">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="4c494-188">해당 구조체 형식은 로컬 함수에 참조로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-188">That struct type would be passed by reference to the local function.</span></span> <span data-ttu-id="4c494-189">구현에서 이러한 차이점은 할당에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-189">This difference in implementation would save on an allocation.</span></span>

<span data-ttu-id="4c494-190">람다 식에 필요한 인스턴스화는 추가 메모리 할당을 의미하며, 시간이 중요한 코드 경로에서 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-190">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time-critical code paths.</span></span> <span data-ttu-id="4c494-191">로컬 함수는 이러한 오버헤드를 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-191">Local functions do not incur this overhead.</span></span> <span data-ttu-id="4c494-192">위의 예제에서 로컬 함수 버전은 람다 식 버전보다 할당 수가 2개 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-192">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

> [!NOTE]
> <span data-ttu-id="4c494-193">이 메서드에 해당하는 로컬 함수는 클로저에 클래스도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-193">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="4c494-194">로컬 함수의 클로저가 `class` 또는 `struct`로 구현되는지 여부는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-194">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="4c494-195">로컬 함수는 `struct`를 사용할 수 있는 반면, 람다는 항상 `class`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-195">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="4c494-196">이 샘플에서 설명하지 않은 한 가지 최종 장점은 `yield return` 구문을 사용해서 로컬 함수를 반복기로 구현하여 값 시퀀스를 생성할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-196">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span> <span data-ttu-id="4c494-197">`yield return` 문은 람다 식에 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-197">The `yield return` statement is not allowed in lambda expressions.</span></span>

<span data-ttu-id="4c494-198">로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-198">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span> <span data-ttu-id="4c494-199">로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4c494-199">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c494-200">참조</span><span class="sxs-lookup"><span data-stu-id="4c494-200">See also</span></span>

- [<span data-ttu-id="4c494-201">메서드</span><span class="sxs-lookup"><span data-stu-id="4c494-201">Methods</span></span>](methods.md)
