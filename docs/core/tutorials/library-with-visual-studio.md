---
title: Visual Studio에서 .NET Standard 클래스 라이브러리 만들기
description: Visual Studio를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7d64ca32bdbe20f949ae575bc4c3f9bbb594fffd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283626"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="34798-103">자습서: Visual Studio에서 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="34798-103">Tutorial: Create a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="34798-104">*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="34798-105">.NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34798-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="34798-106">클래스 라이브러리를 마칠 때 타사 구성 요소로 배포할지 또는 하나 이상의 애플리케이션과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34798-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="34798-107">.NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34798-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="34798-108">이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34798-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="34798-109"><xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34798-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="34798-110">Prerequisites</span></span>

- <span data-ttu-id="34798-111">**.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="34798-111">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="34798-112">이 워크로드를 선택하면 .NET Core 3.1 SDK가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="34798-112">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="34798-113">자세한 내용은 [.NET Core SDK 설치](../install/sdk.md?pivots=os-windows) 문서의 [Visual Studio를 사용하여 설치](../install/sdk.md?pivots=os-windows#install-with-visual-studio) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34798-113">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="34798-114">Visual Studio 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="34798-114">Create a Visual Studio solution</span></span>

<span data-ttu-id="34798-115">먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34798-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="34798-116">Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-116">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="34798-117">동일한 솔루션에 관련 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-117">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="34798-118">빈 솔루션을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-118">To create the blank solution:</span></span>

1. <span data-ttu-id="34798-119">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="34798-119">Open Visual Studio.</span></span>

2. <span data-ttu-id="34798-120">시작 창에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-120">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="34798-121">**새 프로젝트 만들기** 페이지의 검색 상자에 **solution**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-121">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="34798-122">**빈 솔루션** 템플릿을 선택한 후, **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-122">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio의 빈 솔루션 템플릿](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="34798-124">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ClassLibraryProjects**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-124">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="34798-125">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-125">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="34798-126">클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="34798-126">Create a class library project</span></span>

1. <span data-ttu-id="34798-127">"StringLibrary"라는 새로운 .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-127">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="34798-128">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-128">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="34798-129">**새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-129">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="34798-130">언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-130">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="34798-131">**클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-131">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="34798-132">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-132">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="34798-133">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-133">Then, choose **Create**.</span></span>

1. <span data-ttu-id="34798-134">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-134">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="34798-135">**솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-135">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="34798-136">**대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34798-136">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="34798-138">Visual Basic을 사용하는 경우 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="34798-138">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="34798-140">각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34798-140">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="34798-141">이 자습서에서는 코드 파일의 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-141">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="34798-142">*Class1.cs* 또는 *Class1.vb* 코드 창에서 코드를 다음 코드로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-142">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="34798-143">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-143">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="34798-144">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34798-144">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="34798-145">이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-145">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="34798-146">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-146">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="34798-147"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-147">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="34798-148">메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택하여 프로젝트가 오류 없이 컴파일되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-148">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="34798-149">솔루션에 콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="34798-149">Add a console app to the solution</span></span>

<span data-ttu-id="34798-150">사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고하는 콘솔 애플리케이션에서 이 클래스 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-150">Use the class library in a console application that prompts the user to enter a string and reports whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="34798-151">"ShowCase"라는 새 .NET Core 콘솔 애플리케이션을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="34798-152">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="34798-153">**새 프로젝트 추가** 페이지의 검색 상자에 **console**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="34798-154">언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="34798-155">**콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="34798-156">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ShowCase**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="34798-157">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="34798-158">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-158">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio 프로젝트 상황에 맞는 메뉴로 시작 프로젝트 설정](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="34798-160">처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34798-160">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="34798-161">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34798-161">To allow it to call methods in the class library, create a project reference to the class library project.</span></span> <span data-ttu-id="34798-162">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **프로젝트 참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-162">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Visual Studio의 참조 추가 상황에 맞는 메뉴](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="34798-164">**참조 관리자** 대화 상자에서 **StringLibrary** 프로젝트를 선택하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-164">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![StringLibrary를 선택한 참조 관리자 대화 상자](media/library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="34798-166">*Program.cs* 또는 *Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="34798-166">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="34798-167">코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-167">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="34798-168">25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-168">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="34798-169">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-169">The program prompts the user to enter a string.</span></span> <span data-ttu-id="34798-170">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34798-170">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="34798-171">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="34798-171">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="34798-172">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-172">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="34798-173">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-173">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Visual Studio 프로젝트 도구 모음 디버그 단추 표시](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="34798-175">문자열을 입력하고 **Enter** 키를 눌러 프로그램을 사용해 본 다음 **Enter** 키를 눌러 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="34798-175">Try out the program by entering strings and pressing **Enter**, then press **Enter** to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="ShowCase가 실행되는 콘솔 창":::

## <a name="next-steps"></a><span data-ttu-id="34798-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="34798-177">Next steps</span></span>

<span data-ttu-id="34798-178">이 자습서에서는 솔루션을 만들고, 라이브러리 프로젝트를 추가하고, 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="34798-178">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="34798-179">다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34798-179">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34798-180">Visual Studio에서 .NET Core를 사용하여 .NET Standard 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="34798-180">Test a .NET Standard library with .NET Core in Visual Studio</span></span>](testing-library-with-visual-studio.md)
