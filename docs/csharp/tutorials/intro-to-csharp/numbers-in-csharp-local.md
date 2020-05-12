---
title: C#의 숫자 - C# 소개 자습서
description: 숫자 형식, 해당 사용, 속성 및 메서드를 살펴보면서 C#을 학습합니다.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794613"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="7f4f9-103">C\#에서 정수 및 부동 소수점 수 조작</span><span class="sxs-lookup"><span data-stu-id="7f4f9-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="7f4f9-104">이 자습서에서는 C#의 숫자 형식을 대화형으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="7f4f9-105">작은 양의 코드를 작성한 다음 해당 코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="7f4f9-106">이 자습서에는 C#의 숫자 및 수학 연산을 살펴보는 일련의 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="7f4f9-107">이러한 단원에서는 C# 언어의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="7f4f9-108">이 자습서에서는 개발에 사용할 수 있는 머신이 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="7f4f9-109">.NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)에는 Windows, Linux 또는 macOS의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="7f4f9-110">사용할 명령에 대한 간단한 개요는 [개발 도구 익히기](local-environment.md)에 자세한 정보의 링크와 함께 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="7f4f9-111">정수 계산 살펴보기</span><span class="sxs-lookup"><span data-stu-id="7f4f9-111">Explore integer math</span></span>

<span data-ttu-id="7f4f9-112">*numbers-quickstart*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="7f4f9-113">현재 디렉터리로 만들고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="7f4f9-114">원하는 편집기에서 *Program.cs*를 열고 `Console.WriteLine("Hello World!");` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="7f4f9-115">명령 창에 `dotnet run`을 입력하여 이 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="7f4f9-116">정수를 사용하는 기본 수학 연산 중 하나를 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="7f4f9-117">`int` 형식은 **정수**(0, 양의 정수 또는 음의 정수)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="7f4f9-118">더하기의 경우 `+` 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="7f4f9-119">정수에 대해 다른 일반적인 수학 연산은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="7f4f9-120">빼기의 경우 `-`</span><span class="sxs-lookup"><span data-stu-id="7f4f9-120">`-` for subtraction</span></span>
- <span data-ttu-id="7f4f9-121">곱하기의 경우 `*`</span><span class="sxs-lookup"><span data-stu-id="7f4f9-121">`*` for multiplication</span></span>
- <span data-ttu-id="7f4f9-122">나누기의 경우 `/`</span><span class="sxs-lookup"><span data-stu-id="7f4f9-122">`/` for division</span></span>

<span data-ttu-id="7f4f9-123">다른 연산을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-123">Start by exploring those different operations.</span></span> <span data-ttu-id="7f4f9-124">`c`의 값을 쓰는 줄 뒤에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="7f4f9-125">명령 창에 `dotnet run`을 입력하여 이 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="7f4f9-126">원하는 경우 동일한 줄에서 여러 수학 연산을 작성하여 실험할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="7f4f9-127">예를 들어 `c = a + b - 12 * 17;`을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="7f4f9-128">변수와 상수를 혼합해서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="7f4f9-129">C# (또는 다른 프로그래밍 언어)를 살펴보면서 코드를 작성할 때 실수를 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="7f4f9-130">**컴파일러**는 그러한 오류를 찾아 사용자에게 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="7f4f9-131">출력에 오류 메시지가 포함되어 있으면 예제 코드와 창의 코드를 자세히 살펴보고 수정 사항을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="7f4f9-132">이 연습은 C# 코드의 구조를 학습하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="7f4f9-133">첫 번째 단계를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-133">You've finished the first step.</span></span> <span data-ttu-id="7f4f9-134">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="7f4f9-135">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="7f4f9-136">`Main` 메서드의 이름을 `WorkingWithIntegers`로 바꾸고 `WorkingWithIntegers`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="7f4f9-137">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-137">When you finish, your code should look like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a><span data-ttu-id="7f4f9-138">연산 순서 알아보기</span><span class="sxs-lookup"><span data-stu-id="7f4f9-138">Explore order of operations</span></span>

<span data-ttu-id="7f4f9-139">`WorkingWithIntegers()`에 대한 호출을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="7f4f9-140">그러면 이 섹션에서 작업할 때 출력이 덜 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="7f4f9-141">`//`는 C#에서 **주석**을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="7f4f9-142">주석은 소스 코드에 유지하되 코드로 실행하지는 않으려는 모든 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="7f4f9-143">컴파일러는 주석에서 실행 코드를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="7f4f9-144">C# 언어는 수학에서 배운 규칙과 일치하는 규칙으로 여러 가지 수학 연산의 우선 순위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="7f4f9-145">곱하기와 나누기는 더하기와 빼기보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="7f4f9-146">다음 코드를 `Main` 메서드에 추가하고 `dotnet run`을 실행하여 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="7f4f9-147">출력에서는 곱하기가 수행된 후 더하기가 수행되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="7f4f9-148">먼저 수행하려는 연산 주위에 괄호를 추가하여 다른 연산 순서를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="7f4f9-149">다음 줄을 추가하고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="7f4f9-150">여러 다른 연산을 결합하여 자세히 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="7f4f9-151">`Main` 메서드의 아래쪽에 다음과 같은 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="7f4f9-152">`dotnet run`을 다시 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="7f4f9-153">정수에 대해 흥미로운 동작을 이미 알고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="7f4f9-154">정수 나누기는 결과에 소수 또는 소수 부분이 포함될 것으로 예상되는 경우에도 항상 정수 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="7f4f9-155">이 동작을 못 봤다면 `Main` 메서드의 끝에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="7f4f9-156">`dotnet run`을 다시 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="7f4f9-157">넘어가기 전에 이 섹션에서 작성한 모든 코드를 새 메서드에 배치해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="7f4f9-158">이러한 새 메서드의 이름을 `OrderPrecedence`라고 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="7f4f9-159">다음과 같이 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-159">You should write something like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="7f4f9-160">정수 전체 자릿수 및 한도 살펴보기</span><span class="sxs-lookup"><span data-stu-id="7f4f9-160">Explore integer precision and limits</span></span>

<span data-ttu-id="7f4f9-161">마지막 샘플에서는 정수 나누기가 결과를 자르는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="7f4f9-162">**modulo** 연산자(`%` 문자)를 사용하여 **나머지**를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="7f4f9-163">`Main` 메서드에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="7f4f9-164">C# 정수 형식은 한 가지 다른 면에서 수학의 정수와 다릅니다. 즉 `int` 형식에는 최소 한도와 최대 한도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="7f4f9-165">이 코드를 `Main` 메서드에 추가하여 해당 한도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="7f4f9-166">계산이 해당 한도를 초과하는 값을 생성하는 경우 **언더플로** 또는 **오버플로** 조건이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="7f4f9-167">답은 한 한도에서 다른 한도로 래핑하는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="7f4f9-168">다음 두 줄을 `Main` 메서드에 추가하여 예제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="7f4f9-169">답은 최소 (음의) 정수와 아주 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="7f4f9-170">`min + 2`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="7f4f9-171">더하기 연산은 정수에 대해 허용된 값을 **오버플로했습니다**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="7f4f9-172">오버플로가 가능한 가장 큰 정수에서 가장 작은 정수로 “래핑”하기 때문에 답은 아주 큰 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="7f4f9-173">`int` 형식이 요구 사항을 충족하지 않을 때 사용하는 여러 한도와 전체 자릿수가 있는 다른 숫자 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="7f4f9-174">다음으로 다른 형식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-174">Let's explore those other types next.</span></span>

<span data-ttu-id="7f4f9-175">다시 한번, 이 섹션에서 작성한 코드를 별도의 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="7f4f9-176">이 EventHandler의 이름을 `TestLimits`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="7f4f9-177">double 형식 작업</span><span class="sxs-lookup"><span data-stu-id="7f4f9-177">Work with the double type</span></span>

<span data-ttu-id="7f4f9-178">`double` 숫자 형식은 배정밀도 부동 소수점 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="7f4f9-179">이러한 용어는 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-179">Those terms may be new to you.</span></span> <span data-ttu-id="7f4f9-180">**부동 소수점** 수는 아주 크거나 작은 정수가 아닌 수를 나타낼 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="7f4f9-181">**배정밀도**는 값을 저장하는 데 사용되는 이진 자릿수를 설명하는 상대 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="7f4f9-182">**배정밀도** 숫자의 이진 자릿수는 **단정밀도**의 두 배입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="7f4f9-183">최신 컴퓨터에서는 단정밀도 숫자보다 배정밀도를 더 많이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="7f4f9-184">**단정밀도** 숫자는 `float` 키워드를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="7f4f9-185">지금 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-185">Let's explore.</span></span> <span data-ttu-id="7f4f9-186">다음 코드를 추가하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="7f4f9-187">답에 몫의 소수 부분이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="7f4f9-188">double을 사용하여 약간 더 복잡한 식을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="7f4f9-189">double 값의 범위는 정수 값보다 훨씬 큽니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="7f4f9-190">지금까지 작성한 코드 아래에 다음 코드를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="7f4f9-191">이러한 값은 과학적 표기법으로 인쇄됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="7f4f9-192">`E`의 왼쪽에 있는 숫자는 유효 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="7f4f9-193">오른쪽의 숫자는 지수이며 10의 배수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="7f4f9-194">수학의 10진수 숫자와 마찬가지로, C#에서 double에는 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="7f4f9-195">다음 코드를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="7f4f9-196">`0.3` 반복은 `1/3`과 정확하게 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="7f4f9-197">***과제***</span><span class="sxs-lookup"><span data-stu-id="7f4f9-197">***Challenge***</span></span>

<span data-ttu-id="7f4f9-198">`double` 형식을 사용하여 큰 숫자, 작은 숫자, 곱하기 및 나누기로 다른 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="7f4f9-199">더 복잡한 계산을 수행해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-199">Try more complicated calculations.</span></span>

<span data-ttu-id="7f4f9-200">과제를 하느라 약간의 시간을 보낸 후 작성한 코드를 새 메서드에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="7f4f9-201">이러한 새 메서드의 이름을 `WorkWithDoubles`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="7f4f9-202">10진 형식으로 작업</span><span class="sxs-lookup"><span data-stu-id="7f4f9-202">Work with decimal types</span></span>

<span data-ttu-id="7f4f9-203">C#의 기본적인 숫자 형식인 정수 형식과 double 형식을 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="7f4f9-204">학습할 또 다른 형식이 있습니다. 바로 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="7f4f9-205">`decimal` 형식은 범위가 작지만 `double`보다 전체 자릿수가 큽니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="7f4f9-206">이 형식에 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="7f4f9-207">범위가 `double` 형식보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="7f4f9-208">다음 코드를 사용하여 소수점이 있는 더 큰 전체 자릿수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="7f4f9-209">숫자의 `M` 접미사는 상수가 `decimal` 형식을 사용해야 함을 나타내는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="7f4f9-210">형식을 지정하지 않으면 컴파일러는 `double` 형식으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="7f4f9-211">문자 `M`은 `double` 키워드와 `decimal` 키워드 사이에서 가장 시각적으로 고유한 문자로 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="7f4f9-212">소수점 형식을 사용하는 수학에는 소수점 오른쪽에 더 많은 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="7f4f9-213">***과제***</span><span class="sxs-lookup"><span data-stu-id="7f4f9-213">***Challenge***</span></span>

<span data-ttu-id="7f4f9-214">이제 여러 가지 숫자 형식을 살펴봤으므로 반지름이 2.50센티미터인 원의 면적을 계산하는 코드를 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="7f4f9-215">원의 면적은 반지름 제곱 곱하기 PI입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="7f4f9-216">힌트: .NET에는 PI의 상수가 포함되어 있습니다. 즉 해당 값에 사용할 수 있는 <xref:System.Math.PI?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="7f4f9-217">`System.Math` 네임스페이스에 선언된 모든 상수와 마찬가지로 <xref:System.Math.PI?displayProperty=nameWithType>는 `double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="7f4f9-218">이러한 이유로 이 과제에는 `decimal` 값 대신 `double`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="7f4f9-219">19에서 20 사이의 답을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="7f4f9-220">[GitHub에서 완성된 샘플 코드를 보고](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106) 답을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="7f4f9-221">원하는 경우 다른 수식을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="7f4f9-222">“C#의 숫자” 빠른 시작을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="7f4f9-223">자체 개발 환경에서 [분기 및 루프](branches-and-loops-local.md) 빠른 시작을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="7f4f9-224">다음 문서에서는 C#의 숫자에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="7f4f9-225">정수 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="7f4f9-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="7f4f9-226">부동 소수점 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="7f4f9-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="7f4f9-227">기본 제공 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="7f4f9-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
