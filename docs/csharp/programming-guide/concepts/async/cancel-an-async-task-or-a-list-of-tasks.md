---
title: 작업 목록 취소(C#)
description: 취소 토큰을 사용하여 작업 목록에 대한 취소 요청을 신호로 보내는 방법을 알아봅니다.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 84cd1bb413d20b6c13be8415c13c72b57873b1cf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654707"
---
# <a name="cancel-a-list-of-tasks-c"></a>작업 목록 취소(C#)

완료될 때까지 기다리지 않으려는 경우 비동기 콘솔 애플리케이션을 취소할 수 있습니다. 이 항목의 예제에 따라 웹 사이트 목록의 콘텐츠를 다운로드하는 애플리케이션에 취소를 추가할 수 있습니다. <xref:System.Threading.CancellationTokenSource> 인스턴스를 각 작업과 연결하여 많은 작업을 취소할 수 있습니다. <kbd>Enter</kbd> 키를 선택하면 아직 완료되지 않은 모든 작업이 취소됩니다.

이 자습서에서는 다음 내용을 다룹니다.

> [!div class="checklist"]
>
> - .NET 콘솔 애플리케이션 만들기
> - 취소를 지원하는 비동기 애플리케이션 작성
> - 취소 신호 보내기 시연

## <a name="prerequisites"></a>필수 구성 요소

이 자습서를 사용하려면 다음이 필요합니다.

- [.NET 5.0 이상 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)
- IDE(통합 개발 환경)
  - [Visual Studio, Visual Studio Code 또는 Mac용 Visual Studio 권장](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a>예제 애플리케이션 만들기

새 .NET Core 콘솔 애플리케이션을 만듭니다. [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) 명령 또는 [Visual Studio](/visualstudio/install/install-visual-studio)를 사용하여 만들 수 있습니다. 선호하는 코드 편집기에서 *Program.cs* 파일을 엽니다.

### <a name="replace-using-statements"></a>using 문 바꾸기

기존 using 문을 다음 선언으로 바꿉니다.

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>필드 추가하기

`Program` 클래스 정의에서 다음 세 필드를 추가합니다.

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

<xref:System.Threading.CancellationTokenSource>는 요청된 취소를 <xref:System.Threading.CancellationToken>에 신호로 보내는 데 사용됩니다. `HttpClient`는 HTTP 요청을 보내고 HTTP 응답을 받는 기능을 공개합니다. `s_urlList`는 애플리케이션이 처리해야 하는 모든 URL을 저장합니다.

## <a name="update-application-entry-point"></a>애플리케이션 진입점 업데이트

콘솔 애플리케이션의 주 진입점은 `Main` 메서드입니다. 기존 메서드를 다음으로 바꿉니다.

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

업데이트된 `Main` 메서드는 이제 [Async main](../../../whats-new/csharp-7-1.md#async-main)으로 간주되어 실행 파일에 대한 비동기 진입점을 허용합니다. 콘솔에 몇 가지 지침 메시지를 기록한 다음, `cancelTask`라는 <xref:System.Threading.Tasks.Task> 인스턴스를 선언합니다. 그러면 콘솔 키 입력이 읽힙니다. <kbd>Enter</kbd> 키를 누르면 <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType>이 호출됩니다. 그러면 취소 신호가 전송됩니다. 다음으로, `sumPageSizesTask` 변수가 `SumPageSizesAsync` 메서드에서 할당됩니다. 두 작업은 모두 <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>에 전달되며 해당 항목은 두 작업 중 하나가 완료되면 계속됩니다.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>비동기 합계 페이지 크기 메서드 만들기

`SumPageSizesAsync` 메서드 아래에 `Main` 메서드를 추가합니다.

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

<xref:System.Diagnostics.Stopwatch>를 인스턴스화하고 시작함으로써 메서드가 시작됩니다. 그런 다음, `s_urlList`의 각 URL을 반복하고 `ProcessUrlAsync`를 호출합니다. 각 반복에서 `s_cts.Token`은 `ProcessUrlAsync` 메서드에 전달되며 코드는 <xref:System.Threading.Tasks.Task%601>를 반환합니다. 여기서 `TResult`는 정수입니다.

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a>프로세스 메서드 추가

`SumPageSizesAsync` 메서드 아래에 다음 `ProcessUrlAsync` 메서드를 추가합니다.

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync();
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

지정된 URL에서 메서드는 제공된 `client` 인스턴스를 사용하여 응답을 `byte[]`로 가져옵니다. <xref:System.Threading.CancellationToken> 인스턴스는 <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> 메서드에 전달됩니다. `token`은 요청된 취소를 등록하는 데 사용됩니다. URL 및 길이가 콘솔에 기록된 후 길이가 반환됩니다.

### <a name="example-application-output"></a>예제 애플리케이션 출력

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

## <a name="complete-example"></a>전체 예제

다음 코드는 예제에 관한 *Program.cs* 파일의 전체 텍스트입니다.

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a>참고 항목

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [async 및 await를 사용한 비동기 프로그래밍(C#)](index.md)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [일정 기간 이후 비동기 작업 취소(C#)](cancel-async-tasks-after-a-period-of-time.md)
