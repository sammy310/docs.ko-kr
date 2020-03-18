---
title: 완료되면 비동기 작업 처리
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: b618fd6bf80551231d2b285fd0e8aef688d00d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "71736724"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="78c7a-102">비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)</span><span class="sxs-lookup"><span data-stu-id="78c7a-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>

<span data-ttu-id="78c7a-103"><xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>를 사용하면 시작된 순서대로 처리하는 대신 동시에 여러 작업을 시작하고 완료 시 하나씩 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="78c7a-104">다음 예제에서는 쿼리를 사용하여 작업 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="78c7a-105">각 작업은 지정된 웹 사이트의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="78c7a-106">while 루프의 각 반복에서 대기된 `WhenAny` 호출은 다운로드를 먼저 완료하는 작업 컬렉션의 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="78c7a-107">해당 작업은 컬렉션에서 제거되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="78c7a-108">컬렉션에 더 이상 작업이 없을 때까지 루프가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-108">The loop repeats until the collection contains no more tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="78c7a-109">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-109">To run the examples, you must have Visual Studio (2012 or newer) and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-an-example-solution"></a><span data-ttu-id="78c7a-110">예제 솔루션 다운로드</span><span class="sxs-lookup"><span data-stu-id="78c7a-110">Download an example solution</span></span>

<span data-ttu-id="78c7a-111">[Async 샘플: 애플리케이션 세부 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

> [!TIP]
> <span data-ttu-id="78c7a-112">프로젝트를 다운로드하지 않으려는 경우 대신 이 항목의 끝에 있는 *MainWindow.xaml.cs* 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-112">If you don't want to download the project, you can review the *MainWindow.xaml.cs* file at the end of this topic instead.</span></span>

1. <span data-ttu-id="78c7a-113">*.zip* 파일에서 다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-113">Extract the files that you downloaded from the *.zip* file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="78c7a-114">메뉴 모음에서 **파일** > **열기** > **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-114">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="78c7a-115">**프로젝트 열기** 대화 상자에서 다운로드한 샘플 코드가 포함된 폴더를 열고 *AsyncFineTuningCS*  AsyncFineTuningVB/에 대한 솔루션( *.sln*) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-115">In the **Open Project** dialog box, open the folder that holds the sample code you downloaded, and then open the solution (*.sln*) file for *AsyncFineTuningCS*/*AsyncFineTuningVB*.</span></span>

4. <span data-ttu-id="78c7a-116">**솔루션 탐색기**에서 **ProcessTasksAsTheyFinish** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-116">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="78c7a-117">디버그를 하고 프로그램을 실행하려면 <kbd>F5</kbd> 키를 선택하고, 디버그하지 않고 프로그램을 실행하려면 <kbd>Ctrl</kbd>+<kbd>F5</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-117">Choose the <kbd>F5</kbd> key to run the program with debugging or, press <kbd>Ctrl</kbd>+<kbd>F5</kbd> keys to run the program without debugging it.</span></span>

6. <span data-ttu-id="78c7a-118">프로젝트를 여러 번 실행하여 다운로드한 길이가 항상 같은 순서로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

## <a name="create-the-program-yourself"></a><span data-ttu-id="78c7a-119">프로그램 직접 만들기</span><span class="sxs-lookup"><span data-stu-id="78c7a-119">Create the program yourself</span></span>

<span data-ttu-id="78c7a-120">이 예제에서는 [하나가 완료되면 남은 동기 작업 취소(C#)](cancel-remaining-async-tasks-after-one-is-complete.md)에서 개발된 코드에 추가하고 동일한 UI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-120">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](cancel-remaining-async-tasks-after-one-is-complete.md), and it uses the same UI.</span></span>

<span data-ttu-id="78c7a-121">직접 예제를 빌드하려면 [예제 다운로드](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example) 섹션의 지침을 단계별로 따르되, **CancelAfterOneTask**를 시작 프로젝트로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-121">To build the example yourself, step by step, follow the instructions in the [Downloading the Example](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example) section, but set **CancelAfterOneTask** as the startup project.</span></span> <span data-ttu-id="78c7a-122">이 항목의 변경 내용을 해당 프로젝트의 `AccessTheWebAsync` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-122">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="78c7a-123">변경 내용은 별표로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-123">The changes are marked with asterisks.</span></span>

<span data-ttu-id="78c7a-124">**CancelAfterOneTask** 프로젝트에는 실행 시 작업 컬렉션을 만드는 쿼리가 이미 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-124">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="78c7a-125">다음 코드에서는 `ProcessURLAsync`를 호출할 때마다 <xref:System.Threading.Tasks.Task%601>가 반환됩니다. 여기서 `TResult`는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-125">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

<span data-ttu-id="78c7a-126">프로젝트의 *MainWindow.xaml.cs* 파일에서 `AccessTheWebAsync` 메서드를 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-126">In the *MainWindow.xaml.cs* file of the project, make the following changes to the `AccessTheWebAsync` method:</span></span>

- <span data-ttu-id="78c7a-127"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 대신 <xref:System.Linq.Enumerable.ToArray%2A>를 적용하여 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-127">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- <span data-ttu-id="78c7a-128">컬렉션의 각 작업에 대해 다음 단계를 수행하는 `while` 루프를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-128">Add a `while` loop that performs the following steps for each task in the collection:</span></span>

    1. <span data-ttu-id="78c7a-129">컬렉션의 첫 번째 작업을 식별하여 다운로드를 완료하기 위해 `WhenAny` 호출을 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-129">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. <span data-ttu-id="78c7a-130">컬렉션에서 해당 작업을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-130">Removes that task from the collection.</span></span>

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. <span data-ttu-id="78c7a-131">`firstFinishedTask` 호출에서 반환된 `ProcessURLAsync`를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-131">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="78c7a-132">`firstFinishedTask` 변수는 <xref:System.Threading.Tasks.Task%601>입니다. 여기서 `TReturn`은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-132">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="78c7a-133">작업은 이미 완료되었지만, 다음 예제와 같이 다운로드한 웹 사이트의 길이를 검색하도록 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-133">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="78c7a-134">작업에 오류가 발생하는 경우, `await`은 `AggregateException`를 throw하는 `Result` 속성을 읽는 것과 달리 `AggregateException`에 저장된 첫 번째 자식 요소 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-134">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the `Result` property which would throw the `AggregateException`.</span></span>

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

<span data-ttu-id="78c7a-135">프로그램을 여러 번 실행하여 다운로드한 길이가 항상 같은 순서로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-135">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="78c7a-136">예제에 설명된 대로 루프에서 `WhenAny`를 사용하는 것은 적은 수의 작업이 필요한 문제 해결에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="78c7a-137">그러므로 많은 수의 작업을 처리해야 하는 경우에는 다른 접근 방법이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="78c7a-138">자세한 내용 및 예제는 [작업이 완료되었을 때 처리 방법](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c7a-138">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span></span>

## <a name="complete-example"></a><span data-ttu-id="78c7a-139">전체 예제</span><span class="sxs-lookup"><span data-stu-id="78c7a-139">Complete example</span></span>

<span data-ttu-id="78c7a-140">다음 코드는 예제에 대한 *MainWindow.xaml.cs* 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-140">The following code is the complete text of the *MainWindow.xaml.cs* file for the example.</span></span> <span data-ttu-id="78c7a-141">별표는 이 예제에 대해 추가된 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-141">Asterisks mark the elements that were added for this example.</span></span> <span data-ttu-id="78c7a-142">또한 <xref:System.Net.Http>에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-142">Also, take note that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="78c7a-143">[Async 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 프로젝트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c7a-143">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a><span data-ttu-id="78c7a-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78c7a-144">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="78c7a-145">Async 애플리케이션 미세 조정(C#)</span><span class="sxs-lookup"><span data-stu-id="78c7a-145">Fine-Tuning Your Async Application (C#)</span></span>](fine-tuning-your-async-application.md)
- [<span data-ttu-id="78c7a-146">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="78c7a-146">Asynchronous Programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="78c7a-147">Async 샘플: 애플리케이션 미세 조정</span><span class="sxs-lookup"><span data-stu-id="78c7a-147">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
