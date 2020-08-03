---
title: 비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)
description: 이 예제에서 하나의 작업이 완료될 때 나머지 모든 작업을 취소하려면 C#에서 CancellationToken과 함께 Task.WhenAny 메서드를 사용합니다.
ms.date: 07/20/2015
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
ms.openlocfilehash: 6de60c8faa93752961e3703a042885a71972cc4a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925283"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a><span data-ttu-id="31775-103">비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="31775-103">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>
<span data-ttu-id="31775-104"><xref:System.Threading.CancellationToken>과 함께 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> 메서드를 사용하면 한 작업이 완료될 때 나머지 작업을 모두 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31775-104">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="31775-105">`WhenAny` 메서드는 작업의 컬렉션인 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-105">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="31775-106">메서드는 모든 작업을 시작하고 단일 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-106">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="31775-107">컬렉션의 임의 작업이 완료되면 단일 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="31775-107">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="31775-108">이 예제에서는 취소 토큰을 `WhenAny`와 함께 사용하여 작업 컬렉션에서 완료될 첫 번째 작업을 유지하고 나머지 작업을 취소하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31775-108">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="31775-109">각 작업은 웹 사이트의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-109">Each task downloads the contents of a website.</span></span> <span data-ttu-id="31775-110">예제에서는 완료할 첫 번째 다운로드의 콘텐츠 길이를 표시하고 기타 다운로드를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-110">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31775-111">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-111">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="31775-112">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="31775-112">Downloading the Example</span></span>  
 <span data-ttu-id="31775-113">[Async 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후, 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-113">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1. <span data-ttu-id="31775-114">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-114">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2. <span data-ttu-id="31775-115">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-115">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3. <span data-ttu-id="31775-116">**프로젝트 열기** 대화 상자에서 압축을 해제한 샘플 코드가 포함된 폴더를 열고 AsyncFineTuningCS에 대한 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="31775-116">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4. <span data-ttu-id="31775-117">**솔루션 탐색기**에서 **CancelAfterOneTask** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-117">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="31775-118">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-118">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="31775-119">디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-119">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6. <span data-ttu-id="31775-120">프로그램을 여러 번 실행하여 다른 다운로드가 먼저 완료되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-120">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="31775-121">프로젝트를 다운로드하지 않으려는 경우 이 항목의 끝에 있는 MainWindow.xaml.cs 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31775-121">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="31775-122">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="31775-122">Building the Example</span></span>  
 <span data-ttu-id="31775-123">이 항목의 예제는 [비동기 작업 또는 작업 목록 취소(C#)](./cancel-an-async-task-or-a-list-of-tasks.md)에서 개발된 프로젝트에 추가되어 작업 목록을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-123">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="31775-124">**취소** 단추는 명시적으로 사용되지 않지만 예제에서는 같은 UI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-124">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="31775-125">직접 예제를 빌드하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르되, **CancelAListOfTasks**를 **시작 프로젝트**로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-125">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="31775-126">이 항목의 변경 내용을 해당 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-126">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="31775-127">**CancelAListOfTasks** 프로젝트의 MainWindow.xaml.cs 파일에서는 `AccessTheWebAsync`의 루프에서 각 웹 사이트에 대한 처리 단계를 다음 비동기 메서드로 이동하여 전환을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-127">In the MainWindow.xaml.cs file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```csharp  
// ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 <span data-ttu-id="31775-128">`AccessTheWebAsync`에서 이 예제는 쿼리, <xref:System.Linq.Enumerable.ToArray%2A> 메서드 및 `WhenAny` 메서드를 사용하여 작업 배열을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-128">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="31775-129">배열에 `WhenAny`를 적용하면 대기할 때 작업 배열에서 완료에 도달할 첫 번째 작업으로 계산되는 단일 작업이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31775-129">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="31775-130">`AccessTheWebAsync`에서 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-130">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="31775-131">코드 파일에서 변경 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31775-131">Asterisks mark the changes in the code file.</span></span>  
  
1. <span data-ttu-id="31775-132">루프를 주석으로 처리하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-132">Comment out or delete the loop.</span></span>  
  
2. <span data-ttu-id="31775-133">실행될 때 제네릭 작업의 컬렉션을 생성하는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31775-133">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="31775-134">`ProcessURLAsync`를 호출할 때마다 <xref:System.Threading.Tasks.Task%601>가 반환됩니다. 여기서 `TResult`는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="31775-134">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3. <span data-ttu-id="31775-135">`ToArray`를 호출하여 쿼리를 실행하고 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="31775-136">다음 단계에서 `WhenAny` 메서드를 적용하면 `ToArray`를 사용하지 않고 쿼리가 실행되고 작업이 시작되지만 다른 메서드는 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31775-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="31775-137">가장 안전한 방법은 쿼리를 명시적으로 강제 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31775-137">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4. <span data-ttu-id="31775-138">작업 컬렉션에서 `WhenAny`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-138">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="31775-139">`WhenAny`는 `Task(Of Task(Of Integer))` 또는 `Task<Task<int>>`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-139">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="31775-140">즉, `WhenAny`는 대기 시 단일 `Task(Of Integer)` 또는 `Task<int>`로 계산되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-140">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="31775-141">이 단일 작업은 컬렉션에서 완료될 첫 번째 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="31775-141">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="31775-142">첫 번째로 완료된 작업은 `firstFinishedTask`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="31775-142">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="31775-143">`firstFinishedTask`의 형식은 <xref:System.Threading.Tasks.Task%601>입니다. 여기서 `TResult`는 `ProcessURLAsync`의 반환 형식이므로 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="31775-143">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5. <span data-ttu-id="31775-144">이 예제에서는 첫 번째로 완료되는 작업에만 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="31775-144">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="31775-145">따라서 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>을 사용하여 나머지 작업을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-145">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6. <span data-ttu-id="31775-146">마지막으로 다운로드된 콘텐츠의 길이를 검색할 때까지 `firstFinishedTask`를 대기하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-146">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
    ```  
  
 <span data-ttu-id="31775-147">프로그램을 여러 번 실행하여 다른 다운로드가 먼저 완료되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-147">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="31775-148">완성된 예제</span><span class="sxs-lookup"><span data-stu-id="31775-148">Complete Example</span></span>  
 <span data-ttu-id="31775-149">다음 코드는 예제에 대한 전체 MainWindow.xaml.cs 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="31775-149">The following code is the complete MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="31775-150">별표는 이 예제에 대해 추가된 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-150">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="31775-151"><xref:System.Net.Http>에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31775-151">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="31775-152">[비동기 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 프로젝트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31775-152">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
  
namespace CancelAfterOneTask  
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
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.
            //    // Argument ct carries the message if the Cancel button is chosen.
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31775-153">참조</span><span class="sxs-lookup"><span data-stu-id="31775-153">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="31775-154">Async 애플리케이션 미세 조정(C#)</span><span class="sxs-lookup"><span data-stu-id="31775-154">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- [<span data-ttu-id="31775-155">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="31775-155">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="31775-156">비동기 샘플: 애플리케이션 미세 조정</span><span class="sxs-lookup"><span data-stu-id="31775-156">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
