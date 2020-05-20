---
title: Visual Studio에서 .NET Standard 라이브러리 사용
description: Visual Studio 2019를 사용하여 다른 클래스 라이브러리의 멤버를 호출하는 .NET Core 애플리케이션을 빌드합니다.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920452"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="8ac53-103">Visual Studio에서 .NET Standard 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="8ac53-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="8ac53-104">.NET Standard 클래스 라이브러리를 만들고 테스트했으며 라이브러리의 릴리스 버전을 빌드한 경우 다음 단계는 호출자에게 이를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="8ac53-105">다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-105">You can do this in two ways:</span></span>

- <span data-ttu-id="8ac53-106">라이브러리가 단일 솔루션에 사용되는 경우(예: 단일 대형 애플리케이션의 구성 요소인 경우) 솔루션에 프로젝트로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="8ac53-107">라이브러리를 공개적으로 사용 가능한 경우 NuGet 패키지로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="8ac53-108">이 자습서에서는 다음 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8ac53-109">.NET Standard 라이브러리 프로젝트를 참조하는 솔루션에 콘솔 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="8ac53-110">.NET Standard 라이브러리를 포함하는 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="8ac53-111">솔루션에 콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="8ac53-111">Add a console app to your solution</span></span>

<span data-ttu-id="8ac53-112">[Visual Studio에서 .NET Standard 라이브러리 테스트](testing-library-with-visual-studio.md)의 클래스 라이브러리와 동일한 솔루션에 단위 테스트를 포함한 것처럼 애플리케이션을 해당 솔루션의 일부로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="8ac53-113">예를 들어 사용자가 문자열을 입력하도록 요구하고 첫 번째 문자가 대문자인지 여부를 보고하는 콘솔 애플리케이션에서 이 클래스 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="8ac53-114">[Visual Studio에서 .NET Standard 라이브러리 빌드](library-with-visual-studio.md) 문서에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="8ac53-115">"ShowCase"라는 새 .NET Core 콘솔 애플리케이션을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="8ac53-116">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="8ac53-117">**새 프로젝트 추가** 페이지의 검색 상자에 **console**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="8ac53-118">언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="8ac53-119">**콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="8ac53-120">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ShowCase**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="8ac53-121">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="8ac53-122">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio 프로젝트 상황에 맞는 메뉴로 시작 프로젝트 설정](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="8ac53-124">처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="8ac53-125">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="8ac53-126">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Visual Studio의 참조 추가 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="8ac53-128">**참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![StringLibrary를 선택한 참조 관리자 대화 상자](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="8ac53-130">*Program.cs* 또는 *Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="8ac53-131">코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="8ac53-132">25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="8ac53-133">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="8ac53-134">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="8ac53-135">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="8ac53-136">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="8ac53-137">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Visual Studio 프로젝트 도구 모음 디버그 단추 표시](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="8ac53-139">[Visual Studio를 사용하여 C# 또는 Visual Basic .NET Core Hello World 애플리케이션 디버그](debugging-with-visual-studio.md) 및 [Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시](publishing-with-visual-studio.md)의 단계에 따라 이 라이브러리를 사용하는 애플리케이션을 디버그하고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="8ac53-140">NuGet 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="8ac53-140">Create a NuGet package</span></span>

<span data-ttu-id="8ac53-141">클래스 라이브러리를 NuGet 패키지로 게시하여 광범위하게 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="8ac53-142">Visual Studio에서는 NuGet 패키지의 생성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="8ac53-143">이를 만들려면 .NET Core CLI 명령을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="8ac53-144">콘솔 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-144">Open a console window.</span></span>

   <span data-ttu-id="8ac53-145">예를 들어 Windows 작업 표시줄의 검색 상자에서 **명령 프롬프트**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="8ac53-146">**명령 프롬프트** 데스크톱 앱을 선택 하거나 검색 결과에서 이미 선택되어 있는 경우 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="8ac53-147">라이브러리의 프로젝트 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="8ac53-148">이 디렉터리에는 소스 코드 및 프로젝트 파일 *StringLibrary.csproj* 또는 *StringLibrary.vbproj*가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="8ac53-149">[dotnet pack](../tools/dotnet-pack.md) 명령을 실행하여 *.nupkg* 확장명을 포함하는 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="8ac53-150">*dotnet.exe*를 포함하는 디렉터리가 해당 PATH에 없는 경우 콘솔 창에 `where dotnet.exe`를 입력하여 해당 위치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac53-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="8ac53-151">NuGet 패키지를 만드는 방법에 대한 자세한 내용은 [.NET Core CLI로 NuGet 패키지를 만드는 방법](../deploying/creating-nuget-packages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac53-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
