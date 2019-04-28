---
title: '리소스 관리: Use 키워드'
description: 알아봅니다는 F# 키워드 'use' 및 'using' 함수를 초기화 및 리소스의 해제를 제어할 수 있습니다.
ms.date: 05/16/2016
ms.openlocfilehash: 127877a3823faade9bc3c6aefea655c86cc348e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770489"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="c7960-103">리소스 관리: Use 키워드</span><span class="sxs-lookup"><span data-stu-id="c7960-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="c7960-104">키워드에 설명 `use` 하며 `using` 함수, 초기화 및 리소스의 해제를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="c7960-105">자료</span><span class="sxs-lookup"><span data-stu-id="c7960-105">Resources</span></span>

<span data-ttu-id="c7960-106">용어 *리소스* 둘 이상의 방식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="c7960-107">예, 리소스와 같은 문자열, 그래픽 및 like, 하지만이 컨텍스트에서 응용 프로그램을 사용 하는 데이터를 수 있습니다 *리소스* 그래픽 장치 컨텍스트, 파일 핸들, 네트워크와 같은 소프트웨어 또는 운영 체제 리소스에 대 한 참조 및 데이터베이스 연결, 대기 핸들 등과 같은 동시성 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="c7960-108">응용 프로그램에서 이러한 리소스를 사용 하 여 운영 체제 또는 다른 응용 프로그램에 제공 될 수 있도록 풀에 리소스의 이후 릴리스를 뒤에 다른 리소스 공급자에서 리소스를 확보를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="c7960-109">문제는 응용 프로그램은 공용 풀으로 리소스를 해제 하지 않아 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="c7960-110">리소스 관리</span><span class="sxs-lookup"><span data-stu-id="c7960-110">Managing Resources</span></span>

<span data-ttu-id="c7960-111">책임 지 고 효율적으로 응용 프로그램에서 리소스를 관리 하려면 신속 하 게 하 고 예측 가능한 방식으로 리소스를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="c7960-112">.NET Framework를 사용 하면 제공 하 여이 작업을 수행 합니다 `System.IDisposable` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="c7960-113">구현 하는 형식을 `System.IDisposable` 에 `System.IDisposable.Dispose` 메서드를 올바르게 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="c7960-114">응용 프로그램을 잘 작성 된 `System.IDisposable.Dispose` 제한 된 리소스를 보유 하는 모든 개체에 더 이상 필요 없는 경우 즉시 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="c7960-115">다행 스럽게도 대부분의.NET 언어 제공이 쉽게 지원 및 F# 도 예외가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="c7960-116">Dispose 패턴을 지 원하는 두 가지 유용한 언어 구문이: 합니다 `use` 바인딩 및 `using` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="c7960-117">바인딩을 사용합니다</span><span class="sxs-lookup"><span data-stu-id="c7960-117">use Binding</span></span>

<span data-ttu-id="c7960-118">합니다 `use` 키워드에는 유사한 폼을는 `let` 바인딩:</span><span class="sxs-lookup"><span data-stu-id="c7960-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="c7960-119">use *value* = *expression*</span><span class="sxs-lookup"><span data-stu-id="c7960-119">use *value* = *expression*</span></span>

<span data-ttu-id="c7960-120">와 동일한 기능을 제공 하는 `let` 바인딩 하지만 호출을 추가 합니다 `Dispose` 값 범위를 벗어날 때 값에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="c7960-121">컴파일러 경우 값은 값의 null 검사를 삽입 하는 참고 `null`에 대 한 호출 `Dispose` 시도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="c7960-122">다음 예제에서는 파일을 사용 하 여 자동으로 종결 하는 방법의 `use` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> <span data-ttu-id="c7960-123">사용할 수 있습니다 `use` 계산 식에 사용자 지정된 버전의 경우는 `use` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="c7960-124">자세한 내용은 [시퀀스](sequences.md)를 [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="c7960-125">함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="c7960-125">using Function</span></span>

<span data-ttu-id="c7960-126">`using` 함수는 다음과 같은 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-126">The `using` function has the following form:</span></span>

<span data-ttu-id="c7960-127">`using` (*expression1*) *함수 또는 람다*</span><span class="sxs-lookup"><span data-stu-id="c7960-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="c7960-128">에 `using` 식을 *expression1* 삭제 해야 하는 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="c7960-129">결과인 *expression1* (삭제 해야 하는 개체)가 인수로 *값*를 *함수 또는 람다*, 단일 필요한 함수 중 하나는 생성 된 값과 일치 하는 형식 인수의 남은 *expression1*, 또는 해당 형식의 인수를 필요로 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="c7960-130">런타임에서 호출 된 함수의 실행의 끝 `Dispose` 리소스를 해제 (값이 아니라면 `null`, Dispose에 대 한 호출 시도 하지는 경우).</span><span class="sxs-lookup"><span data-stu-id="c7960-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="c7960-131">다음 예제는 `using` 람다 식 사용 하 여 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="c7960-132">에서는 다음 예제는 `using` 함수를 사용 하 여 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="c7960-133">일부 인수가 이미 적용 하는 함수 일 수는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="c7960-134">다음 코드 예제에서는 이 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-134">The following code example demonstrates this.</span></span> <span data-ttu-id="c7960-135">문자열을 포함 하는 파일을 만들면 `XYZ`합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="c7960-136">합니다 `using` 함수 및 `use` 바인딩은 거의 같은 방식으로 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="c7960-137">합니다 `using` 키워드 좀 더 잘 제어할 때 `Dispose` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="c7960-138">사용 하는 경우 `using`, `Dispose` 사용 하는 경우, 함수 또는 람다 식의 끝에서 호출 되는 `use` 키워드를 `Dispose` 포함 하는 코드 블록의 끝에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="c7960-139">일반적으로 사용 하려는 `use` of를 `using` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c7960-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7960-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="c7960-140">See also</span></span>

- [<span data-ttu-id="c7960-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c7960-141">F# Language Reference</span></span>](index.md)