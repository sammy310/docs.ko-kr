---
title: Visual Studio에서 WPF 응용 프로그램 만들기
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: 9d5b5b8a479efd3918dc23616aa331cc07a901ac
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972188"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="778a1-102">연습: 내 첫 WPF 데스크톱 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="778a1-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="778a1-103">이 문서에서는 대부분의 WPF 응용 프로그램에 공통 된 요소를 포함 하는 Windows Presentation Foundation (WPF) 데스크톱 응용 프로그램을 개발 하는 방법을 보여 줍니다. XAML (Extensible Application Markup Language) 태그, 코드 숨김으로, 응용 프로그램 정의, 컨트롤, 레이아웃, 데이터 바인딩 및 스타일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="778a1-104">응용 프로그램을 개발 하려면 Visual Studio를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="778a1-105">이 연습에는 다음 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="778a1-106">XAML을 사용 하 여 응용 프로그램 UI (사용자 인터페이스)의 모양을 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="778a1-107">응용 프로그램의 동작을 빌드하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="778a1-108">응용 프로그램을 관리 하는 응용 프로그램 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="778a1-109">응용 프로그램 UI를 구성 하는 컨트롤을 추가 하 고 레이아웃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="778a1-110">응용 프로그램 UI 전체에 일관 된 모양의 스타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="778a1-111">Ui를 데이터에 바인딩하여 데이터에서 UI를 채우고 데이터와 UI를 동기화 된 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="778a1-112">이 연습을 마치면 사용자가 선택한 사용자에 대 한 경비 보고서를 볼 수 있도록 하는 독립 실행형 Windows 응용 프로그램을 작성 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="778a1-113">응용 프로그램은 브라우저 스타일 창에서 호스팅되는 여러 WPF 페이지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="778a1-114">이 연습을 빌드하는 데 사용 되는 샘플 코드는 Visual Basic 및 C# [연습 WPF 앱 샘플 코드](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="778a1-115">이 문서의 오른쪽 위에 있는 C# **\< 드롭다운을 사용 하 />** 여 및 Visual Basic 사이에 샘플 코드의 코드 언어를 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="778a1-116">전제 조건</span><span class="sxs-lookup"><span data-stu-id="778a1-116">Prerequisites</span></span>

- <span data-ttu-id="778a1-117">Visual Studio 2017 이상 (이 문서에서는 Visual Studio 2019 사용)</span><span class="sxs-lookup"><span data-stu-id="778a1-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="778a1-118">최신 버전의 Visual Studio를 설치 하는 방법에 대 한 자세한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="778a1-119">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="778a1-119">Create the application project</span></span>

<span data-ttu-id="778a1-120">첫 번째 단계는 응용 프로그램 정의, 페이지 2 개 및 이미지를 포함 하는 응용 프로그램 인프라를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="778a1-121">Visual Basic 또는 시각적 개체 C# **`ExpenseIt`** 에서 새 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="778a1-122">Visual Studio를 열고 **시작** 메뉴에서 **새 프로젝트 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="778a1-123">**새 프로젝트 만들기** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="778a1-124">**언어** 드롭다운에서 **C#** 또는 **Visual Basic**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="778a1-125">**WPF 앱 (.NET Framework)** 템플릿을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![새 프로젝트 만들기 대화 상자](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="778a1-127">**새 프로젝트 구성** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="778a1-128">프로젝트 이름을 **`ExpenseIt`** 입력 하 고 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![새 프로젝트 구성 대화 상자](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="778a1-130">Visual Studio에서 프로젝트를 만들고 **mainwindow.xaml**이라는 기본 응용 프로그램 창에 대 한 디자이너를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="778a1-131">*응용 프로그램 .xaml* (Visual Basic) 또는 app.xaml (C#)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="778a1-132">이 XAML 파일은 WPF 응용 프로그램 및 모든 응용 프로그램 리소스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="778a1-133">또한이 파일을 사용 하 여 UI를 지정 합니다 .이 경우에는 응용 프로그램이 시작 될 때 자동으로 표시 되는 UI (이 경우 *mainwindow.xaml*)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="778a1-134">XAML은 Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="778a1-135">그리고에서 C#다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="778a1-136">*Mainwindow.xaml*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="778a1-137">이 XAML 파일은 응용 프로그램의 주 창이 며 페이지에서 만든 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="778a1-138">클래스 <xref:System.Windows.Window> 는 창 속성 (예: 제목, 크기 또는 아이콘)을 정의 하 고 닫기 또는 숨기기와 같은 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="778a1-139">다음 XAML과 같이 <xref:System.Windows.Navigation.NavigationWindow> 요소를로변경합니다.<xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="778a1-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="778a1-140">이 앱은 사용자 입력에 따라 다른 콘텐츠를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="778a1-141">이렇게 하면 main <xref:System.Windows.Window> 을 <xref:System.Windows.Navigation.NavigationWindow>로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="778a1-142"><xref:System.Windows.Navigation.NavigationWindow>의 <xref:System.Windows.Window>모든 속성을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="778a1-143">XAML <xref:System.Windows.Navigation.NavigationWindow> 파일의 요소는 <xref:System.Windows.Navigation.NavigationWindow> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="778a1-144">자세한 내용은 [탐색 개요](../app-development/navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="778a1-145">태그 사이에서 요소를 <xref:System.Windows.Controls.Grid> 제거 합니다. <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="778a1-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="778a1-146"><xref:System.Windows.Navigation.NavigationWindow> 요소에 대 한 XAML 코드에서 다음 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="778a1-147">속성을 "`ExpenseIt`"로 설정 합니다. <xref:System.Windows.Window.Title%2A></span><span class="sxs-lookup"><span data-stu-id="778a1-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="778a1-148"><xref:System.Windows.FrameworkElement.Height%2A> 속성을 350 픽셀로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="778a1-149"><xref:System.Windows.FrameworkElement.Width%2A> 속성을 500 픽셀로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="778a1-150">XAML은 Visual Basic에 대해 다음과 같이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="778a1-151">그리고 다음과 같이 합니다 C#.</span><span class="sxs-lookup"><span data-stu-id="778a1-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="778a1-152">*Mainwindow.xaml* 또는 *MainWindow.xaml.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="778a1-153">이 파일은 *mainwindow.xaml*에 선언 된 이벤트를 처리 하는 코드를 포함 하는 코드를 포함 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="778a1-154">이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="778a1-155">를 사용 C#하는 `MainWindow` 경우에서 <xref:System.Windows.Navigation.NavigationWindow>파생 되도록 클래스를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="778a1-156">Visual Basic XAML에서 창을 변경할 때 자동으로 발생 합니다. 이제 C# 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="778a1-157">응용 프로그램에 파일 추가</span><span class="sxs-lookup"><span data-stu-id="778a1-157">Add files to the application</span></span>

<span data-ttu-id="778a1-158">이 섹션에서는 애플리케이션에 두 페이지와 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="778a1-159">프로젝트에 새 페이지를 추가 하 고 이름을 *`ExpenseItHome.xaml`* 로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="778a1-160">**솔루션 탐색기** **`ExpenseIt`** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **페이지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="778a1-161">**새 항목 추가** 대화 상자에서 **페이지 (WPF)** 템플릿이 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="778a1-162">이름을 **`ExpenseItHome`** 입력 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="778a1-163">이 페이지는 응용 프로그램이 시작 될 때 표시 되는 첫 번째 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="778a1-164">에 대 한 경비 보고서를 표시 하기 위해 선택할 사용자의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="778a1-165">를 *`ExpenseItHome.xaml`* 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="778a1-166"><xref:System.Windows.Controls.Page.Title%2A> 을"`ExpenseIt - Home`"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="778a1-167">`DesignHeight` 및`DesignWidth` 요소 값을 300 픽셀로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-167">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="778a1-168">이제 XAML이 Visual Basic에 대해 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="778a1-169">그리고 다음과 같이 합니다 C#.</span><span class="sxs-lookup"><span data-stu-id="778a1-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="778a1-170">*Mainwindow.xaml*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="778a1-171">요소에 속성을 <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 추가 하 고 "`ExpenseItHome.xaml`"로 설정 합니다. <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="778a1-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="778a1-172">이는 *`ExpenseItHome.xaml`* 응용 프로그램이 시작 될 때 열리는 첫 페이지로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="778a1-173">Visual Basic의 XAML 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="778a1-174">및 C#:</span><span class="sxs-lookup"><span data-stu-id="778a1-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="778a1-175">**속성** 창의 **기타** 범주에서 **원본** 속성을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![속성 창의 원본 속성](./media/properties-source.png)

1. <span data-ttu-id="778a1-177">프로젝트에 다른 새 WPF 페이지를 추가 하 고 이름을 *expensereportpage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="778a1-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="778a1-178">**솔루션 탐색기** **`ExpenseIt`** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **페이지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="778a1-179">**새 항목 추가** 대화 상자에서 **페이지 (WPF)** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="778a1-180">**Expensereportpage.xaml**이름을 입력 한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="778a1-181">이 페이지에서는 **`ExpenseItHome`** 페이지에서 선택한 사용자에 대 한 경비 보고서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="778a1-182">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="778a1-183"><xref:System.Windows.Controls.Page.Title%2A> 을"`ExpenseIt - View Expense`"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="778a1-184">`DesignHeight` 및`DesignWidth` 요소 값을 300 픽셀로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-184">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="778a1-185">*Expensereportpage.xaml* 는 Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="778a1-186">그리고에서 C#다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="778a1-187">*Expenseithome.xaml* 및 *expensereportpage.xaml*, *ExpenseItHome.xaml.cs* 및 *ExpenseReportPage.xaml.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="778a1-188">새 페이지 파일을 만드는 경우 Visual Studio에서 자동으로 해당 *코드 숨김으로* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="778a1-189">이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="778a1-190">코드는 **`ExpenseItHome`** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="778a1-191">**Expensereportpage.xaml**에 대해 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="778a1-192">*워터 마크 .png* 라는 이미지를 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="778a1-193">사용자 고유의 이미지를 만들거나 샘플 코드에서 파일을 복사 하거나 [여기](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-193">You can create your own image, copy the file from the sample code, or get it [here](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png).</span></span>

    1. <span data-ttu-id="778a1-194">프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고**기존 항목** **추가** > 를 선택 하거나 **Shift**+**Alt**+**A**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="778a1-195">**기존 항목 추가** 대화 상자에서 파일 필터를 **모든 파일** 또는 **이미지 파일**로 설정 하 고 사용 하려는 이미지 파일을 찾은 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="778a1-196">응용 프로그램 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="778a1-196">Build and run the application</span></span>

1. <span data-ttu-id="778a1-197">응용 프로그램을 빌드하고 실행 하려면 **F5** 키를 누르거나 **디버그** 메뉴에서 **디버깅 시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="778a1-198">다음 그림에서는 <xref:System.Windows.Navigation.NavigationWindow> 단추가 있는 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![응용 프로그램을 빌드하고 실행 한 후](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="778a1-200">Visual Studio로 돌아가려면 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="778a1-201">레이아웃 만들기</span><span class="sxs-lookup"><span data-stu-id="778a1-201">Create the layout</span></span>

<span data-ttu-id="778a1-202">레이아웃은 UI 요소를 배치 하는 순서가 지정 된 방법을 제공 하며 UI 크기를 조정할 때 해당 요소의 크기와 위치도 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="778a1-203">일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="778a1-204"><xref:System.Windows.Controls.Canvas>-캔버스 영역에 상대적인 좌표를 사용 하 여 자식 요소의 위치를 명시적으로 지정할 수 있는 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="778a1-205"><xref:System.Windows.Controls.DockPanel>-자식 요소를 서로 상대적인 가로 또는 세로로 정렬할 수 있는 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="778a1-206"><xref:System.Windows.Controls.Grid>-열과 행으로 구성 되는 유연한 그리드 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="778a1-207"><xref:System.Windows.Controls.StackPanel>-가로 또는 세로 방향으로 사용할 수 있는 한 줄로 자식 요소를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="778a1-208"><xref:System.Windows.Controls.VirtualizingStackPanel>-가로 또는 세로 방향으로 한 줄로 콘텐츠를 정렬 하 고 가상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="778a1-209"><xref:System.Windows.Controls.WrapPanel>-콘텐츠를 포함 하는 상자의 가장자리에 있는 다음 줄로 줄 바꿈 하는 왼쪽에서 오른쪽으로 자식 요소를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="778a1-210">이후 정렬은 방향 속성의 값에 따라 위쪽에서 아래쪽으로 또는 오른쪽에서 왼쪽으로 순차적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="778a1-211">이러한 각 레이아웃 컨트롤은 자식 요소에 대해 특정 형식의 레이아웃을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="778a1-212">`ExpenseIt`페이지 크기를 조정할 수 있으며, 각 페이지에는 다른 요소와 함께 가로 및 세로 방향으로 정렬 되는 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="778a1-213">이 예제에서는 <xref:System.Windows.Controls.Grid> 응용 프로그램에 대 한 레이아웃 요소로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="778a1-214">요소에 대 한 <xref:System.Windows.Controls.Panel> 자세한 내용은 [패널 개요](../controls/panels-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="778a1-215">레이아웃에 대 한 자세한 내용은 [레이아웃](../advanced/layout.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="778a1-216">이 섹션에서는 <xref:System.Windows.Controls.Grid> 의 *`ExpenseItHome.xaml`* 에 열 및 행 정의를 추가 하 여 세 개의 행과 10 픽셀 여백으로 단일 열 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="778a1-217">에서 *`ExpenseItHome.xaml`* 요소의<xref:System.Windows.Controls.Grid> 속성을 <xref:System.Windows.FrameworkElement.Margin%2A> 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당 하는 "10, 0, 10, 10"으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="778a1-218">**속성** 창의 **레이아웃** 범주에서 **여백** 값을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![속성 창 여백 값](./media/properties-margin.png)

2. <span data-ttu-id="778a1-220"><xref:System.Windows.Controls.Grid> 태그 사이에 다음 XAML을 추가 하 여 행 및 열 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="778a1-221">두 <xref:System.Windows.Controls.RowDefinition.Height%2A> 행의는로 <xref:System.Windows.GridLength.Auto%2A>설정 됩니다. 즉, 행의 내용에 따라 행의 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="778a1-222">기본값 <xref:System.Windows.Controls.RowDefinition.Height%2A> 은 크기 <xref:System.Windows.GridUnitType.Star> 조정입니다. 즉, 행 높이가 사용 가능한 공간의 가중치가 적용 된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="778a1-223">예를 들어 각 <xref:System.Windows.Controls.RowDefinition.Height%2A> 행에 "\*"가 있는 경우 각각은 사용 가능한 공간의 절반 인 높이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="778a1-224">이제 <xref:System.Windows.Controls.Grid> 에 다음 XAML이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="778a1-225">컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="778a1-225">Add controls</span></span>

<span data-ttu-id="778a1-226">이 섹션에서는 홈 페이지 UI를 업데이트 하 여 경비 보고서를 표시 하는 사람을 선택할 수 있는 사람 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="778a1-227">컨트롤은 사용자가 애플리케이션과 상호 작용할 수 있게 하는 UI 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="778a1-228">자세한 내용은 [컨트롤](../controls/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="778a1-229">이 UI를 만들려면 다음 요소를에 *`ExpenseItHome.xaml`* 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="778a1-230"><xref:System.Windows.Controls.ListBox> 사용자의 목록에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="778a1-231"><xref:System.Windows.Controls.Label> 목록 헤더의입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="778a1-232"><xref:System.Windows.Controls.Button> 목록에서 선택한 사용자에 대 한 경비 보고서를 보려면 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="778a1-233">각 컨트롤은 연결 된 속성을 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 설정 하 여의 행에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="778a1-234">연결 된 속성에 대 한 자세한 내용은 [연결 된 속성 개요](../advanced/attached-properties-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="778a1-235">에서 *`ExpenseItHome.xaml`* 태그<xref:System.Windows.Controls.Grid> 사이에 다음 XAML을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="778a1-236">**도구 상자** 창에서 디자인 창으로 끌어 오고 **속성** 창에서 속성을 설정 하 여 컨트롤을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="778a1-237">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-237">Build and run the application.</span></span>

    <span data-ttu-id="778a1-238">다음 그림에서는 사용자가 만든 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-238">The following illustration shows the controls you created:</span></span>

![이름 목록을 표시 하는 ExpenseIt 샘플 스크린샷](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="778a1-240">이미지 및 제목 추가</span><span class="sxs-lookup"><span data-stu-id="778a1-240">Add an image and a title</span></span>

<span data-ttu-id="778a1-241">이 섹션에서는 이미지와 페이지 제목으로 홈 페이지 UI를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="778a1-242">에서 *`ExpenseItHome.xaml`* <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정 230<xref:System.Windows.Controls.ColumnDefinition.Width%2A> 픽셀을 사용 하 여에 다른 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="778a1-243">에 다른 행 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>을 추가 하 여 총 4 개 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="778a1-244">세 가지 컨트롤 (테두리, ListBox 및 단추) <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 각각의 속성을 1로 설정 하 여 컨트롤을 두 번째 열로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="778a1-245">3 개의 컨트롤 (테두리, ListBox 및 단추 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> )과 border 요소 각각에 대해 해당 값을 1 씩 증가 하 여 각 컨트롤을 한 행 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="778a1-246">이제 세 가지 컨트롤에 대 한 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="778a1-247">`<Grid>` 태그와 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> 태그`</Grid>` 사이에 다음 XAML을 추가 하 여 속성을 *워터 마크 .png* 이미지 파일로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="778a1-248">요소 앞에 "경비 보고서 <xref:System.Windows.Controls.Label> 보기" 내용이 포함 된를 추가 합니다. <xref:System.Windows.Controls.Border></span><span class="sxs-lookup"><span data-stu-id="778a1-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="778a1-249">이 레이블은 페이지의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="778a1-250">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-250">Build and run the application.</span></span>

<span data-ttu-id="778a1-251">다음 그림에서는 방금 추가한 항목의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-251">The following illustration shows the results of what you just added:</span></span>

![새 이미지 배경과 페이지 제목을 보여 주는 ExpenseIt 샘플 스크린샷](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="778a1-253">이벤트를 처리 하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="778a1-253">Add code to handle events</span></span>

1. <span data-ttu-id="778a1-254">에서 *`ExpenseItHome.xaml`* 요소<xref:System.Windows.Controls.Button> 에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="778a1-255">자세한 내용은 [방법: 간단한 이벤트 처리기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="778a1-256">*`ExpenseItHome.xaml.vb`* *또는`ExpenseItHome.xaml.cs`* 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="778a1-257">`ExpenseItHome` 클래스에 다음 코드를 추가 하 여 단추 클릭 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="778a1-258">이벤트 처리기가 **expensereportpage.xaml** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="778a1-259">Expensereportpage.xaml에 대 한 UI 만들기</span><span class="sxs-lookup"><span data-stu-id="778a1-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="778a1-260">*Expensereportpage.xaml* 는 **`ExpenseItHome`** 페이지에서 선택한 사용자에 대 한 경비 보고서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="778a1-261">이 섹션에서는 **expensereportpage.xaml**에 대 한 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="778a1-262">또한 다양 한 UI 요소에 배경 및 채우기 색을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="778a1-263">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="778a1-264"><xref:System.Windows.Controls.Grid> 태그 사이에 다음 XAML을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="778a1-265">이 UI는와 유사 *`ExpenseItHome.xaml`* <xref:System.Windows.Controls.DataGrid>합니다. 단, 보고서 데이터는에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="778a1-266">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-266">Build and run the application.</span></span>

4. <span data-ttu-id="778a1-267">**보기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-267">Select the **View** button.</span></span>

    <span data-ttu-id="778a1-268">경비 보고서 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-268">The expense report page appears.</span></span> <span data-ttu-id="778a1-269">또한 뒤로 탐색 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="778a1-270">다음 그림에서는 *expensereportpage.xaml*에 추가 된 UI 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Expensereportpage.xaml에 대해 만든 UI를 보여 주는 ExpenseIt 샘플 스크린샷](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="778a1-272">스타일 컨트롤</span><span class="sxs-lookup"><span data-stu-id="778a1-272">Style controls</span></span>

<span data-ttu-id="778a1-273">UI에서 같은 형식의 모든 요소에 대해 다양 한 요소의 모양이 동일 하 게 표시 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="778a1-274">UI는 [스타일](../controls/styling-and-templating.md) 을 사용 하 여 여러 요소에서 모양을 다시 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="778a1-275">스타일의 재사용은 XAML 생성 및 관리를 간소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="778a1-276">이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="778a1-277">*응용 프로그램 .xaml* 또는 app.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="778a1-278"><xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 태그 사이에 다음 XAML을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="778a1-279">이 XAML은 다음 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="778a1-280">`headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>에 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="778a1-281">`labelStyle`: 컨트롤의 <xref:System.Windows.Controls.Label> 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="778a1-282">`columnHeaderStyle`: 의 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="778a1-283">`listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="778a1-284">`listHeaderTextStyle`: 목록 헤더 <xref:System.Windows.Controls.Label>의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="778a1-285">`buttonStyle`: 의 형식을 지정 <xref:System.Windows.Controls.Button> `ExpenseItHome.xaml`하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="778a1-286">스타일은 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소의 리소스 및 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="778a1-287">이 위치에서 스타일은 애플리케이션의 모든 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="778a1-288">.NET 앱에서 리소스를 사용 하는 방법에 대 한 예제는 [응용 프로그램 리소스 사용](../advanced/how-to-use-application-resources.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="778a1-289">에서 *`ExpenseItHome.xaml`* 요소<xref:System.Windows.Controls.Grid> 사이에 있는 모든 항목을 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="778a1-290">스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="778a1-291">예를 들어는 `headerTextStyle` "경비 보고서 보기" <xref:System.Windows.Controls.Label>에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="778a1-292">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="778a1-293"><xref:System.Windows.Controls.Grid> 요소 사이에 있는 모든 항목을 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="778a1-294">이 XAML은 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="778a1-295">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-295">Build and run the application.</span></span> <span data-ttu-id="778a1-296">창 모양은 이전과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-296">The window appearance is the same as previously.</span></span>

    ![마지막 섹션과 동일한 모양의 샘플 스크린샷 ExpenseIt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="778a1-298">Visual Studio로 돌아가려면 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="778a1-299">컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="778a1-299">Bind data to a control</span></span>

<span data-ttu-id="778a1-300">이 섹션에서는 다양 한 컨트롤에 바인딩되는 XML 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="778a1-301">에서 *`ExpenseItHome.xaml`* <xref:System.Windows.Data.XmlDataProvider> 열린 <xref:System.Windows.Controls.Grid> 요소 뒤에 다음 XAML을 추가 하 여 각 사용자에 대 한 데이터를 포함 하는를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="778a1-302">데이터는 <xref:System.Windows.Controls.Grid> 리소스로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="778a1-303">일반적으로이 데이터는 파일로 로드 되지만 편의상 데이터가 인라인으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="778a1-304">요소 내 <xref:System.Windows.Controls.ListBox>에서 요소`<XmlDataProvider>` 뒤에 데이터 `<xref:System.Windows.DataTemplate>` 를 표시 하는 방법을 정의 하는 다음 요소를 추가 합니다. `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="778a1-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="778a1-305">데이터 템플릿에 대 한 자세한 내용은 [데이터 템플릿 개요](../data/data-templating-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="778a1-306">기존 <xref:System.Windows.Controls.ListBox> 를 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="778a1-307">이 XAML은 <xref:System.Windows.Controls.ListBox> 의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 데이터 소스에 바인딩하고 데이터 템플릿을로 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="778a1-308">컨트롤에 데이터 연결</span><span class="sxs-lookup"><span data-stu-id="778a1-308">Connect data to controls</span></span>

<span data-ttu-id="778a1-309">다음으로는 **`ExpenseItHome`** 페이지에서 선택한 이름을 검색 하 고 **expensereportpage.xaml**의 생성자에 전달 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="778a1-310">**Expensereportpage.xaml** 는 *expensereportpage.xaml* 에 정의 된 컨트롤이 바인딩되는 전달 된 항목으로 데이터 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="778a1-311">*ExpenseReportPage.xaml.vb* 또는 *ExpenseReportPage.xaml.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="778a1-312">선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="778a1-313">*`ExpenseItHome.xaml.vb`* *또는`ExpenseItHome.xaml.cs`* 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="778a1-314">선택한 사람의 비용 보고서 데이터를 전달 하는 새 생성자를 호출 하도록 이벤트처리기를변경합니다.<xref:System.Windows.Controls.Primitives.ButtonBase.Click></span><span class="sxs-lookup"><span data-stu-id="778a1-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="778a1-315">데이터 템플릿을 사용 하 여 데이터 스타일</span><span class="sxs-lookup"><span data-stu-id="778a1-315">Style data with data templates</span></span>

<span data-ttu-id="778a1-316">이 섹션에서는 데이터 템플릿을 사용 하 여 데이터 바인딩된 목록의 각 항목에 대 한 UI를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="778a1-317">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="778a1-318">"Name" 및 "학과" <xref:System.Windows.Controls.Label> 요소의 내용을 적절 한 데이터 원본 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="778a1-319">데이터 바인딩에 대 한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="778a1-320"><xref:System.Windows.Controls.Grid> 시작 요소 뒤에 경비 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="778a1-321">요소를 요소<xref:System.Windows.Controls.DataGrid> 아래의 <xref:System.Windows.Controls.DataGridTemplateColumn> 로 바꾸고 템플릿을 적용 합니다. <xref:System.Windows.Controls.DataGridTextColumn></span><span class="sxs-lookup"><span data-stu-id="778a1-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="778a1-322">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-322">Build and run the application.</span></span>

6. <span data-ttu-id="778a1-323">사용자를 선택한 다음 **보기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="778a1-324">다음 그림에서는 컨트롤, 레이아웃, 스타일 `ExpenseIt` , 데이터 바인딩 및 데이터 템플릿이 적용 된 응용 프로그램의 두 페이지를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![응용 프로그램의 두 페이지 모두 이름 목록과 경비 보고서를 표시 합니다.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="778a1-326">이 샘플은 WPF의 특정 기능을 보여 주며 보안, 지역화 및 접근성과 같은 항목에 대 한 모든 모범 사례를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="778a1-327">WPF 및 .NET 앱 개발 모범 사례에 대 한 포괄적인 적용 범위는 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="778a1-328">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="778a1-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="778a1-329">보안</span><span class="sxs-lookup"><span data-stu-id="778a1-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="778a1-330">WPF 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="778a1-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="778a1-331">WPF 성능</span><span class="sxs-lookup"><span data-stu-id="778a1-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="778a1-332">다음 단계</span><span class="sxs-lookup"><span data-stu-id="778a1-332">Next steps</span></span>

<span data-ttu-id="778a1-333">이 연습에서는 Windows Presentation Foundation (WPF)를 사용 하 여 UI를 만들기 위한 다양 한 기술을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="778a1-334">이제 데이터 바인딩된 .NET 앱의 구성 요소를 기본적으로 이해 하 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a1-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="778a1-335">WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="778a1-336">WPF 아키텍처</span><span class="sxs-lookup"><span data-stu-id="778a1-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="778a1-337">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="778a1-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="778a1-338">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="778a1-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="778a1-339">레이아웃</span><span class="sxs-lookup"><span data-stu-id="778a1-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="778a1-340">애플리케이션을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="778a1-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="778a1-341">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="778a1-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="778a1-342">컨트롤</span><span class="sxs-lookup"><span data-stu-id="778a1-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="778a1-343">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="778a1-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="778a1-344">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="778a1-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="778a1-345">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="778a1-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="778a1-346">참고 항목</span><span class="sxs-lookup"><span data-stu-id="778a1-346">See also</span></span>

- [<span data-ttu-id="778a1-347">패널 개요</span><span class="sxs-lookup"><span data-stu-id="778a1-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="778a1-348">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="778a1-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="778a1-349">WPF 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="778a1-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="778a1-350">스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="778a1-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
