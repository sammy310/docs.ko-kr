---
title: 완료되면 비동기 작업 처리
description: 이 예제에서는 C#에서 Task.WhenAny를 사용하여 여러 작업을 시작하고 해당 결과를 시작한 순서가 아닌 완료될 때 처리하는 방법을 보여줍니다.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: c2fe66e865a2c88f4cae50b816f9326614fcbb89
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812031"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a><span data-ttu-id="1bccf-103">완료되면 비동기 작업 처리(C#)</span><span class="sxs-lookup"><span data-stu-id="1bccf-103">Process asynchronous tasks as they complete (C#)</span></span>

<span data-ttu-id="1bccf-104"><xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>를 사용하면 시작된 순서대로 처리하는 대신 동시에 여러 작업을 시작하고 완료 시 하나씩 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-104">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they're completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="1bccf-105">다음 예제에서는 쿼리를 사용하여 작업 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-105">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="1bccf-106">각 작업은 지정된 웹 사이트의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-106">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="1bccf-107">while 루프의 각 반복에서 대기된 <xref:System.Threading.Tasks.Task.WhenAny%2A> 호출은 다운로드를 먼저 완료하는 작업 컬렉션의 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-107">In each iteration of a while loop, an awaited call to <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="1bccf-108">해당 작업은 컬렉션에서 제거되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-108">That task is removed from the collection and processed.</span></span> <span data-ttu-id="1bccf-109">컬렉션에 더 이상 작업이 없을 때까지 루프가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-109">The loop repeats until the collection contains no more tasks.</span></span>

## <a name="create-example-application"></a><span data-ttu-id="1bccf-110">예제 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="1bccf-110">Create example application</span></span>

<span data-ttu-id="1bccf-111">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-111">Create a new .NET Core console application.</span></span> <span data-ttu-id="1bccf-112">[dotnet new console](../../../../core/tools/dotnet-new.md#console) 명령 또는 [Visual Studio](/visualstudio/install/install-visual-studio)를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-112">You can create one by using the [dotnet new console](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="1bccf-113">선호하는 코드 편집기에서 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-113">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="1bccf-114">using 문 바꾸기</span><span class="sxs-lookup"><span data-stu-id="1bccf-114">Replace using statements</span></span>

<span data-ttu-id="1bccf-115">기존 using 문을 다음 선언으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-115">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="1bccf-116">필드 추가하기</span><span class="sxs-lookup"><span data-stu-id="1bccf-116">Add fields</span></span>

<span data-ttu-id="1bccf-117">`Program` 클래스 정의에 다음 두 개 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-117">In the `Program` class definition, add the following two fields:</span></span>

```csharp
static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

<span data-ttu-id="1bccf-118">`HttpClient`는 HTTP 요청을 보내고 HTTP 응답을 받는 기능을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-118">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="1bccf-119">`s_urlList`는 애플리케이션이 처리해야 하는 모든 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-119">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="1bccf-120">애플리케이션 진입점 업데이트</span><span class="sxs-lookup"><span data-stu-id="1bccf-120">Update application entry point</span></span>

<span data-ttu-id="1bccf-121">콘솔 애플리케이션의 주 진입점은 `Main` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-121">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="1bccf-122">기존 메서드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-122">Replace the existing method with the following:</span></span>

```csharp
static Task Main() => SumPageSizesAsync();
```

<span data-ttu-id="1bccf-123">업데이트된 `Main` 메서드는 이제 [Async main](../../../whats-new/csharp-7-1.md#async-main)으로 간주되어 실행 파일에 대한 비동기 진입점을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-123">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7-1.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="1bccf-124">`SumPageSizesAsync`에 대한 호출로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-124">It is expressed a call to `SumPageSizesAsync`.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="1bccf-125">비동기 합계 페이지 크기 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="1bccf-125">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="1bccf-126">`SumPageSizesAsync` 메서드 아래에 `Main` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-126">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="1bccf-127"><xref:System.Diagnostics.Stopwatch>를 인스턴스화하고 시작함으로써 메서드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-127">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="1bccf-128">그런 다음, 실행 시 작업 컬렉션을 만드는 쿼리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-128">It then includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="1bccf-129">다음 코드에서는 `ProcessUrlAsync`를 호출할 때마다 <xref:System.Threading.Tasks.Task%601>가 반환됩니다. 여기서 `TResult`는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-129">Each call to `ProcessUrlAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

<span data-ttu-id="1bccf-130">LINQ를 통한 [지연된 실행](../linq/deferred-execution-example.md)으로 인해 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>를 호출하여 각 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-130">Due to [deferred execution](../linq/deferred-execution-example.md) with the LINQ, you call <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> to start each task.</span></span>

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

<span data-ttu-id="1bccf-131">`while` 루프는 컬렉션의 각 작업에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-131">The `while` loop performs the following steps for each task in the collection:</span></span>

1. <span data-ttu-id="1bccf-132">다운로드를 완료한 컬렉션에서 첫 번째 작업을 식별하기 위해 `WhenAny` 호출을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-132">Awaits a call to `WhenAny` to identify the first task in the collection that has finished its download.</span></span>

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. <span data-ttu-id="1bccf-133">컬렉션에서 해당 작업을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-133">Removes that task from the collection.</span></span>

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. <span data-ttu-id="1bccf-134">`ProcessUrlAsync` 호출에서 반환된 `finishedTask`를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-134">Awaits `finishedTask`, which is returned by a call to `ProcessUrlAsync`.</span></span> <span data-ttu-id="1bccf-135">`finishedTask` 변수는 <xref:System.Threading.Tasks.Task%601>입니다. 여기서 `TResult`은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-135">The `finishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span> <span data-ttu-id="1bccf-136">작업은 이미 완료되었지만, 다음 예제와 같이 다운로드한 웹 사이트의 길이를 검색하도록 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-136">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="1bccf-137">작업에 오류가 발생하는 경우 `await`는 `AggregateException`을 throw하는 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> 속성을 읽는 것과 달리 `AggregateException`에 저장된 첫 번째 자식 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-137">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> property, which would throw the `AggregateException`.</span></span>

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a><span data-ttu-id="1bccf-138">프로세스 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="1bccf-138">Add process method</span></span>

<span data-ttu-id="1bccf-139">`SumPageSizesAsync` 메서드 아래에 다음 `ProcessUrlAsync` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-139">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="1bccf-140">지정된 URL에서 메서드는 제공된 `client` 인스턴스를 사용하여 응답을 `byte[]`로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-140">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="1bccf-141">URL 및 길이가 콘솔에 기록된 후 길이가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-141">The length is returned after the URL and length is written to the console.</span></span>

<span data-ttu-id="1bccf-142">프로그램을 여러 번 실행하여 다운로드한 길이가 항상 같은 순서로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-142">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="1bccf-143">예제에 설명된 대로 루프에서 `WhenAny`를 사용하는 것은 적은 수의 작업이 필요한 문제 해결에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-143">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="1bccf-144">그러므로 많은 수의 작업을 처리해야 하는 경우에는 다른 접근 방법이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-144">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="1bccf-145">자세한 내용 및 예제는 [작업이 완료되었을 때 처리 방법](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bccf-145">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span></span>

## <a name="complete-example"></a><span data-ttu-id="1bccf-146">전체 예제</span><span class="sxs-lookup"><span data-stu-id="1bccf-146">Complete example</span></span>

<span data-ttu-id="1bccf-147">다음 코드는 예제에 관한 *Program.cs* 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="1bccf-147">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="1bccf-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bccf-148">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="1bccf-149">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="1bccf-149">Asynchronous programming with async and await (C#)</span></span>](index.md)
