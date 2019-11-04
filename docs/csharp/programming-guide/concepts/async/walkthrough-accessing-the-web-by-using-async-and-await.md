---
title: '연습: async 및 await를 사용하여 웹에 액세스(C#)'
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: 30677be2299dfa4411263dc5c61093fc0ca0f442
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73195646"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="81df6-102">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="81df6-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>

<span data-ttu-id="81df6-103">async/await 기능을 사용하여 비동기 프로그램을 보다 쉽고 직관적인 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="81df6-104">동기 코드처럼 보이는 비동기 코드를 작성하고 일반적으로 비동기 코드에 수반되는 어려운 콜백 함수 및 연속 작업을 컴파일러에서 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="81df6-105">비동기 기능에 대한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍(C#)](./index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="81df6-106">이 연습은 웹 사이트 목록에 있는 바이트 수의 합계를 계산하는 동기 WPF(Windows Presentation Foundation) 애플리케이션에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="81df6-107">그런 다음 새로운 기능을 사용하여 애플리케이션을 비동기 솔루션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="81df6-108">애플리케이션을 직접 빌드하지 않으려면 [비동기 샘플: 웹 연습에 액세스(C# 및 Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)를 다운로드하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-108">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

> [!NOTE]
> <span data-ttu-id="81df6-109">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-109">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="81df6-110">WPF 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="81df6-110">Create a WPF application</span></span>

1. <span data-ttu-id="81df6-111">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="81df6-112">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-112">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="81df6-113">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-113">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="81df6-114">**설치된 템플릿** 창에서 Visual C#을 선택한 다음 프로젝트 형식 목록에서 **WPF 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-114">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="81df6-115">**이름** 텍스트 상자에 `AsyncExampleWPF`를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-115">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

     <span data-ttu-id="81df6-116">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-116">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="81df6-117">간단한 WPF MainWindow 디자인</span><span class="sxs-lookup"><span data-stu-id="81df6-117">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="81df6-118">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-118">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="81df6-119">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴를 열고 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-119">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="81df6-120">**Button** 컨트롤 및 **TextBox** 컨트롤을 **MainWindow** 창에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-120">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="81df6-121">**TextBox** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-121">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="81df6-122">**Name** 속성을 `resultsTextBox`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-122">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="81df6-123">**Height** 속성을 250으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-123">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="81df6-124">**Width** 속성을 500으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-124">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="81df6-125">**Text** 탭에서 Lucida Console 또는 Global Monospace 같은 고정 폭 글꼴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-125">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="81df6-126">**Button** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-126">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="81df6-127">**Name** 속성을 `startButton`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-127">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="81df6-128">**Content** 속성 값을 **Button**에서 **Start**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-128">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="81df6-129">텍스트 상자와 단추가 둘 다 **MainWindow** 창에 나타나도록 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-129">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

     <span data-ttu-id="81df6-130">WPF XAML 디자이너에 대한 자세한 내용은 [XAML 디자이너를 사용하여 UI 만들기](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-130">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="81df6-131">참조 추가</span><span class="sxs-lookup"><span data-stu-id="81df6-131">Add a reference</span></span>

1. <span data-ttu-id="81df6-132">**솔루션 탐색기**에서 프로젝트의 이름을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-132">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="81df6-133">메뉴 모음에서 **프로젝트** > **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-133">On the menu bar, choose **Project** > **Add Reference**.</span></span>

     <span data-ttu-id="81df6-134">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-134">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="81df6-135">대화 상자 맨 위에서 프로젝트가 .NET Framework 4.5 이상을 대상으로 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-135">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="81df6-136">**어셈블리** 범주에서 **프레임워크**가 선택되지 않은 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-136">In the **Assemblies** category, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="81df6-137">이름 목록에서 **System.Net.Http** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-137">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="81df6-138">**확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-138">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-using-directives"></a><span data-ttu-id="81df6-139">필요한 using 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="81df6-139">Add necessary using directives</span></span>

1. <span data-ttu-id="81df6-140">**솔루션 탐색기**에서 MainWindow.xaml.cs의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-140">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

2. <span data-ttu-id="81df6-141">다음 `using` 지시문이 없는 경우 코드 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-141">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a><span data-ttu-id="81df6-142">동기 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="81df6-142">Create a synchronous app</span></span>

1. <span data-ttu-id="81df6-143">디자인 창 MainWindow.xaml에서 **시작** 단추를 두 번 클릭하여 MainWindow.xaml.cs에서 `startButton_Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-143">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="81df6-144">MainWindow.xaml.cs에서 다음 코드를 `startButton_Click`의 본문에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-144">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    <span data-ttu-id="81df6-145">이 코드는 애플리케이션 `SumPageSizes`를 구동하는 메서드를 호출하고 컨트롤이 `startButton_Click`으로 반환될 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-145">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="81df6-146">동기 솔루션에 대한 코드에는 다음 네 가지 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-146">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="81df6-147">`SumPageSizes` - `SetUpURLList`에서 웹 페이지 URL 목록을 가져온 다음 `GetURLContents` 및 `DisplayResults`를 호출하여 각 URL을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-147">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="81df6-148">`SetUpURLList` - 웹 주소 목록을 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-148">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="81df6-149">`GetURLContents` - 각 웹 사이트의 콘텐츠를 다운로드하고 해당 콘텐츠를 바이트 배열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-149">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="81df6-150">`DisplayResults`- 각 URL에 대한 바이트 배열의 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-150">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="81df6-151">다음 네 개 메서드를 복사한 다음 MainWindow.xaml.cs의 `startButton_Click` 이벤트 처리기 아래에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-151">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
        {
            "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290136.aspx",
            "https://msdn.microsoft.com/library/ee256749.aspx",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
            }
        }

        // Return the result as a byte array.
        return content.ToArray();
    }

    private void DisplayResults(string url, byte[] content)
    {
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as
        // Lucida Console or Global Monospace.
        var bytes = content.Length;
        // Strip off the "https://".
        var displayURL = url.Replace("https://", "");
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="81df6-152">동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="81df6-152">Test the synchronous solution</span></span>

<span data-ttu-id="81df6-153">**F5** 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-153">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

<span data-ttu-id="81df6-154">다음 목록과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-154">Output that resembles the following list should appear:</span></span>

```text
msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
msdn.microsoft.com                                            33964
msdn.microsoft.com/library/hh290136.aspx               225793
msdn.microsoft.com/library/ee256749.aspx               143577
msdn.microsoft.com/library/hh290138.aspx               237372
msdn.microsoft.com/library/hh290140.aspx               128279
msdn.microsoft.com/library/dd470362.aspx               157649
msdn.microsoft.com/library/aa578028.aspx               204457
msdn.microsoft.com/library/ms404677.aspx               176405
msdn.microsoft.com/library/ff730837.aspx               143474

Total bytes returned:  1834802

Control returned to startButton_Click.
```

<span data-ttu-id="81df6-155">개수를 표시하려면 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-155">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="81df6-156">이 시간 동안 UI 스레드는 차단되어 요청한 리소스가 다운로드될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-156">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="81df6-157">따라서 **시작** 단추를 선택한 후에도 표시 창을 이동, 최대화, 최소화할 수 없으며 닫을 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-157">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="81df6-158">이러한 작업은 바이트 개수가 나타나기 시작할 때까지 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-158">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="81df6-159">웹 사이트가 응답하지 않는 경우 실패한 사이트를 표시하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-159">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="81df6-160">대기를 중지하고 프로그램을 닫는 것도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-160">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="81df6-161">GetURLContents를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="81df6-161">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="81df6-162">동기 솔루션을 비동기 솔루션으로 변환하려면 `GetURLContents`에서 시작하는 것이 가장 좋습니다. <xref:System.Net.HttpWebRequest> 메서드 <xref:System.Net.HttpWebRequest.GetResponse%2A> 및 <xref:System.IO.Stream> 메서드 <xref:System.IO.Stream.CopyTo%2A> 호출은 애플리케이션이 웹에 액세스하는 위치이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-162">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="81df6-163">.NET Framework는 두 메서드의 비동기 버전을 제공하여 변환을 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-163">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

     <span data-ttu-id="81df6-164">`GetURLContents`에서 사용되는 메서드에 대한 자세한 내용은 <xref:System.Net.WebRequest>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-164">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81df6-165">이 연습 단계를 수행하면 여러 가지 컴파일러 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-165">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="81df6-166">이러한 오류는 무시하고 연습을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-166">You can ignore them and continue with the walkthrough.</span></span>

     <span data-ttu-id="81df6-167">`GetURLContents`의 셋째 줄에서 호출되는 메서드를 `GetResponse`에서 비동기 작업 기반 <xref:System.Net.WebRequest.GetResponseAsync%2A> 메서드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-167">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. <span data-ttu-id="81df6-168">`GetResponseAsync`는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-168">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="81df6-169">이 경우 *작업 반환 변수* `TResult`는 <xref:System.Net.WebResponse> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-169">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="81df6-170">작업은 요청한 데이터를 다운로드하고 작업을 실행하여 완료한 후 실제 `WebResponse` 개체를 생성한다는 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-170">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

     <span data-ttu-id="81df6-171">작업에서 `WebResponse` 값을 검색하려면 다음 코드에 표시된 대로 [await](../../../language-reference/operators/await.md) 연산자를 `GetResponseAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-171">To retrieve the `WebResponse` value from the task, apply an [await](../../../language-reference/operators/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     <span data-ttu-id="81df6-172">`GetURLContents` 연산자는 대기 중인 작업이 완료될 때까지 현재 메서드 `await`의 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-172">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="81df6-173">반면, 컨트롤은 현재 메서드의 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-173">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="81df6-174">이 예제에서 현재 메서드는 `GetURLContents`이고 호출자는 `SumPageSizes`입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-174">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="81df6-175">작업이 완료되면 약속된 `WebResponse` 개체가 대기 중인 작업의 값으로 생성되고 `response` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-175">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

     <span data-ttu-id="81df6-176">위의 문을 다음과 같은 두 개의 문으로 구분하여 수행되는 작업을 명확하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-176">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     <span data-ttu-id="81df6-177">`webReq.GetResponseAsync`를 호출하면 `Task(Of WebResponse)` 또는 `Task<WebResponse>`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-177">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="81df6-178">그러면 await 연산자가 작업에 적용되어 `WebResponse` 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-178">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>

     <span data-ttu-id="81df6-179">비동기 메서드가 작업의 완료에 따라 달라지지 않는 작업을 수행해야 하는 경우 메서드는 비동기 메서드를 호출한 후와 `await` 연산자가 적용되기 전의 두 문 사이에서 해당 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-179">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="81df6-180">예제는 [방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) 및 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-180">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="81df6-181">이전 단계에서 `await` 연산자를 추가했으므로 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-181">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="81df6-182">이 연산자는 [async](../../../language-reference/keywords/async.md) 한정자로 표시되는 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-182">The operator can be used only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="81df6-183">`CopyTo` 호출을 `CopyToAsync` 호출로 바꾸는 변환 단계를 반복하는 동안에는 오류를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-183">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="81df6-184">호출되는 메서드의 이름을 <xref:System.IO.Stream.CopyToAsync%2A>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-184">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="81df6-185">`CopyTo` 또는 `CopyToAsync` 메서드는 바이트를 해당 인수 `content`에 복사하고 의미 있는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-185">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="81df6-186">동기 버전에서 `CopyTo` 호출은 값을 반환하지 않는 단순 문입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-186">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="81df6-187">비동기 버전 `CopyToAsync`는 <xref:System.Threading.Tasks.Task>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-187">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="81df6-188">작업은 "Task(void)"처럼 작동하고 메서드를 대기하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-188">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="81df6-189">다음 코드에 표시된 대로 `Await` 또는 `await`를 `CopyToAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-189">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         <span data-ttu-id="81df6-190">위의 문은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-190">The previous statement abbreviates the following two lines of code.</span></span>

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. <span data-ttu-id="81df6-191">`GetURLContents`에서 수행해야 할 나머지 작업은 메서드 시그니처를 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-191">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="81df6-192">`await` 연산자는 [async](../../../language-reference/keywords/async.md) 한정자로 표시되는 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-192">You can use the `await` operator only in methods that are marked with the [async](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="81df6-193">다음 코드에 표시된 대로 한정자를 추가하여 메서드를 *비동기 메서드*로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-193">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. <span data-ttu-id="81df6-194">C#에서 비동기 메서드의 반환 형식은 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> 또는 `void`만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-194">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="81df6-195">일반적으로 `void`의 반환 형식은 비동기 이벤트 처리기에서만 사용되며, 여기서 `void`는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-195">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="81df6-196">경우에 따라 완료된 메서드에 T 형식의 값을 반환하는 [return](../../../language-reference/keywords/return.md) 문이 있는 경우 `Task(T)`를 사용하고, 완료된 메서드에서 의미 있는 값을 반환하지 않는 경우 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-196">In other cases, you use `Task(T)` if the completed method has a [return](../../../language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="81df6-197">`Task` 반환 형식은 "Task(void)" 의미로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-197">You can think of the `Task` return type as meaning "Task(void)."</span></span>

     <span data-ttu-id="81df6-198">자세한 내용은 [비동기 반환 형식(C#)](./async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-198">For more information, see [Async Return Types (C#)](./async-return-types.md).</span></span>

     <span data-ttu-id="81df6-199">`GetURLContents` 메서드에는 return 문이 있고 이 문은 바이트 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-199">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="81df6-200">따라서 비동기 버전의 반환 형식은 Task(T)이며, 여기서 T는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-200">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="81df6-201">다음과 같이 메서드 시그니처를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-201">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="81df6-202">반환 형식을 `Task<byte[]>`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-202">Change the return type to `Task<byte[]>`.</span></span>

    - <span data-ttu-id="81df6-203">규칙에 따라 비동기 메서드에는 "Async"로 끝나는 이름이 있으므로 `GetURLContentsAsync` 메서드의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-203">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

     <span data-ttu-id="81df6-204">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-204">The following code shows these changes.</span></span>

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     <span data-ttu-id="81df6-205">몇 가지 변경 작업을 통해 `GetURLContents`가 비동기 메서드로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-205">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="81df6-206">SumPageSizes를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="81df6-206">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="81df6-207">`SumPageSizes`에 대한 이전 절차의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-207">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="81df6-208">먼저 `GetURLContents` 호출을 비동기 호출로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-208">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="81df6-209">호출되는 메서드의 이름을 `GetURLContents`에서 `GetURLContentsAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-209">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="81df6-210">`GetURLContentsAsync`에서 반환하는 작업에 `await`를 적용하여 바이트 배열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-210">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

     <span data-ttu-id="81df6-211">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-211">The following code shows these changes.</span></span>

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     <span data-ttu-id="81df6-212">위의 할당은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-212">The previous assignment abbreviates the following two lines of code.</span></span>

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. <span data-ttu-id="81df6-213">메서드의 시그니처를 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-213">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="81df6-214">`async` 한정자를 사용하여 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-214">Mark the method with the `async` modifier.</span></span>

    - <span data-ttu-id="81df6-215">메서드 이름에 "Async"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-215">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="81df6-216">`SumPageSizesAsync`는 T에 대한 값을 반환하지 않으므로 이번에는 작업 반환 변수 T가 없습니다. 메서드에 `return` 문이 없습니다. 그러나 메서드는 대기 가능하도록 `Task`를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-216">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="81df6-217">따라서 메서드의 반환 형식을 `void`에서 `Task`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-217">Therefore, change the return type of the method from `void` to `Task`.</span></span>

    <span data-ttu-id="81df6-218">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-218">The following code shows these changes.</span></span>

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     <span data-ttu-id="81df6-219">`SumPageSizes`가 `SumPageSizesAsync`로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-219">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="81df6-220">startButton_Click을 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="81df6-220">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="81df6-221">이벤트 처리기에서 호출된 메서드의 이름을 `SumPageSizes`에서 `SumPageSizesAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-221">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="81df6-222">`SumPageSizesAsync`는 비동기 메서드이므로 이벤트 처리기에서 코드를 변경하여 결과를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-222">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

     <span data-ttu-id="81df6-223">`SumPageSizesAsync` 호출은 `GetURLContentsAsync`에서 `CopyToAsync` 호출을 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-223">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="81df6-224">이 호출에서는 `Task(T)`가 아니라 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-224">The call returns a `Task`, not a `Task(T)`.</span></span>

     <span data-ttu-id="81df6-225">이전 절차에서처럼 한 개 또는 두 개의 문을 사용하여 호출을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-225">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="81df6-226">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-226">The following code shows these changes.</span></span>

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. <span data-ttu-id="81df6-227">실수로 작업을 다시 입력하지 않도록 하려면 `startButton_Click`의 맨 위에 다음 문을 추가하여 **시작** 단추를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-227">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     <span data-ttu-id="81df6-228">이벤트 처리기의 끝에서 단추를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-228">You can reenable the button at the end of the event handler.</span></span>

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     <span data-ttu-id="81df6-229">재입력에 대한 자세한 내용은 [비동기 앱에서 재입력 처리(C#)](./handling-reentrancy-in-async-apps.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81df6-229">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="81df6-230">마지막으로 `async` 한정자를 선언에 추가하여 이벤트 처리기에서 `SumPagSizesAsync`를 기다릴 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-230">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     <span data-ttu-id="81df6-231">일반적으로 이벤트 처리기의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-231">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="81df6-232">이벤트 처리기가 `void`를 반환해야 하므로 반환 형식은 `Task`로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-232">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>

     <span data-ttu-id="81df6-233">동기에서 비동기 처리로 프로젝트 변환이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-233">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="81df6-234">비동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="81df6-234">Test the asynchronous solution</span></span>

1. <span data-ttu-id="81df6-235">**F5** 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-235">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="81df6-236">동기 솔루션의 출력과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-236">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="81df6-237">그러나 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-237">However, notice the following differences.</span></span>

    - <span data-ttu-id="81df6-238">처리가 완료된 후 결과가 모두 동시에 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-238">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="81df6-239">예를 들어 두 프로그램 모두 텍스트 상자를 지우는 줄을 `startButton_Click`에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-239">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="81df6-240">의도는 하나의 결과 집합이 나타난 후 몇 초 동안 **시작** 단추를 선택하면 실행 사이에 텍스트 상자를 지우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-240">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="81df6-241">동기 버전에서는 다운로드가 완료되고 UI 스레드에서 자유롭게 다른 작업을 수행할 수 있게 되면 두 번째로 개수가 표시되기 직전에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-241">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="81df6-242">비동기 버전에서는 **시작** 단추를 선택한 직후에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-242">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="81df6-243">가장 중요한 점은 다운로드하는 동안 UI 스레드가 차단되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-243">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="81df6-244">웹 리소스를 다운로드하고, 개수를 계산하고, 표시하는 동안 창을 이동하거나 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-244">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="81df6-245">웹 사이트 중 하나가 속도가 느리거나 응답하지 않는 경우 **닫기** 단추(오른쪽 위 모서리에 있는 빨간색 필드의 x)를 선택하여 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-245">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-method-geturlcontentsasync-with-a-net-framework-method"></a><span data-ttu-id="81df6-246">GetURLContentsAsync 메서드를 .NET Framework 메서드로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="81df6-246">Replace method GetURLContentsAsync with a .NET Framework method</span></span>

1. <span data-ttu-id="81df6-247">.NET Framework 4.5는 사용할 수 있는 다양한 비동기 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-247">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="81df6-248">그 중 하나인 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>가 바로 이 연습에 필요한 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-248">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="81df6-249">이전 절차에서 만든 `GetURLContentsAsync` 메서드 대신 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-249">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

     <span data-ttu-id="81df6-250">첫 번째 단계로 `SumPageSizesAsync` 메서드에서 `HttpClient` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-250">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="81df6-251">메서드의 시작 부분에 다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-251">Add the following declaration at the start of the method.</span></span>

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. <span data-ttu-id="81df6-252">`SumPageSizesAsync,`에서 `GetURLContentsAsync` 메서드 호출을 `HttpClient` 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-252">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. <span data-ttu-id="81df6-253">작성한 `GetURLContentsAsync` 메서드를 제거하거나 주석 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-253">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="81df6-254">**F5** 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-254">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="81df6-255">이 버전의 프로젝트 동작은 "비동기 솔루션을 테스트하려면" 절차에서 설명한 동작과 일치해야 하지만 사용자의 노력은 훨씬 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-255">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example-code"></a><span data-ttu-id="81df6-256">예제 코드</span><span class="sxs-lookup"><span data-stu-id="81df6-256">Example code</span></span>

<span data-ttu-id="81df6-257">다음 코드는 직접 작성한 `GetURLContentsAsync` 메서드를 사용하여 동기 솔루션에서 비동기 솔루션으로 변환하는 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-257">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="81df6-258">원래의 동기 솔루션과 매우 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-258">Notice that it strongly resembles the original, synchronous solution.</span></span>

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
                }
            }
            // Return the result as a byte array.
            return content.ToArray();
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

<span data-ttu-id="81df6-259">다음 코드는 `HttpClient` 메서드 `GetByteArrayAsync`를 사용하는 솔루션에 대한 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="81df6-259">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="81df6-260">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81df6-260">See also</span></span>

- [<span data-ttu-id="81df6-261">비동기 샘플: 웹 연습에 액세스(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81df6-261">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="81df6-262">async</span><span class="sxs-lookup"><span data-stu-id="81df6-262">async</span></span>](../../../language-reference/keywords/async.md)
- [<span data-ttu-id="81df6-263">await</span><span class="sxs-lookup"><span data-stu-id="81df6-263">await</span></span>](../../../language-reference/operators/await.md)
- [<span data-ttu-id="81df6-264">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="81df6-264">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="81df6-265">비동기 반환 형식(C#)</span><span class="sxs-lookup"><span data-stu-id="81df6-265">Async Return Types (C#)</span></span>](./async-return-types.md)
- [<span data-ttu-id="81df6-266">TAP(작업 기반 비동기 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="81df6-266">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/download/details.aspx?id=19957)
- [<span data-ttu-id="81df6-267">방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)</span><span class="sxs-lookup"><span data-stu-id="81df6-267">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="81df6-268">방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="81df6-268">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
