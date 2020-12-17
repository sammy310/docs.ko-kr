---
title: 예외 처리 - C# 프로그래밍 가이드
description: 예외 처리에 대해 알아봅니다. try-catch, try-finally 및 try-catch-finally 문 예제를 살펴봅니다.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: fabf1413ba498232e67f45460195fe96e25fab0a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110197"
---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="71ebb-104">예외 처리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="71ebb-104">Exception Handling (C# Programming Guide)</span></span>

<span data-ttu-id="71ebb-105">[try](../../language-reference/keywords/try-catch.md) 블록은 C# 프로그래머가 예외의 영향을 받을 수 있는 코드를 분할하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-105">A [try](../../language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="71ebb-106">연결된 [catch](../../language-reference/keywords/try-catch.md) 블록은 결과 예외를 처리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-106">Associated [catch](../../language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="71ebb-107">[finally](../../language-reference/keywords/try-finally.md) 블록에는 `try` 블록에서 할당되는 리소스 해제와 같이 `try` 블록에서 예외가 throw되는지 여부와 관계없이 실행되는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-107">A [finally](../../language-reference/keywords/try-finally.md) block contains code that is run whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="71ebb-108">`try` 블록에는 하나 이상의 연결된 `catch` 블록, `finally` 블록 또는 둘 다가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-108">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>

<span data-ttu-id="71ebb-109">다음 예제에서는 `try-catch` 문, `try-finally` 문 및 `try-catch-finally` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-109">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryFinallyStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchFinallyStructure":::

<span data-ttu-id="71ebb-110">`try` 블록에 `catch` 또는 `finally` 블록이 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-110">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>

## <a name="catch-blocks"></a><span data-ttu-id="71ebb-111">catch 블록</span><span class="sxs-lookup"><span data-stu-id="71ebb-111">Catch Blocks</span></span>

<span data-ttu-id="71ebb-112">`catch` 블록에서는 catch할 예외의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-112">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="71ebb-113">형식 사양을 *예외 필터* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-113">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="71ebb-114">예외 형식은 <xref:System.Exception>에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-114">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="71ebb-115">일반적으로 `try` 블록에서 throw될 수 있는 모든 예외를 처리하는 방법을 알고 있거나 `catch` 블록의 끝에 [throw](../../language-reference/keywords/throw.md) 문을 포함한 경우가 아니라면 <xref:System.Exception>을 예외 필터로 지정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="71ebb-115">In general, don't specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you've included a [throw](../../language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>

<span data-ttu-id="71ebb-116">다른 예외 클래스를 사용하는 여러 `catch` 블록을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-116">Multiple `catch` blocks with different exception classes can be chained together.</span></span> <span data-ttu-id="71ebb-117">`catch` 블록은 코드의 위에서 아래로 계산되지만 throw되는 각 예외에 대해 하나의 `catch` 블록만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-117">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="71ebb-118">throw된 예외의 정확한 형식이나 기본 클래스를 지정하는 첫 번째 `catch` 블록이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-118">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="71ebb-119">`catch` 블록에서 일치하는 예외 클래스를 지정하지 않으면 `catch` 블록이 문에 있는 경우 어느 형식도 없는 블록이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-119">If no `catch` block specifies a matching exception class, a `catch` block that doesn't have any type is selected, if one is present in the statement.</span></span> <span data-ttu-id="71ebb-120">먼저 가장 구체적인(즉, 최다 파생) 예외 클래스를 사용하여 `catch` 블록을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-120">It's important to position `catch` blocks with the most specific (that is, the most derived) exception classes first.</span></span>

<span data-ttu-id="71ebb-121">다음 조건을 충족하는 경우 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-121">Catch exceptions when the following conditions are true:</span></span>

- <span data-ttu-id="71ebb-122">예외가 throw되는 이유를 충분히 이해하고 있으면 <xref:System.IO.FileNotFoundException> 개체를 catch할 때 새 파일 이름을 입력하라는 메시지를 사용자에게 표시하는 경우처럼 구체적인 복구를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-122">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>
- <span data-ttu-id="71ebb-123">보다 구체적인 새 예외를 생성하고 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-123">You can create and throw a new, more specific exception.</span></span>
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowMoreSpecificException":::
- <span data-ttu-id="71ebb-124">추가 처리를 위해 예외를 전달하기 전에 부분적으로 처리하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-124">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="71ebb-125">다음 예제에서 `catch` 블록은 예외를 다시 throw하기 전에 오류 로그에 항목을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-125">In the following example, a `catch` block is used to add an entry to an error log before rethrowing the exception.</span></span>
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="RethrowError":::

<span data-ttu-id="71ebb-126">‘예외 필터’를 지정하여 catch 절에 부울 식을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-126">You can also specify *exception filters* to add a boolean expression to a catch clause.</span></span> <span data-ttu-id="71ebb-127">이렇게 하면 해당 조건이 true인 경우에만 특정 catch 절이 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-127">These indicate that a specific catch clause matches only when that condition is true.</span></span> <span data-ttu-id="71ebb-128">다음 예제에서는 두 catch 절에서 같은 예외 클래스를 사용하지만 추가 조건을 확인하여 다른 오류 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-128">In the following example, both catch clauses use the same exception class, but an additional condition is checked to create a different error message:</span></span>

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="DemonstrateExceptionFilter":::

<span data-ttu-id="71ebb-129">항상 `false`를 반환하는 예외 필터를 사용하여 모든 예외를 검사하지만 처리하지는 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-129">An exception filter that always returns `false` can be used to examine all exceptions but not process them.</span></span> <span data-ttu-id="71ebb-130">일반적인 용도는 예외를 기록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-130">A typical use is to log exceptions:</span></span>

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="ShowExceptionFilter":::

<span data-ttu-id="71ebb-131">`LogException` 메서드는 항상 `false`를 반환하므로 이 예외 필터를 사용하는 `catch` 절 중 어느 것도 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-131">The `LogException` method always returns `false`, no `catch` clause using this exception filter matches.</span></span> <span data-ttu-id="71ebb-132">catch 절은 <xref:System.Exception?displayProperty=nameWithType>을 사용하는 범용일 수 있으며 이후 절이 더 구체적인 예외 클래스를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-132">The catch clause can be general, using <xref:System.Exception?displayProperty=nameWithType>, and later clauses can process more specific exception classes.</span></span>

## <a name="finally-blocks"></a><span data-ttu-id="71ebb-133">Finally 블록</span><span class="sxs-lookup"><span data-stu-id="71ebb-133">Finally Blocks</span></span>

<span data-ttu-id="71ebb-134">`finally` 블록에서는 `try` 블록에서 수행된 작업을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-134">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="71ebb-135">`finally` 블록이 있는 경우 `try` 블록 및 일치하는 모든 `catch` 블록 다음에 마지막으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-135">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="71ebb-136">`finally` 블록은 예외가 throw되었는지 또는 예외 형식과 일치하는 `catch` 블록이 있는지와 관계없이 항상 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-136">A `finally` block always runs, whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>

<span data-ttu-id="71ebb-137">`finally` 블록은 런타임의 가비지 수집기가 개체를 종료할 때까지 기다리지 않고 파일 스트림, 데이터베이스 연결, 그래픽 핸들 등의 리소스를 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-137">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="71ebb-138">자세한 내용은 [using 문](../../language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71ebb-138">For more information See the [using Statement](../../language-reference/keywords/using-statement.md).</span></span>

<span data-ttu-id="71ebb-139">다음 예제에서는 `finally` 블록을 사용하여 `try` 블록에서 연 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-139">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="71ebb-140">파일을 닫기 전에 파일 핸들의 상태를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-140">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="71ebb-141">`try` 블록에서 파일을 열 수 없는 경우 파일 핸들은 값이 `null`이며 `finally` 블록은 파일을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-141">If the `try` block can't open the file, the file handle still has the value `null` and the `finally` block doesn't try to close it.</span></span> <span data-ttu-id="71ebb-142">대신 `try` 블록에서 파일을 연 경우 `finally` 블록에서 열려 있는 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-142">Instead, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CleanupIfNotNull":::

## <a name="c-language-specification"></a><span data-ttu-id="71ebb-143">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="71ebb-143">C# Language Specification</span></span>

<span data-ttu-id="71ebb-144">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [예외](~/_csharplang/spec/exceptions.md) 및 [try 문](~/_csharplang/spec/statements.md#the-try-statement)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71ebb-144">For more information, see [Exceptions](~/_csharplang/spec/exceptions.md) and [The try statement](~/_csharplang/spec/statements.md#the-try-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="71ebb-145">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ebb-145">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71ebb-146">참조</span><span class="sxs-lookup"><span data-stu-id="71ebb-146">See also</span></span>

- [<span data-ttu-id="71ebb-147">C# 참조</span><span class="sxs-lookup"><span data-stu-id="71ebb-147">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="71ebb-148">try-catch</span><span class="sxs-lookup"><span data-stu-id="71ebb-148">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="71ebb-149">try-finally</span><span class="sxs-lookup"><span data-stu-id="71ebb-149">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="71ebb-150">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="71ebb-150">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
- [<span data-ttu-id="71ebb-151">using 문</span><span class="sxs-lookup"><span data-stu-id="71ebb-151">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
