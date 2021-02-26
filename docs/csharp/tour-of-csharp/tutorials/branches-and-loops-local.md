---
title: 분기 및 루프 - C# 소개 자습서
description: 분기 및 루프에 관한 이 자습서에서는 C# 코드를 작성하여 문을 반복적으로 실행하기 위한 조건부 분기 및 루프를 지원하는 언어 구문을 살펴봅니다.
ms.date: 02/05/2021
ms.openlocfilehash: c609286f0c60432f9df7c1174f6fda699e2d0fbc
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100626644"
---
# <a name="learn-conditional-logic-with-branch-and-loop-statements"></a><span data-ttu-id="928c0-103">분기 및 루프 문이 포함된 조건부 논리 알아보기</span><span class="sxs-lookup"><span data-stu-id="928c0-103">Learn conditional logic with branch and loop statements</span></span>

<span data-ttu-id="928c0-104">이 자습서에서는 변수를 검사하고 해당 변수에 따라 실행 경로를 변경하는 코드를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-104">This tutorial teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="928c0-105">C# 코드를 작성하고 컴파일 및 실행 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="928c0-106">이 자습서에는 C#에서 분기 및 루프 구문을 살펴보는 일련의 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-106">The tutorial contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="928c0-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-107">These lessons teach you the fundamentals of the C# language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="928c0-108">사전 준비 사항</span><span class="sxs-lookup"><span data-stu-id="928c0-108">Prerequisites</span></span>

<span data-ttu-id="928c0-109">이 자습서에서는 컴퓨터가 로컬 개발용으로 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-109">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="928c0-110">Windows, Linux 또는 macOS에서 .NET CLI를 사용하여 애플리케이션을 만들고, 빌드하고, 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-110">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="928c0-111">Mac과 Windows에서 Visual Studio 2019를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-111">On Mac and Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="928c0-112">설정 지침은 [로컬 환경 설정](local-environment.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-112">For setup instructions, see [Set up your local environment](local-environment.md).</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="928c0-113">`if` 문을 사용하여 결정하기</span><span class="sxs-lookup"><span data-stu-id="928c0-113">Make decisions using the `if` statement</span></span>

<span data-ttu-id="928c0-114">*branches-tutorial* 이라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-114">Create a directory named *branches-tutorial*.</span></span> <span data-ttu-id="928c0-115">현재 디렉터리로 만들고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-115">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n BranchesAndLoops -o .
```

<span data-ttu-id="928c0-116">이 명령은 현재 디렉터리에 새 .NET 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-116">This command creates a new .NET console application in the current directory.</span></span> <span data-ttu-id="928c0-117">원하는 편집기에서 *Program.cs* 를 열고 콘텐츠를 다음 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-117">Open *Program.cs* in your favorite editor, and replace the contents with the following code:</span></span>

```csharp
using System;

int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="928c0-118">콘솔 창에 `dotnet run`을 입력하여 이 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-118">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="928c0-119">“The answer is greater than 10.”(답은 10보다 큽니다.)이라는 메시지가</span><span class="sxs-lookup"><span data-stu-id="928c0-119">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="928c0-120">콘솔에 출력되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-120">printed to your console.</span></span> <span data-ttu-id="928c0-121">합계가 10보다 작도록 `b`의 선언을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-121">Modify the declaration of `b` so that the sum is less than 10:</span></span>

```csharp
int b = 3;
```

<span data-ttu-id="928c0-122">`dotnet run`을 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-122">Type `dotnet run` again.</span></span> <span data-ttu-id="928c0-123">답이 10보다 작기 때문에 아무것도 출력되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-123">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="928c0-124">테스트하는 **조건** 은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-124">The **condition** you're testing is false.</span></span> <span data-ttu-id="928c0-125">`if` 문에 대해 가능한 분기 중 하나(true 분기)만 작성했기 때문에 실행할 코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-125">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="928c0-126">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-126">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="928c0-127">컴파일러가 오류를 찾아 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-127">The compiler will find and report the errors.</span></span> <span data-ttu-id="928c0-128">오류 출력 및 오류를 생성한 코드를 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-128">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="928c0-129">일반적으로 컴파일러 오류는 문제를 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-129">The compiler error can usually help you find the problem.</span></span>

<span data-ttu-id="928c0-130">이 첫 번째 샘플에서는 `if`의 기능과 부울 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-130">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="928c0-131">*부울* 은 `true` 또는 `false`의 두 값 중 하나를 가질 수 있는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-131">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="928c0-132">C#은 부울 변수에 대한 특수 형식 `bool`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-132">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="928c0-133">`if` 문은 `bool`의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-133">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="928c0-134">값이 `true`인 경우 `if` 뒤의 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-134">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="928c0-135">그렇지 않으면 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-135">Otherwise, it's skipped.</span></span> <span data-ttu-id="928c0-136">조건을 확인하고 해당 조건에 따라 문을 실행하는 이 프로세스는 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-136">This process of checking conditions and executing statements based on those conditions is powerful.</span></span>

## <a name="make-if-and-else-work-together"></a><span data-ttu-id="928c0-137">if와 else를 함께 사용하기</span><span class="sxs-lookup"><span data-stu-id="928c0-137">Make if and else work together</span></span>

<span data-ttu-id="928c0-138">true 분기와 false 분기의 여러 코드를 실행하려면 조건이 false일 때 실행되는 `else` 분기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-138">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="928c0-139">`else` 분기를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-139">Try an `else` branch.</span></span> <span data-ttu-id="928c0-140">아래 코드의 마지막 두 줄을 추가합니다(처음 네 줄은 이미 있음).</span><span class="sxs-lookup"><span data-stu-id="928c0-140">Add the last two lines in the code below (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="928c0-141">`else` 키워드 뒤의 문은 테스트하는 조건이 `false`인 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-141">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="928c0-142">`if` 및 `else`를 부울 조건과 결합하면 `true`와 `false` 조건을 모두 처리하는 데 필요한 모든 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-142">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="928c0-143">`if` 및 `else` 문 아래의 들여쓰기는 사용자가 보기 편하도록 하기 위함입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-143">The indentation under the `if` and `else` statements is for human readers.</span></span> <span data-ttu-id="928c0-144">C# 언어는 들여쓰기 또는 공백을 중요하게 취급하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-144">The C# language doesn't treat indentation or white space as significant.</span></span> <span data-ttu-id="928c0-145">`if` 또는 `else` 키워드 뒤의 문은 조건에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-145">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="928c0-146">이 자습서의 모든 샘플에서는 문의 제어 흐름을 기준으로 줄을 들여쓰는 일반적인 방법을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-146">All the samples in this tutorial follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="928c0-147">들여쓰기는 중요하지 않기 때문에 `{` 및 `}`를 사용하여 두 개 이상의 문이 조건부로 실행되는 블록의 일부가 되는 시기를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-147">Because indentation isn't significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="928c0-148">C# 프로그래머는 일반적으로 모든 `if` 및 `else` 절에서 중괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-148">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="928c0-149">다음 예제는 앞서 작성한 코드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-149">The following example is the same as the one you created.</span></span> <span data-ttu-id="928c0-150">다음 코드와 일치하도록 위의 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-150">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="928c0-151">이 자습서의 나머지 부분에서 코드 샘플에는 일반적인 방법에 따라 모두 중괄호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-151">Through the rest of this tutorial, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="928c0-152">더 복잡한 조건을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-152">You can test more complicated conditions.</span></span> <span data-ttu-id="928c0-153">지금까지 작성한 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-153">Add the following code after the code you've written so far:</span></span>

```csharp
int c = 4;
if ((a + b + c > 10) && (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not equal to the second");
}
```

<span data-ttu-id="928c0-154">`==` 기호는 같음을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-154">The `==` symbol tests for *equality*.</span></span> <span data-ttu-id="928c0-155">`==`을 사용하면 같음 테스트가 `a = 5`에서 확인한 할당과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-155">Using `==` distinguishes the test for equality from assignment, which you saw in `a = 5`.</span></span>

<span data-ttu-id="928c0-156">`&&`는 “and”를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-156">The `&&` represents "and".</span></span> <span data-ttu-id="928c0-157">true 분기에서 문을 실행하려면 두 조건이 모두 true여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-157">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="928c0-158">이러한 예제에서는 `{` 및 `}`로 문을 묶으면 각 조건부 분기에 여러 문을 가질 수 있음도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-158">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span> <span data-ttu-id="928c0-159">`||`을 사용하여 “or”를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-159">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="928c0-160">지금까지 작성한 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-160">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not equal to the second");
}
```

<span data-ttu-id="928c0-161">`a`, `b` 및 `c`의 값을 수정하고 `&&` 및 `||` 간에 전환하여 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-161">Modify the values of `a`, `b`, and `c` and switch between `&&` and `||` to explore.</span></span> <span data-ttu-id="928c0-162">`&&` 및 `||` 연산자가 어떻게 작동하는지 더 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-162">You'll gain more understanding of how the `&&` and `||` operators work.</span></span>

<span data-ttu-id="928c0-163">첫 번째 단계를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-163">You've finished the first step.</span></span> <span data-ttu-id="928c0-164">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-164">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="928c0-165">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-165">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="928c0-166">`ExploreIf()`라는 메서드에 기존 코드를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-166">Put the existing code in a method called `ExploreIf()`.</span></span> <span data-ttu-id="928c0-167">프로그램 위에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-167">Call it from the top of your program.</span></span> <span data-ttu-id="928c0-168">변경을 완료하면 코드가 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-168">When you finished those changes, your code should look like the following:</span></span>

```csharp
using System;

ExploreIf();

void ExploreIf()
{
    int a = 5;
    int b = 3;
    if (a + b > 10)
    {
        Console.WriteLine("The answer is greater than 10");
    }
    else
    {
        Console.WriteLine("The answer is not greater than 10");
    }

    int c = 4;
    if ((a + b + c > 10) && (a > b))
    {
        Console.WriteLine("The answer is greater than 10");
        Console.WriteLine("And the first number is greater than the second");
    }
    else
    {
        Console.WriteLine("The answer is not greater than 10");
        Console.WriteLine("Or the first number is not greater than the second");
    }

    if ((a + b + c > 10) || (a > b))
    {
        Console.WriteLine("The answer is greater than 10");
        Console.WriteLine("Or the first number is greater than the second");
    }
    else
    {
        Console.WriteLine("The answer is not greater than 10");
        Console.WriteLine("And the first number is not greater than the second");
    }
}
```

<span data-ttu-id="928c0-169">`ExploreIf()`에 대한 호출을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-169">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="928c0-170">그러면 이 섹션에서 작업할 때 출력이 덜 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-170">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="928c0-171">`//`는 C#에서 **주석** 을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-171">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="928c0-172">주석은 소스 코드에 유지하되 코드로 실행하지는 않으려는 모든 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-172">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="928c0-173">컴파일러는 주석에서 실행 코드를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-173">The compiler doesn't generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="928c0-174">루프를 사용하여 작업 반복</span><span class="sxs-lookup"><span data-stu-id="928c0-174">Use loops to repeat operations</span></span>

<span data-ttu-id="928c0-175">이 섹션에서는 **루프** 를 사용하여 문을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-175">In this section, you use **loops** to repeat statements.</span></span> <span data-ttu-id="928c0-176">`ExploreIf` 호출 후 이 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-176">Add this code after the call to `ExploreIf`:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="928c0-177">`while` 문은 조건을 검사하고 `while` 뒤에 있는 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-177">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="928c0-178">조건이 false가 될 때까지 반복적으로 조건을 확인하고 해당 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-178">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="928c0-179">이 예제에서는 다른 새 연산자가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-179">There's one other new operator in this example.</span></span> <span data-ttu-id="928c0-180">`counter` 변수 뒤의 `++`는 **증가** 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-180">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="928c0-181">이 연산자는 `counter`의 값에 1을 더하고 해당 값을 `counter` 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-181">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="928c0-182">코드를 실행할 때 `while` 루프 조건이 false로 바뀌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-182">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="928c0-183">그러하지 않으면 프로그램이 종료되지 않는 **무한 루프** 를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-183">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="928c0-184">이러한 내용이 이 샘플에 설명되어 있지는 않은데, **CTRL-C** 또는 다른 방법을 사용하여 프로그램을 강제 종료해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-184">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="928c0-185">`while` 루프는 `while` 뒤에 코드를 실행하기 전에 조건을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-185">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="928c0-186">`do` ... `while` 루프는 코드를 먼저 실행한 후 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-186">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="928c0-187">*do while* 루프는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-187">The *do while* loop is shown in the following code:</span></span>

```csharp
int counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="928c0-188">이 `do` 루프 및 이전 `while` 루프는 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-188">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="928c0-189">for 루프 작업</span><span class="sxs-lookup"><span data-stu-id="928c0-189">Work with the for loop</span></span>

<span data-ttu-id="928c0-190">C#에서는 일반적으로 **for** 루프가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-190">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="928c0-191">다음 코드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-191">Try this code:</span></span>

```csharp
for (int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
}
```

<span data-ttu-id="928c0-192">이전 코드는 `while` 루프 및 이미 사용한 `do` 루프와 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-192">The previous code does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="928c0-193">`for` 문에는 작동 방식을 제어하는 세 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-193">The `for` statement has three parts that control how it works.</span></span>

<span data-ttu-id="928c0-194">첫 번째 부분은 **for 이니셜라이저입니다**. `int index = 0;`은 `index`가 루프 변수임을 선언하고 첫 번째 값을 `0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-194">The first part is the **for initializer**: `int index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="928c0-195">중간 부분은 **for 조건입니다**. `index < 10`은 이 `for` 루프가 카운터 값이 10보다 작으면 계속 실행됨을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-195">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="928c0-196">마지막 부분은 **for 반복기입니다**. `index++`는 `for` 문 다음의 블록을 실행한 후 루프 변수를 수정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-196">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="928c0-197">여기서 `index`는 블록이 실행될 때마다 1씩 증가하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-197">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="928c0-198">직접 실험해 보세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-198">Experiment yourself.</span></span> <span data-ttu-id="928c0-199">다음 변형을 각각 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-199">Try each of the following variations:</span></span>

- <span data-ttu-id="928c0-200">다른 값으로 시작하도록 이니셜라이저를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-200">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="928c0-201">다른 값에서 중지하도록 조건을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-201">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="928c0-202">완료하면, 학습한 내용을 토대로 직접 코드를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-202">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

<span data-ttu-id="928c0-203">이 자습서에서 다루지 않은 다른 반복 문이 하나 있는데, `foreach` 문이 그것입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-203">There's one other looping statement that isn't covered in this tutorial: the `foreach` statement.</span></span> <span data-ttu-id="928c0-204">`foreach` 문은 항목 시퀀스의 모든 항목에 대해 해당 문을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-204">The `foreach` statement repeats its statement for every item in a sequence of items.</span></span> <span data-ttu-id="928c0-205">컬렉션과 함께 사용되는 경우가 가장 많으므로 다음 자습서에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-205">It's most often used with *collections*, so it's covered in the next tutorial.</span></span>

## <a name="created-nested-loops"></a><span data-ttu-id="928c0-206">중첩 루프 만들기</span><span class="sxs-lookup"><span data-stu-id="928c0-206">Created nested loops</span></span>

<span data-ttu-id="928c0-207">`while`, `do` 또는 `for` 루프를 다른 루프 내에 중첩하여 내부 루프에 있는 각 항목과 외부 루프에 있는 각 항목의 조합을 사용하여 행렬을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-207">A `while`, `do`, or `for` loop can be nested inside another loop to create a matrix using the combination of each item in the outer loop with each item in the inner loop.</span></span> <span data-ttu-id="928c0-208">행과 열을 나타내는 영숫자 쌍 세트를 작성하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-208">Let's do that to build a set of alphanumeric pairs to represent rows and columns.</span></span>

<span data-ttu-id="928c0-209">하나의 `for` 루프가 행을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-209">One `for` loop can generate the rows:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    Console.WriteLine($"The row is {row}");
}
```

<span data-ttu-id="928c0-210">다른 루프는 열을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-210">Another loop can generate the columns:</span></span>

```csharp
for (char column = 'a'; column < 'k'; column++)
{
    Console.WriteLine($"The column is {column}");
}
```

<span data-ttu-id="928c0-211">한 루프를 다른 루프 안에 중첩하여 쌍을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-211">You can nest one loop inside the other to form pairs:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    for (char column = 'a'; column < 'k'; column++)
    {
        Console.WriteLine($"The cell is ({row}, {column})");
    }
}
```

<span data-ttu-id="928c0-212">내부 루프의 전체 실행마다 외부 루프가 한 번씩 증가하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-212">You can see that the outer loop increments once for each full run of the inner loop.</span></span> <span data-ttu-id="928c0-213">행과 열 중첩을 반대로 바꾸고 변경 내용을 직접 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-213">Reverse the row and column nesting, and see the changes for yourself.</span></span> <span data-ttu-id="928c0-214">완료되면 `ExploreLoops()`라는 메서드에 이 섹션의 코드를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-214">When you're done, place the code from this section in a method called `ExploreLoops()`.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="928c0-215">분기 및 루프 결합</span><span class="sxs-lookup"><span data-stu-id="928c0-215">Combine branches and loops</span></span>

<span data-ttu-id="928c0-216">이제 C# 언어로 된 `if` 문과 루프 구조를 확인했습니다. C# 코드를 작성하여 3으로 나눌 수 있는, 1에서 20까지의 모든 정수의 합계를 찾을 수 있는지 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-216">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="928c0-217">다음은 몇 가지 힌트입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-217">Here are a few hints:</span></span>

- <span data-ttu-id="928c0-218">`%` 연산자는 나누기 연산의 나머지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-218">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="928c0-219">`if` 문은 숫자가 합계의 일부여야 하는지를 확인하는 조건을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-219">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="928c0-220">`for` 루프는 1에서 20까지의 모든 숫자에 대해 일련의 단계를 반복하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-220">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="928c0-221">직접 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-221">Try it yourself.</span></span> <span data-ttu-id="928c0-222">그런 다음 어떻게 했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-222">Then check how you did.</span></span> <span data-ttu-id="928c0-223">답으로 63을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-223">You should get 63 for an answer.</span></span> <span data-ttu-id="928c0-224">[GitHub에서 완성된 코드를 보고](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54) 가능한 한 가지 답을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-224">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="928c0-225">“분기 및 루프” 자습서를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-225">You've completed the "branches and loops" tutorial.</span></span>

<span data-ttu-id="928c0-226">자체 개발 환경에서 [배열 및 컬렉션](arrays-and-collections.md) 자습서를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-226">You can continue with the [Arrays and collections](arrays-and-collections.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="928c0-227">다음 문서에서 이러한 개념을 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-227">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="928c0-228">If 및 else 문</span><span class="sxs-lookup"><span data-stu-id="928c0-228">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="928c0-229">While 문</span><span class="sxs-lookup"><span data-stu-id="928c0-229">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="928c0-230">Do 문</span><span class="sxs-lookup"><span data-stu-id="928c0-230">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="928c0-231">For 문</span><span class="sxs-lookup"><span data-stu-id="928c0-231">For statement</span></span>](../../language-reference/keywords/for.md)
