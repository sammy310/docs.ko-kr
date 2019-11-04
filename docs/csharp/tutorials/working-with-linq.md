---
title: LINQ 작업
description: 이 자습서에서는 LINQ를 사용하여 시퀀스를 생성하고, LINQ 쿼리에서 사용할 메서드를 작성하고, 즉시 계산 및 지연 계산 간을 구분하는 방법을 알아봅니다.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: b25cd1763511f460537bccaf6011a3d23390ea72
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039167"
---
# <a name="working-with-linq"></a><span data-ttu-id="cc445-103">LINQ 작업</span><span class="sxs-lookup"><span data-stu-id="cc445-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="cc445-104">소개</span><span class="sxs-lookup"><span data-stu-id="cc445-104">Introduction</span></span>

<span data-ttu-id="cc445-105">이 자습서에서는 .NET Core 및 C# 언어의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-105">This tutorial teaches you features in .NET Core and the C# language.</span></span> <span data-ttu-id="cc445-106">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-106">You’ll learn:</span></span>

- <span data-ttu-id="cc445-107">LINQ를 사용하여 시퀀스를 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="cc445-107">How to generate sequences with LINQ.</span></span>
- <span data-ttu-id="cc445-108">LINQ 쿼리에서 쉽게 사용할 수 있는 메서드를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="cc445-108">How to write methods that can be easily used in LINQ queries.</span></span>
- <span data-ttu-id="cc445-109">즉시 계산 및 지연 계산을 구분하는 방법</span><span class="sxs-lookup"><span data-stu-id="cc445-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="cc445-110">모든 마술사들이 기본적으로 익히는 기술 중 하나인 [파로 셔플](https://en.wikipedia.org/wiki/Faro_shuffle)을 보여 주는 애플리케이션을 빌드하여 이러한 기술을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="cc445-111">간단히 말해서 파로 셔플은 카드 데크를 정확히 절반으로 분할한 다음 각 절반의 각 카드를 교차로 섞어 원래 데크 순서로 다시 빌드하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="cc445-112">마술사들은 카드를 섞은 후에 모든 카드가 알려진 위치로 들어가고 순서가 반복 패턴을 가지게 되므로 이 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span>

<span data-ttu-id="cc445-113">이 자습서에서는 데이터 시퀀스 조작 과정을 간단하게 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-113">For your purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="cc445-114">빌드할 애플리케이션은 카드 데크를 생성하고 섞은 다음 매번 섞는 시퀀스를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="cc445-115">또한 업데이트된 순서를 원래 순서와 비교할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="cc445-116">이 자습서는 여러 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="cc445-117">각 단계 후에 애플리케이션을 실행하고 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="cc445-118">[완료된 샘플](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq)은 GitHub의 dotnet/samples 리포지토리에서도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="cc445-119">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc445-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc445-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="cc445-120">Prerequisites</span></span>

<span data-ttu-id="cc445-121">.NET Core를 실행하도록 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="cc445-122">[.NET Core 다운로드](https://dotnet.microsoft.com/download) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-122">You can find the installation instructions on the [.NET Core Download](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="cc445-123">Windows, Ubuntu Linux, OS X 또는 Docker 컨테이너에서 이 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="cc445-124">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="cc445-125">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="cc445-126">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="cc445-127">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="cc445-127">Create the Application</span></span>

<span data-ttu-id="cc445-128">첫 번째 단계에서는 새 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-128">The first step is to create a new application.</span></span> <span data-ttu-id="cc445-129">명령 프롬프트를 열고 애플리케이션에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="cc445-130">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-130">Make that the current directory.</span></span> <span data-ttu-id="cc445-131">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="cc445-132">이렇게 하면 기본 "Hello World" 애플리케이션에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="cc445-133">이전에 C#을 사용해본 적이 없으면 [이 자습서](console-teleprompter.md)에서 C# 프로그램의 구조를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cc445-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="cc445-134">해당 부분을 읽고 여기로 돌아와 LINQ에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-134">You can read that and then return here to learn more about LINQ.</span></span>

## <a name="creating-the-data-set"></a><span data-ttu-id="cc445-135">데이터 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="cc445-135">Creating the Data Set</span></span>

<span data-ttu-id="cc445-136">시작하기 전에 `dotnet new console`에서 생성된 `Program.cs` 파일의 맨 위에 다음 줄이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-136">Before you begin, make sure that the following lines are at the top of the `Program.cs` file generated by `dotnet new console`:</span></span>

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="cc445-137">이러한 세 줄(`using` 문)이 파일 맨 위에 없으면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-137">If these three lines (`using` statements) aren't at the top of the file, our program will not compile.</span></span>

<span data-ttu-id="cc445-138">이제 필요한 참조가 모두 있으므로 카드 데크의 구성 요소를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-138">Now that you have all of the references that you'll need, consider what constitutes a deck of cards.</span></span> <span data-ttu-id="cc445-139">일반적으로 플레잉 카드 데크에는 네 개의 짝패가 있으며, 각 짝패에 13개의 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-139">Commonly, a deck of playing cards has four suits, and each suit has thirteen values.</span></span> <span data-ttu-id="cc445-140">일반적으로 즉시 `Card` 클래스를 만들고 `Card` 개체 컬렉션을 수동으로 채우는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-140">Normally, you might consider creating a `Card` class right off the bat and populating a collection of `Card` objects by hand.</span></span> <span data-ttu-id="cc445-141">LINQ를 사용하면 일반적인 방법보다 더 간결하게 카드 데크 생성을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-141">With LINQ, you can be more concise than the usual way of dealing with creating a deck of cards.</span></span> <span data-ttu-id="cc445-142">`Card` 클래스를 만드는 대신, 각각 짝패와 순위를 나타내는 두 개의 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-142">Instead of creating a `Card` class, you can create two sequences to represent suits and ranks, respectively.</span></span> <span data-ttu-id="cc445-143">순위와 짝패를 <xref:System.Collections.Generic.IEnumerable%601> 문자열로 생성하는 간단한 [*반복기 메서드*](../iterators.md#enumeration-sources-with-iterator-methods) 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-143">You'll create a really simple pair of [*iterator methods*](../iterators.md#enumeration-sources-with-iterator-methods) that will generate the ranks and suits as <xref:System.Collections.Generic.IEnumerable%601>s of strings:</span></span>

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="cc445-144">이 코드를 `Program.cs` 파일의 `Main` 메서드 아래에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-144">Place these underneath the `Main` method in your `Program.cs` file.</span></span> <span data-ttu-id="cc445-145">이러한 두 메서드는 `yield return` 구문을 활용하여 실행 시 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-145">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="cc445-146">컴파일러는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 개체를 빌드하고 요청 시 문자열 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-146">The compiler builds an object that implements <xref:System.Collections.Generic.IEnumerable%601> and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="cc445-147">이제 이러한 반복기 메서드를 사용하여 카드 데크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-147">Now, use these iterator methods to create the deck of cards.</span></span> <span data-ttu-id="cc445-148">LINQ 쿼리를 `Main` 메서드에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-148">You'll place the LINQ query in our `Main` method.</span></span> <span data-ttu-id="cc445-149">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-149">Here's a look at it:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

<span data-ttu-id="cc445-150">여러 `from` 절이 <xref:System.Linq.Enumerable.SelectMany%2A>를 생성합니다. 그러면 첫 번째 시퀀스의 각 요소를 두 번째 시퀀스의 각 요소와 조합하는 단일 시퀀스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-150">The multiple `from` clauses produce a <xref:System.Linq.Enumerable.SelectMany%2A>, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="cc445-151">이 순서는 현재 목적에 따라 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-151">The order is important for our purposes.</span></span> <span data-ttu-id="cc445-152">첫 번째 소스 시퀀스(Suites)의 첫 번째 요소는 두 번째 시퀀스(Ranks)의 모든 요소와 조합됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-152">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Ranks).</span></span> <span data-ttu-id="cc445-153">그 결과 첫 번째 세트의 13개 카드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-153">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="cc445-154">이 프로세스는 첫 번째 시퀀스(Suites)의 각 요소에 대해 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-154">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="cc445-155">최종 결과는 카드 데크를 세트별로 정렬한 후 다시 값별로 정렬한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-155">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="cc445-156">위에서 사용한 쿼리 구문에 LINQ를 작성할지, 아니면 메서드 구문을 대신 사용할지에 따라 항상 하나의 구문 형식에서 다른 구문 형식으로 전환할 수 있다는 것을 명심하세요.</span><span class="sxs-lookup"><span data-stu-id="cc445-156">It's important to keep in mind that whether you choose to write your LINQ in the query syntax used above or use method syntax instead, it's always possible to go from one form of syntax to the other.</span></span> <span data-ttu-id="cc445-157">쿼리 구문으로 작성된 위 쿼리는 다음과 같이 메서드 구문으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-157">The above query written in query syntax can be written in method syntax as:</span></span>

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

<span data-ttu-id="cc445-158">컴파일러는 쿼리 구문으로 작성된 LINQ 문을 동등한 메서드 호출 구문으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-158">The compiler translates LINQ statements written with query syntax into the equivalent method call syntax.</span></span> <span data-ttu-id="cc445-159">따라서 선택한 구문과 관계없이 두 버전의 쿼리가 동일한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-159">Therefore, regardless of your syntax choice, the two versions of the query produce the same result.</span></span> <span data-ttu-id="cc445-160">사용자의 상황에 가장 적합한 구문을 선택합니다. 예를 들어 일부 멤버가 메서드 구문을 사용하는 데 어려움을 겪고 있는 팀에서는 쿼리 구문을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-160">Choose which syntax works best for your situation: for instance, if you're working in a team where some of the members have difficulty with method syntax, try to prefer using query syntax.</span></span>

<span data-ttu-id="cc445-161">계속해서 지금 빌드한 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-161">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="cc445-162">데크에 있는 52개의 모든 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-162">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="cc445-163">디버거에서 이 샘플을 실행하면 `Suits()` 및 `Ranks()` 메서드가 실행되는 방식을 확인할 수 있어서 매우 유용하다는 것을 알게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-163">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Ranks()` methods execute.</span></span> <span data-ttu-id="cc445-164">각 시퀀스의 각 문자열이 필요할 때만 생성된다는 것도 명확히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-164">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![52개의 카드를 작성하는 앱을 표시하는 콘솔 창](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="cc445-166">순서 조작</span><span class="sxs-lookup"><span data-stu-id="cc445-166">Manipulating the Order</span></span>

<span data-ttu-id="cc445-167">다음으로, 데크의 카드 순서를 섞는 메서드를 중심으로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-167">Next, focus on how you're going to shuffle the cards in the deck.</span></span> <span data-ttu-id="cc445-168">좋은 순서 섞기의 첫 번째 단계는 데크를 두 개로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-168">The first step in any good shuffle is to split the deck in two.</span></span> <span data-ttu-id="cc445-169">LINQ API에 속하는 <xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 메서드가 이 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-169">The <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods that are part of the LINQ APIs provide that feature for you.</span></span> <span data-ttu-id="cc445-170">`foreach` 루프 아래에 카드를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-170">Place them underneath the `foreach` loop:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

<span data-ttu-id="cc445-171">하지만 표준 라이브러리에는 이용할 수 있는 순서 섞기 메서드가 없으므로 고유한 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-171">However, there's no shuffle method to take advantage of in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="cc445-172">만들려는 순서 섞기 메서드는 LINQ 기반 프로그램에서 사용할 여러 기술을 보여 주므로 단계에서 이 프로세스의 각 부분을 설명하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-172">The shuffle method you'll be creating illustrates several techniques that you'll use with LINQ-based programs, so each part of this process will be explained in steps.</span></span>

<span data-ttu-id="cc445-173">LINQ 쿼리에서 반환되는 <xref:System.Collections.Generic.IEnumerable%601>을 조작하는 방법에 몇 가지 기능을 추가하려면 [확장 메서드](../programming-guide/classes-and-structs/extension-methods.md)라는 특수한 종류의 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-173">In order to add some functionality to how you interact with the <xref:System.Collections.Generic.IEnumerable%601> you'll get back from LINQ queries, you'll need to write some special kinds of methods called [extension methods](../programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="cc445-174">간단히 말해, 확장 메서드는 기능을 추가하려는 원래 형식을 수정하지 않고 기존 형식에 새로운 기능을 추가하는 특별한 용도의 *정적 메서드*입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-174">Briefly, an extension method is a special purpose *static method* that adds new functionality to an already-existing type without having to modify the original type you want to add functionality to.</span></span>

<span data-ttu-id="cc445-175">`Extensions.cs`라는 프로그램에 새 ‘정적’ 클래스 파일을 추가하여 확장 메서드에 새로운 홈을 제공한 다음, 첫 번째 확장 메서드 빌드를 시작합니다. </span><span class="sxs-lookup"><span data-stu-id="cc445-175">Give your extension methods a new home by adding a new *static* class file to your program called `Extensions.cs`, and then start building out the first extension method:</span></span>

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

<span data-ttu-id="cc445-176">메서드 시그니처, 특히 매개 변수를 잠시 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-176">Look at the method signature for a moment, specifically the parameters:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="cc445-177">이 메서드에 첫 번째 인수에 대한 `this` 한정자가 추가되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-177">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="cc445-178">즉, 마치 첫 번째 인수 형식의 멤버 메서드인 것처럼 이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-178">That means you call the method as though it were a member method of the type of the first argument.</span></span> <span data-ttu-id="cc445-179">또한 이 메서드 선언은 입력 및 출력 형식이 `IEnumerable<T>`인 표준 관용구를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-179">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="cc445-180">이러한 방식에서는 LINQ 메서드가 서로 사슬처럼 연결되어 좀 더 복잡한 쿼리를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-180">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

<span data-ttu-id="cc445-181">데크를 절반씩 분할했으므로 이러한 절반을 조인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-181">Naturally, since you split the deck into halves, you'll need to join those halves together.</span></span> <span data-ttu-id="cc445-182">코드에서는 이 작업을 위해 <xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>을 통해 얻은 두 시퀀스를 동시에 모두 열거하고 요소를 *`interleaving`* 한 다음, 이제 순서가 섞인 카드 데크인 하나의 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-182">In code, this means you'll be enumerating both of the sequences you acquired through <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> at once, *`interleaving`* the elements, and creating one sequence: your now-shuffled deck of cards.</span></span> <span data-ttu-id="cc445-183">두 시퀀스에 작동하는 LINQ 메서드를 작성하려면 <xref:System.Collections.Generic.IEnumerable%601> 작동 방식을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-183">Writing a LINQ method that works with two sequences requires that you understand how <xref:System.Collections.Generic.IEnumerable%601> works.</span></span>

<span data-ttu-id="cc445-184"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 한 가지 메서드인 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-184">The <xref:System.Collections.Generic.IEnumerable%601> interface has one method: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span></span> <span data-ttu-id="cc445-185"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>에서 반환된 개체에는 다음 요소로 이동하기 위한 메서드와 시퀀스의 현재 요소를 검색하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-185">The object returned by <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="cc445-186">이러한 두 멤버를 사용하여 컬렉션을 열거하고 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-186">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="cc445-187">이 Interleave 메서드는 반복기 메서드이므로, 컬렉션을 빌드하고 반환하는 대신, 위에 표시된 `yield return` 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-187">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span>

<span data-ttu-id="cc445-188">해당 메서드의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-188">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="cc445-189">이 메서드를 작성했으므로 `Main` 메서드로 돌아가 데크 순서를 한 번 섞습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-189">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="cc445-190">비교</span><span class="sxs-lookup"><span data-stu-id="cc445-190">Comparisons</span></span>

<span data-ttu-id="cc445-191">데크가 원래 순서로 돌아가는 데 몇 번을 섞어야 할까요?</span><span class="sxs-lookup"><span data-stu-id="cc445-191">How many shuffles it takes to set the deck back to its original order?</span></span> <span data-ttu-id="cc445-192">알아내려면 두 시퀀스가 서로 같은지 확인하는 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-192">To find out, you'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="cc445-193">이 메서드를 만든 후에는 데크 순서를 섞는 코드를 루프에 배치하고 데크가 원래 순서로 돌아갈 때를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-193">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="cc445-194">두 시퀀스가 서로 같은지를 확인하는 메서드를 작성하는 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-194">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="cc445-195">데크를 섞기 위해 작성한 메서드와 비슷한 구조를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-195">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="cc445-196">그렇지만 이번에는 각 요소를 `yield return`하는 대신, 각 시퀀스의 일치하는 요소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-196">Only this time, instead of `yield return`ing each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="cc445-197">전체 시퀀스가 열거된 경우 모든 요소가 일치하면 시퀀스도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-197">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="cc445-198">다음에서는 두 번째 LINQ 관용구인 터미널 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-198">This shows a second LINQ idiom: terminal methods.</span></span> <span data-ttu-id="cc445-199">여기서는 시퀀스를 입력으로 사용하고(또는 이 경우 두 개의 시퀀스) 단일 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-199">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="cc445-200">터미널 메서드를 사용하는 경우, 항상 LINQ 쿼리의 메서드 체인에서 최종 메서드이므로 이름이 “터미널”입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-200">When using terminal methods, they are always the final method in a chain of methods for a LINQ query, hence the name "terminal".</span></span>

<span data-ttu-id="cc445-201">이 메서드를 사용하여 데크가 원래 순서로 돌아갈 때를 확인하면 작동 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-201">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="cc445-202">순서 섞기 코드를 루프 내에 포함하고, `SequenceEquals()` 메서드를 적용하여 시퀀스가 원래 순서가 될 때 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-202">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="cc445-203">이 메서드는 시퀀스 대신 단일 값을 반환하므로 어떤 쿼리에서든지 항상 마지막 메서드로 사용되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-203">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="cc445-204">지금까지 작성한 코드를 실행하고 순서를 섞을 때마다 데크가 어떻게 다시 배열되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-204">Run the code you've got so far and take note of how the deck rearranges on each shuffle.</span></span> <span data-ttu-id="cc445-205">8번 순서 섞기(do-while 루프 반복) 후에 데크는 시작하는 LINQ 쿼리에서 처음 만들었을 때 데크의 원래 구성으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-205">After 8 shuffles (iterations of the do-while loop), the deck returns to the original configuration it was in when you first created it from the starting LINQ query.</span></span>

## <a name="optimizations"></a><span data-ttu-id="cc445-206">최적화</span><span class="sxs-lookup"><span data-stu-id="cc445-206">Optimizations</span></span>

<span data-ttu-id="cc445-207">지금까지 빌드한 샘플은 ‘외부 순서 섞기’를 실행합니다. 즉, 맨 위 및 맨 아래 카드가 실행할 때마다 항상 같은 위치에 있습니다. </span><span class="sxs-lookup"><span data-stu-id="cc445-207">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="cc445-208">한 가지 부분을 변경하겠습니다. 52장 카드의 위치가 모두 변경되는 ‘내부 순서 섞기’를 대신 사용하겠습니다. </span><span class="sxs-lookup"><span data-stu-id="cc445-208">Let's make one change: we'll use an *in shuffle* instead, where all 52 cards change position.</span></span> <span data-ttu-id="cc445-209">내부 순서 섞기의 경우 반으로 나눈 아래쪽 부분의 첫 번째 카드가 데크의 첫 번째 카드가 되도록 데크를 인터리빙합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-209">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="cc445-210">즉, 반으로 나눈 위쪽 부분의 마지막 카드가 맨 아래 카드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-210">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="cc445-211">이는 단일 코드 줄에 대한 간단한 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-211">This is a simple change to a singular line of code.</span></span> <span data-ttu-id="cc445-212"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>의 위치를 전환하여 현재 순서 섞기 쿼리를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-212">Update the current shuffle query by switching the positions of <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span> <span data-ttu-id="cc445-213">이렇게 하면 데크의 위쪽 절반과 아래쪽 절반의 순서가 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-213">This will change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="cc445-214">프로그램을 다시 실행합니다. 그러면 데크가 자체적으로 순서를 변경하는 데 52회 반복된다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-214">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="cc445-215">또한 프로그램이 계속 실행될 때 몇 가지 심각한 성능 저하를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-215">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="cc445-216">그 이유로는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-216">There are a number of reasons for this.</span></span> <span data-ttu-id="cc445-217">이 성능 저하의 주요 원인 중 하나인 비효율적인 [‘지연 계산’](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) 사용을 해결할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="cc445-217">You can tackle one of the major causes of this performance drop: inefficient use of [*lazy evaluation*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

<span data-ttu-id="cc445-218">간단히 말해, 지연 계산은 해당 값이 필요할 때까지 문이 계산되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-218">Briefly, lazy evaluation states that the evaluation of a statement is not performed until its value is needed.</span></span> <span data-ttu-id="cc445-219">LINQ 쿼리는 지연 계산되는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-219">LINQ queries are statements that are evaluated lazily.</span></span> <span data-ttu-id="cc445-220">요소가 요청될 때만 시퀀스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-220">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="cc445-221">일반적으로 이것이 LINQ의 큰 장점입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-221">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="cc445-222">그러나 이러한 프로그램에서 사용하면 실행 시간이 기하급수적으로 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-222">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="cc445-223">LINQ 쿼리를 사용하여 원래 데크를 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-223">Remember that we generated the original deck using a LINQ query.</span></span> <span data-ttu-id="cc445-224">각 순서 섞기는 이전 데크에 대해 세 개의 LINQ 쿼리를 수행하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-224">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="cc445-225">이러한 모든 쿼리는 느리게 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-225">All these are performed lazily.</span></span> <span data-ttu-id="cc445-226">즉, 시퀀스가 요청될 때마다 다시 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-226">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="cc445-227">52번째 반복에 도달할 때까지 원래 데크를 아주 여러 번 다시 생성하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-227">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="cc445-228">이 동작을 보여 주기 위해 로그를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-228">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="cc445-229">그런 후에 문제를 해결해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-229">Then, you'll fix it.</span></span>

<span data-ttu-id="cc445-230">`Extensions.cs` 파일에서 아래 메서드를 입력하거나 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-230">In your `Extensions.cs` file, type in or copy the method below.</span></span> <span data-ttu-id="cc445-231">이 확장 메서드는 프로젝트 디렉터리에 `debug.log`라는 새 파일을 만들고 현재 실행 중인 쿼리를 로그 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-231">This extension method creates a new file called `debug.log` within your project directory and records what query is currently being executed to the log file.</span></span> <span data-ttu-id="cc445-232">이 확장 메서드를 임의 쿼리에 추가하여 해당 쿼리가 실행되었음을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-232">This extension method can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="cc445-233">`File` 아래에 빨간색 물결이 나타나면 존재하지 않는다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-233">You will see a red squiggle under `File`, meaning it doesn't exist.</span></span> <span data-ttu-id="cc445-234">컴파일러가 `File`을 인식하지 못하기 때문에 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-234">It won't compile, since the compiler doesn't know what `File` is.</span></span> <span data-ttu-id="cc445-235">이 문제를 해결하려면 `Extensions.cs`의 첫 번째 줄 아래에 다음 코드 줄을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-235">To solve this problem, make sure to add the following line of code under the very first line in `Extensions.cs`:</span></span>

```csharp
using System.IO;
```

<span data-ttu-id="cc445-236">이렇게 하면 문제가 해결되고 빨간색 오류가 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-236">This should solve the issue and the red error disappears.</span></span>

<span data-ttu-id="cc445-237">그런 후 로그 메시지를 사용하여 각 쿼리의 정의를 계측합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-237">Next, instrument the definition of each query with a log message:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="cc445-238">쿼리에 액세스할 때마다 로깅하지는 않고,</span><span class="sxs-lookup"><span data-stu-id="cc445-238">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="cc445-239">원래 쿼리를 만들 때만 로깅합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-239">You log only when you create the original query.</span></span> <span data-ttu-id="cc445-240">프로그램을 실행하는 데 여전히 오래 걸리지만 이제 이유를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-240">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="cc445-241">로깅을 켠 상태로 내부 순서 섞기를 실행하다가 지치면 외부 순서 섞기로 다시 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-241">If you run out of patience running the in shuffle with logging turned on, switch back to the out shuffle.</span></span> <span data-ttu-id="cc445-242">여전히 지연 계산 효과가 나타날 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-242">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="cc445-243">한 번 실행에서 모든 값 및 세트 생성을 비롯한 2592개의 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-243">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="cc445-244">여기서 코드 성능을 개선하여 수행하는 실행 횟수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-244">You can improve the performance of the code here to reduce the number of executions you make.</span></span> <span data-ttu-id="cc445-245">간단한 해결 방법은 카드 데크를 구성하는 원래 LINQ 쿼리의 결과를 ‘캐시’하는 것입니다. </span><span class="sxs-lookup"><span data-stu-id="cc445-245">A simple fix you can make is to *cache* the results of the original LINQ query that constructs the deck of cards.</span></span> <span data-ttu-id="cc445-246">현재, do-while 루프가 반복될 때마다 쿼리를 계속해서 다시 실행하고 카드 데크를 다시 구성하며 매번 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-246">Currently, you're executing the queries again and again every time the do-while loop goes through an iteration, re-constructing the deck of cards and reshuffling it every time.</span></span> <span data-ttu-id="cc445-247">카드 데크를 캐시하려면 LINQ 메서드 <xref:System.Linq.Enumerable.ToArray%2A> 및 <xref:System.Linq.Enumerable.ToList%2A>를 활용합니다. 두 메서드를 쿼리에 추가하면 지정된 대로 동일한 작업을 수행하지만, 이제 호출하도록 선택한 메서드에 따라 배열이나 목록에 결과를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-247">To cache the deck of cards, you can leverage the LINQ methods <xref:System.Linq.Enumerable.ToArray%2A> and <xref:System.Linq.Enumerable.ToList%2A>; when you append them to the queries, they'll perform the same actions you've told them to, but now they'll store the results in an array or a list, depending on which method you choose to call.</span></span> <span data-ttu-id="cc445-248">LINQ 메서드 <xref:System.Linq.Enumerable.ToArray%2A>를 두 쿼리에 모두 추가하고 프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-248">Append the LINQ method <xref:System.Linq.Enumerable.ToArray%2A> to both queries and run the program again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="cc445-249">이제 외부 순서 섞기가 30개 쿼리로 줄었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-249">Now the out shuffle is down to 30 queries.</span></span> <span data-ttu-id="cc445-250">내부 순서 섞기로 다시 실행해도 비슷하게 개선된 것을 확인할 수 있습니다. 이제 162개 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-250">Run again with the in shuffle and you'll see similar improvements: it now executes 162 queries.</span></span>

<span data-ttu-id="cc445-251">이 예제는 지연 계산이 성능 문제를 일으킬 수 있는 사용 사례를 중점적으로 나타내도록 **작성**되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-251">Please note that this example is **designed** to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="cc445-252">지연 계산이 코드 성능에 영향을 줄 수 있는 위치를 확인하는 것만큼이나 모든 쿼리를 즉시 실행해야 하는 것은 아님을 이해하는 것도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-252">While it's important to see where lazy evaluation can impact code performance, it's equally important to understand that not all queries should run eagerly.</span></span> <span data-ttu-id="cc445-253"><xref:System.Linq.Enumerable.ToArray%2A>를 사용하지 않을 경우 발생하는 성능 저하는 카드 데크의 새로운 배열이 각각 이전 배열에서 빌드되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-253">The performance hit you incur without using <xref:System.Linq.Enumerable.ToArray%2A> is because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="cc445-254">지연 계산을 사용한다는 것은 각 새 데크 구성이 원래 데크에서 빌드되며, 심지어 `startingDeck`를 빌드한 코드를 실행하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-254">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="cc445-255">이로 인해 많은 양의 추가 작업이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-255">That causes a large amount of extra work.</span></span>

<span data-ttu-id="cc445-256">실제로 즉시 계산을 사용할 때 잘 실행되는 알고리즘도 있고, 지연 계산을 사용할 때 잘 실행되는 알고리즘도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-256">In practice, some algorithms run well using eager evaluation, and others run well using lazy evaluation.</span></span> <span data-ttu-id="cc445-257">일상적인 사용에서 지연 계산은 대체로 데이터베이스 엔진과 같이 데이터 소스가 별도 프로세스일 때 사용하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-257">For daily usage, lazy evaluation is usually a better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="cc445-258">데이터베이스의 경우 지연 계산을 통해 더 복잡한 쿼리에서 데이터베이스 프로세스로 하나의 왕복만 실행하고 나머지 코드 부분으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-258">For databases, lazy evaluation allows more complex queries to execute only one round trip to the database process and back to the rest of your code.</span></span> <span data-ttu-id="cc445-259">LINQ에서는 지연 계산을 실행할지, 아니면 즉시 계산을 실행할지를 유연하게 선택할 수 있으므로 프로세스를 측정하여 최상의 성능을 제공하는 계산 종류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-259">LINQ is flexible whether you choose to utilize lazy or eager evaluation, so measure your processes and pick whichever kind of evaluation gives you the best performance.</span></span>

## <a name="conclusion"></a><span data-ttu-id="cc445-260">결론</span><span class="sxs-lookup"><span data-stu-id="cc445-260">Conclusion</span></span>

<span data-ttu-id="cc445-261">이 프로젝트에서는 다음 내용을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-261">In this project, you covered:</span></span>

- <span data-ttu-id="cc445-262">LINQ 쿼리를 사용하여 데이터를 의미 있는 시퀀스로 집계</span><span class="sxs-lookup"><span data-stu-id="cc445-262">using LINQ queries to aggregate data into a meaningful sequence</span></span>
- <span data-ttu-id="cc445-263">고유한 사용자 지정 기능을 LINQ 쿼리에 추가하는 확장 메서드 작성</span><span class="sxs-lookup"><span data-stu-id="cc445-263">writing Extension methods to add our own custom functionality to LINQ queries</span></span>
- <span data-ttu-id="cc445-264">LINQ 쿼리에서 성능 저하와 같은 성능 문제가 발생할 수 있는 코드 영역 찾기</span><span class="sxs-lookup"><span data-stu-id="cc445-264">locating areas in our code where our LINQ queries might run into performance issues like degraded speed</span></span>
- <span data-ttu-id="cc445-265">LINQ 쿼리와 관련된 지연 및 즉시 계산과 쿼리 성능에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="cc445-265">lazy and eager evaluation in regards to LINQ queries and the implications they might have on query performance</span></span>

<span data-ttu-id="cc445-266">LINQ 외에도 마법사가 카드 속임수에 사용하는 기술에 대해 약간 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-266">Aside from LINQ, you learned a bit about a technique magicians use for card tricks.</span></span> <span data-ttu-id="cc445-267">마술사는 데크에서 모든 카드가 이동하는 위치를 제어할 수 있으므로 파로 순서 섞기 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc445-267">Magicians use the Faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="cc445-268">이제 기술을 알고 있으니, 다른 모든 사용자를 위해 망치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cc445-268">Now that you know, don't spoil it for everyone else!</span></span>

<span data-ttu-id="cc445-269">LINQ에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc445-269">For more information on LINQ, see:</span></span>

- [<span data-ttu-id="cc445-270">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="cc445-270">Language Integrated Query (LINQ)</span></span>](../programming-guide/concepts/linq/index.md)
  - [<span data-ttu-id="cc445-271">LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="cc445-271">Introduction to LINQ</span></span>](../programming-guide/concepts/linq/index.md)
  - [<span data-ttu-id="cc445-272">기본 LINQ 쿼리 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="cc445-272">Basic LINQ Query Operations (C#)</span></span>](../programming-guide/concepts/linq/basic-linq-query-operations.md)
  - [<span data-ttu-id="cc445-273">LINQ를 통한 데이터 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="cc445-273">Data Transformations With LINQ (C#)</span></span>](../programming-guide/concepts/linq/data-transformations-with-linq.md)
  - [<span data-ttu-id="cc445-274">LINQ의 쿼리 구문 및 메서드 구문(C#)</span><span class="sxs-lookup"><span data-stu-id="cc445-274">Query Syntax and Method Syntax in LINQ (C#)</span></span>](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
  - [<span data-ttu-id="cc445-275">LINQ를 지원하는 C# 기능</span><span class="sxs-lookup"><span data-stu-id="cc445-275">C# Features That Support LINQ</span></span>](../programming-guide/concepts/linq/features-that-support-linq.md)
