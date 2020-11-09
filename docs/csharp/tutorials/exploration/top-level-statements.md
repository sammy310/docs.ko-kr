---
title: 최상위 문 - C# 자습서
description: 이 자습서에서는 아이디어를 탐색하는 동안 최상위 문을 사용하여 개념을 실험하고 증명하는 방법을 보여 줍니다.
ms.date: 10/28/2020
ms.openlocfilehash: 5e5dc6cec382baa69ac8cb4625684315bb2cd5e0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282260"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a><span data-ttu-id="c13e3-103">자습서: 배우는 동안 최상위 문을 사용하여 코드를 빌드하는 아이디어 탐색</span><span class="sxs-lookup"><span data-stu-id="c13e3-103">Tutorial: Explore ideas using top-level statements to build code as you learn</span></span>

<span data-ttu-id="c13e3-104">이 자습서에서 학습할 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-104">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="c13e3-105">최상위 문 사용을 제어하는 규칙을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-105">Learn the rules governing your use of top-level statements.</span></span>
> - <span data-ttu-id="c13e3-106">최상위 문을 사용하여 알고리즘을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-106">Use top-level statements to explore algorithms.</span></span>
> - <span data-ttu-id="c13e3-107">탐색을 재사용 가능한 구성 요소로 리팩터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-107">Refactor explorations into reusable components.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c13e3-108">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c13e3-108">Prerequisites</span></span>

<span data-ttu-id="c13e3-109">C# 9 컴파일러를 포함하는 .NET 5를 실행하도록 머신을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-109">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="c13e3-110">C# 9 컴파일러는 [Visual Studio 2019 버전 16.9 미리 보기 1](https://visualstudio.microsoft.com/vs/preview/) 또는 [.NET 5.0 SDK](https://dot.net/get-dotnet5)부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-110">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="c13e3-111">이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-111">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="start-exploring"></a><span data-ttu-id="c13e3-112">다양한 콘텐츠 살펴보기</span><span class="sxs-lookup"><span data-stu-id="c13e3-112">Start exploring</span></span>

<span data-ttu-id="c13e3-113">최상위 문을 사용하면 프로그램의 진입점을 클래스의 정적 메서드에 배치하여 필요한 추가 공식 절차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-113">Top-level statements enable you to avoid the extra ceremony required by placing your program's entry point in a static method in a class.</span></span> <span data-ttu-id="c13e3-114">새 콘솔 애플리케이션의 일반적인 시작점은 다음 코드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-114">The typical starting point for a new console application looks like the following code:</span></span>

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="c13e3-115">위 코드는 `dotnet new console` 명령을 실행하고 새 콘솔 애플리케이션을 만든 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-115">The preceding code is the result of running the `dotnet new console` command and creating a new console application.</span></span> <span data-ttu-id="c13e3-116">11줄의 코드에 단 한 줄의 실행 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-116">Those 11 lines contain only one line of executable code.</span></span> <span data-ttu-id="c13e3-117">새 최상위 문 기능을 사용하여 해당 프로그램을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-117">You can simplify that program with the new top-level statements feature.</span></span> <span data-ttu-id="c13e3-118">이렇게 하면 해당 프로그램에서 두 개 줄을 제외한 모든 줄을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-118">That enables you to remove all but two of the lines in this program:</span></span>

```csharp
using System;

Console.WriteLine("Hello World!");
```

<span data-ttu-id="c13e3-119">이 작업은 새로운 아이디어 탐색을 시작하는 데 필요한 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-119">This action simplifies what's needed to begin exploring new ideas.</span></span> <span data-ttu-id="c13e3-120">스크립팅 시나리오에서 또는 탐색하는 데 최상위 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-120">You can use top-level statements for scripting scenarios, or to explore.</span></span> <span data-ttu-id="c13e3-121">적용되는 기본 사항을 확인한 후 코드의 리팩터링을 시작하고 빌드한 재사용 가능 구성 요소의 메서드, 클래스 또는 기타 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-121">Once you've got the basics working, you can start refactoring the code and create methods, classes, or other assemblies for reusable components you've built.</span></span> <span data-ttu-id="c13e3-122">최상위 문은 빠른 실험 및 초보자 자습서를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-122">Top-level statements do enable quick experimentation and beginner tutorials.</span></span> <span data-ttu-id="c13e3-123">또한 실험에서 전체 프로그램까지 원활한 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-123">They also provide a smooth path from experimentation to full programs.</span></span>

<span data-ttu-id="c13e3-124">최상위 문은 파일에 표시된 순서대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-124">Top-level statements are executed in the order they appear in the file.</span></span> <span data-ttu-id="c13e3-125">최상위 문은 애플리케이션의 한 소스 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-125">Top-level statements can only be used in one source file in your application.</span></span> <span data-ttu-id="c13e3-126">둘 이상의 파일에서 사용하는 경우 컴파일러에서 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-126">The compiler generates an error if you use them in more than one file.</span></span>

## <a name="build-a-magic-net-answer-machine"></a><span data-ttu-id="c13e3-127">매직 .NET 응답 머신 빌드</span><span class="sxs-lookup"><span data-stu-id="c13e3-127">Build a magic .NET answer machine</span></span>

<span data-ttu-id="c13e3-128">이 자습서에서는 임의 응답을 사용하여 “예” 또는 “아니요” 질문에 대답하는 콘솔 애플리케이션을 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-128">For this tutorial, let's build a console application that answers a "yes" or "no" question with a random answer.</span></span> <span data-ttu-id="c13e3-129">기능을 단계별로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-129">You'll build out the functionality step by step.</span></span> <span data-ttu-id="c13e3-130">일반적인 프로그램의 구조에 필요한 공식 절차가 아닌 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-130">You can focus on your task rather than ceremony needed for the structure of a typical program.</span></span> <span data-ttu-id="c13e3-131">그런 다음, 기능에 만족하면 필요한 경우 애플리케이션을 리팩터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-131">Then, once you're happy with the functionality, you can refactor the application as you see fit.</span></span>

<span data-ttu-id="c13e3-132">좋은 시작점은 질문을 다시 콘솔에 쓰는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-132">A good starting point is to write the question back to the console.</span></span> <span data-ttu-id="c13e3-133">먼저 다음 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-133">You can start by writing the following code:</span></span>

```csharp
using System;

Console.WriteLine(args);
```

<span data-ttu-id="c13e3-134">`args` 변수를 선언하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-134">You don't declare an `args` variable.</span></span> <span data-ttu-id="c13e3-135">최상위 문이 포함된 단일 소스 파일의 경우 컴파일러는 명령줄 인수를 의미하는 `args`를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-135">For the single source file that contains your top-level statements, the compiler recognizes `args` to mean the command-line arguments.</span></span> <span data-ttu-id="c13e3-136">인수 형식은 모든 C# 프로그램과 같이 `string[]`입니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-136">The type of args is a `string[]`, as in all C# programs.</span></span>

<span data-ttu-id="c13e3-137">다음 `dotnet run` 명령을 실행하여 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-137">You can test your code by running the following `dotnet run` command:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

<span data-ttu-id="c13e3-138">명령줄에 있는 `--` 뒤의 인수는 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-138">The arguments after the `--` on the command line are passed to the program.</span></span> <span data-ttu-id="c13e3-139">콘솔에 인쇄된 항목인 `args` 변수 형식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-139">You can see the type of the `args` variable, because that's what's printed to the console:</span></span>

```console
System.String[]
```

<span data-ttu-id="c13e3-140">콘솔에 질문을 쓰려면 인수를 열거하고 공백으로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-140">To write the question to the console, you'll need to enumerate the arguments and separate them with a space.</span></span> <span data-ttu-id="c13e3-141">`WriteLine` 호출을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-141">Replace the `WriteLine` call with the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

<span data-ttu-id="c13e3-142">이제 프로그램을 실행하면 질문을 인수 문자열로 올바르게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-142">Now, when you run the program, it will correctly display the question as a string of arguments.</span></span>

## <a name="respond-with-a-random-answer"></a><span data-ttu-id="c13e3-143">임의 응답으로 응답</span><span class="sxs-lookup"><span data-stu-id="c13e3-143">Respond with a random answer</span></span>

<span data-ttu-id="c13e3-144">질문을 에코한 후에는 임의 응답을 생성하는 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-144">After echoing the question, you can add the code to generate the random answer.</span></span> <span data-ttu-id="c13e3-145">먼저 가능한 응답의 배열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-145">Start by adding an array of possible answers:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

<span data-ttu-id="c13e3-146">이 배열에는 긍정 응답 12개, 커밋이 아닌 응답 6개, 부정 응답 6개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-146">This array has 12 answers that are affirmative, six that are non-committal, and six that are negative.</span></span> <span data-ttu-id="c13e3-147">다음으로, 다음 코드를 추가하여 배열에서 임의 응답을 생성하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-147">Next, add the following code to generate and display a random answer from the array:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

<span data-ttu-id="c13e3-148">애플리케이션을 다시 실행하여 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-148">You can run the application again to see the results.</span></span> <span data-ttu-id="c13e3-149">다음 출력과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-149">You should see something like the following output:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

<span data-ttu-id="c13e3-150">이 코드는 질문에 응답하지만 기능을 하나 더 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-150">This code answers the questions, but let's add one more feature.</span></span> <span data-ttu-id="c13e3-151">질문 앱에서 응답에 관한 생각을 시뮬레이트하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-151">You'd like your question app to simulate thinking about the answer.</span></span> <span data-ttu-id="c13e3-152">이렇게 하려면 약간의 ASCII 애니메이션을 추가하고 작동 중에 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-152">You can do that by adding a bit of ASCII animation, and pausing while working.</span></span>  <span data-ttu-id="c13e3-153">질문을 에코하는 줄 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-153">Add the following code after the line that echoes the question:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

<span data-ttu-id="c13e3-154">또한 소스 파일의 맨 위에 `using` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-154">You'll also need to add a `using` statement to the top of the source file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="c13e3-155">`using` 문은 파일의 다른 문 앞에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-155">The `using` statements must be before any other statements in the file.</span></span> <span data-ttu-id="c13e3-156">그렇지 않으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-156">Otherwise, it's a compiler error.</span></span> <span data-ttu-id="c13e3-157">프로그램을 다시 실행하여 애니메이션을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-157">You can run the program again and see the animation.</span></span> <span data-ttu-id="c13e3-158">이를 통해 더 나은 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-158">That makes a better experience.</span></span> <span data-ttu-id="c13e3-159">원하는 대로 지연 길이를 실험합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-159">Experiment with the length of the delay to match your taste.</span></span>

<span data-ttu-id="c13e3-160">앞의 코드는 공백으로 구분된 회전하는 선 세트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-160">The preceding code creates a set of spinning lines separated by a space.</span></span> <span data-ttu-id="c13e3-161">`await` 키워드를 추가하면 컴파일러가 프로그램 진입점을 `async` 한정자가 있는 메서드로 생성하고 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>를 반환하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-161">Adding the `await` keyword instructs the compiler to generate the program entry point as a method that has the `async` modifier, and returns a <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c13e3-162">이 프로그램은 값을 반환하지 않으므로 프로그램 진입점이 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-162">This program does not return a value, so the program entry point returns a `Task`.</span></span> <span data-ttu-id="c13e3-163">프로그램이 정수 값을 반환하는 경우 최상위 문의 끝에 return 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-163">If your program returns an integer value, you would add a return statement to the end of your top-level statements.</span></span> <span data-ttu-id="c13e3-164">return 문은 반환할 정수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-164">That return statement would specify the integer value to return.</span></span> <span data-ttu-id="c13e3-165">최상위 문에 `await` 식이 포함된 경우 반환 형식은 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-165">If your top-level statements include an `await` expression, the return type becomes <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.</span></span>

## <a name="refactoring-for-the-future"></a><span data-ttu-id="c13e3-166">미래를 위한 리팩터링</span><span class="sxs-lookup"><span data-stu-id="c13e3-166">Refactoring for the future</span></span>

<span data-ttu-id="c13e3-167">프로그램은 다음 코드와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-167">Your program should look like the following code:</span></span>

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

<span data-ttu-id="c13e3-168">앞의 코드는 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-168">The preceding code is reasonable.</span></span> <span data-ttu-id="c13e3-169">예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-169">It works.</span></span> <span data-ttu-id="c13e3-170">하지만 재사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-170">But it isn't reusable.</span></span> <span data-ttu-id="c13e3-171">이제 애플리케이션이 작동하고 있으므로 재사용 가능한 부분을 가져오겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-171">Now that you have the application working, it's time to pull out reusable parts.</span></span>

<span data-ttu-id="c13e3-172">한 후보는 대기 중인 애니메이션을 표시하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-172">One candidate is the code that displays the waiting animation.</span></span> <span data-ttu-id="c13e3-173">해당 코드 조각은 메서드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-173">That snippet can become a method:</span></span>

<span data-ttu-id="c13e3-174">먼저 파일에서 로컬 함수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-174">You can start by creating a local function in your file.</span></span> <span data-ttu-id="c13e3-175">현재 애니메이션을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-175">Replace the current animation with the following code:</span></span>

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

<span data-ttu-id="c13e3-176">앞의 코드는 main 메서드 내에 로컬 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-176">The preceding code creates a local function inside your main method.</span></span> <span data-ttu-id="c13e3-177">그래도 재사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-177">That's still not reusable.</span></span> <span data-ttu-id="c13e3-178">따라서 해당 코드를 클래스로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-178">So, extract that code into a class.</span></span> <span data-ttu-id="c13e3-179">*utilities.cs* 라는 새 파일을 만들고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-179">Create a new file named *utilities.cs* and add the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

<span data-ttu-id="c13e3-180">최상위 문은 한 파일에만 있을 수 있으며, 해당 파일은 네임스페이스나 형식을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-180">Top-level statements can only be in one file, and that file cannot contain namespaces or types.</span></span>

<span data-ttu-id="c13e3-181">마지막으로, 애니메이션 코드를 정리하여 일부 중복을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-181">Finally, you can clean the animation code to remove some duplication:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Utilities.cs" ID="Animation":::

<span data-ttu-id="c13e3-182">이제 전체 애플리케이션이 있으며 나중에 사용할 수 있도록 재사용 가능한 부분을 리팩터링했습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-182">Now you have a complete application, and you've refactored the reusable parts for later use.</span></span>

## <a name="summary"></a><span data-ttu-id="c13e3-183">요약</span><span class="sxs-lookup"><span data-stu-id="c13e3-183">Summary</span></span>

<span data-ttu-id="c13e3-184">최상위 문을 사용하면 새 알고리즘을 탐색하는 데 사용할 간단한 프로그램을 더 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-184">Top-level statements make it easier to create simple programs for use to explore new algorithms.</span></span> <span data-ttu-id="c13e3-185">코드의 다른 조각을 시도하여 알고리즘을 실험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-185">You can experiment with algorithms by trying different snippets of code.</span></span> <span data-ttu-id="c13e3-186">작동 기능을 알아본 후에는 코드를 더 쉽게 유지 관리할 수 있도록 리팩터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-186">Once you've learned what works, you can refactor the code to be more maintainable.</span></span>

<span data-ttu-id="c13e3-187">최상위 문은 콘솔 애플리케이션을 기반으로 하는 프로그램을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-187">Top-level statements simplify programs that are based on console applications.</span></span> <span data-ttu-id="c13e3-188">여기에는 Azure Functions, GitHub Actions, 기타 작은 유틸리티가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13e3-188">These include Azure functions, GitHub actions, and other small utilities.</span></span>
