---
title: 일정 기간 이후 비동기 작업 취소(C#)
description: C#에서 CancellationTokenSource.CancelAfter 메서드를 사용하여 이 예제의 기간 내에 완료되지 않은 연결된 작업의 취소를 예약합니다.
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: f32af1d893c60ac17648f60fa3aa90adaa0383e8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925294"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="518de-103">일정 기간 이후 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="518de-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="518de-104">작업이 완료될 때까지 대기하지 않으려는 경우 일정 기간 후에 <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> 메서드를 사용하여 비동기 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518de-104">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="518de-105">이 메서드는 `CancelAfter` 식으로 지정된 일정 기간 내에 완료되지 않은 연결된 작업의 취소를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-105">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="518de-106">이 예제는 [비동기 작업 또는 작업 목록 취소(C#)](./cancel-an-async-task-or-a-list-of-tasks.md)에서 개발된 코드에 추가되어 웹 사이트 목록을 다운로드하고 각 웹 사이트의 콘텐츠 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-106">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="518de-107">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-107">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-the-example"></a><span data-ttu-id="518de-108">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="518de-108">Download the example</span></span>

<span data-ttu-id="518de-109">[Async 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후, 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-109">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="518de-110">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-110">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="518de-111">메뉴 모음에서 **파일** > **열기** > **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-111">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="518de-112">**프로젝트 열기** 대화 상자에서 압축을 해제한 샘플 코드가 포함된 폴더를 열고 AsyncFineTuningCS에 대한 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="518de-112">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="518de-113">**솔루션 탐색기**에서 **CancelAfterTime** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-113">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="518de-114">**F5** 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-114">Choose the **F5** key to run the project.</span></span> <span data-ttu-id="518de-115">또는 **Ctrl**+**F5**를 눌러 디버그하지 않고 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-115">(Or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

6. <span data-ttu-id="518de-116">프로그램을 여러 번 실행하여 모든 웹 사이트 또는 일부 웹 사이트에 대한 출력이 표시되는지, 또는 웹 사이트에 대한 출력이 표시되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-116">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

<span data-ttu-id="518de-117">프로젝트를 다운로드하지 않으려는 경우 이 항목의 끝에 있는 MainWindow.xaml.cs 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518de-117">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>

## <a name="build-the-example"></a><span data-ttu-id="518de-118">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="518de-118">Build the example</span></span>

<span data-ttu-id="518de-119">이 항목의 예제는 [비동기 작업 또는 작업 목록 취소(C#)](./cancel-an-async-task-or-a-list-of-tasks.md)에서 개발된 프로젝트에 추가되어 작업 목록을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-119">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="518de-120">**취소** 단추는 명시적으로 사용되지 않지만 예제에서는 같은 UI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-120">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="518de-121">직접 예제를 빌드하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르되, **CancelAListOfTasks**를 **시작 프로젝트**로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-121">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="518de-122">이 항목의 변경 내용을 해당 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-122">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="518de-123">작업이 취소됨으로 표시되기 전에 소요되는 최대 시간을 지정하려면 다음 예제와 같이 `CancelAfter` 호출을 `startButton_Click`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-123">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="518de-124">추가된 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="518de-124">The addition is marked with asterisks.</span></span>

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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
```

 <span data-ttu-id="518de-125">프로그램을 여러 번 실행하여 모든 웹 사이트 또는 일부 웹 사이트에 대한 출력이 표시되는지, 또는 웹 사이트에 대한 출력이 표시되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-125">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="518de-126">다음은 샘플 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="518de-126">The following output is a sample.</span></span>

```output
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="518de-127">전체 예제</span><span class="sxs-lookup"><span data-stu-id="518de-127">Complete example</span></span>

<span data-ttu-id="518de-128">다음 코드는 예제에 대한 MainWindow.xaml.cs 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="518de-128">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="518de-129">별표는 이 예제에 대해 추가된 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-129">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="518de-130"><xref:System.Net.Http>에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="518de-130">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="518de-131">[비동기 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 프로젝트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518de-131">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="518de-132">참조</span><span class="sxs-lookup"><span data-stu-id="518de-132">See also</span></span>

- [<span data-ttu-id="518de-133">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="518de-133">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="518de-134">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="518de-134">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="518de-135">비동기 작업 또는 작업 목록 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="518de-135">Cancel an Async Task or a List of Tasks (C#)</span></span>](./cancel-an-async-task-or-a-list-of-tasks.md)
- [<span data-ttu-id="518de-136">Async 애플리케이션 미세 조정(C#)</span><span class="sxs-lookup"><span data-stu-id="518de-136">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- [<span data-ttu-id="518de-137">비동기 샘플: 애플리케이션 미세 조정</span><span class="sxs-lookup"><span data-stu-id="518de-137">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
