---
title: '리소스 관리: Use 키워드'
description: 리소스의 초기화 F# 및 해제를 제어할 수 있는 ' use ' 키워드 및 ' using ' 함수에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627263"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="176f4-103">리소스 관리: Use 키워드</span><span class="sxs-lookup"><span data-stu-id="176f4-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="176f4-104">이 항목에서는 리소스의 `use` 초기화 및 `using` 해제를 제어할 수 있는 키워드 및 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="176f4-105">리소스</span><span class="sxs-lookup"><span data-stu-id="176f4-105">Resources</span></span>

<span data-ttu-id="176f4-106">*리소스* 라는 용어는 여러 가지 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="176f4-107">예, 리소스는 응용 프로그램에서 사용 하는 데이터 (예: 문자열, 그래픽 등) 일 수 있지만,이 컨텍스트에서 *리소스* 는 그래픽 장치 컨텍스트, 파일 핸들, 네트워크, 데이터베이스 등의 소프트웨어 또는 운영 체제 리소스를 참조 합니다. 연결, 대기 핸들 등의 동시성 개체 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="176f4-108">응용 프로그램에서 이러한 리소스를 사용 하는 경우 다른 응용 프로그램에 제공 될 수 있도록 운영 체제 또는 다른 리소스 공급자의 리소스를 획득 한 다음 나중에 해당 리소스를 풀에 릴리스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="176f4-109">응용 프로그램에서 리소스를 공용 풀로 다시 해제 하지 않을 때 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="176f4-110">리소스 관리</span><span class="sxs-lookup"><span data-stu-id="176f4-110">Managing Resources</span></span>

<span data-ttu-id="176f4-111">응용 프로그램에서 리소스를 효율적이 고 체계적으로 관리 하려면 예측 가능한 방식으로 리소스를 즉시 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="176f4-112">.NET Framework는 인터페이스를 `System.IDisposable` 제공 하 여이 작업을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="176f4-113">을 구현 `System.IDisposable` 하는 형식에 `System.IDisposable.Dispose` 는 리소스가 올바르게 해제 되는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="176f4-114">잘 작성 된 응용 프로그램은 `System.IDisposable.Dispose` 제한 된 리소스를 보유 하는 개체가 더 이상 필요 하지 않을 때 즉시 호출 되도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="176f4-115">다행히 대부분의 .NET 언어는이를 용이 하 게 하는 F# 지원을 제공 하며, 예외는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="176f4-116">Dispose 패턴 `use` 을 지 원하는 두 가지 유용한 언어 구문은 바인딩과 `using` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="176f4-117">바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="176f4-117">use Binding</span></span>

<span data-ttu-id="176f4-118">키워드의 형식은 `let` 바인딩의 형식과 비슷합니다. `use`</span><span class="sxs-lookup"><span data-stu-id="176f4-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="176f4-119">*값* = *식* 사용</span><span class="sxs-lookup"><span data-stu-id="176f4-119">use *value* = *expression*</span></span>

<span data-ttu-id="176f4-120">`let` 바인딩과 동일한 기능을 제공 하지만 값이 범위를 벗어나면 값 `Dispose` 에 대 한 호출을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="176f4-121">컴파일러는 값에 null 검사를 삽입 하므로 값이 인 `null`경우에 대 `Dispose` 한 호출이 시도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="176f4-122">다음 예제에서는 키워드를 `use` 사용 하 여 파일을 자동으로 닫는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> <span data-ttu-id="176f4-123">계산 식에 `use` 를 사용할 수 있습니다 .이 경우 사용자 지정 된 버전 `use` 의 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="176f4-124">자세한 내용은 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md)및 [계산 식](computation-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="176f4-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="176f4-125">using 함수</span><span class="sxs-lookup"><span data-stu-id="176f4-125">using Function</span></span>

<span data-ttu-id="176f4-126">함수 `using` 는 다음과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-126">The `using` function has the following form:</span></span>

<span data-ttu-id="176f4-127">`using`(*expression1*) *함수 또는-람다*</span><span class="sxs-lookup"><span data-stu-id="176f4-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="176f4-128">식에서 expression1는 삭제 해야 하는 개체를 만듭니다. `using`</span><span class="sxs-lookup"><span data-stu-id="176f4-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="176f4-129">*Expression1* (삭제 해야 하는 개체)의 결과는 인수, *값*, *함수 또는 람다*가 됩니다 .이 함수는에 의해 *생성 된 값과 일치 하는 형식에 대해 남아 있는 단일 인수를 필요로 하는 함수입니다. expression1*또는 해당 형식의 인수를 필요로 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="176f4-130">함수 실행이 끝날 때 런타임은 리소스를 호출 `Dispose` 하 고 해제 합니다 .이 경우 값이이 `null`고, 그렇지 않으면 Dispose에 대 한 호출이 시도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="176f4-131">다음 예에서는 람다 식이 `using` 있는 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="176f4-132">다음 예에서는 함수를 `using` 사용 하는 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="176f4-133">함수는 일부 인수를 이미 적용 한 함수 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="176f4-134">다음 코드 예제에서는 이 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-134">The following code example demonstrates this.</span></span> <span data-ttu-id="176f4-135">문자열이 `XYZ`포함 된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="176f4-136">`using` 함수와`use` 바인딩은 거의 동일한 방식으로 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="176f4-137">키워드 `using` 는를 호출 하는 경우 `Dispose` 에 대 한 더 많은 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="176f4-138">를 `using` `use` `Dispose` 사용 하는 경우은 함수 또는 람다 식의 끝에서 호출 됩니다. 키워드를 사용 하는 경우 포함 하는 코드 블록의 끝에서가 호출 됩니다. `Dispose`</span><span class="sxs-lookup"><span data-stu-id="176f4-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="176f4-139">일반적으로 `use` `using` 함수 대신를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="176f4-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="176f4-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="176f4-140">See also</span></span>

- [<span data-ttu-id="176f4-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="176f4-141">F# Language Reference</span></span>](index.md)
