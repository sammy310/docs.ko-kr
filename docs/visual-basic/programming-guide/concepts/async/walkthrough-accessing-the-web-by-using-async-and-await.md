---
title: '연습: Async 및 Await를 사용하여 웹에 액세스'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 41ededd4d4335b78b8d7a33e8fe387c7d632cbee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400747"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="5cd6a-102">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="5cd6a-103">async/await 기능을 사용하여 비동기 프로그램을 보다 쉽고 직관적인 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="5cd6a-104">동기 코드처럼 보이는 비동기 코드를 작성하고 일반적으로 비동기 코드에 수반되는 어려운 콜백 함수 및 연속 작업을 컴파일러에서 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="5cd6a-105">비동기 기능에 대 한 자세한 내용은 [async And wait (Visual Basic)를 사용한 비동기 프로그래밍](index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](index.md).</span></span>

<span data-ttu-id="5cd6a-106">이 연습은 웹 사이트 목록에 있는 바이트 수의 합계를 계산하는 동기 WPF(Windows Presentation Foundation) 애플리케이션에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="5cd6a-107">그런 다음 새로운 기능을 사용하여 애플리케이션을 비동기 솔루션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="5cd6a-108">애플리케이션을 직접 빌드하지 않으려면 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)에서 "Async 샘플: 웹 연습에 액세스(C# 및 Visual Basic)"를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

<span data-ttu-id="5cd6a-109">이 연습에서는 다음 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-109">In this walkthrough, you complete the following tasks:</span></span>

> [!div class="checklist"]
>
> - [<span data-ttu-id="5cd6a-110">WPF 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="5cd6a-110">Create a WPF application</span></span>](#create-a-wpf-application)
> - [<span data-ttu-id="5cd6a-111">간단한 WPF MainWindow 디자인</span><span class="sxs-lookup"><span data-stu-id="5cd6a-111">Design a simple WPF MainWindow</span></span>](#design-a-simple-wpf-mainwindow)
> - [<span data-ttu-id="5cd6a-112">참조 추가</span><span class="sxs-lookup"><span data-stu-id="5cd6a-112">Add a reference</span></span>](#add-a-reference)
> - [<span data-ttu-id="5cd6a-113">필요한 Imports 문 추가</span><span class="sxs-lookup"><span data-stu-id="5cd6a-113">Add necessary Imports statements</span></span>](#add-necessary-imports-statements)
> - [<span data-ttu-id="5cd6a-114">동기 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5cd6a-114">Create a synchronous application</span></span>](#create-a-synchronous-application)
> - [<span data-ttu-id="5cd6a-115">동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5cd6a-115">Test the synchronous solution</span></span>](#test-the-synchronous-solution)
> - [<span data-ttu-id="5cd6a-116">GetURLContents를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-116">Convert GetURLContents to an asynchronous method</span></span>](#convert-geturlcontents-to-an-asynchronous-method)
> - [<span data-ttu-id="5cd6a-117">SumPageSizes를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-117">Convert SumPageSizes to an asynchronous method</span></span>](#convert-sumpagesizes-to-an-asynchronous-method)
> - [<span data-ttu-id="5cd6a-118">startButton_Click을 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-118">Convert startButton_Click to an asynchronous method</span></span>](#convert-startbutton_click-to-an-asynchronous-method)
> - [<span data-ttu-id="5cd6a-119">비동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5cd6a-119">Test the asynchronous solution</span></span>](#test-the-asynchronous-solution)
> - [<span data-ttu-id="5cd6a-120">GetURLContentsAsync 메서드를 .NET Framework 메서드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-120">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

<span data-ttu-id="5cd6a-121">전체 비동기 예제는 [예제](#example) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-121">See the [Example](#example) section for the complete asynchronous example.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5cd6a-122">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5cd6a-122">Prerequisites</span></span>

<span data-ttu-id="5cd6a-123">Visual Studio 2012 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="5cd6a-124">자세한 내용은 Visual Studio [다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 페이지를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-124">For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="5cd6a-125">WPF 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="5cd6a-125">Create a WPF application</span></span>

1. <span data-ttu-id="5cd6a-126">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-126">Start Visual Studio.</span></span>

2. <span data-ttu-id="5cd6a-127">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="5cd6a-128">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-128">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="5cd6a-129">**설치 된 템플릿** 창에서 Visual Basic을 선택한 다음 프로젝트 형식 목록에서 **WPF 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="5cd6a-130">**이름** 텍스트 상자에 `AsyncExampleWPF`를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

    <span data-ttu-id="5cd6a-131">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-131">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="5cd6a-132">간단한 WPF MainWindow 디자인</span><span class="sxs-lookup"><span data-stu-id="5cd6a-132">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="5cd6a-133">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="5cd6a-134">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴를 열고 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="5cd6a-135">**Button** 컨트롤 및 **TextBox** 컨트롤을 **MainWindow** 창에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="5cd6a-136">**TextBox** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="5cd6a-137">**Name** 속성을 `resultsTextBox`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-137">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="5cd6a-138">**Height** 속성을 250으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-138">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="5cd6a-139">**Width** 속성을 500으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-139">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="5cd6a-140">**Text** 탭에서 Lucida Console 또는 Global Monospace 같은 고정 폭 글꼴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="5cd6a-141">**Button** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="5cd6a-142">**Name** 속성을 `startButton`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-142">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="5cd6a-143">**Content** 속성 값을 **Button**에서 **Start**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="5cd6a-144">텍스트 상자와 단추가 둘 다 **MainWindow** 창에 나타나도록 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

    <span data-ttu-id="5cd6a-145">WPF XAML 디자이너에 대한 자세한 내용은 [XAML 디자이너를 사용하여 UI 만들기](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="5cd6a-146">참조 추가</span><span class="sxs-lookup"><span data-stu-id="5cd6a-146">Add a reference</span></span>

1. <span data-ttu-id="5cd6a-147">**솔루션 탐색기**에서 프로젝트의 이름을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-147">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="5cd6a-148">메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>

    <span data-ttu-id="5cd6a-149">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-149">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="5cd6a-150">대화 상자 맨 위에서 프로젝트가 .NET Framework 4.5 이상을 대상으로 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="5cd6a-151">**어셈블리** 영역에서 **프레임워크**가 선택되지 않은 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="5cd6a-152">이름 목록에서 **System.Net.Http** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-152">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="5cd6a-153">**확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-153">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-imports-statements"></a><span data-ttu-id="5cd6a-154">필요한 Imports 문 추가</span><span class="sxs-lookup"><span data-stu-id="5cd6a-154">Add necessary Imports statements</span></span>

1. <span data-ttu-id="5cd6a-155">**솔루션 탐색기**에서 mainwindow.xaml의 바로 가기 메뉴를 열고 **코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

2. <span data-ttu-id="5cd6a-156">`Imports`아직 없는 경우 코드 파일의 맨 위에 다음 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a><span data-ttu-id="5cd6a-157">동기 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5cd6a-157">Create a synchronous application</span></span>

1. <span data-ttu-id="5cd6a-158">디자인 창 Mainwindow.xaml에서 **시작** 단추를 두 번 클릭 하 여 `startButton_Click` mainwindow.xaml에 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="5cd6a-159">Mainwindow.xaml에서 다음 코드를의 본문에 복사 `startButton_Click` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    <span data-ttu-id="5cd6a-160">이 코드는 애플리케이션 `SumPageSizes`를 구동하는 메서드를 호출하고 컨트롤이 `startButton_Click`으로 반환될 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="5cd6a-161">동기 솔루션에 대한 코드에는 다음 네 가지 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-161">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="5cd6a-162">`SumPageSizes` - `SetUpURLList`에서 웹 페이지 URL 목록을 가져온 다음 `GetURLContents` 및 `DisplayResults`를 호출하여 각 URL을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="5cd6a-163">`SetUpURLList` - 웹 주소 목록을 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="5cd6a-164">`GetURLContents` - 각 웹 사이트의 콘텐츠를 다운로드하고 해당 콘텐츠를 바이트 배열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="5cd6a-165">`DisplayResults`- 각 URL에 대한 바이트 배열의 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="5cd6a-166">다음 네 가지 메서드를 복사한 다음 `startButton_Click` mainwindow.xaml의 이벤트 처리기 아래에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="5cd6a-167">동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5cd6a-167">Test the synchronous solution</span></span>

1. <span data-ttu-id="5cd6a-168">F5 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="5cd6a-169">다음 목록과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-169">Output that resembles the following list should appear:</span></span>

    ```console
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

    <span data-ttu-id="5cd6a-170">개수를 표시하려면 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="5cd6a-171">이 시간 동안 UI 스레드는 차단되어 요청한 리소스가 다운로드될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="5cd6a-172">따라서 **시작** 단추를 선택한 후에도 표시 창을 이동, 최대화, 최소화할 수 없으며 닫을 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="5cd6a-173">이러한 작업은 바이트 개수가 나타나기 시작할 때까지 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="5cd6a-174">웹 사이트가 응답하지 않는 경우 실패한 사이트를 표시하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="5cd6a-175">대기를 중지하고 프로그램을 닫는 것도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-175">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="5cd6a-176">GetURLContents를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-176">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="5cd6a-177">동기 솔루션을 비동기 솔루션으로 변환 하려면 메서드를 호출 하 고 메서드를 호출 하는 것이 `GetURLContents` <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> 응용 프로그램에서 웹에 액세스 하는 위치 이기 때문에를 시작 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web.</span></span> <span data-ttu-id="5cd6a-178">.NET Framework는 두 메서드의 비동기 버전을 제공하여 변환을 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

    <span data-ttu-id="5cd6a-179">`GetURLContents`에서 사용되는 메서드에 대한 자세한 내용은 <xref:System.Net.WebRequest>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cd6a-180">이 연습 단계를 수행하면 여러 가지 컴파일러 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="5cd6a-181">이러한 오류는 무시하고 연습을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-181">You can ignore them and continue with the walkthrough.</span></span>

    <span data-ttu-id="5cd6a-182">`GetURLContents`의 셋째 줄에서 호출되는 메서드를 `GetResponse`에서 비동기 작업 기반 <xref:System.Net.WebRequest.GetResponseAsync%2A> 메서드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. <span data-ttu-id="5cd6a-183">`GetResponseAsync`는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="5cd6a-184">이 경우 *작업 반환 변수*는 `TResult` 형식 <xref:System.Net.WebResponse> 입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="5cd6a-185">작업은 요청한 데이터를 다운로드하고 작업을 실행하여 완료한 후 실제 `WebResponse` 개체를 생성한다는 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

    <span data-ttu-id="5cd6a-186">`WebResponse`작업에서 값을 검색 하려면 [Await](../../../language-reference/operators/await-operator.md) `GetResponseAsync` 다음 코드에 표시 된 것 처럼에 대 한 호출에 wait 연산자를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    <span data-ttu-id="5cd6a-187">`GetURLContents` 연산자는 대기 중인 작업이 완료될 때까지 현재 메서드 `Await`의 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="5cd6a-188">반면, 컨트롤은 현재 메서드의 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="5cd6a-189">이 예제에서 현재 메서드는 `GetURLContents`이고 호출자는 `SumPageSizes`입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="5cd6a-190">작업이 완료되면 약속된 `WebResponse` 개체가 대기 중인 작업의 값으로 생성되고 `response` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

    <span data-ttu-id="5cd6a-191">위의 문을 다음과 같은 두 개의 문으로 구분하여 수행되는 작업을 명확하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    <span data-ttu-id="5cd6a-192">`webReq.GetResponseAsync`를 호출하면 `Task(Of WebResponse)` 또는 `Task<WebResponse>`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="5cd6a-193">그런 다음 `Await` 연산자를 작업에 적용 하 여 값을 검색 합니다 `WebResponse` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>

    <span data-ttu-id="5cd6a-194">비동기 메서드가 작업의 완료에 따라 달라지지 않는 작업을 수행해야 하는 경우 메서드는 비동기 메서드를 호출한 후와 await 연산자가 적용되기 전의 두 문 사이에서 해당 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="5cd6a-195">예제 [는 방법: async 및 wait를 사용 하 여 병렬로 여러 웹 요청 만들기 (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) 및 [방법: 작업을 사용 하 여 비동기 연습 확장 (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="5cd6a-196">이전 단계에서 `Await` 연산자를 추가했으므로 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="5cd6a-197">연산자는 [Async](../../../language-reference/modifiers/async.md) 한정자로 표시 된 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-197">The operator can be used only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="5cd6a-198">`CopyTo` 호출을 `CopyToAsync` 호출로 바꾸는 변환 단계를 반복하는 동안에는 오류를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="5cd6a-199">호출되는 메서드의 이름을 <xref:System.IO.Stream.CopyToAsync%2A>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="5cd6a-200">`CopyTo` 또는 `CopyToAsync` 메서드는 바이트를 해당 인수 `content`에 복사하고 의미 있는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="5cd6a-201">동기 버전에서 `CopyTo` 호출은 값을 반환하지 않는 단순 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="5cd6a-202">비동기 버전 `CopyToAsync`는 <xref:System.Threading.Tasks.Task>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="5cd6a-203">작업은 "Task(void)"처럼 작동하고 메서드를 대기하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="5cd6a-204">다음 코드에 표시된 대로 `Await` 또는 `await`를 `CopyToAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         <span data-ttu-id="5cd6a-205">위의 문은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-205">The previous statement abbreviates the following two lines of code.</span></span>

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. <span data-ttu-id="5cd6a-206">`GetURLContents`에서 수행해야 할 나머지 작업은 메서드 시그니처를 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="5cd6a-207">`Await`연산자는 [Async](../../../language-reference/modifiers/async.md) 한정자로 표시 된 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="5cd6a-208">다음 코드에 표시된 대로 한정자를 추가하여 메서드를 *비동기 메서드*로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. <span data-ttu-id="5cd6a-209">비동기 메서드의 반환 형식은,만 될 수 있습니다 <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="5cd6a-210">Visual Basic에서 메서드는 `Task` 또는 `Task(Of T)`를 반환하는 `Function`이거나 `Sub`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="5cd6a-211">일반적으로 `Sub` 메서드는가 필요한 비동기 이벤트 처리기 에서만 사용 됩니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="5cd6a-212">다른 경우에는 `Task(T)` completed 메서드에 T 형식의 값을 반환 하는 [Return](../../../language-reference/statements/return-statement.md) 문이 있는 경우를 사용 하 고, `Task` 완료 된 메서드에서 의미 있는 값을 반환 하지 않는 경우를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>

    <span data-ttu-id="5cd6a-213">자세한 내용은 [비동기 반환 형식 (Visual Basic)](async-return-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-213">For more information, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>

    <span data-ttu-id="5cd6a-214">`GetURLContents` 메서드에는 return 문이 있고 이 문은 바이트 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="5cd6a-215">따라서 비동기 버전의 반환 형식은 Task(T)이며, 여기서 T는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="5cd6a-216">다음과 같이 메서드 시그니처를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-216">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="5cd6a-217">반환 형식을 `Task(Of Byte())`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-217">Change the return type to `Task(Of Byte())`.</span></span>

    - <span data-ttu-id="5cd6a-218">규칙에 따라 비동기 메서드에는 "Async"로 끝나는 이름이 있으므로 `GetURLContentsAsync` 메서드의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

    <span data-ttu-id="5cd6a-219">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-219">The following code shows these changes.</span></span>

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    <span data-ttu-id="5cd6a-220">몇 가지 변경 작업을 통해 `GetURLContents`가 비동기 메서드로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="5cd6a-221">SumPageSizes를 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-221">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="5cd6a-222">`SumPageSizes`에 대한 이전 절차의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="5cd6a-223">먼저 `GetURLContents` 호출을 비동기 호출로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="5cd6a-224">호출되는 메서드의 이름을 `GetURLContents`에서 `GetURLContentsAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="5cd6a-225">`GetURLContentsAsync`에서 반환하는 작업에 `Await`를 적용하여 바이트 배열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

    <span data-ttu-id="5cd6a-226">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-226">The following code shows these changes.</span></span>

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    <span data-ttu-id="5cd6a-227">위의 할당은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-227">The previous assignment abbreviates the following two lines of code.</span></span>

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. <span data-ttu-id="5cd6a-228">메서드의 시그니처를 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-228">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="5cd6a-229">`Async` 한정자를 사용하여 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-229">Mark the method with the `Async` modifier.</span></span>

    - <span data-ttu-id="5cd6a-230">메서드 이름에 "Async"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-230">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="5cd6a-231">는 T에 대 한 값을 반환 하지 않으므로 이번에는 작업 반환 변수 T가 없습니다. `SumPageSizesAsync` (메서드에 문이 없습니다 `Return` .) 그러나 메서드는 대기 가능을 반환 해야 합니다 `Task` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="5cd6a-232">따라서 메서드 형식을에서로 변경 합니다 `Sub` `Function` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="5cd6a-233">함수의 반환 형식은 `Task`입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-233">The return type of the function is `Task`.</span></span>

    <span data-ttu-id="5cd6a-234">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-234">The following code shows these changes.</span></span>

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    <span data-ttu-id="5cd6a-235">`SumPageSizes`가 `SumPageSizesAsync`로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="5cd6a-236">startButton_Click을 비동기 메서드로 변환</span><span class="sxs-lookup"><span data-stu-id="5cd6a-236">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="5cd6a-237">이벤트 처리기에서 호출된 메서드의 이름을 `SumPageSizes`에서 `SumPageSizesAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="5cd6a-238">`SumPageSizesAsync`는 비동기 메서드이므로 이벤트 처리기에서 코드를 변경하여 결과를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

    <span data-ttu-id="5cd6a-239">`SumPageSizesAsync` 호출은 `GetURLContentsAsync`에서 `CopyToAsync` 호출을 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="5cd6a-240">이 호출에서는 `Task(T)`가 아니라 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-240">The call returns a `Task`, not a `Task(T)`.</span></span>

    <span data-ttu-id="5cd6a-241">이전 절차에서처럼 한 개 또는 두 개의 문을 사용하여 호출을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="5cd6a-242">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-242">The following code shows these changes.</span></span>

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. <span data-ttu-id="5cd6a-243">실수로 작업을 다시 입력하지 않도록 하려면 `startButton_Click`의 맨 위에 다음 문을 추가하여 **시작** 단추를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    <span data-ttu-id="5cd6a-244">이벤트 처리기의 끝에서 단추를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-244">You can reenable the button at the end of the event handler.</span></span>

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    <span data-ttu-id="5cd6a-245">재입력에 대 한 자세한 내용은 [비동기 앱에서 재입력 처리 (Visual Basic)](handling-reentrancy-in-async-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="5cd6a-246">마지막으로 `Async` 한정자를 선언에 추가하여 이벤트 처리기에서 `SumPagSizesAsync`를 기다릴 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    <span data-ttu-id="5cd6a-247">일반적으로 이벤트 처리기의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="5cd6a-248">`Task`이벤트 처리기가 Visual Basic의 프로시저 여야 하므로 반환 형식은로 변경 되지 않습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>

    <span data-ttu-id="5cd6a-249">동기에서 비동기 처리로 프로젝트 변환이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="5cd6a-250">비동기 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5cd6a-250">Test the asynchronous solution</span></span>

1. <span data-ttu-id="5cd6a-251">F5 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="5cd6a-252">동기 솔루션의 출력과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="5cd6a-253">그러나 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-253">However, notice the following differences.</span></span>

    - <span data-ttu-id="5cd6a-254">처리가 완료된 후 결과가 모두 동시에 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="5cd6a-255">예를 들어 두 프로그램 모두 텍스트 상자를 지우는 줄을 `startButton_Click`에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="5cd6a-256">의도는 하나의 결과 집합이 나타난 후 몇 초 동안 **시작** 단추를 선택하면 실행 사이에 텍스트 상자를 지우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="5cd6a-257">동기 버전에서는 다운로드가 완료되고 UI 스레드에서 자유롭게 다른 작업을 수행할 수 있게 되면 두 번째로 개수가 표시되기 직전에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="5cd6a-258">비동기 버전에서는 **시작** 단추를 선택한 직후에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="5cd6a-259">가장 중요한 점은 다운로드하는 동안 UI 스레드가 차단되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="5cd6a-260">웹 리소스를 다운로드하고, 개수를 계산하고, 표시하는 동안 창을 이동하거나 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="5cd6a-261">웹 사이트 중 하나가 속도가 느리거나 응답하지 않는 경우 **닫기** 단추(오른쪽 위 모서리에 있는 빨간색 필드의 x)를 선택하여 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a><span data-ttu-id="5cd6a-262">GetURLContentsAsync 메서드를 .NET Framework 메서드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-262">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>

1. <span data-ttu-id="5cd6a-263">.NET Framework는 사용할 수 있는 여러 비동기 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-263">The .NET Framework provides many async methods that you can use.</span></span> <span data-ttu-id="5cd6a-264">이러한 메서드 중 하나는 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> 이 연습에 필요한 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-264">One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough.</span></span> <span data-ttu-id="5cd6a-265">이전 절차에서 만든 `GetURLContentsAsync` 메서드 대신 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

    <span data-ttu-id="5cd6a-266">첫 번째 단계는 메서드에 개체를 만드는 것입니다 <xref:System.Net.Http.HttpClient> `SumPageSizesAsync` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-266">The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="5cd6a-267">메서드의 시작 부분에 다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-267">Add the following declaration at the start of the method.</span></span>

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. <span data-ttu-id="5cd6a-268">`SumPageSizesAsync,`에서 `GetURLContentsAsync` 메서드 호출을 `HttpClient` 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. <span data-ttu-id="5cd6a-269">작성한 `GetURLContentsAsync` 메서드를 제거하거나 주석 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="5cd6a-270">F5 키를 선택하여 프로그램을 실행한 후 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="5cd6a-271">이 버전의 프로젝트 동작은 "비동기 솔루션을 테스트하려면" 절차에서 설명한 동작과 일치해야 하지만 사용자의 노력은 훨씬 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example"></a><span data-ttu-id="5cd6a-272">예제</span><span class="sxs-lookup"><span data-stu-id="5cd6a-272">Example</span></span>

<span data-ttu-id="5cd6a-273">다음은 비동기 메서드를 사용 하는 변환 된 비동기 솔루션의 전체 예제입니다 `GetURLContentsAsync` .</span><span class="sxs-lookup"><span data-stu-id="5cd6a-273">The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method.</span></span> <span data-ttu-id="5cd6a-274">원래의 동기 솔루션과 매우 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-274">Notice that it strongly resembles the original, synchronous solution.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

<span data-ttu-id="5cd6a-275">다음 코드는 `HttpClient` 메서드 `GetByteArrayAsync`를 사용하는 솔루션에 대한 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd6a-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a><span data-ttu-id="5cd6a-276">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cd6a-276">See also</span></span>

- [<span data-ttu-id="5cd6a-277">Async 샘플: 웹 연습에 액세스(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-277">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="5cd6a-278">Wait 연산자</span><span class="sxs-lookup"><span data-stu-id="5cd6a-278">Await Operator</span></span>](../../../language-reference/operators/await-operator.md)
- [<span data-ttu-id="5cd6a-279">Async</span><span class="sxs-lookup"><span data-stu-id="5cd6a-279">Async</span></span>](../../../language-reference/modifiers/async.md)
- [<span data-ttu-id="5cd6a-280">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="5cd6a-281">비동기 반환 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-281">Async Return Types (Visual Basic)</span></span>](async-return-types.md)
- [<span data-ttu-id="5cd6a-282">TAP(작업 기반 비동기 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-282">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/download/details.aspx?id=19957)
- [<span data-ttu-id="5cd6a-283">방법: Task.WhenAll을 사용하여 비동기 연습 확장(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-283">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="5cd6a-284">방법: Async 및 Await를 사용하여 병렬로 여러 웹 요청 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cd6a-284">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
