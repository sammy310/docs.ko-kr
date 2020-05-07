---
title: 비동기 스트림 생성 및 사용
description: 이 고급 자습서에서는 비동기 스트림을 생성하고 사용하는 방법을 보여 줍니다. 비동기 스트림은 비동기적으로 생성될 수 있는 데이터 시퀀스를 사용하는 보다 자연스러운 방법을 제공합니다.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: 03254e5208a048469f4753d632de7b0d451cde40
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200108"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a><span data-ttu-id="c1744-104">자습서: C# 8.0 및 .NET Core 3.0을 사용하여 비동기 스트림 생성 및 사용</span><span class="sxs-lookup"><span data-stu-id="c1744-104">Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0</span></span>

<span data-ttu-id="c1744-105">C# 8.0에서는 데이터의 스트리밍 소스를 모델링하는 **비동기 스트림**을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-105">C# 8.0 introduces **async streams**, which model a streaming source of data.</span></span> <span data-ttu-id="c1744-106">데이터 스트림은 종종 요소를 비동기적으로 검색하거나 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-106">Data streams often retrieve or generate elements asynchronously.</span></span> <span data-ttu-id="c1744-107">비동기 스트림은 .NET Standard 2.1에 도입된 새 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-107">Async streams rely on new interfaces introduced in .NET Standard 2.1.</span></span> <span data-ttu-id="c1744-108">이 인터페이스는 .NET Core 3.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-108">These interfaces are supported in .NET Core 3.0 and later.</span></span> <span data-ttu-id="c1744-109">비동기 스트리밍 데이터 소스의 자연스러운 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-109">They provide a natural programming model for asynchronous streaming data sources.</span></span>

<span data-ttu-id="c1744-110">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-110">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="c1744-111">데이터 요소 시퀀스를 비동기적으로 생성하는 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-111">Create a data source that generates a sequence of data elements asynchronously.</span></span>
> - <span data-ttu-id="c1744-112">데이터 소스를 비동기적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-112">Consume that data source asynchronously.</span></span>
> - <span data-ttu-id="c1744-113">비동기 스트림의 취소 및 캡처된 컨텍스트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-113">Support cancellation and captured contexts for asynchronous streams.</span></span>
> - <span data-ttu-id="c1744-114">새 인터페이스 및 데이터 소스가 이전 동기 데이터 시퀀스로 기본 설정되는 경우를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-114">Recognize when the new interface and data source are preferred to earlier synchronous data sequences.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1744-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1744-115">Prerequisites</span></span>

<span data-ttu-id="c1744-116">C# 8.0 컴파일러를 포함하여 .NET Core를 실행하도록 컴퓨터를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-116">You'll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="c1744-117">C# 8 컴파일러는 [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 또는 [.NET CORE 3.0 SDK](https://dotnet.microsoft.com/download)부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-117">The C# 8 compiler is available starting with [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="c1744-118">GitHub GraphQL 엔드포인트에 액세스할 수 있도록 [GitHub 액세스 토큰](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-118">You'll need to create a [GitHub access token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) so that you can access the GitHub GraphQL endpoint.</span></span> <span data-ttu-id="c1744-119">GitHub 액세스 토큰에 사용할 다음 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-119">Select the following permissions for your GitHub Access Token:</span></span>

- <span data-ttu-id="c1744-120">repo:status</span><span class="sxs-lookup"><span data-stu-id="c1744-120">repo:status</span></span>
- <span data-ttu-id="c1744-121">public_repo</span><span class="sxs-lookup"><span data-stu-id="c1744-121">public_repo</span></span>

<span data-ttu-id="c1744-122">GitHub API 엔드포인트의 액세스 권한을 부여하는 데 사용할 수 있도록 액세스 토큰을 안전한 장소에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-122">Save the access token in a safe place so you can use it to gain access to the GitHub API endpoint.</span></span>

> [!WARNING]
> <span data-ttu-id="c1744-123">개인용 액세스 토큰을 안전하게 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-123">Keep your personal access token secure.</span></span> <span data-ttu-id="c1744-124">개인용 액세스 토큰이 있는 소프트웨어는 액세스 권한을 사용하여 GitHub API 호출을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-124">Any software with your personal access token could make GitHub API calls using your access rights.</span></span>

<span data-ttu-id="c1744-125">이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-125">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="run-the-starter-application"></a><span data-ttu-id="c1744-126">시작 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="c1744-126">Run the starter application</span></span>

<span data-ttu-id="c1744-127">[csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/start) 폴더의 [dotnet/docs](https://github.com/dotnet/docs) 리포지토리에서 이 자습서에 사용된 시작 애플리케이션의 코드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-127">You can get the code for the starter application used in this tutorial from the [dotnet/docs](https://github.com/dotnet/docs) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/start) folder.</span></span>

<span data-ttu-id="c1744-128">시작 애플리케이션은 [GitHub GraphQL](https://developer.github.com/v4/) 인터페이스를 사용하여 [dotnet/docs](https://github.com/dotnet/docs) 리포지토리에 기록된 최근 문제를 검색하는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-128">The starter application is a console application that uses the [GitHub GraphQL](https://developer.github.com/v4/) interface to retrieve recent issues written in the [dotnet/docs](https://github.com/dotnet/docs) repository.</span></span> <span data-ttu-id="c1744-129">먼저 시작 앱 `Main` 메서드의 다음 코드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-129">Start by looking at the following code for the starter app `Main` method:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetStarterAppMain" :::

<span data-ttu-id="c1744-130">`GitHubKey` 환경 변수를 개인용 액세스 토큰으로 설정하거나, `GenEnvVariable` 호출의 마지막 인수를 개인용 액세스 토큰으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-130">You can either set a `GitHubKey` environment variable to your personal access token, or you can replace the last argument in the call to `GenEnvVariable` with your personal access token.</span></span> <span data-ttu-id="c1744-131">소스를 다른 사용자와 공유하는 경우 소스 코드에 액세스 코드를 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c1744-131">Don't put your access code in source code if you'll be sharing the source with others.</span></span> <span data-ttu-id="c1744-132">공유된 소스 리포지토리에 액세스 코드를 업로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c1744-132">Never upload access codes to a shared source repository.</span></span>

<span data-ttu-id="c1744-133">GitHub 클라이언트를 만든 후 `Main`의 코드는 진행 보고 개체 및 취소 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-133">After creating the GitHub client, the code in `Main` creates a progress reporting object and a cancellation token.</span></span> <span data-ttu-id="c1744-134">해당 개체가 만들어지면 `Main`이 `runPagedQueryAsync`를 호출하여 250개의 가장 최근 생성된 문제를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-134">Once those objects are created, `Main` calls `runPagedQueryAsync` to retrieve the most recent 250 created issues.</span></span> <span data-ttu-id="c1744-135">작업이 완료되면 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-135">After that task has finished, the results are displayed.</span></span>

<span data-ttu-id="c1744-136">시작 애플리케이션을 실행할 때 이 애플리케이션의 실행 방식에 대한 몇 가지 중요한 사항을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-136">When you run the starter application, you can make some important observations about how this application runs.</span></span>  <span data-ttu-id="c1744-137">GitHub에서 반환된 각 페이지에 대해 보고된 진행 상황이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-137">You'll see progress reported for each page returned from GitHub.</span></span> <span data-ttu-id="c1744-138">GitHub가 각 새로운 문제 페이지를 반환하기 전에 분명한 일시 정지를 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-138">You can observe a noticeable pause before GitHub returns each new page of issues.</span></span> <span data-ttu-id="c1744-139">마지막으로 이 문제는 10페이지가 GitHub에서 모두 검색된 후에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-139">Finally, the issues are displayed only after all 10 pages have been retrieved from GitHub.</span></span>

## <a name="examine-the-implementation"></a><span data-ttu-id="c1744-140">구현 살펴보기</span><span class="sxs-lookup"><span data-stu-id="c1744-140">Examine the implementation</span></span>

<span data-ttu-id="c1744-141">구현은 이전 섹션에서 설명한 동작을 관찰한 이유를 드러냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-141">The implementation reveals why you observed the behavior discussed in the previous section.</span></span> <span data-ttu-id="c1744-142">`runPagedQueryAsync`에 대한 코드를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-142">Examine the code for `runPagedQueryAsync`:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetRunPagedQuery" :::

<span data-ttu-id="c1744-143">앞 코드의 페이징 알고리즘 및 비동기 구조를 중점적으로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-143">Let's concentrate on the paging algorithm and async structure of the preceding code.</span></span> <span data-ttu-id="c1744-144">(GitHub GraphQL API에 대한 자세한 내용은 [GitHub GraphQL 설명서](https://developer.github.com/v4/guides/)를 참조하세요.) `runPagedQueryAsync` 메서드는 가장 최근에서 가장 오래된 순서로 문제를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-144">(You can consult the [GitHub GraphQL documentation](https://developer.github.com/v4/guides/) for details on the GitHub GraphQL API.) The `runPagedQueryAsync` method enumerates the issues from most recent to oldest.</span></span> <span data-ttu-id="c1744-145">이 메서드는 페이지당 25개 문제를 요청하고 응답의 `pageInfo` 구조체를 검사하여 이전 페이지를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-145">It requests 25 issues per page and examines the `pageInfo` structure of the response to continue with the previous page.</span></span> <span data-ttu-id="c1744-146">다중 페이지 응답에 대한 GraphQL의 표준 페이징 지원을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-146">That follows GraphQL's standard paging support for multi-page responses.</span></span> <span data-ttu-id="c1744-147">응답에는 이전 페이지를 요청하는 데 사용되는 `hasPreviousPages` 값과 `startCursor` 값을 포함하는 `pageInfo` 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-147">The response includes a `pageInfo` object that includes a `hasPreviousPages` value and a `startCursor` value used to request the previous page.</span></span> <span data-ttu-id="c1744-148">문제는 `nodes` 배열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-148">The issues are in the `nodes` array.</span></span> <span data-ttu-id="c1744-149">`runPagedQueryAsync` 메서드는 모든 페이지의 모든 결과를 포함하는 배열에 해당 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-149">The `runPagedQueryAsync` method appends these nodes to an array that contains all the results from all pages.</span></span>

<span data-ttu-id="c1744-150">결과 페이지를 검색 및 복원한 후에 `runPagedQueryAsync`가 진행 상황을 보고하고 취소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-150">After retrieving and restoring a page of results, `runPagedQueryAsync` reports progress and checks for cancellation.</span></span> <span data-ttu-id="c1744-151">취소가 요청된 경우 `runPagedQueryAsync`가 <xref:System.OperationCanceledException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-151">If cancellation has been requested, `runPagedQueryAsync` throws an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="c1744-152">이 코드에서 여러 가지 요소를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-152">There are several elements in this code that can be improved.</span></span> <span data-ttu-id="c1744-153">가장 중요한 것은 `runPagedQueryAsync`가 반환된 모든 문제에 대해 스토리지를 할당해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-153">Most importantly, `runPagedQueryAsync` must allocate storage for all the issues returned.</span></span> <span data-ttu-id="c1744-154">모든 미해결 문제를 검색하면 모든 검색된 문제를 저장하는 데 훨씬 더 많은 메모리가 필요하므로 이 샘플은 250개 문제만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-154">This sample stops at 250 issues because retrieving all open issues would require much more memory to store all the retrieved issues.</span></span> <span data-ttu-id="c1744-155">진행률 보고서 및 취소 지원 프로토콜로 인해 알고리즘을 처음 읽을 때 이해하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-155">The protocols for supporting progress reports and cancellation make the algorithm harder to understand on its first reading.</span></span> <span data-ttu-id="c1744-156">추가 형식 및 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-156">More types and APIs are involved.</span></span> <span data-ttu-id="c1744-157">취소 요청 위치 및 제공 위치를 파악하려면 <xref:System.Threading.CancellationTokenSource> 및 연결된 <xref:System.Threading.CancellationToken>을 통해 통신을 추적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-157">You must trace the communications through the <xref:System.Threading.CancellationTokenSource> and its associated <xref:System.Threading.CancellationToken> to understand where cancellation is requested and where it's granted.</span></span>

## <a name="async-streams-provide-a-better-way"></a><span data-ttu-id="c1744-158">더 나은 방법을 제공하는 비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="c1744-158">Async streams provide a better way</span></span>

<span data-ttu-id="c1744-159">비동기 스트림 및 연결된 언어 지원으로 해당 문제가 모두 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-159">Async streams and the associated language support address all those concerns.</span></span> <span data-ttu-id="c1744-160">시퀀스를 생성하는 코드에서 이제 `yield return`을 사용하여 `async` 한정자로 선언된 메서드에서 요소를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-160">The code that generates the sequence can now use `yield return` to return elements in a method that was declared with the `async` modifier.</span></span> <span data-ttu-id="c1744-161">`foreach` 루프를 통해 시퀀스를 사용하는 것처럼 `await foreach` 루프를 통해 비동기 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-161">You can consume an async stream using an `await foreach` loop just as you consume any sequence using a `foreach` loop.</span></span>

<span data-ttu-id="c1744-162">이 새로운 언어 기능은 .NET Standard 2.1에 추가되고 .NET Core 3.0에 구현된 세 가지 새 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-162">These new language features depend on three new interfaces added to .NET Standard 2.1 and implemented in .NET Core 3.0:</span></span>

- <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>
- <xref:System.IAsyncDisposable?displayProperty=nameWithType>

<span data-ttu-id="c1744-163">이 세 가지 인터페이스는 대부분의 C# 개발자에게 익숙합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-163">These three interfaces should be familiar to most C# developers.</span></span> <span data-ttu-id="c1744-164">이 인터페이스는 동기 인터페이스와 유사한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-164">They behave in a manner similar to their synchronous counterparts:</span></span>

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

<span data-ttu-id="c1744-165">익숙하지 않을 수도 있는 하나의 형식은 <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-165">One type that may be unfamiliar is <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c1744-166">`ValueTask` 구조체는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스에 유사한 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-166">The `ValueTask` struct provides a similar API to the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c1744-167">`ValueTask`는 성능상의 이유로 해당 인터페이스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-167">`ValueTask` is used in these interfaces for performance reasons.</span></span>

## <a name="convert-to-async-streams"></a><span data-ttu-id="c1744-168">비동기 스트림으로 변환</span><span class="sxs-lookup"><span data-stu-id="c1744-168">Convert to async streams</span></span>

<span data-ttu-id="c1744-169">그런 다음, `runPagedQueryAsync` 메서드를 변환하여 비동기 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-169">Next, convert the `runPagedQueryAsync` method to generate an async stream.</span></span> <span data-ttu-id="c1744-170">먼저 `runPagedQueryAsync`의 시그니처를 변경하여 `IAsyncEnumerable<JToken>`을 반환하고 다음 코드에 표시된 대로 매개 변수 목록에서 취소 토큰 및 진행 개체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-170">First, change the signature of `runPagedQueryAsync` to return an `IAsyncEnumerable<JToken>`, and remove the cancellation token and progress objects from the parameter list as shown in the following code:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetUpdateSignature" :::

<span data-ttu-id="c1744-171">시작 코드는 다음 코드에 표시된 대로 페이지가 검색될 때 각 페이지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-171">The starter code processes each page as the page is retrieved, as shown in the following code:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetProcessPage" :::

<span data-ttu-id="c1744-172">해당 세 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-172">Replace those three lines with the following code:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetYieldReturnPage" :::

<span data-ttu-id="c1744-173">이 메서드의 앞부분에 있는 `finalResults` 선언 및 수정한 루프 뒤에 있는 `return` 문을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-173">You can also remove the declaration of `finalResults` earlier in this method and the `return` statement that follows the loop you modified.</span></span>

<span data-ttu-id="c1744-174">비동기 스트림을 생성하기 위한 변경을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-174">You've finished the changes to generate an async stream.</span></span> <span data-ttu-id="c1744-175">완료된 메서드는 다음 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-175">The finished method should resemble the following code:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetGenerateAsyncStream" :::

<span data-ttu-id="c1744-176">그런 다음, 컬렉션을 사용하는 코드를 변경하여 비동기 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-176">Next, you change the code that consumes the collection to consume the async stream.</span></span> <span data-ttu-id="c1744-177">문제 컬렉션을 처리하는 `Main`에서 다음 코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-177">Find the following code in `Main` that processes the collection of issues:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetEnumerateOldStyle" :::

<span data-ttu-id="c1744-178">해당 코드를 다음 `await foreach` 루프로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-178">Replace that code with the following `await foreach` loop:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetEnumerateAsyncStream" :::

<span data-ttu-id="c1744-179">새 인터페이스 <xref:System.Collections.Generic.IAsyncEnumerator%601>는 <xref:System.IAsyncDisposable>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-179">The new interface <xref:System.Collections.Generic.IAsyncEnumerator%601> derives from <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="c1744-180">즉, 루프가 완료되면 이전 루프가 스트림을 비동기적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-180">That means the preceding loop will asynchronously dispose the stream when the loop finishes.</span></span> <span data-ttu-id="c1744-181">루프는 다음 코드와 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-181">You can imagine the loop looks like the following code:</span></span>

```csharp
int num = 0;
var enumerator = runPagedQueryAsync(client, PagedIssueQuery, "docs").GetEnumeratorAsync();
try
{
    while (await enumerator.MoveNextAsync())
    {
        var issue = enumerator.Current;
        Console.WriteLine(issue);
        Console.WriteLine($"Received {++num} issues in total");
    }
} finally
{
    if (enumerator != null)
        await enumerator.DisposeAsync();
}
```

<span data-ttu-id="c1744-182">기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-182">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="c1744-183">컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-183">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="c1744-184">동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1744-184">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="c1744-185">비동기 스트림은 다른 `async` 메서드와 동일한 프로토콜을 사용하여 취소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-185">Async streams support cancellation using the same protocol as other `async` methods.</span></span> <span data-ttu-id="c1744-186">취소를 지원하기 위해 다음과 같이 비동기 반복기 메서드의 시그니처를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-186">You would modify the signature for the async iterator method as follows to support cancellation:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetGenerateWithCancellation" :::

<span data-ttu-id="c1744-187"><xref:System.Runtime.CompilerServices.EnumeratorCancellationAttribute?dipslayProperty=nameWithType> 특성을 사용하면 컴파일러는 비동기 반복기 본문에 표시되는 `GetAsyncEnumerator`에 전달된 토큰을 해당 인수로 만드는 <xref:System.Collections.Generic.IAsyncEnumerator%601>에 관한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-187">The <xref:System.Runtime.CompilerServices.EnumeratorCancellationAttribute?dipslayProperty=nameWithType> attribute causes the compiler to generate code for the <xref:System.Collections.Generic.IAsyncEnumerator%601> that makes the token passed to `GetAsyncEnumerator` visible to the body of the async iterator as that argument.</span></span> <span data-ttu-id="c1744-188">`runQueryAsync` 내에서 토큰 상태를 검사하고 요청 시 추가 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-188">Inside `runQueryAsync`, you could examine the state of the token and cancel further work if requested.</span></span>

<span data-ttu-id="c1744-189">다른 확장 메서드인 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.WithCancellation%2A>을 사용하여 취소 토큰을 비동기 스트림에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-189">You use another extension method, <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.WithCancellation%2A>, to pass the cancellation token to the async stream.</span></span> <span data-ttu-id="c1744-190">다음과 같이 문제를 열거하는 루프를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-190">You would modify the loop enumerating the issues as follows:</span></span>

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetEnumerateWithCancellation" :::

<span data-ttu-id="c1744-191">[csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/finished) 폴더의 [dotnet/docs](https://github.com/dotnet/docs) 리포지토리에서 완료된 자습서의 코드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-191">You can get the code for the finished tutorial from the [dotnet/docs](https://github.com/dotnet/docs) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/finished) folder.</span></span>

## <a name="run-the-finished-application"></a><span data-ttu-id="c1744-192">완료된 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="c1744-192">Run the finished application</span></span>

<span data-ttu-id="c1744-193">애플리케이션을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-193">Run the application again.</span></span> <span data-ttu-id="c1744-194">해당 동작을 시작 애플리케이션의 동작과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-194">Contrast its behavior with the behavior of the starter application.</span></span> <span data-ttu-id="c1744-195">결과의 첫 번째 페이지는 사용 가능한 즉시 열거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-195">The first page of results is enumerated as soon as it's available.</span></span> <span data-ttu-id="c1744-196">새로운 각 페이지가 요청 및 검색될 때 확인 가능한 일시 정지가 있고 난 뒤 다음 페이지의 결과가 빠르게 열거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-196">There's an observable pause as each new page is requested and retrieved, then the next page's results are quickly enumerated.</span></span> <span data-ttu-id="c1744-197">취소를 처리하는 데는 `try` / `catch` 블록이 필요하지 않습니다. 호출자가 컬렉션의 열거를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-197">The `try` / `catch` block isn't needed to handle cancellation: the caller can stop enumerating the collection.</span></span> <span data-ttu-id="c1744-198">각 페이지가 다운로드될 때 비동기 스트림이 결과를 생성하므로 진행이 명확하게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-198">Progress is clearly reported because the async stream generates results as each page is downloaded.</span></span> <span data-ttu-id="c1744-199">반환된 각 문제에 대한 상태는 `await foreach` 루프에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-199">The status for each issue returned is seamlessly included in the `await foreach` loop.</span></span> <span data-ttu-id="c1744-200">진행 상황을 추적하는 데 콜백 개체가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-200">You don't need a callback object to track progress.</span></span>

<span data-ttu-id="c1744-201">코드를 검사하여 향상된 메모리 사용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-201">You can see improvements in memory use by examining the code.</span></span> <span data-ttu-id="c1744-202">열거되기 전에 모든 결과를 저장하기 위해 더 이상 컬렉션을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-202">You no longer need to allocate a collection to store all the results before they're enumerated.</span></span> <span data-ttu-id="c1744-203">호출자는 결과를 사용하는 방법 및 스토리지 컬렉션이 필요한지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-203">The caller can determine how to consume the results and if a storage collection is needed.</span></span>

<span data-ttu-id="c1744-204">시작 및 완료된 애플리케이션을 둘 다 실행하고 직접 구현 간 차이를 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-204">Run both the starter and finished applications and you can observe the differences between the implementations for yourself.</span></span> <span data-ttu-id="c1744-205">완료한 후 이 자습서를 시작할 때 만든 GitHub 액세스 토큰을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-205">You can delete the GitHub access token you created when you started this tutorial after you've finished.</span></span> <span data-ttu-id="c1744-206">공격자가 해당 토큰의 액세스 권한을 얻으면 사용자의 자격 증명을 사용하여 GitHub API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1744-206">If an attacker gained access to that token, they could access GitHub APIs using your credentials.</span></span>
