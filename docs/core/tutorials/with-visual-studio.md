---
title: Visual Studio에서 .NET Core를 사용하여 Hello World 애플리케이션 만들기
description: Visual Studio에서 C# 또는 Visual Basic을 사용하여 첫 번째 .NET Core 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 738fc49a820c3c5d94fb35c1bf7a8b718ed75cb3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394822"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="402fd-103">자습서: Visual Studio 2019에서 첫 번째 .NET Core 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="402fd-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="402fd-104">이 문서에서는 Visual Studio 2019에서 Hello World .NET Core 콘솔 애플리케이션을 만들고 실행하는 과정을 단계별로 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="402fd-105">Hello World 애플리케이션은 일반적으로 초보자에게 새 프로그래밍 언어를 소개하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="402fd-106">이 프로그램은 단순히 “Hello World!” 라는 문구를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="402fd-107">화면에 출력했습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="402fd-108">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="402fd-108">Prerequisites</span></span>

- <span data-ttu-id="402fd-109">**.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.4](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상</span><span class="sxs-lookup"><span data-stu-id="402fd-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="402fd-110">이 워크로드를 선택하면 .NET Core 3.1 SDK가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="402fd-111">자세한 내용은 [.NET Core SDK 설치](../install/sdk.md?pivots=os-windows) 문서의 [Visual Studio를 사용하여 설치](../install/sdk.md?pivots=os-windows#install-with-visual-studio) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402fd-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="402fd-112">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="402fd-112">Create the app</span></span>

<span data-ttu-id="402fd-113">다음 지침에서는 간단한 Hello World 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="402fd-114">C#</span><span class="sxs-lookup"><span data-stu-id="402fd-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="402fd-115">Visual Studio 2019를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="402fd-116">“HelloWorld”라는 새로운 C# .NET Core 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="402fd-117">시작 창에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-117">On the start window, choose **Create a new project**.</span></span>

      ![Visual Studio 시작 창에서 새 프로젝트 만들기 버튼 선택](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="402fd-119">**새 프로젝트 만들기** 페이지의 검색 상자에 **console**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="402fd-120">그런 다음, 언어 목록에서 **C#** 을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="402fd-121">**콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![필터가 선택된 새 프로젝트 만들기 창](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="402fd-123">.NET Core 템플릿이 표시되지 않으면 필요한 워크로드가 설치되지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="402fd-124">**원하는 항목을 찾을 수 없나요?** 메시지에서 **추가 도구 및 기능 설치** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="402fd-125">Visual Studio 설치 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="402fd-126">**.NET Core 플랫폼 간 개발** 워크로드가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="402fd-127">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **HelloWorld**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="402fd-128">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-128">Then, choose **Create**.</span></span>

      ![프로젝트 이름, 위치 및 솔루션 이름 필드를 사용하여 새 프로젝트 창을 구성합니다.](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="402fd-130">.NET Core용 C# 콘솔 애플리케이션 템플릿은 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`로 `Program` 클래스를 자동으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="402fd-131">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="402fd-132">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio 및 새 HelloWorld 프로젝트](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[<span data-ttu-id="402fd-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="402fd-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="402fd-135">Visual Studio 2019를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="402fd-136">“HelloWorld”라는 새로운 Visual Basic .NET Core 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="402fd-137">시작 창에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-137">On the start window, choose **Create a new project**.</span></span>

      ![Visual Studio 시작 창에서 새 프로젝트 만들기 버튼 선택](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="402fd-139">**새 프로젝트 만들기** 페이지의 검색 상자에 **console**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="402fd-140">다음으로 언어 목록에서 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="402fd-141">**콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![콘솔 앱(.NET Framework)에 대한 Visual Basic 템플릿을 선택합니다.](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="402fd-143">.NET Core 템플릿이 표시되지 않으면 필요한 워크로드가 설치되지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="402fd-144">**원하는 항목을 찾을 수 없나요?** 메시지에서 **추가 도구 및 기능 설치** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="402fd-145">Visual Studio 설치 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="402fd-146">**.NET Core 플랫폼 간 개발** 워크로드가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="402fd-147">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **HelloWorld**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="402fd-148">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="402fd-149">.NET Core용 콘솔 앱 템플릿은 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`로 `Program` 클래스를 자동으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="402fd-150">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="402fd-151">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 `args` 매개 변수에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio 및 새 HelloWorld 프로젝트](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="402fd-153">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="402fd-154"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 리터럴 문자열 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="402fd-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="402fd-155">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="402fd-156">앱 실행</span><span class="sxs-lookup"><span data-stu-id="402fd-156">Run the app</span></span>

1. <span data-ttu-id="402fd-157">프로그램을 실행하려면 도구 모음에서 **HelloWorld**를 선택하거나 **F5**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![HelloWorld 실행 단추가 선택된 Visual Studio 도구 모음](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="402fd-159">콘솔 창이 열리고 "Hello World!"라는 텍스트가</span><span class="sxs-lookup"><span data-stu-id="402fd-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="402fd-160">화면에 표시되며 일부 Visual Studio 디버그 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![“Hello World 계속하려면 아무 키나 누르세요.”를 표시하는 콘솔 창](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="402fd-162">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="402fd-163">앱 향상</span><span class="sxs-lookup"><span data-stu-id="402fd-163">Enhance the app</span></span>

<span data-ttu-id="402fd-164">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="402fd-165">다음 지침에 따라 앱을 수정하고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-165">The following instructions modify and run the app again:</span></span>

# <a name="c"></a>[<span data-ttu-id="402fd-166">C#</span><span class="sxs-lookup"><span data-stu-id="402fd-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="402fd-167">현재 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/HelloWorld.cs#1)]

   <span data-ttu-id="402fd-168">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="402fd-168">This code displays "What is your name?"</span></span> <span data-ttu-id="402fd-169">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="402fd-170">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="402fd-171">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="402fd-172">마지막으로, [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)을 사용하여 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="402fd-173">**빌드** > **솔루션 빌드**를 선택하여 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="402fd-174">프로그램을 실행하려면 도구 모음에서 **HelloWorld**를 선택하거나 **F5**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="402fd-175">이름을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![수정된 프로그램 출력이 표시된 콘솔 창](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="402fd-177">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-177">Press any key to close the console window.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="402fd-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="402fd-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="402fd-179">현재 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/Program.vb#1)]

   <span data-ttu-id="402fd-180">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="402fd-180">This code displays "What is your name?"</span></span> <span data-ttu-id="402fd-181">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="402fd-182">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="402fd-183">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="402fd-184">마지막으로, [보간된 문자열](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)을 사용하여 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="402fd-185">**빌드** > **솔루션 빌드**를 선택하여 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="402fd-186">프로그램을 실행하려면 도구 모음에서 **HelloWorld**를 선택하거나 **F5**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="402fd-187">이름을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![수정된 프로그램 출력이 표시된 콘솔 창](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="402fd-189">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="402fd-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="402fd-190">Next steps</span></span>

<span data-ttu-id="402fd-191">이 문서에서는 첫 번째 .NET Core 애플리케이션을 만들고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="402fd-192">다음 단계에서는 앱을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="402fd-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="402fd-193">Visual Studio에서 .NET Core Hello World 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="402fd-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
