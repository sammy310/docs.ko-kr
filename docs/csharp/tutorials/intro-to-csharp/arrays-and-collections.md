---
title: 컬렉션 작업 - C# 소개 자습서
description: 이 자습서에서는 목록 컬렉션을 살펴보면서 C#에 대해 학습합니다.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: e2282df21420630634911e07f4fb3b94f34a792b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414685"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="70529-103">일반 목록 형식을 사용하여 데이터 컬렉션을 관리하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="70529-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="70529-104">이 소개 자습서에서는 C# 언어 및 <xref:System.Collections.Generic.List%601> 클래스의 기본 사항을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="70529-105">이 자습서에서는 개발에 사용할 수 있는 머신이 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="70529-106">.NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)에는 Windows, Linux 또는 macOS의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-106">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="70529-107">사용할 명령에 대한 간단한 개요는 [개발 도구 익히기](local-environment.md)에 자세한 정보의 링크와 함께 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="70529-108">기본 목록 예제</span><span class="sxs-lookup"><span data-stu-id="70529-108">A basic list example</span></span>

<span data-ttu-id="70529-109">*list-tutorial*이라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70529-109">Create a directory named *list-tutorial*.</span></span> <span data-ttu-id="70529-110">현재 디렉터리로 지정하고 `dotnet new console`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-110">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="70529-111">편집기에서 *Program.cs*를 열고 기존 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70529-111">Open *Program.cs* in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="70529-112">`<name>`을 사용자의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70529-112">Replace `<name>` with your name.</span></span> <span data-ttu-id="70529-113">*Program.cs*를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-113">Save *Program.cs*.</span></span> <span data-ttu-id="70529-114">콘솔 창에 `dotnet run`을 입력하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="70529-114">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="70529-115">문자열 목록을 만들고, 해당 목록에 세 개의 이름을 추가하고, 모든 CAPS에 이름을 인쇄했습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-115">You've created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="70529-116">이전 자습서에서 학습한 개념을 사용하여 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-116">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="70529-117">이름을 표시하는 코드는 [문자열 보간](../../language-reference/tokens/interpolated.md) 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-117">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="70529-118">`string` 앞에 `$` 문자를 넣으면 문자열 선언에 C# 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-118">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="70529-119">실제 문자열은 C# 코드를 생성하는 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70529-119">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="70529-120">이 예제에서는 <xref:System.String.ToUpper%2A> 메서드를 호출했기 때문에 `{name.ToUpper()}`를 대문자로 변환된 각 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70529-120">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="70529-121">계속해서 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-121">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="70529-122">목록 콘텐츠 수정</span><span class="sxs-lookup"><span data-stu-id="70529-122">Modify list contents</span></span>

<span data-ttu-id="70529-123">생성한 컬렉션은 <xref:System.Collections.Generic.List%601> 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-123">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="70529-124">이 형식은 요소의 시퀀스를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-124">This type stores sequences of elements.</span></span> <span data-ttu-id="70529-125">꺾쇠 괄호 사이의 요소 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-125">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="70529-126">이 <xref:System.Collections.Generic.List%601> 형식은 늘리거나 줄일 수 있어 요소를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-126">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="70529-127">`Main` 메서드에서 `}`를 닫기 전에 이 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-127">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="70529-128">목록 끝에 이름을 두 개 더 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-128">You've added two more names to the end of the list.</span></span> <span data-ttu-id="70529-129">또한 이름을 하나 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-129">You've also removed one as well.</span></span> <span data-ttu-id="70529-130">파일을 저장하고 `dotnet run`을 입력하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="70529-130">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="70529-131"><xref:System.Collections.Generic.List%601>를 사용하면 **인덱스**별로 각 항목을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-131">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="70529-132">목록 이름 뒤 `[`와 `]` 토큰 사이에 인덱스를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-132">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="70529-133">C#은 첫 번째 인덱스에 0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-133">C# uses 0 for the first index.</span></span> <span data-ttu-id="70529-134">방금 추가한 코드 바로 아래에 이 코드를 추가하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-134">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="70529-135">목록의 끝을 벗어나는 인덱스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-135">You can't access an index beyond the end of the list.</span></span> <span data-ttu-id="70529-136">인덱스는 0부터 시작하므로, 가장 큰 유효 인덱스는 목록의 항목 수보다 하나 작습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-136">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="70529-137"><xref:System.Collections.Generic.List%601.Count%2A> 속성을 사용하여 목록의 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-137">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="70529-138">Main 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-138">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="70529-139">파일을 저장하고 `dotnet run`을 다시 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-139">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="70529-140">목록 검색 및 정렬</span><span class="sxs-lookup"><span data-stu-id="70529-140">Search and sort lists</span></span>

<span data-ttu-id="70529-141">샘플에서는 상대적으로 작은 목록을 사용하지만 애플리케이션에서는 수천에 달하는 많은 요소가 포함된 목록을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-141">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="70529-142">이러한 큰 컬렉션에서 요소를 찾으려면 여러 항목의 목록을 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-142">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="70529-143"><xref:System.Collections.Generic.List%601.IndexOf%2A> 메서드는 항목을 검색하고 항목의 인덱스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-143">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="70529-144">목록에 항목이 없으면 `IndexOf`가 `-1`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-144">If the item isn't in the list, `IndexOf` returns `-1`.</span></span> <span data-ttu-id="70529-145">`Main` 메서드의 맨 아래에 이 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="70529-146">목록의 항목도 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="70529-147"><xref:System.Collections.Generic.List%601.Sort%2A> 메서드는 일반적인 순서(문자열의 경우 사전순)로 목록의 모든 항목을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically for strings).</span></span> <span data-ttu-id="70529-148">`Main` 메서드의 맨 아래에 이 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="70529-149">파일을 저장하고 `dotnet run`을 입력하여 이 최신 버전을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="70529-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="70529-150">다음 섹션을 시작하기 전에 현재 코드를 별도의 메서드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="70529-151">이렇게 하면 새 예제 작업을 쉽게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="70529-152">`Main` 메서드의 이름을 `WorkingWithStrings`로 바꾸고 `WorkingWithStrings`를 호출하는 새 `Main` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="70529-153">작업을 마치면 코드가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70529-153">When you've finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="70529-154">다른 형식 목록</span><span class="sxs-lookup"><span data-stu-id="70529-154">Lists of other types</span></span>

<span data-ttu-id="70529-155">지금까지 목록에 `string` 형식을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="70529-156">다른 형식을 사용하여 <xref:System.Collections.Generic.List%601>를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="70529-157">숫자 집합을 빌드하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="70529-158">새 `Main` 메서드의 맨 아래에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="70529-159">정수 목록을 만들고 처음 두 정수를 값 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="70529-160">숫자 시퀀스인 *피보나치 시퀀스*의 첫 번째 두 값입니다.</span><span class="sxs-lookup"><span data-stu-id="70529-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="70529-161">다음 각 피보나치 수는 이전의 두 수의 합계를 사용하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="70529-162">이 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="70529-163">파일을 저장하고 `dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="70529-164">이 섹션에만 집중하려면 `WorkingWithStrings();`를 호출하는 코드를 주석으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="70529-165">`// WorkingWithStrings();`처럼 호출 앞에 `/` 문자를 두 개 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="70529-166">과제</span><span class="sxs-lookup"><span data-stu-id="70529-166">Challenge</span></span>

<span data-ttu-id="70529-167">이 단원과 이전 단원에서 학습한 개념을 함께 적용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="70529-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="70529-168">피보나치 수를 사용하여 지금까지 빌드한 내용을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="70529-169">코드를 작성하여 시퀀스에서 처음 20개 수를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="70529-170">(힌트: 20번째 피보나치 수는 6765입니다.)</span><span class="sxs-lookup"><span data-stu-id="70529-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="70529-171">과제 완료</span><span class="sxs-lookup"><span data-stu-id="70529-171">Complete challenge</span></span>

<span data-ttu-id="70529-172">[GitHub에서 완료된 샘플 코드를 보고](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23) 예제 솔루션을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span></span>

<span data-ttu-id="70529-173">루프의 각 반복을 통해 목록의 마지막 두 정수를 사용하고, 더하고, 해당 값을 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="70529-174">목록에 20개의 항목이 추가될 때까지 루프가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="70529-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="70529-175">축하합니다. 목록 자습서를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="70529-176">자체 개발 환경에서 [클래스 소개](introduction-to-classes.md) 자습서를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="70529-177">.NET 기본 사항 문서의 [컬렉션](../../../standard/collections/index.md)에서 `List` 형식 작업에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70529-177">You can learn more about working with the `List` type in the .NET fundamentals article on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="70529-178">다른 많은 컬렉션 형식에 대해서도 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="70529-178">You'll also learn about many other collection types.</span></span>
