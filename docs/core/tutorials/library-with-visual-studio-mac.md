---
title: Mac용 Visual Studio를 사용하여 .NET 클래스 라이브러리 만들기
description: Mac용 Visual Studio를 사용하여 .NET 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 11/30/2020
ms.openlocfilehash: 1b6b26de06d18d505fa6dde3ff9779a3dab3f1e6
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599309"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-for-mac"></a><span data-ttu-id="313a0-103">자습서: Mac용 Visual Studio를 사용하여 .NET 클래스 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="313a0-103">Tutorial: Create a .NET class library using Visual Studio for Mac</span></span>

<span data-ttu-id="313a0-104">이 자습서에서는 단일 문자열 처리 메서드를 포함하는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-104">In this tutorial, you create a class library that contains a single string-handling method.</span></span>

<span data-ttu-id="313a0-105">*클래스 라이브러리* 는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="313a0-106">라이브러리가 .NET Standard 2.0을 대상으로 하는 경우 .NET Standard 2.0을 지원하는 .NET 구현(.NET Framework 포함)에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="313a0-107">라이브러리가 .NET 5를 대상으로 하는 경우 .NET 5를 대상으로 하는 모든 애플리케이션에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="313a0-108">이 자습서에서는 .NET 5를 대상으로 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-108">This tutorial shows how to target .NET 5.</span></span>

> [!NOTE]
> <span data-ttu-id="313a0-109">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-109">Your feedback is highly valued.</span></span> <span data-ttu-id="313a0-110">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="313a0-111">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고** 를 선택하거나 시작 화면에서 **문제 보고** 를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="313a0-112">[Developer Community](https://aka.ms/feedback/report?space=41)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-112">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> - <span data-ttu-id="313a0-113">제안하려면 메뉴에서 **도움말** > **제안하기** 를 선택하거나 시작 화면에서 **제안하기** 를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://aka.ms/feedback/suggest?space=41)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="313a0-114">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="313a0-114">Prerequisites</span></span>

* <span data-ttu-id="313a0-115">[Mac용 Visual Studio 버전 8.8 이상 설치](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="313a0-115">[Install Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="313a0-116">.NET Core 설치 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="313a0-117">Xamarin 설치는 .NET 개발에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-117">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="313a0-118">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="313a0-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="313a0-119">[자습서: Mac용 Visual Studio](/visualstudio/mac/installation)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="313a0-120">[지원되는 macOS 버전](../install/macos.md).</span><span class="sxs-lookup"><span data-stu-id="313a0-120">[Supported macOS versions](../install/macos.md).</span></span>
  * <span data-ttu-id="313a0-121">[Mac용 Visual Studio에서 지원되는 .NET 버전](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="313a0-121">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="313a0-122">클래스 라이브러리 프로젝트로 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="313a0-122">Create a solution with a class library project</span></span>

<span data-ttu-id="313a0-123">Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="313a0-124">솔루션과 솔루션의 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="313a0-125">나중에 동일한 솔루션에 관련 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="313a0-126">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="313a0-127">시작 창에서 **새 프로젝트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="313a0-128">**새 프로젝트의 템플릿 선택** 대화 상자에서 **웹 및 콘솔** > **라이브러리** > **클래스 라이브러리** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-128">In the **Choose a template for your new project** dialog select **Web and Console** > **Library** > **Class Library**, and then select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="새 프로젝트 대화 상자":::

1. <span data-ttu-id="313a0-130">**새 클래스 라이브러리 구성** 대화 상자에서 **.NET 5.0** 을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-130">In the **Configure your new Class Library** dialog, choose **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="313a0-131">프로젝트 이름을 "StringLibrary", 솔루션 이름을 "ClassLibraryProjects"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-131">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="313a0-132">**솔루션 디렉터리 내에 프로젝트 디렉터리를 만드세요** 를 선택한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-132">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="313a0-133">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-133">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Mac용 Visual Studio 새 프로젝트 대화 상자 옵션":::

1. <span data-ttu-id="313a0-135">주 메뉴에서 **보기** > **솔루션** 을 선택하고, 고정 아이콘을 선택해 패드를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-135">From the main menu, select **View** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="솔루션 패드의 고정 아이콘":::

1. <span data-ttu-id="313a0-137">**솔루션** 패드에서 `StringLibrary` 노드를 확장하여 템플릿에 제공되는 클래스 파일 *Class1.cs* 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-137">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="313a0-138"><kbd>ctrl</kbd> 키를 누른 채로 파일을 클릭하고 상황에 맞는 메뉴에서 **이름 바꾸기** 를 선택한 후 파일 이름을 *StringLibrary.cs* 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-138"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="313a0-139">파일을 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-139">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="313a0-140"><kbd>⌘</kbd><kbd>S</kbd>(<kbd>command</kbd>+<kbd>S</kbd>)를 눌러 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-140">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="313a0-141">IDE 창 아래쪽 여백에서 **오류** 를 선택하여 **오류** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-141">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="313a0-142">**빌드 출력** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-142">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="오류 단추를 표시하는 Visual Studio Mac IDE의 아래쪽 여백":::

1. <span data-ttu-id="313a0-144">메뉴에서 **빌드** > **모두 빌드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-144">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="313a0-145">솔루션이 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-145">The solution builds.</span></span> <span data-ttu-id="313a0-146">빌드 출력 패널에 빌드가 성공적으로 수행되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-146">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="빌드 성공 메시지를 표시하는 오류 패널의 Visual Studio Mac 빌드 출력 창":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="313a0-148">솔루션에 콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="313a0-148">Add a console app to the solution</span></span>

<span data-ttu-id="313a0-149">클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="313a0-150">이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="313a0-151">**솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 `ClassLibraryProjects` 솔루션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-151">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="313a0-152">**웹 및 콘솔** > **앱** 템플릿에서 템플릿을 선택하여 새로운 **콘솔 애플리케이션** 프로젝트를 추가하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-152">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="313a0-153">**대상 프레임워크** 로 **.NET 5.0** 을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-153">Select **.NET 5.0** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="313a0-154">프로젝트 이름을 **ShowCase** 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-154">Name the project **ShowCase**.</span></span> <span data-ttu-id="313a0-155">**만들기** 를 선택하여 솔루션에 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-155">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="ShowCase 프로젝트 추가":::

1. <span data-ttu-id="313a0-157">*Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-157">Open the *Program.cs* file.</span></span> <span data-ttu-id="313a0-158">코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-158">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="313a0-159">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-159">The program prompts the user to enter a string.</span></span> <span data-ttu-id="313a0-160">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-160">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="313a0-161">사용자가 문자열을 입력하지 않고 <kbd>enter</kbd> 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-161">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="313a0-162">코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-162">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="313a0-163">25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-163">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="313a0-164">프로젝트 참조 추가</span><span class="sxs-lookup"><span data-stu-id="313a0-164">Add a project reference</span></span>

<span data-ttu-id="313a0-165">처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="313a0-166">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="313a0-167">**솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 새로운 **ShowCase** 프로젝트의 **종속성** 노드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-167">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="313a0-168">상황에 맞는 메뉴에서 **참조 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-168">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="313a0-169">**참조** 대화 상자에서 **StringLibrary** 를 선택하고 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-169">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="313a0-170">앱 실행</span><span class="sxs-lookup"><span data-stu-id="313a0-170">Run the app</span></span>

1. <span data-ttu-id="313a0-171">**ShowCase** 프로젝트를 <kbd>ctrl</kbd> 키를 누른 채로 클릭하고 상황에 맞는 메뉴에서 **프로젝트 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-171"><kbd>ctrl</kbd>-click the **ShowCase** project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="313a0-172">문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-172">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="실행 중인 앱을 보여 주는 Mac용 Visual Studio 콘솔 창":::

## <a name="additional-resources"></a><span data-ttu-id="313a0-174">추가 자료</span><span class="sxs-lookup"><span data-stu-id="313a0-174">Additional resources</span></span>

* [<span data-ttu-id="313a0-175">.NET CLI를 사용하여 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="313a0-175">Develop libraries with the .NET CLI</span></span>](libraries.md)
* [<span data-ttu-id="313a0-176">Mac용 Visual Studio 2019 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="313a0-176">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
* <span data-ttu-id="313a0-177">[지원되는 .NET Standard 버전 및 플랫폼](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="313a0-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="313a0-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="313a0-178">Next steps</span></span>

<span data-ttu-id="313a0-179">이 자습서에서는 솔루션과 라이브러리 프로젝트를 만들고 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-179">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="313a0-180">다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="313a0-180">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="313a0-181">Mac용 Visual Studio를 사용하여 .NET 클래스 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="313a0-181">Test a .NET class library using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
