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
# <a name="process-asynchronous-tasks-as-they-complete-c"></a>완료되면 비동기 작업 처리(C#)

<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>를 사용하면 시작된 순서대로 처리하는 대신 동시에 여러 작업을 시작하고 완료 시 하나씩 처리할 수 있습니다.

다음 예제에서는 쿼리를 사용하여 작업 컬렉션을 만듭니다. 각 작업은 지정된 웹 사이트의 콘텐츠를 다운로드합니다. while 루프의 각 반복에서 대기된 <xref:System.Threading.Tasks.Task.WhenAny%2A> 호출은 다운로드를 먼저 완료하는 작업 컬렉션의 작업을 반환합니다. 해당 작업은 컬렉션에서 제거되고 처리됩니다. 컬렉션에 더 이상 작업이 없을 때까지 루프가 반복됩니다.

## <a name="create-example-application"></a>예제 애플리케이션 만들기

새 .NET Core 콘솔 애플리케이션을 만듭니다. [dotnet new console](../../../../core/tools/dotnet-new.md#console) 명령 또는 [Visual Studio](/visualstudio/install/install-visual-studio)를 사용하여 만들 수 있습니다. 선호하는 코드 편집기에서 *Program.cs* 파일을 엽니다.

### <a name="replace-using-statements"></a>using 문 바꾸기

기존 using 문을 다음 선언으로 바꿉니다.

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>필드 추가하기

`Program` 클래스 정의에 다음 두 개 필드를 추가합니다.

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

`HttpClient`는 HTTP 요청을 보내고 HTTP 응답을 받는 기능을 공개합니다. `s_urlList`는 애플리케이션이 처리해야 하는 모든 URL을 저장합니다.

## <a name="update-application-entry-point"></a>애플리케이션 진입점 업데이트

콘솔 애플리케이션의 주 진입점은 `Main` 메서드입니다. 기존 메서드를 다음으로 바꿉니다.

```csharp
static Task Main() => SumPageSizesAsync();
```

업데이트된 `Main` 메서드는 이제 [Async main](../../../whats-new/csharp-7-1.md#async-main)으로 간주되어 실행 파일에 대한 비동기 진입점을 허용합니다. `SumPageSizesAsync`에 대한 호출로 표현됩니다.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>비동기 합계 페이지 크기 메서드 만들기

`SumPageSizesAsync` 메서드 아래에 `Main` 메서드를 추가합니다.

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

<xref:System.Diagnostics.Stopwatch>를 인스턴스화하고 시작함으로써 메서드가 시작됩니다. 그런 다음, 실행 시 작업 컬렉션을 만드는 쿼리를 포함합니다. 다음 코드에서는 `ProcessUrlAsync`를 호출할 때마다 <xref:System.Threading.Tasks.Task%601>가 반환됩니다. 여기서 `TResult`는 정수입니다.

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

LINQ를 통한 [지연된 실행](../linq/deferred-execution-example.md)으로 인해 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>를 호출하여 각 작업을 시작합니다.

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

`while` 루프는 컬렉션의 각 작업에서 다음 단계를 수행합니다.

1. 다운로드를 완료한 컬렉션에서 첫 번째 작업을 식별하기 위해 `WhenAny` 호출을 기다립니다.

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. 컬렉션에서 해당 작업을 제거합니다.

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. `ProcessUrlAsync` 호출에서 반환된 `finishedTask`를 대기합니다. `finishedTask` 변수는 <xref:System.Threading.Tasks.Task%601>입니다. 여기서 `TResult`은 정수입니다. 작업은 이미 완료되었지만, 다음 예제와 같이 다운로드한 웹 사이트의 길이를 검색하도록 기다립니다. 작업에 오류가 발생하는 경우 `await`는 `AggregateException`을 throw하는 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> 속성을 읽는 것과 달리 `AggregateException`에 저장된 첫 번째 자식 예외를 throw합니다.

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a>프로세스 메서드 추가

`SumPageSizesAsync` 메서드 아래에 다음 `ProcessUrlAsync` 메서드를 추가합니다.

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

지정된 URL에서 메서드는 제공된 `client` 인스턴스를 사용하여 응답을 `byte[]`로 가져옵니다. URL 및 길이가 콘솔에 기록된 후 길이가 반환됩니다.

프로그램을 여러 번 실행하여 다운로드한 길이가 항상 같은 순서로 표시되는지 확인합니다.

> [!CAUTION]
> 예제에 설명된 대로 루프에서 `WhenAny`를 사용하는 것은 적은 수의 작업이 필요한 문제 해결에 적합합니다. 그러므로 많은 수의 작업을 처리해야 하는 경우에는 다른 접근 방법이 더 효율적입니다. 자세한 내용 및 예제는 [작업이 완료되었을 때 처리 방법](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete)을 참조하세요.

## <a name="complete-example"></a>전체 예제

다음 코드는 예제에 관한 *Program.cs* 파일의 전체 텍스트입니다.

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a>참고 항목

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [async 및 await를 사용한 비동기 프로그래밍(C#)](index.md)
