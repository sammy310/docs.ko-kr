---
title: .NET의 예외 처리 및 Throw
description: .NET의 예외 처리 및 throw 방법에 대해 알아보세요. 예외는 .NET 작업이 애플리케이션에 대한 오류를 나타내는 방법입니다.
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
ms.openlocfilehash: 89d88e3128917125d1a09466ed4e230604d6978c
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662773"
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="239ca-104">.NET의 예외 처리 및 Throw</span><span class="sxs-lookup"><span data-stu-id="239ca-104">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="239ca-105">애플리케이션은 실행 중에 발생하는 오류를 일관된 방식으로 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-105">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="239ca-106">.NET에서는 일관된 방식으로 애플리케이션에 오류를 알리기 위한 모델을 제공합니다. .NET 작업은 예외를 throw하여 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-106">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="239ca-107">예외</span><span class="sxs-lookup"><span data-stu-id="239ca-107">Exceptions</span></span>

<span data-ttu-id="239ca-108">예외란 프로그램 실행 중 발생한 모든 오류 상태 또는 예기치 못한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-108">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="239ca-109">예외는 사용 중인 코드 또는 호출한 코드(예: 공유 라이브러리)의 오류, 사용 불가능한 운영 체제 리소스, 런타임에서 발생한 예기치 못한 상황(예: 확인할 수 없는 코드) 등에 의해 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-109">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that can't be verified), and so on.</span></span> <span data-ttu-id="239ca-110">사용 중인 애플리케이션이 이러한 일부 상황으로부터 복구될 수 있지만 복구될 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-110">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="239ca-111">대부분의 애플리케이션 예외로부터는 복구할 수 있지만 대부분의 런타임 예외로부터는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-111">Although you can recover from most application exceptions, you can't recover from most runtime exceptions.</span></span>

<span data-ttu-id="239ca-112">.NET에서 예외는 <xref:System.Exception?displayProperty=nameWithType> 클래스에서 상속되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-112">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="239ca-113">예외는 문제가 발생한 코드 영역에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-113">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="239ca-114">예외는 애플리케이션에서 해당 예외를 처리하거나 프로그램이 종료될 때까지 스택으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-114">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="239ca-115">예외 대 일반적인 오류 처리 방법</span><span class="sxs-lookup"><span data-stu-id="239ca-115">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="239ca-116">일반적으로 언어 오류 처리 모델은 오류를 감지하고 해당 오류 처리기를 찾는 언어 고유의 방식에 의존하거나 운영 체제에서 제공하는 오류 처리 메커니즘에 의존했습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-116">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="239ca-117">.NET에서 예외 처리를 구현하는 방법에는 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-117">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="239ca-118">예외 throw 및 처리는 .NET 프로그래밍 언어에서 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-118">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="239ca-119">예외 처리에 특정한 언어 구문이 필요하지는 않지만, 각 언어에서 고유한 구문을 정의할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-119">Doesn't require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="239ca-120">프로세스 및 컴퓨터 경계 간에도 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-120">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="239ca-121">예외 처리 코드를 애플리케이션에 추가하여 프로그램 안정성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-121">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="239ca-122">예외는 반환 코드 등의 다른 오류 알림 방법에 비해 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-122">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="239ca-123">예외가 throw되고 사용자가 처리하지 않을 경우 런타임에서 애플리케이션을 종료하기 때문에 오류가 발견되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-123">Failures don't go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="239ca-124">오류 반환 코드를 검사하지 못한 코드의 결과로 잘못된 값이 시스템 전체에 계속 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-124">Invalid values don't continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span>

## <a name="common-exceptions"></a><span data-ttu-id="239ca-125">일반적인 예외</span><span class="sxs-lookup"><span data-stu-id="239ca-125">Common exceptions</span></span>

<span data-ttu-id="239ca-126">다음 표에서는 몇 가지 일반적인 예외 및 예외가 발생할 수 있는 경우의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-126">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="239ca-127">예외 형식</span><span class="sxs-lookup"><span data-stu-id="239ca-127">Exception type</span></span> | <span data-ttu-id="239ca-128">설명</span><span class="sxs-lookup"><span data-stu-id="239ca-128">Description</span></span> | <span data-ttu-id="239ca-129">예제</span><span class="sxs-lookup"><span data-stu-id="239ca-129">Example</span></span> |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | <span data-ttu-id="239ca-130">모든 예외의 기본 클래스.</span><span class="sxs-lookup"><span data-stu-id="239ca-130">Base class for all exceptions.</span></span> | <span data-ttu-id="239ca-131">없음(이 예외의 파생된 클래스 사용).</span><span class="sxs-lookup"><span data-stu-id="239ca-131">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <span data-ttu-id="239ca-132">배열이 올바르지 않게 인덱싱된 경우에만 런타임에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-132">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="239ca-133">유효 범위를 벗어난 배열 인덱싱:</span><span class="sxs-lookup"><span data-stu-id="239ca-133">Indexing an array outside its valid range:</span></span> <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | <span data-ttu-id="239ca-134">null 개체가 참조되는 경우에만 런타임에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-134">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | <span data-ttu-id="239ca-135">잘못된 상태에 있는 경우에 메서드에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-135">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="239ca-136">기본 컬렉션에서 항목을 제거한 후 `Enumerator.MoveNext()` 호출.</span><span class="sxs-lookup"><span data-stu-id="239ca-136">Calling `Enumerator.MoveNext()` after removing an item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <span data-ttu-id="239ca-137">모든 인수 예외에 대한 기본 클래스.</span><span class="sxs-lookup"><span data-stu-id="239ca-137">Base class for all argument exceptions.</span></span> | <span data-ttu-id="239ca-138">없음(이 예외의 파생된 클래스 사용).</span><span class="sxs-lookup"><span data-stu-id="239ca-138">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <span data-ttu-id="239ca-139">인수에 Null을 허용하지 않는 메서드에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-139">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | <span data-ttu-id="239ca-140">인수가 지정된 범위에 있는지 확인하는 메서드에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="239ca-140">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="239ca-141">참조</span><span class="sxs-lookup"><span data-stu-id="239ca-141">See also</span></span>

- [<span data-ttu-id="239ca-142">Exception 클래스 및 속성</span><span class="sxs-lookup"><span data-stu-id="239ca-142">Exception Class and Properties</span></span>](exception-class-and-properties.md)
- [<span data-ttu-id="239ca-143">방법: Try-Catch 블록을 사용하여 예외 catch</span><span class="sxs-lookup"><span data-stu-id="239ca-143">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
- [<span data-ttu-id="239ca-144">방법: catch 블록에서 특정 예외 사용</span><span class="sxs-lookup"><span data-stu-id="239ca-144">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
- [<span data-ttu-id="239ca-145">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="239ca-145">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="239ca-146">방법: 사용자 정의 예외 만들기</span><span class="sxs-lookup"><span data-stu-id="239ca-146">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="239ca-147">사용자 필터 예외 처리기 사용</span><span class="sxs-lookup"><span data-stu-id="239ca-147">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
- [<span data-ttu-id="239ca-148">방법: Finally 블록 사용</span><span class="sxs-lookup"><span data-stu-id="239ca-148">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
- [<span data-ttu-id="239ca-149">COM Interop 예외 처리</span><span class="sxs-lookup"><span data-stu-id="239ca-149">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
- [<span data-ttu-id="239ca-150">예외에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="239ca-150">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)
- [<span data-ttu-id="239ca-151">모든 개발자가 런타임 예외에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="239ca-151">What Every Dev needs to Know About Exceptions in the Runtime</span></span>](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/exceptions.md)
