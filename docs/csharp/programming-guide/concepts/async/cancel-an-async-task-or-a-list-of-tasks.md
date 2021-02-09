---
title: 작업 목록 취소(C#)
description: 취소 토큰을 사용하여 작업 목록에 대한 취소 요청을 신호로 보내는 방법을 알아봅니다.
ms.date: 02/03/2021
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 532c61ab6499583620ba2ee5c710c58f7886f89d
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585743"
---
# <a name="cancel-a-list-of-tasks-c"></a><span data-ttu-id="ad422-103">작업 목록 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="ad422-103">Cancel a list of tasks (C#)</span></span>

<span data-ttu-id="ad422-104">완료될 때까지 기다리지 않으려는 경우 비동기 콘솔 애플리케이션을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-104">You can cancel an async console application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="ad422-105">이 항목의 예제에 따라 웹 사이트 목록의 콘텐츠를 다운로드하는 애플리케이션에 취소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-105">By following the example in this topic, you can add a cancellation to an application that downloads the contents of a list of websites.</span></span> <span data-ttu-id="ad422-106"><xref:System.Threading.CancellationTokenSource> 인스턴스를 각 작업과 연결하여 많은 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-106">You can cancel many tasks by associating the <xref:System.Threading.CancellationTokenSource> instance with each task.</span></span> <span data-ttu-id="ad422-107"><kbd>Enter</kbd> 키를 선택하면 아직 완료되지 않은 모든 작업이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-107">If you select the <kbd>Enter</kbd> key, you cancel all tasks that aren't yet complete.</span></span>

<span data-ttu-id="ad422-108">이 자습서에서는 다음 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-108">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="ad422-109">.NET 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ad422-109">Creating a .NET console application</span></span>
> - <span data-ttu-id="ad422-110">취소를 지원하는 비동기 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="ad422-110">Writing an async application that supports cancellation</span></span>
> - <span data-ttu-id="ad422-111">취소 신호 보내기 시연</span><span class="sxs-lookup"><span data-stu-id="ad422-111">Demonstrating signaling cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad422-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ad422-112">Prerequisites</span></span>

<span data-ttu-id="ad422-113">이 자습서를 사용하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-113">This tutorial requires the following:</span></span>

- [<span data-ttu-id="ad422-114">.NET 5.0 이상 SDK</span><span class="sxs-lookup"><span data-stu-id="ad422-114">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="ad422-115">IDE(통합 개발 환경)</span><span class="sxs-lookup"><span data-stu-id="ad422-115">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="ad422-116">Visual Studio, Visual Studio Code 또는 Mac용 Visual Studio 권장</span><span class="sxs-lookup"><span data-stu-id="ad422-116">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a><span data-ttu-id="ad422-117">예제 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ad422-117">Create example application</span></span>

<span data-ttu-id="ad422-118">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-118">Create a new .NET Core console application.</span></span> <span data-ttu-id="ad422-119">[`dotnet new console`](../../../../core/tools/dotnet-new.md#console) 명령 또는 [Visual Studio](/visualstudio/install/install-visual-studio)를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-119">You can create one by using the [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="ad422-120">선호하는 코드 편집기에서 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-120">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="ad422-121">using 문 바꾸기</span><span class="sxs-lookup"><span data-stu-id="ad422-121">Replace using statements</span></span>

<span data-ttu-id="ad422-122">기존 using 문을 다음 선언으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-122">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="ad422-123">필드 추가하기</span><span class="sxs-lookup"><span data-stu-id="ad422-123">Add fields</span></span>

<span data-ttu-id="ad422-124">`Program` 클래스 정의에서 다음 세 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-124">In the `Program` class definition, add these three fields:</span></span>

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

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

<span data-ttu-id="ad422-125"><xref:System.Threading.CancellationTokenSource>는 요청된 취소를 <xref:System.Threading.CancellationToken>에 신호로 보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-125">The <xref:System.Threading.CancellationTokenSource> is used to signal a requested cancellation to a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="ad422-126">`HttpClient`는 HTTP 요청을 보내고 HTTP 응답을 받는 기능을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-126">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="ad422-127">`s_urlList`는 애플리케이션이 처리해야 하는 모든 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-127">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="ad422-128">애플리케이션 진입점 업데이트</span><span class="sxs-lookup"><span data-stu-id="ad422-128">Update application entry point</span></span>

<span data-ttu-id="ad422-129">콘솔 애플리케이션의 주 진입점은 `Main` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-129">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="ad422-130">기존 메서드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-130">Replace the existing method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="ad422-131">업데이트된 `Main` 메서드는 이제 [Async main](../../../whats-new/csharp-7.md#async-main)으로 간주되어 실행 파일에 대한 비동기 진입점을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-131">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="ad422-132">콘솔에 몇 가지 지침 메시지를 기록한 다음, `cancelTask`라는 <xref:System.Threading.Tasks.Task> 인스턴스를 선언합니다. 그러면 콘솔 키 입력이 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-132">It writes a few instructional messages to the console, then declares a <xref:System.Threading.Tasks.Task> instance named `cancelTask`, which will read console key strokes.</span></span> <span data-ttu-id="ad422-133"><kbd>Enter</kbd> 키를 누르면 <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType>이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-133">If the <kbd>Enter</kbd> key is pressed, a call to <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> is made.</span></span> <span data-ttu-id="ad422-134">그러면 취소 신호가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-134">This will signal cancellation.</span></span> <span data-ttu-id="ad422-135">다음으로, `sumPageSizesTask` 변수가 `SumPageSizesAsync` 메서드에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-135">Next, the `sumPageSizesTask` variable is assigned from the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="ad422-136">두 작업은 모두 <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>에 전달되며 해당 항목은 두 작업 중 하나가 완료되면 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-136">Both tasks are then passed to <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, which will continue when any of the two tasks have completed.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="ad422-137">비동기 합계 페이지 크기 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="ad422-137">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="ad422-138">`SumPageSizesAsync` 메서드 아래에 `Main` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-138">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="ad422-139"><xref:System.Diagnostics.Stopwatch>를 인스턴스화하고 시작함으로써 메서드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-139">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="ad422-140">그런 다음, `s_urlList`의 각 URL을 반복하고 `ProcessUrlAsync`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-140">It then loops through each URL in the `s_urlList` and calls `ProcessUrlAsync`.</span></span> <span data-ttu-id="ad422-141">각 반복에서 `s_cts.Token`은 `ProcessUrlAsync` 메서드에 전달되며 코드는 <xref:System.Threading.Tasks.Task%601>를 반환합니다. 여기서 `TResult`는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-141">With each iteration, the `s_cts.Token` is passed into the `ProcessUrlAsync` method and the code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a><span data-ttu-id="ad422-142">프로세스 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="ad422-142">Add process method</span></span>

<span data-ttu-id="ad422-143">`SumPageSizesAsync` 메서드 아래에 다음 `ProcessUrlAsync` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-143">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="ad422-144">지정된 URL에서 메서드는 제공된 `client` 인스턴스를 사용하여 응답을 `byte[]`로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-144">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="ad422-145"><xref:System.Threading.CancellationToken> 인스턴스는 <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-145">The <xref:System.Threading.CancellationToken> instance is passed into the <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> and <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="ad422-146">`token`은 요청된 취소를 등록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-146">The `token` is used to register for requested cancellation.</span></span> <span data-ttu-id="ad422-147">URL 및 길이가 콘솔에 기록된 후 길이가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-147">The length is returned after the URL and length is written to the console.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="ad422-148">예제 애플리케이션 출력</span><span class="sxs-lookup"><span data-stu-id="ad422-148">Example application output</span></span>

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="ad422-149">전체 예제</span><span class="sxs-lookup"><span data-stu-id="ad422-149">Complete example</span></span>

<span data-ttu-id="ad422-150">다음 코드는 예제에 관한 *Program.cs* 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="ad422-150">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="ad422-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad422-151">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="ad422-152">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="ad422-152">Asynchronous programming with async and await (C#)</span></span>](index.md)

## <a name="next-steps"></a><span data-ttu-id="ad422-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ad422-153">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ad422-154">일정 기간 이후 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="ad422-154">Cancel async tasks after a period of time (C#)</span></span>](cancel-async-tasks-after-a-period-of-time.md)
