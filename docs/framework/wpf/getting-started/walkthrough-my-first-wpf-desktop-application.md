---
title: 비주얼 스튜디오 2019에서 첫 번째 WPF 응용 프로그램을 만들기 - .NET 프레임 워크
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 9381873faa8cca1accf95d823f5183a218d28813
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646425"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="f05c7-102">자습서: Visual Studio 2019에서 첫 번째 WPF 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f05c7-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="f05c7-103">이 문서에서는 대부분의 WPF 응용 프로그램에 공통적인 요소인 확장 가능한 응용 프로그램 태그 언어(XAML) 태그, 코드 숨김, 응용 프로그램 정의, 컨트롤, 레이아웃, 데이터 바인딩 및 스타일과 같은 요소를 포함하는 WPF(Windows 프레젠테이션 Foundation) 데스크톱 응용 프로그램을 개발하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="f05c7-104">응용 프로그램을 개발하려면 Visual Studio를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="f05c7-105">이 자습서에서는 다음 작업 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f05c7-106">WPF 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-106">Create a WPF project.</span></span>
> - <span data-ttu-id="f05c7-107">XAML을 사용하여 응용 프로그램의 사용자 인터페이스(UI)의 모양을 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="f05c7-108">코드를 작성하여 응용 프로그램의 동작을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="f05c7-109">응용 프로그램을 관리하는 응용 프로그램 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="f05c7-110">컨트롤을 추가하고 레이아웃을 만들어 응용 프로그램 UI를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="f05c7-111">응용 프로그램의 UI 전체에서 일관된 모양을 위한 스타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="f05c7-112">UI를 데이터에 바인딩하여 데이터에서 UI를 채우고 데이터와 UI를 동기화된 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="f05c7-113">자습서가 끝나면 사용자가 선택한 사용자에 대한 비용 보고서를 볼 수 있는 독립 실행형 Windows 응용 프로그램을 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="f05c7-114">응용 프로그램은 브라우저 스타일 창에서 호스팅되는 여러 WPF 페이지로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="f05c7-115">이 자습서에서 사용되는 샘플 코드는 [자습서 WPF 앱 샘플 코드에서](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)시각적 기본 및 C#에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="f05c7-116">이 페이지 위에 있는 언어 선택기를 사용하여 샘플 코드의 코드 언어를 C#과 Visual Basic 간에 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f05c7-117">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f05c7-117">Prerequisites</span></span>

- <span data-ttu-id="f05c7-118">**.NET 데스크톱 개발** 워크로드가 설치된 [Visual Studio 2019입니다.](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="f05c7-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="f05c7-119">최신 버전의 Visual Studio 설치에 대한 자세한 내용은 [Visual Studio 설치를](/visualstudio/install/install-visual-studio)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="f05c7-120">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="f05c7-120">Create the application project</span></span>

<span data-ttu-id="f05c7-121">첫 번째 단계는 응용 프로그램 정의, 두 페이지 및 이미지를 포함하는 응용 프로그램 인프라를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="f05c7-122">시각적 기본 또는 시각적 C #라는 이름의 **`ExpenseIt`** 새 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="f05c7-123">비주얼 스튜디오를 열고 **시작** 메뉴에서 **새 프로젝트 만들기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="f05c7-124">**새 프로젝트 만들기** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="f05c7-125">**언어** 드롭다운에서 **C#** 또는 **시각적 기본**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="f05c7-126">**WPF 앱(.NET 프레임워크)** 템플릿을 선택한 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![새 프로젝트 만들기 대화 상자](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="f05c7-128">**새 프로젝트 구성** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="f05c7-129">프로젝트 이름을 **`ExpenseIt`** 입력한 다음 **만들기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![새 프로젝트 대화 상자 구성](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="f05c7-131">Visual Studio에서 프로젝트를 만들고 **MainWindow.xaml**이라는 기본 응용 프로그램 창에 대 한 디자이너를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="f05c7-132">*응용 프로그램.xaml* (시각적 기본) 또는 *App.xaml* (C #)를 엽니 다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="f05c7-133">이 XAML 파일은 WPF 응용 프로그램 및 모든 응용 프로그램 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="f05c7-134">또한 이 파일을 사용하여 응용 프로그램이 시작될 때 자동으로 표시되는 이 경우 *MainWindow.xaml을*지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="f05c7-135">XAML은 시각적 기본에서 다음과 같이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="f05c7-136">그리고 C #의 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="f05c7-137">*오픈 메인윈도우.xaml*.</span><span class="sxs-lookup"><span data-stu-id="f05c7-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="f05c7-138">이 XAML 파일은 응용 프로그램의 기본 창이며 페이지에서 만든 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="f05c7-139">클래스는 <xref:System.Windows.Window> 제목, 크기 또는 아이콘과 같은 창의 속성을 정의하고 닫거나 숨기는 등의 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="f05c7-140">다음 <xref:System.Windows.Window> XAML에 표시된 대로 요소를 <xref:System.Windows.Navigation.NavigationWindow>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="f05c7-141">이 응용 프로그램은 사용자 입력에 따라 다른 콘텐츠로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="f05c7-142">이것이 주 <xref:System.Windows.Window> 를 로 변경해야 <xref:System.Windows.Navigation.NavigationWindow>하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="f05c7-143"><xref:System.Windows.Navigation.NavigationWindow>의 <xref:System.Windows.Window>모든 속성을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="f05c7-144">XAML 파일의 <xref:System.Windows.Navigation.NavigationWindow> 요소는 클래스의 인스턴스를 <xref:System.Windows.Navigation.NavigationWindow> 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="f05c7-145">자세한 내용은 [탐색 개요를](../app-development/navigation-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="f05c7-146"><xref:System.Windows.Navigation.NavigationWindow> 태그 사이에서 <xref:System.Windows.Controls.Grid> 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="f05c7-147">요소에 대한 XAML 코드의 다음 <xref:System.Windows.Navigation.NavigationWindow> 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="f05c7-148"><xref:System.Windows.Window.Title%2A> 속성을 "로`ExpenseIt`설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="f05c7-149"><xref:System.Windows.FrameworkElement.Height%2A> 속성을 350픽셀로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="f05c7-150"><xref:System.Windows.FrameworkElement.Width%2A> 속성을 500픽셀로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="f05c7-151">XAML은 시각적 기본에 대해 다음과 같이 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="f05c7-152">그리고 C #에 대한 다음처럼 :</span><span class="sxs-lookup"><span data-stu-id="f05c7-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="f05c7-153">*메인윈도우.xaml.vb* 또는 *MainWindow.xaml.cs.*</span><span class="sxs-lookup"><span data-stu-id="f05c7-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="f05c7-154">이 파일은 *MainWindow.xaml*에서 선언 된 이벤트를 처리하는 코드를 포함하는 코드 숨은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="f05c7-155">이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="f05c7-156">C#을 사용하는 경우 `MainWindow` 에서 파생되는 클래스를 변경합니다. <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="f05c7-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="f05c7-157">시각적 기본에서 XAML에서 창을 변경할 때 자동으로 발생 합니다. 이제 C# 코드는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="f05c7-158">응용 프로그램에 파일 추가</span><span class="sxs-lookup"><span data-stu-id="f05c7-158">Add files to the application</span></span>

<span data-ttu-id="f05c7-159">이 섹션에서는 애플리케이션에 두 페이지와 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="f05c7-160">프로젝트에 새 페이지를 추가하고 이름을 지정합니다. *`ExpenseItHome.xaml`*</span><span class="sxs-lookup"><span data-stu-id="f05c7-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="f05c7-161">**솔루션 탐색기에서**프로젝트 노드를 **`ExpenseIt`** 마우스 오른쪽 단추로 클릭하고**페이지** **추가를** > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="f05c7-162">새 **항목 추가** 대화 상자에서 **페이지(WPF)** 템플릿이 이미 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="f05c7-163">이름을 **`ExpenseItHome`** 입력한 다음 **에 추가를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="f05c7-164">이 페이지는 응용 프로그램을 시작할 때 표시되는 첫 번째 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="f05c7-165">비용 보고서를 표시하기 위해 선택할 수 있는 사용자 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="f05c7-166">을 *`ExpenseItHome.xaml`* 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="f05c7-167"><xref:System.Windows.Controls.Page.Title%2A> "를`ExpenseIt - Home`"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="f05c7-168">`DesignHeight` 350픽셀과 `DesignWidth` 500픽셀로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="f05c7-169">이제 XAML이 시각적 기본에 대해 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="f05c7-170">그리고 C #에 대한 다음처럼 :</span><span class="sxs-lookup"><span data-stu-id="f05c7-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="f05c7-171">*오픈 메인윈도우.xaml*.</span><span class="sxs-lookup"><span data-stu-id="f05c7-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="f05c7-172">요소에 속성을 추가하고 ""로`ExpenseItHome.xaml`설정합니다. <xref:System.Windows.Navigation.NavigationWindow.Source%2A> <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="f05c7-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="f05c7-173">이 *`ExpenseItHome.xaml`* 설정은 응용 프로그램이 시작될 때 열리는 첫 번째 페이지로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="f05c7-174">시각적 기본의 예제 XAML:</span><span class="sxs-lookup"><span data-stu-id="f05c7-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="f05c7-175">그리고 C #에서 :</span><span class="sxs-lookup"><span data-stu-id="f05c7-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="f05c7-176">속성 **창의** **기타** 범주에서 **소스** 속성을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![속성 창의 소스 속성](./media/properties-source.png)

1. <span data-ttu-id="f05c7-178">프로젝트에 다른 새 WPF 페이지를 추가하고 *ExpenseReportPage.xaml의*이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="f05c7-179">**솔루션 탐색기에서**프로젝트 노드를 **`ExpenseIt`** 마우스 오른쪽 단추로 클릭하고**페이지** **추가를** > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="f05c7-180">새 **항목 추가** 대화 상자에서 **페이지(WPF)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="f05c7-181">**비용 보고서 페이지**라는 이름을 입력한 다음 에 **추가를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="f05c7-182">이 페이지에는 **`ExpenseItHome`** 페이지에서 선택한 사람의 지출 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="f05c7-183">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="f05c7-184"><xref:System.Windows.Controls.Page.Title%2A> "를`ExpenseIt - View Expense`"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="f05c7-185">`DesignHeight` 350픽셀과 `DesignWidth` 500픽셀로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="f05c7-186">*이제 지출 보고서Page.xaml은* 시각적 기본에서 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="f05c7-187">그리고 C #의 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="f05c7-188">오픈 *ExpenseItHome.xaml.vb* 및 *비용 보고서Page.xaml.vb,* 또는 *ExpenseItHome.xaml.cs* *및 ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="f05c7-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="f05c7-189">새 페이지 파일을 만들 면 Visual Studio에서 *자동으로 코드 숨 파일이* 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="f05c7-190">이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="f05c7-191">코드는 **`ExpenseItHome`** 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="f05c7-192">그리고 **비용 보고서 페이지에**대한 다음과 같은 :</span><span class="sxs-lookup"><span data-stu-id="f05c7-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="f05c7-193">프로젝트에 *watermark.png라는* 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="f05c7-194">사용자 고유의 이미지를 만들거나 샘플 코드에서 파일을 복사하거나 [microsoft/WPF-샘플](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub 리포지토리에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="f05c7-195">프로젝트 노드를 마우스 오른쪽 단추로 클릭하고**기존 항목** **추가를** > 선택하거나 **Shift**+**Alt**+**A를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="f05c7-196">기존 **항목 추가** 대화 상자에서 파일 필터를 **모든 파일** 또는 **이미지 파일로**설정하고 사용할 이미지 파일로 찾아이동한 다음 **추가를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="f05c7-197">애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="f05c7-197">Build and run the application</span></span>

1. <span data-ttu-id="f05c7-198">응용 프로그램을 빌드하고 실행하려면 **F5를** 누르거나 **디버그** 메뉴에서 **디버깅 시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="f05c7-199">다음 그림에서는 <xref:System.Windows.Navigation.NavigationWindow> 단추를 가진 응용 프로그램을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![빌드하고 실행한 후 응용 프로그램.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="f05c7-201">응용 프로그램을 닫아 Visual Studio로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="f05c7-202">레이아웃 만들기</span><span class="sxs-lookup"><span data-stu-id="f05c7-202">Create the layout</span></span>

<span data-ttu-id="f05c7-203">레이아웃은 UI 요소를 배치하는 순서가 정해된 방법을 제공하며 UI의 크기를 조정할 때 해당 요소의 크기와 위치도 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="f05c7-204">일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="f05c7-205"><xref:System.Windows.Controls.Canvas>- 캔버스 영역을 기준으로 한 좌표를 사용하여 자식 요소를 명시적으로 배치할 수 있는 영역을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="f05c7-206"><xref:System.Windows.Controls.DockPanel>- 서로 에 대해 가로 또는 세로로 자식 요소를 정렬 할 수있는 영역을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="f05c7-207"><xref:System.Windows.Controls.Grid>- 열과 행으로 구성된 유연한 그리드 영역을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="f05c7-208"><xref:System.Windows.Controls.StackPanel>- 자식 요소를 가로 또는 세로로 향할 수 있는 한 줄로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="f05c7-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- 수평 또는 수직 방향의 한 줄에 콘텐츠를 정렬하고 가상화합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="f05c7-210"><xref:System.Windows.Controls.WrapPanel>- 하위 요소를 왼쪽에서 오른쪽으로 순차적으로 배치하여 포함된 상자의 가장자리에 있는 다음 줄로 콘텐츠를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="f05c7-211">후속 순서는 방향 속성의 값에 따라 위에서 아래로 또는 오른쪽에서 왼쪽으로 순차적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="f05c7-212">이러한 각 레이아웃 컨트롤은 자식 요소에 대한 특정 유형의 레이아웃을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="f05c7-213">`ExpenseIt`페이지의 크기를 조정할 수 있으며 각 페이지에는 다른 요소와 함께 가로 및 세로로 정렬된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="f05c7-214">이 예제에서는 <xref:System.Windows.Controls.Grid> 응용 프로그램의 레이아웃 요소로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="f05c7-215">요소에 대한 <xref:System.Windows.Controls.Panel> 자세한 내용은 [패널 개요를](../controls/panels-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="f05c7-216">레이아웃에 대한 자세한 내용은 [레이아웃](../advanced/layout.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="f05c7-217">이 섹션에서는 <xref:System.Windows.Controls.Grid> 에서 *`ExpenseItHome.xaml`* 열 및 행 정의를 추가하여 세 개의 행과 10픽셀 여백이 있는 단일 열 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="f05c7-218">에서 *`ExpenseItHome.xaml`* 요소의 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Grid> 속성을 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당하는 "10,0,10,10"으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="f05c7-219">**레이아웃** 범주에서 **속성** 창에서 **여백** 값을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![속성 창의 여백 값](./media/properties-margin.png)

2. <span data-ttu-id="f05c7-221">태그 사이에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가하여 행 및 열 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="f05c7-222">두 <xref:System.Windows.Controls.RowDefinition.Height%2A> 행 중 의 <xref:System.Windows.GridLength.Auto%2A>집합은 행의 내용에 따라 행의 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="f05c7-223"><xref:System.Windows.Controls.RowDefinition.Height%2A> 기본값은 <xref:System.Windows.GridUnitType.Star> 크기 조정이며, 이는 행 높이가 사용 가능한 공간의 가중치 비율임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="f05c7-224">예를 들어 두 행에 <xref:System.Windows.Controls.RowDefinition.Height%2A> 각각 "\*"가 있는 경우 각각 사용 가능한 공간의 절반인 높이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="f05c7-225">이제 <xref:System.Windows.Controls.Grid> 다음 XAML이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="f05c7-226">컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="f05c7-226">Add controls</span></span>

<span data-ttu-id="f05c7-227">이 섹션에서는 홈 페이지 UI를 업데이트하여 지출 보고서를 표시할 사람을 한 사람을 선택하는 사람 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="f05c7-228">컨트롤은 사용자가 애플리케이션과 상호 작용할 수 있게 하는 UI 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="f05c7-229">자세한 내용은 [컨트롤](../controls/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="f05c7-230">이 UI를 만들려면 다음 요소를 추가합니다. *`ExpenseItHome.xaml`*</span><span class="sxs-lookup"><span data-stu-id="f05c7-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="f05c7-231">A(사람 <xref:System.Windows.Controls.ListBox> 목록)입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="f05c7-232">A(목록 <xref:System.Windows.Controls.Label> 헤더용)입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="f05c7-233">A(목록에서 <xref:System.Windows.Controls.Button> 선택한 사람의 지출 보고서를 보려면 클릭합니다).</span><span class="sxs-lookup"><span data-stu-id="f05c7-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="f05c7-234">각 컨트롤은 연결된 속성을 <xref:System.Windows.Controls.Grid> 설정하여 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 의 행에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="f05c7-235">연결된 속성에 대한 자세한 내용은 [연결된 속성 개요를](../advanced/attached-properties-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="f05c7-236">에서 *`ExpenseItHome.xaml`* 태그 사이의 어딘가에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="f05c7-237">**도구 상자** 창에서 디자인 창으로 드래그한 다음 **속성** 창에서 해당 속성을 설정하여 컨트롤을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="f05c7-238">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-238">Build and run the application.</span></span>

    <span data-ttu-id="f05c7-239">다음 그림에서는 만든 컨트롤을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f05c7-239">The following illustration shows the controls you created:</span></span>

![비용그것은 이름 목록을 표시하는 샘플 스크린 샷](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="f05c7-241">이미지 및 제목 추가</span><span class="sxs-lookup"><span data-stu-id="f05c7-241">Add an image and a title</span></span>

<span data-ttu-id="f05c7-242">이 섹션에서는 이미지와 페이지 제목으로 홈 페이지 UI를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="f05c7-243">에서 *`ExpenseItHome.xaml`* 230픽셀로 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정된 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 다른 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="f05c7-244"><xref:System.Windows.Controls.Grid.RowDefinitions%2A>에 다른 행을 추가하여 총 4개의 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="f05c7-245">세 가지 컨트롤(테두리, ListBox 및 단추)에서 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성을 1로 설정하여 컨트롤을 두 번째 열로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="f05c7-246">세 컨트롤(테두리, ListBox 및 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> Button) 및 테두리 요소에 대해 각 컨트롤의 값을 1씩 증가시켜 각 컨트롤을 행 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="f05c7-247">이제 세 컨트롤에 대한 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="f05c7-248">다음 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> XAML을 태그와 `</Grid>` 태그 사이에 추가하여 다음 XAML을 `<Grid>` 추가하여 *filemark.png* 이미지 파일로 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="f05c7-249">요소 <xref:System.Windows.Controls.Border> 앞에 "비용 <xref:System.Windows.Controls.Label> 보고서 보기"라는 내용과 함께 a를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="f05c7-250">이 레이블은 페이지의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="f05c7-251">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-251">Build and run the application.</span></span>

<span data-ttu-id="f05c7-252">다음 그림에서는 방금 추가한 내용의 결과를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f05c7-252">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt 샘플 스크린샷으로 새 이미지 배경 및 페이지 제목 표시](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="f05c7-254">이벤트를 처리하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="f05c7-254">Add code to handle events</span></span>

1. <span data-ttu-id="f05c7-255">에서 *`ExpenseItHome.xaml`* 요소에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 추가합니다. <xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="f05c7-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="f05c7-256">자세한 내용은 [방법: 간단한 이벤트 처리기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="f05c7-257">열기 *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* 또는 .</span><span class="sxs-lookup"><span data-stu-id="f05c7-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="f05c7-258">`ExpenseItHome` 클래스에 다음 코드를 추가하여 단추 클릭 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="f05c7-259">이벤트 처리기가 **비용 보고서 페이지** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="f05c7-260">비용 보고서 페이지에 대한 UI 만들기</span><span class="sxs-lookup"><span data-stu-id="f05c7-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="f05c7-261">*비용 보고서Page.xaml* **`ExpenseItHome`** 페이지에서 선택한 사람에 대 한 비용 보고서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="f05c7-262">이 섹션에서는 **비용 보고서 페이지에**대한 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="f05c7-263">또한 다양한 UI 요소에 배경 및 채우기 색상을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="f05c7-264">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="f05c7-265">태그 사이에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="f05c7-266">이 UI는 *`ExpenseItHome.xaml`* 에 표시된 보고서 데이터를 제외하면 와 <xref:System.Windows.Controls.DataGrid>유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="f05c7-267">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-267">Build and run the application.</span></span>

4. <span data-ttu-id="f05c7-268">보기 단추를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-268">Select the **View** button.</span></span>

    <span data-ttu-id="f05c7-269">경비 보고서 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-269">The expense report page appears.</span></span> <span data-ttu-id="f05c7-270">또한 뒤로 탐색 버튼이 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="f05c7-271">다음 그림에서는 *ExpenseReportPage.xaml에*추가된 UI 요소를 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt 방금 비용 보고서 페이지에 대해 만든 UI를 보여주는 샘플 스크린샷입니다.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="f05c7-273">스타일 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f05c7-273">Style controls</span></span>

<span data-ttu-id="f05c7-274">다양한 요소의 모양은 UI에서 동일한 형식의 모든 요소에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="f05c7-275">UI는 [스타일을](../../../desktop-wpf/fundamentals/styles-templates-overview.md) 사용하여 여러 요소에서 모양을 재사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-275">UI uses [styles](../../../desktop-wpf/fundamentals/styles-templates-overview.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="f05c7-276">스타일 재사용성은 XAML 생성 및 관리를 단순화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="f05c7-277">이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="f05c7-278">*응용 프로그램.xaml* 또는 *App.xaml을*엽니 다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="f05c7-279">태그 사이에 다음 XAML을 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="f05c7-280">이 XAML은 다음 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="f05c7-281">`headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="f05c7-282">`labelStyle`: <xref:System.Windows.Controls.Label> 컨트롤의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="f05c7-283">`columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="f05c7-284">`listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="f05c7-285">`listHeaderTextStyle`: 목록 헤더의 <xref:System.Windows.Controls.Label>서식을 지정하려면 .</span><span class="sxs-lookup"><span data-stu-id="f05c7-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="f05c7-286">`buttonStyle`: 에 `ExpenseItHome.xaml` <xref:System.Windows.Controls.Button> 서식을 지정하려면 .</span><span class="sxs-lookup"><span data-stu-id="f05c7-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="f05c7-287">스타일은 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소의 리소스 및 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="f05c7-288">이 위치에서 스타일은 애플리케이션의 모든 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="f05c7-289">.NET 앱에서 리소스를 사용하는 예는 [응용 프로그램 리소스 사용을](../advanced/how-to-use-application-resources.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="f05c7-290">에서 *`ExpenseItHome.xaml`* <xref:System.Windows.Controls.Grid> 요소 간의 모든 것을 다음 XAML로 바꿉꿉입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="f05c7-291">스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="f05c7-292">예를 들어"비용 `headerTextStyle` 보고서 보기"에 <xref:System.Windows.Controls.Label>적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="f05c7-293">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="f05c7-294"><xref:System.Windows.Controls.Grid> 요소 간의 모든 것을 다음 XAML로 바꿉꿉입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="f05c7-295">이 XAML은 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="f05c7-296">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-296">Build and run the application.</span></span> <span data-ttu-id="f05c7-297">창 모양은 이전과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-297">The window appearance is the same as previously.</span></span>

    ![ExpenseIt 샘플 스크린샷은 마지막 섹션과 동일한 모양을 가지고 있습니다.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="f05c7-299">응용 프로그램을 닫아 Visual Studio로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="f05c7-300">데이터를 컨트롤에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-300">Bind data to a control</span></span>

<span data-ttu-id="f05c7-301">이 섹션에서는 다양한 컨트롤에 바인딩된 XML 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="f05c7-302">에서 *`ExpenseItHome.xaml`* 열기 <xref:System.Windows.Controls.Grid> 요소 후 다음 XAML을 추가하여 <xref:System.Windows.Data.XmlDataProvider> 각 사용자의 데이터를 포함하는 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="f05c7-303">데이터는 리소스로 <xref:System.Windows.Controls.Grid> 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="f05c7-304">일반적으로 이 데이터는 파일로 로드되지만 간단히 하기 위해 데이터가 인라인으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="f05c7-305">`<Grid.Resources>` 요소 내에서 다음 `<xref:System.Windows.DataTemplate>` 요소를 추가하여 요소 다음에 데이터를 <xref:System.Windows.Controls.ListBox>표시하는 방법을 정의합니다. `<XmlDataProvider>`</span><span class="sxs-lookup"><span data-stu-id="f05c7-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="f05c7-306">데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요를](../data/data-templating-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="f05c7-307">기존 <xref:System.Windows.Controls.ListBox> XAML을 다음 XAML로 바꿉꿉입니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="f05c7-308">이 XAML은 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 <xref:System.Windows.Controls.ListBox> 데이터 원본에 바인딩하고 데이터 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>템플릿을 으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="f05c7-309">데이터를 컨트롤에 연결</span><span class="sxs-lookup"><span data-stu-id="f05c7-309">Connect data to controls</span></span>

<span data-ttu-id="f05c7-310">다음으로 페이지에서 선택한 **`ExpenseItHome`** 이름을 검색하고 **ExpenseReportPage의**생성자에게 전달하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="f05c7-311">**ExpenseReportPage는** *ExpenseReportPage.xaml에* 바인딩하는 컨트롤인 전달된 항목으로 데이터 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="f05c7-312">비용 *보고서 열기페이지.xaml.vb* 또는 *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="f05c7-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="f05c7-313">선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="f05c7-314">열기 *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* 또는 .</span><span class="sxs-lookup"><span data-stu-id="f05c7-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="f05c7-315"><xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 변경하여 선택한 사람의 비용 보고서 데이터를 전달하는 새 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="f05c7-316">데이터 템플릿으로 데이터 스타일</span><span class="sxs-lookup"><span data-stu-id="f05c7-316">Style data with data templates</span></span>

<span data-ttu-id="f05c7-317">이 섹션에서는 데이터 템플릿을 사용하여 데이터 바인딩 된 목록의 각 항목에 대한 UI를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="f05c7-318">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="f05c7-319">"이름" 및 "Department" <xref:System.Windows.Controls.Label> 요소의 내용을 적절한 데이터 원본 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="f05c7-320">데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="f05c7-321">열기 <xref:System.Windows.Controls.Grid> 요소 후 비용 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="f05c7-322"><xref:System.Windows.Controls.DataGridTextColumn> 요소를 <xref:System.Windows.Controls.DataGrid> 요소 아래에 있는 요소로 <xref:System.Windows.Controls.DataGridTemplateColumn> 바꾸고 템플릿을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="f05c7-323">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-323">Build and run the application.</span></span>

6. <span data-ttu-id="f05c7-324">사람을 선택한 다음 **보기** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="f05c7-325">다음 그림에서는 컨트롤, `ExpenseIt` 레이아웃, 스타일, 데이터 바인딩 및 데이터 템플릿이 적용된 응용 프로그램의 두 페이지를 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![이름 목록과 비용 보고서를 표시하는 앱의 두 페이지.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="f05c7-327">이 샘플에서는 WPF의 특정 기능을 보여 주며 보안, 지역화 및 접근성과 같은 모든 모범 사례를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="f05c7-328">WPF 및 .NET 앱 개발 모범 사례에 대한 포괄적인 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05c7-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="f05c7-329">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="f05c7-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="f05c7-330">보안</span><span class="sxs-lookup"><span data-stu-id="f05c7-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="f05c7-331">WPF 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="f05c7-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="f05c7-332">WPF 성능</span><span class="sxs-lookup"><span data-stu-id="f05c7-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="f05c7-333">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f05c7-333">Next steps</span></span>

<span data-ttu-id="f05c7-334">이 연습에서는 WPF(Windows 프레젠테이션 파운데이션)를 사용하여 UI를 만드는 여러 가지 기술을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="f05c7-335">이제 데이터 바인딩 .NET 앱의 구성 요소를 기본적으로 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05c7-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="f05c7-336">WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f05c7-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="f05c7-337">WPF 아키텍처</span><span class="sxs-lookup"><span data-stu-id="f05c7-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="f05c7-338">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="f05c7-338">XAML overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="f05c7-339">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="f05c7-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="f05c7-340">레이아웃</span><span class="sxs-lookup"><span data-stu-id="f05c7-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="f05c7-341">애플리케이션을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f05c7-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="f05c7-342">애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="f05c7-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="f05c7-343">컨트롤</span><span class="sxs-lookup"><span data-stu-id="f05c7-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="f05c7-344">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="f05c7-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="f05c7-345">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="f05c7-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="f05c7-346">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="f05c7-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="f05c7-347">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f05c7-347">See also</span></span>

- [<span data-ttu-id="f05c7-348">패널 개요</span><span class="sxs-lookup"><span data-stu-id="f05c7-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="f05c7-349">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="f05c7-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="f05c7-350">WPF 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="f05c7-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="f05c7-351">스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="f05c7-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
