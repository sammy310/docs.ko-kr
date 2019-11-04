---
title: 비동기 스트림 생성 및 사용
description: 이 고급 자습서에서는 비동기 스트림을 생성 및 사용하여 비동기적으로 생성될 수 있는 데이터 시퀀스를 사용하는 더 자연스러운 방법을 제공하는 시나리오를 보여 줍니다.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: 412e5de5d9d73846fe2af36e3def383364389c75
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039216"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a><span data-ttu-id="a4e5a-103">자습서: C# 8.0 및 .NET Core 3.0을 사용하여 비동기 스트림 생성 및 사용</span><span class="sxs-lookup"><span data-stu-id="a4e5a-103">Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0</span></span>

<span data-ttu-id="a4e5a-104">C# 8.0은 데이터 스트림의 요소를 비동기적으로 검색하거나 생성할 수 있는 경우 데이터의 스트리밍 소스를 모델링하는 **비동기 스트림**을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-104">C# 8.0 introduces **async streams**, which model a streaming source of data when the elements in the data stream may be retrieved or generated asynchronously.</span></span> <span data-ttu-id="a4e5a-105">비동기 스트림은 .NET Standard 2.1에서 도입되고 .NET Core 3.0에서 구현된 새 인터페이스를 사용하여 비동기 스트리밍 데이터 소스의 일반 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-105">Async streams rely on new interfaces introduced in .NET Standard 2.1 and implemented in .NET Core 3.0 to provide a natural programming model for asynchronous streaming data sources.</span></span>

<span data-ttu-id="a4e5a-106">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="a4e5a-107">데이터 요소 시퀀스를 비동기적으로 생성하는 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-107">Create a data source that generates a sequence of data elements asynchronously.</span></span>
> - <span data-ttu-id="a4e5a-108">데이터 소스를 비동기적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-108">Consume that data source asynchronously.</span></span>
> - <span data-ttu-id="a4e5a-109">새 인터페이스 및 데이터 소스가 이전 동기 데이터 시퀀스로 기본 설정되는 경우를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-109">Recognize when the new interface and data source are preferred to earlier synchronous data sequences.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4e5a-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a4e5a-110">Prerequisites</span></span>

<span data-ttu-id="a4e5a-111">C# 8.0 컴파일러를 포함하여 .NET Core를 실행하도록 머신을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-111">You’ll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="a4e5a-112">C# 8 컴파일러는 [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 또는 [.NET CORE 3.0 SDK](https://dotnet.microsoft.com/download)부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-112">The C# 8 compiler is available starting with [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="a4e5a-113">GitHub GraphQL 엔드포인트에 액세스할 수 있도록 [GitHub 액세스 토큰](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-113">You'll need to create a [GitHub access token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) so that you can access the GitHub GraphQL endpoint.</span></span> <span data-ttu-id="a4e5a-114">GitHub 액세스 토큰에 사용할 다음 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-114">Select the following permissions for your GitHub Access Token:</span></span>

- <span data-ttu-id="a4e5a-115">repo:status</span><span class="sxs-lookup"><span data-stu-id="a4e5a-115">repo:status</span></span>
- <span data-ttu-id="a4e5a-116">public_repo</span><span class="sxs-lookup"><span data-stu-id="a4e5a-116">public_repo</span></span>

<span data-ttu-id="a4e5a-117">GitHub API 엔드포인트의 액세스 권한을 부여하는 데 사용할 수 있도록 액세스 토큰을 안전한 장소에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-117">Save the access token in a safe place so you can use it to gain access to the GitHub API endpoint.</span></span>

> [!WARNING]
> <span data-ttu-id="a4e5a-118">개인용 액세스 토큰을 안전하게 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-118">Keep your personal access token secure.</span></span> <span data-ttu-id="a4e5a-119">개인용 액세스 토큰이 있는 소프트웨어는 액세스 권한을 사용하여 GitHub API 호출을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-119">Any software with your personal access token could make GitHub API calls using your access rights.</span></span>

<span data-ttu-id="a4e5a-120">이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-120">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="run-the-starter-application"></a><span data-ttu-id="a4e5a-121">시작 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a4e5a-121">Run the starter application</span></span>

<span data-ttu-id="a4e5a-122">[csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) 폴더의 [dotnet/samples](https://github.com/dotnet/samples) 리포지토리에서 이 자습서에 사용된 시작 애플리케이션의 코드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-122">You can get the code for the starter application used in this tutorial from our [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) folder.</span></span>

<span data-ttu-id="a4e5a-123">시작 애플리케이션은 [GitHub GraphQL](https://developer.github.com/v4/) 인터페이스를 사용하여 [dotnet/docs](https://github.com/dotnet/docs) 리포지토리에 기록된 최근 문제를 검색하는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-123">The starter application is a console application that uses the [GitHub GraphQL](https://developer.github.com/v4/) interface to retrieve recent issues written in the [dotnet/docs](https://github.com/dotnet/docs) repository.</span></span> <span data-ttu-id="a4e5a-124">먼저 시작 앱 `Main` 메서드의 다음 코드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-124">Start by looking at the following code for the starter app `Main` method:</span></span>

[!code-csharp[StarterAppMain](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

<span data-ttu-id="a4e5a-125">`GitHubKey` 환경 변수를 개인용 액세스 토큰으로 설정하거나, `GenEnvVariable` 호출의 마지막 인수를 개인용 액세스 토큰으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-125">You can either set a `GitHubKey` environment variable to your personal access token, or you can replace the last argument in the call to `GenEnvVariable` with your personal access token.</span></span> <span data-ttu-id="a4e5a-126">소스를 다른 항목과 함께 저장하거나 공유 소스 리포지토리에 넣을 경우에는 액세스 코드를 소스 코드에 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-126">Don't put your access code in source code if you'll be saving the source with others, or putting it in a shared source repository.</span></span>

<span data-ttu-id="a4e5a-127">GitHub 클라이언트를 만든 후 `Main`의 코드는 진행 보고 개체 및 취소 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-127">After creating the GitHub client, the code in `Main` creates a progress reporting object and a cancellation token.</span></span> <span data-ttu-id="a4e5a-128">해당 개체가 만들어지면 `Main`이 `runPagedQueryAsync`를 호출하여 250개의 가장 최근 생성된 문제를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-128">Once those objects are created, `Main` calls `runPagedQueryAsync` to retrieve the most recent 250 created issues.</span></span> <span data-ttu-id="a4e5a-129">작업이 완료되면 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-129">After that task has finished, the results are displayed.</span></span>

<span data-ttu-id="a4e5a-130">시작 애플리케이션을 실행할 때 이 애플리케이션의 실행 방식에 대한 몇 가지 중요한 사항을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-130">When you run the starter application, you can make some important observations about how this application runs.</span></span>  <span data-ttu-id="a4e5a-131">GitHub에서 반환된 각 페이지에 대해 보고된 진행 상황이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-131">You'll see progress reported for each page returned from GitHub.</span></span> <span data-ttu-id="a4e5a-132">GitHub가 각 새로운 문제 페이지를 반환하기 전에 분명한 일시 정지를 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-132">You can observe a noticeable pause before GitHub returns each new page of issues.</span></span> <span data-ttu-id="a4e5a-133">마지막으로 이 문제는 10페이지가 GitHub에서 모두 검색된 후에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-133">Finally, the issues are displayed only after all 10 pages have been retrieved from GitHub.</span></span>

## <a name="examine-the-implementation"></a><span data-ttu-id="a4e5a-134">구현 살펴보기</span><span class="sxs-lookup"><span data-stu-id="a4e5a-134">Examine the implementation</span></span>

<span data-ttu-id="a4e5a-135">구현은 이전 섹션에서 설명한 동작을 관찰한 이유를 드러냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-135">The implementation reveals why you observed the behavior discussed in the previous section.</span></span> <span data-ttu-id="a4e5a-136">`runPagedQueryAsync`에 대한 코드를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-136">Examine the code for `runPagedQueryAsync`:</span></span>

[!code-csharp[RunPagedQueryStarter](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

<span data-ttu-id="a4e5a-137">앞 코드의 페이징 알고리즘 및 비동기 구조를 중점적으로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-137">Let's concentrate on the paging algorithm and async structure of the preceding code.</span></span> <span data-ttu-id="a4e5a-138">(GitHub GraphQL API에 대한 자세한 내용은 [GitHub GraphQL 설명서](https://developer.github.com/v4/guides/)를 참조하세요.) `runPagedQueryAsync` 메서드는 가장 최근에서 가장 오래된 순서로 문제를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-138">(You can consult the [GitHub GraphQL documentation](https://developer.github.com/v4/guides/) for details on the GitHub GraphQL API.) The `runPagedQueryAsync` method enumerates the issues from most recent to oldest.</span></span> <span data-ttu-id="a4e5a-139">이 메서드는 페이지당 25개 문제를 요청하고 응답의 `pageInfo` 구조체를 검사하여 이전 페이지를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-139">It requests 25 issues per page and examines the `pageInfo` structure of the response to continue with the previous page.</span></span> <span data-ttu-id="a4e5a-140">다중 페이지 응답에 대한 GraphQL의 표준 페이징 지원을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-140">That follows GraphQL's standard paging support for multi-page responses.</span></span> <span data-ttu-id="a4e5a-141">응답에는 이전 페이지를 요청하는 데 사용되는 `hasPreviousPages` 값과 `startCursor` 값을 포함하는 `pageInfo` 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-141">The response includes a `pageInfo` object that includes a `hasPreviousPages` value and a `startCursor` value used to request the previous page.</span></span> <span data-ttu-id="a4e5a-142">문제는 `nodes` 배열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-142">The issues are in the `nodes` array.</span></span> <span data-ttu-id="a4e5a-143">`runPagedQueryAsync` 메서드는 모든 페이지의 모든 결과를 포함하는 배열에 해당 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-143">The `runPagedQueryAsync` method appends these nodes to an array that contains all the results from all pages.</span></span>

<span data-ttu-id="a4e5a-144">결과 페이지를 검색 및 복원한 후에 `runPagedQueryAsync`가 진행 상황을 보고하고 취소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-144">After retrieving and restoring a page of results, `runPagedQueryAsync` reports progress and checks for cancellation.</span></span> <span data-ttu-id="a4e5a-145">취소가 요청된 경우 `runPagedQueryAsync`가 <xref:System.OperationCanceledException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-145">If cancellation has been requested, `runPagedQueryAsync` throws an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="a4e5a-146">이 코드에서 여러 가지 요소를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-146">There are several elements in this code that can be improved.</span></span> <span data-ttu-id="a4e5a-147">가장 중요한 것은 `runPagedQueryAsync`가 반환된 모든 문제에 대해 스토리지를 할당해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-147">Most importantly, `runPagedQueryAsync` must allocate storage for all the issues returned.</span></span> <span data-ttu-id="a4e5a-148">모든 미해결 문제를 검색하면 모든 검색된 문제를 저장하는 데 훨씬 더 많은 메모리가 필요하므로 이 샘플은 250개 문제만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-148">This sample stops at 250 issues because retrieving all open issues would require much more memory to store all the retrieved issues.</span></span> <span data-ttu-id="a4e5a-149">또한 진행 지원 및 취소 지원 프로토콜로 인해 알고리즘을 처음 읽을 때 이해하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-149">In addition, the protocols for supporting progress and supporting cancellation make the algorithm harder to understand on its first reading.</span></span> <span data-ttu-id="a4e5a-150">진행이 보고되는 위치를 찾으려면 progress 클래스를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-150">You must look for the progress class to find where progress is reported.</span></span> <span data-ttu-id="a4e5a-151">또한 취소 요청 위치 및 제공 위치를 파악하려면 <xref:System.Threading.CancellationTokenSource> 및 연결된 <xref:System.Threading.CancellationToken>을 통해 통신을 추적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-151">You also have to trace the communications through the <xref:System.Threading.CancellationTokenSource> and its associated <xref:System.Threading.CancellationToken> to understand where cancellation is requested and where it's granted.</span></span>

## <a name="async-streams-provide-a-better-way"></a><span data-ttu-id="a4e5a-152">더 나은 방법을 제공하는 비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="a4e5a-152">Async streams provide a better way</span></span>

<span data-ttu-id="a4e5a-153">비동기 스트림 및 연결된 언어 지원으로 해당 문제가 모두 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-153">Async streams and the associated language support address all those concerns.</span></span> <span data-ttu-id="a4e5a-154">시퀀스를 생성하는 코드에서 이제 `yield return`을 사용하여 `async` 한정자로 선언된 메서드에서 요소를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-154">The code that generates the sequence can now use `yield return` to return elements in a method that was declared with the `async` modifier.</span></span> <span data-ttu-id="a4e5a-155">`foreach` 루프를 통해 시퀀스를 사용하는 것처럼 `await foreach` 루프를 통해 비동기 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-155">You can consume an async stream using an `await foreach` loop just as you consume any sequence using a `foreach` loop.</span></span>

<span data-ttu-id="a4e5a-156">이 새로운 언어 기능은 .NET Standard 2.1에 추가되고 .NET Core 3.0에 구현된 세 가지 새 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-156">These new language features depend on three new interfaces added to .NET Standard 2.1 and implemented in .NET Core 3.0:</span></span>

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

<span data-ttu-id="a4e5a-157">이 세 가지 인터페이스는 대부분의 C# 개발자에게 익숙합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-157">These three interfaces should be familiar to most C# developers.</span></span> <span data-ttu-id="a4e5a-158">이 인터페이스는 동기 인터페이스와 유사한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-158">They behave in a manner similar to their synchronous counterparts:</span></span>

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

<span data-ttu-id="a4e5a-159">익숙하지 않을 수도 있는 하나의 형식은 <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-159">One type that may be unfamiliar is <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a4e5a-160">`ValueTask` 구조체는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스에 유사한 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-160">The `ValueTask` struct provides a similar API to the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a4e5a-161">`ValueTask`는 성능상의 이유로 해당 인터페이스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-161">`ValueTask` is used in these interfaces for performance reasons.</span></span>

## <a name="convert-to-async-streams"></a><span data-ttu-id="a4e5a-162">비동기 스트림으로 변환</span><span class="sxs-lookup"><span data-stu-id="a4e5a-162">Convert to async streams</span></span>

<span data-ttu-id="a4e5a-163">그런 다음, `runPagedQueryAsync` 메서드를 변환하여 비동기 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-163">Next, convert the `runPagedQueryAsync` method to generate an async stream.</span></span> <span data-ttu-id="a4e5a-164">먼저 `runPagedQueryAsync`의 시그니처를 변경하여 `IAsyncEnumerable<JToken>`을 반환하고 다음 코드에 표시된 대로 매개 변수 목록에서 취소 토큰 및 진행 개체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-164">First, change the signature of `runPagedQueryAsync` to return an `IAsyncEnumerable<JToken>`, and remove the cancellation token and progress objects from the parameter list as shown in the following code:</span></span>

[!code-csharp[FinishedSignature](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

<span data-ttu-id="a4e5a-165">시작 코드는 다음 코드에 표시된 대로 페이지가 검색될 때 각 페이지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-165">The starter code processes each page as the page is retrieved, as shown in the following code:</span></span>

[!code-csharp[StarterPaging](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

<span data-ttu-id="a4e5a-166">해당 세 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-166">Replace those three lines with the following code:</span></span>

[!code-csharp[FinishedPaging](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

<span data-ttu-id="a4e5a-167">이 메서드의 앞부분에 있는 `finalResults` 선언 및 수정한 루프 뒤에 있는 `return` 문을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-167">You can also remove the declaration of `finalResults` earlier in this method and the `return` statement that follows the loop you modified.</span></span>

<span data-ttu-id="a4e5a-168">비동기 스트림을 생성하기 위한 변경을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-168">You've finished the changes to generate an async stream.</span></span> <span data-ttu-id="a4e5a-169">완료된 메서드는 아래 코드와 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-169">The finished method should resemble the code below:</span></span>

[!code-csharp[FinishedGenerate](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

<span data-ttu-id="a4e5a-170">그런 다음, 컬렉션을 사용하는 코드를 변경하여 비동기 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-170">Next, you change the code that consumes the collection to consume the async stream.</span></span> <span data-ttu-id="a4e5a-171">문제 컬렉션을 처리하는 `Main`에서 다음 코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-171">Find the following code in `Main` that processes the collection of issues:</span></span>

[!code-csharp[EnumerateOldStyle](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

<span data-ttu-id="a4e5a-172">해당 코드를 다음 `await foreach` 루프로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-172">Replace that code with the following `await foreach` loop:</span></span>

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

<span data-ttu-id="a4e5a-173">[csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) 폴더의 [dotnet/samples](https://github.com/dotnet/samples) 리포지토리에서 완료된 자습서의 코드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-173">You can get the code for the finished tutorial from the [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) folder.</span></span>

## <a name="run-the-finished-application"></a><span data-ttu-id="a4e5a-174">완료된 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a4e5a-174">Run the finished application</span></span>

<span data-ttu-id="a4e5a-175">애플리케이션을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-175">Run the application again.</span></span> <span data-ttu-id="a4e5a-176">해당 동작을 시작 애플리케이션의 동작과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-176">Contrast its behavior with the behavior of the starter application.</span></span> <span data-ttu-id="a4e5a-177">결과의 첫 번째 페이지는 사용 가능한 즉시 열거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-177">The first page of results is enumerated as soon as it's available.</span></span> <span data-ttu-id="a4e5a-178">새로운 각 페이지가 요청 및 검색될 때 확인 가능한 일시 정지가 있고 난 뒤 다음 페이지의 결과가 빠르게 열거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-178">There's an observable pause as each new page is requested and retrieved, then the next page's results are quickly enumerated.</span></span> <span data-ttu-id="a4e5a-179">취소를 처리하는 데는 `try` / `catch` 블록이 필요하지 않습니다. 호출자가 컬렉션의 열거를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-179">The `try` / `catch` block isn't needed to handle cancellation: the caller can stop enumerating the collection.</span></span> <span data-ttu-id="a4e5a-180">각 페이지가 다운로드될 때 비동기 스트림이 결과를 생성하므로 진행이 명확하게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-180">Progress is clearly reported because the async stream generates results as each page is downloaded.</span></span> <span data-ttu-id="a4e5a-181">반환된 각 문제에 대한 상태는 `await foreach` 루프에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-181">The status for each issue returned is seamlessly included in the `await foreach` loop.</span></span> <span data-ttu-id="a4e5a-182">진행 상황을 추적하는 데 콜백 개체가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-182">You don't need a callback object to track progress.</span></span>

<span data-ttu-id="a4e5a-183">코드를 검사하여 향상된 메모리 사용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-183">You can see improvements in memory use by examining the code.</span></span> <span data-ttu-id="a4e5a-184">열거되기 전에 모든 결과를 저장하기 위해 더 이상 컬렉션을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-184">You no longer need to allocate a collection to store all the results before they're enumerated.</span></span> <span data-ttu-id="a4e5a-185">호출자는 결과를 사용하는 방법 및 스토리지 컬렉션이 필요한지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-185">The caller can determine how to consume the results and if a storage collection is needed.</span></span>

<span data-ttu-id="a4e5a-186">시작 및 완료된 애플리케이션을 둘 다 실행하고 직접 구현 간 차이를 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-186">Run both the starter and finished applications and you can observe the differences between the implementations for yourself.</span></span> <span data-ttu-id="a4e5a-187">완료한 후 이 자습서를 시작할 때 만든 GitHub 액세스 토큰을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-187">You can delete the GitHub access token you created when you started this tutorial after you've finished.</span></span> <span data-ttu-id="a4e5a-188">공격자가 해당 토큰의 액세스 권한을 얻으면 사용자의 자격 증명을 사용하여 GitHub API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e5a-188">If an attacker gained access to that token, they could access GitHub APIs using your credentials.</span></span>
