---
title: Mac용 Visual Studio를 사용하여 완전한 .NET Core 솔루션 빌드
description: 이 문서에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다.
ms.date: 12/19/2019
ms.openlocfilehash: 8c9fcca404a3875b6bb7f9cf20551a017ff553c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239965"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="fb0af-103">Mac용 Visual Studio를 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드</span><span class="sxs-lookup"><span data-stu-id="fb0af-103">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="fb0af-104">Visual Studio for Mac은 .NET Core 애플리케이션 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="fb0af-105">이 문서에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-105">This article walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="fb0af-106">이 자습서에서는 사용자가 입력하는 검색어 및 텍스트 문자열을 수락하고, 클래스 라이브러리의 메서드를 사용하여 해당 검색어가 문자열에 나타나는 횟수를 계산하고, 사용자에게 결과를 반환하는 애플리케이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-106">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="fb0af-107">이 솔루션에는 유닛 테스트 개념을 소개하기 위해 클래스 라이브러리에 대한 단위 테스트도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-107">The solution also includes unit testing for the class library as an introduction to unit testing concepts.</span></span> <span data-ttu-id="fb0af-108">전체 샘플에 대한 자습서를 수행하려면 [샘플 솔루션](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-108">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="fb0af-109">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb0af-109">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="fb0af-110">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-110">Your feedback is highly valued.</span></span> <span data-ttu-id="fb0af-111">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-111">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="fb0af-112">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-112">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="fb0af-113">[Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-113">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="fb0af-114">제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-114">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb0af-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb0af-115">Prerequisites</span></span>

- [<span data-ttu-id="fb0af-116">.NET Core SDK 3.1 이상</span><span class="sxs-lookup"><span data-stu-id="fb0af-116">.NET Core SDK 3.1 or later</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="fb0af-117">Mac용 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="fb0af-117">Visual Studio 2019 for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

<span data-ttu-id="fb0af-118">필수 조건에 대한 자세한 내용은 [.NET Core 종속성 및 요구 사항](../install/dependencies.md?pivots=os-macos)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb0af-118">For more information on prerequisites, see the [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-macos).</span></span> <span data-ttu-id="fb0af-119">Mac용 Visual Studio 2019의 전체 시스템 요구 사항은 [Mac용 Visual Studio 2019 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2019-system-requirements-mac)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb0af-119">For the full system requirements of Visual Studio 2019 for Mac, see [Visual Studio 2019 for Mac Product Family System Requirements](/visualstudio/productinfo/vs2019-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="fb0af-120">라이브러리 빌드</span><span class="sxs-lookup"><span data-stu-id="fb0af-120">Building a library</span></span>

1. <span data-ttu-id="fb0af-121">시작 창에서 **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-121">On the start window, select **New Project**.</span></span> <span data-ttu-id="fb0af-122">**새 프로젝트** 대화 상자의 **.NET Core** 노드에서 **.NET Standard 라이브러리** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-122">In the **New Project** dialog under the **.NET Core** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="fb0af-123">이 명령을 사용하면 .NET Core를 대상으로 하는 .NET Standard 라이브러리와 [.NET Standard](../../standard/net-standard.md)의 버전 2.1을 지원하는 기타 .NET 구현이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-123">This command creates a .NET Standard library that targets .NET Core as well as any other .NET implementation that supports version 2.1 of the [.NET Standard](../../standard/net-standard.md).</span></span> <span data-ttu-id="fb0af-124">여러 버전의 .NET Core SDK가 설치되어 있는 경우 라이브러리에 대해 다른 버전의 .NET Standard를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-124">If you have multiple versions of the .NET Core SDK installed, you can choose different versions of .NET Standard for your library.</span></span> <span data-ttu-id="fb0af-125">“.NET Standard 2.1”을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-125">Choose ".NET Standard 2.1" and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-126">![Mac용 Visual Studio 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-126">![Visual Studio for Mac New project dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span></span>

1. <span data-ttu-id="fb0af-127">프로젝트의 이름을 "TextUtils"("텍스트 유틸리티"의 약식 이름)로, 솔루션 이름을 "WordCounter"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="fb0af-128">**솔루션 디렉터리 내에 프로젝트 디렉터리를 만드세요.** 를 선택한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="fb0af-129">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-129">Select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-130">![Mac용 Visual Studio 새 프로젝트 대화 상자 옵션](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-130">![Visual Studio for Mac New project dialog options](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span></span>

1. <span data-ttu-id="fb0af-131">**솔루션** 패드에서 `TextUtils` 노드를 확장하여 템플릿에 제공되는 클래스 파일 *Class1.cs*를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-131">In the **Solution** pad, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="fb0af-132">Ctrl 키를 누른 채로 파일을 클릭하고 상황에 맞는 메뉴에서 **이름 바꾸기**를 선택한 후 파일 이름을 *WordCount.cs*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-132">Ctrl-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="fb0af-133">파일을 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-133">Open the file and replace the contents with the following code:</span></span>

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/TextUtils/WordCount.cs)]

1. <span data-ttu-id="fb0af-134">세 가지 방법, 즉 바로 가기 키 <kbd>&#8984;</kbd>+<kbd>s</kbd>를 사용하거나, 메뉴에서 **파일** > **저장**을 선택하거나, 파일 탭을 Ctrl 키를 누른 채로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-134">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or ctrl-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="fb0af-135">다음 그림에서는 IDE 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-135">The following image shows the IDE window:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-136">![클래스 라이브러리 파일 및 메서드가 있는 Mac용 Visual Studio IDE 창](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-136">![Visual Studio for Mac IDE window with class library file and method](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span></span>

1. <span data-ttu-id="fb0af-137">IDE 창 아래쪽 여백에서 **오류**를 선택하여 **오류** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-137">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="fb0af-138">**빌드 출력** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-138">Select the **Build Output** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-139">![오류 단추를 표시하는 Visual Studio Mac IDE의 아래쪽 여백](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-139">![Bottom margin of the Visual Studio Mac IDE showing the Errors button](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span></span>

1. <span data-ttu-id="fb0af-140">메뉴에서 **빌드** > **모두 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-140">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="fb0af-141">솔루션이 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-141">The solution builds.</span></span> <span data-ttu-id="fb0af-142">빌드 출력 패널에 빌드가 성공적으로 수행되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-142">The build output panel shows that the build is successful.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-143">![빌드 성공 메시지를 표시하는 오류 패널의 Visual Studio Mac 빌드 출력 창](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-143">![Visual Studio Mac Build output pane of the Errors panel with Build successful message](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span></span>

## <a name="creating-a-test-project"></a><span data-ttu-id="fb0af-144">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fb0af-144">Creating a test project</span></span>

<span data-ttu-id="fb0af-145">단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-145">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="fb0af-146">이 자습서에서 사용하는 테스트 프레임워크는 [xUnit(버전 2.4.0 이상)](https://xunit.github.io/)이며, 이는 xUnit 테스트 프로젝트가 다음 단계에서 솔루션에 추가될 때 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-146">The testing framework that you use in this tutorial is [xUnit (version 2.4.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="fb0af-147">**솔루션** 사이드바에서 `WordCounter` 솔루션을 Ctrl 키를 누른 채로 클릭하고 **추가** > **새 프로젝트 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-147">In the **Solution** sidebar, ctrl-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="fb0af-148">**새 프로젝트** 대화 상자의 **.NET Core** 노드에서 **테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-148">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="fb0af-149">**xUnit 테스트 프로젝트**와 **다음**을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-149">Select the **xUnit Test Project** followed by **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-150">![xUnit 테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-150">![Visual Studio Mac New Project dialog creating xUnit test project](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span></span>

1. <span data-ttu-id="fb0af-151">여러 버전의 .NET Core SDK가 있는 경우 이 프로젝트의 버전을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-151">If you have multiple versions of the .NET Core SDK, you'll need to select the version for this project.</span></span> <span data-ttu-id="fb0af-152">**.NET Core 3.1**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-152">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="fb0af-153">새 프로젝트의 이름을 "TestLibrary"로 지정하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-153">Name the new project "TestLibrary" and select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-154">![프로젝트 이름을 제공하는 Visual Studio Mac 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-154">![Visual Studio Mac New Project dialog providing project name](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span></span>

1. <span data-ttu-id="fb0af-155">테스트 라이브러리가 `WordCount` 클래스에 대해 작동하도록 하기 위해 `TextUtils` 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-155">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="fb0af-156">**솔루션** 사이드바에서 **TestLibrary** 아래의 **종속성**을 Ctrl 키를 누른 채로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-156">In the **Solution** sidebar, ctrl-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="fb0af-157">상황에 맞는 메뉴에서 **참조 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-157">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="fb0af-158">**참조 편집** 대화 상자의 **프로젝트** 탭에서 **TextUtils** 프로젝트를 선택합니다. **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-158">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab. Select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-159">![Visual Studio Mac 참조 편집 대화 상자](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-159">![Visual Studio Mac Edit References dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span></span>

1. <span data-ttu-id="fb0af-160">**TestLibrary** 프로젝트에서 *UnitTest1.cs* 파일 이름을 *TextUtilsTests.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-160">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="fb0af-161">파일을 열고 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-161">Open the file and replace the code with the following code:</span></span>

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   <span data-ttu-id="fb0af-162">다음 이미지는 단위 테스트 코드를 포함하는 IDE를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-162">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="fb0af-163">`Assert.NotEqual` 문을 신중히 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-163">Pay attention to the `Assert.NotEqual` statement.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-164">![IDE 주 창에서 Mac용 Visual Studio 초기 단위 테스트](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-164">![Visual Studio for Mac Initial unit test in the IDE main window](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span></span>

   <span data-ttu-id="fb0af-165">한 번 새 테스트를 실패하도록 만들어 테스트 논리가 올바른지 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-165">It's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="fb0af-166">이 메서드는 이름 "Jack"(대문자)과 "Jack" 및 "jack"(대문자 및 소문자)을 포함하는 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-166">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="fb0af-167">`GetWordCount` 메서드는 제대로 작동하면 검색 단어 인스턴스 2를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-167">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="fb0af-168">의도적으로 이 테스트가 실패하도록 하기 위해 먼저 검색 단어 "Jack"의 두 인스턴스가 `GetWordCount` 메서드에 의해 반환되지 않음을 어설션하는 테스트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-168">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="fb0af-169">다음 단계를 계속 진행하여 의도적으로 이 테스트가 실패하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-169">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="fb0af-170">화면 오른쪽의 **단위 테스트** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-170">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="fb0af-171">메뉴에서 **보기** > **테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-171">Select **View** > **Tests** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-172">![Mac용 Visual Studio 단위 테스트 패널](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-172">![Visual Studio for Mac Unit Tests panel](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span></span>

1. <span data-ttu-id="fb0af-173">패널을 열어두려면 **고정** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-173">Click the **Dock** icon to keep the panel open.</span></span> <span data-ttu-id="fb0af-174">(다음 이미지에서 강조된 것과 같습니다.)</span><span class="sxs-lookup"><span data-stu-id="fb0af-174">(Highlighted in the following image.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-175">![Mac용 Visual Studio 단위 테스트 패널 고정 아이콘](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-175">![Visual Studio for Mac Unit Tests panel dock icon](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span></span>

1. <span data-ttu-id="fb0af-176">**모두 실행** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="fb0af-177">테스트가 실패합니다. 이것은 올바른 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-177">The test fails, which is the correct result.</span></span> <span data-ttu-id="fb0af-178">테스트 메서드는 `inputString`, "Jack"의 2개 인스턴스가 `GetWordCount` 메서드에 제공된 문자열 "Jack jack"에서 반환되지 않음을 어설션합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-178">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="fb0af-179">단어의 대/소문자가 `GetWordCount` 메서드에서 제외되었으므로 두 개의 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-179">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="fb0af-180">2가 2와 *과 같지 않다는* 어설션은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-180">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="fb0af-181">결과는 올바르고 테스트 논리는 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-181">This result is the correct outcome, and the logic of our test is good.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-182">![Mac용 Visual Studio 테스트 실패 표시](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-182">![Visual Studio for Mac test failure display](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="fb0af-183">`Assert.NotEqual`을 `Assert.Equal`로 변경하여 `IgnoreCasing` 테스트 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-183">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="fb0af-184">바로 가기 키 <kbd>Ctrl</kbd>+<kbd>s</kbd>와 메뉴의 **파일** > **저장**을 사용하거나 파일 탭을 Ctrl 키를 누른 채로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-184">Save the file by using the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or ctrl-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="fb0af-185">`inputString` "Jack jack"이 `GetWordCount`로 전달된 상태로 `searchWord` "Jack"은 2개 인스턴스를 반환할 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-185">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="fb0af-186">**단위 테스트** 패널의 **테스트 실행** 단추 또는 화면 하단에 있는 **테스트 결과** 패널의 **테스트 다시 실행** 단추를 클릭하여 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-186">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="fb0af-187">테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-187">The test passes.</span></span> <span data-ttu-id="fb0af-188">문자열 "Jack jack"(대/소문자 무시)에는 "Jack" 인스턴스가 2개 있고 테스트 어설션은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-188">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-189">![Mac용 Visual Studio 테스트 통과 표시](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-189">![Visual Studio for Mac tests pass display](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

1. <span data-ttu-id="fb0af-190">`Fact`를 사용하여 개별 반환 값을 테스트하는 것은 단위 테스트로 수행할 수 있는 작업의 시작일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-190">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="fb0af-191">다른 강력한 기법에서는 `Theory`를 사용하여 한 번에 여러 개의 값을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-191">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="fb0af-192">다음 메서드를 `TextUtils_GetWordCountShould` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-192">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="fb0af-193">이 메서드를 추가한 후 클래스에는 다음 두 개의 메서드가 존재하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-193">You have two methods in the class after you add this method:</span></span>

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   <span data-ttu-id="fb0af-194">`CountInstancesCorrectly`는 `GetWordCount` 메서드가 올바르게 계산하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-194">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="fb0af-195">`InlineData`는 확인할 개수, 검색 단어 및 입력 문자열을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-195">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="fb0af-196">테스트 메서드는 데이터의 각 줄에 대해 한 번만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-196">The test method runs once for each line of data.</span></span> <span data-ttu-id="fb0af-197">데이터에 포함된 개수가 올바르며 해당 값이 `GetWordCount` 메서드에 의해 반환된 개수와 일치한다는 것을 알더라도 `Assert.NotEqual`을 사용하여 먼저 실패를 어설션하는지 한 번 더 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-197">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="fb0af-198">의도적으로 이 테스트가 실패하도록 하는 단계를 수행하는 일이 처음에는 시간 낭비처럼 보일 수 있지만 먼저 실패하여 테스트의 논리를 검토하는 일은 테스트 논리에서 중요한 확인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-198">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="fb0af-199">실패할 것으로 예상했는데 통과한 테스트 메서드가 나타날 때 테스트 논리에서 버그가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-199">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="fb0af-200">테스트 메서드를 만들 때마다 이 단계를 수행하는 것은 가치 있는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-200">It's worth the effort to take this step every time you create a test method.</span></span>

1. <span data-ttu-id="fb0af-201">파일을 저장하고 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-201">Save the file and run the tests again.</span></span> <span data-ttu-id="fb0af-202">대/소문자 구분 테스트는 통과하지만 세 가지 계산 테스트는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-202">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="fb0af-203">결과는 예상하던 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-203">This outcome is exactly what you expect to happen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-204">![Mac용 Visual Studio 테스트 실패 예상됨](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-204">![Visual Studio for Mac expected test failure](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="fb0af-205">`Assert.NotEqual`을 `Assert.Equal`로 변경하여 `CountInstancesCorrectly` 테스트 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-205">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="fb0af-206">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-206">Save the file.</span></span> <span data-ttu-id="fb0af-207">테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-207">Run the tests again.</span></span> <span data-ttu-id="fb0af-208">모든 테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-208">All tests pass.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-209">![Mac용 Visual Studio 테스트 통과 예상됨](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-209">![Visual Studio for Mac expected test passes](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

## <a name="adding-a-console-app"></a><span data-ttu-id="fb0af-210">콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="fb0af-210">Adding a console app</span></span>

1. <span data-ttu-id="fb0af-211">**솔루션** 사이드바에서 `WordCounter` 솔루션을 Ctrl 키를 누른 채로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-211">In the **Solution** sidebar, ctrl-click the `WordCounter` solution.</span></span> <span data-ttu-id="fb0af-212">**.NET Core** > **앱** 템플릿에서 템플릿을 선택하여 새 **콘솔 애플리케이션** 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-212">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="fb0af-213">**새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-213">Select **Next**.</span></span> <span data-ttu-id="fb0af-214">프로젝트 이름을 **WordCounterApp**으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-214">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="fb0af-215">**만들기**를 선택하여 솔루션에 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-215">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="fb0af-216">**솔루션** 사이드바에서 새 **WordCounterApp** 프로젝트에서 **종속성**을 Ctrl 키를 누른 채로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-216">In the **Solutions** sidebar, ctrl-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="fb0af-217">**참조 편집** 대화 상자에서 **TextUtils**를 선택하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-217">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="fb0af-218">*Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-218">Open the *Program.cs* file.</span></span> <span data-ttu-id="fb0af-219">코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-219">Replace the code with the following code:</span></span>

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/WordCounterApp/Program.cs)]

1. <span data-ttu-id="fb0af-220">`WordCounterApp` 프로젝트를 Ctrl 키를 누른 채로 클릭하고 상황에 맞는 메뉴에서 **프로젝트 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-220">Ctrl-click on the `WordCounterApp` project and select **Run project** from the context menu.</span></span> <span data-ttu-id="fb0af-221">앱을 실행할 때 콘솔 창의 프롬프트에 검색 단어 및 입력 문자열 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-221">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="fb0af-222">앱은 문자열에서 검색 단어가 표시되는 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-222">The app indicates the number of times the search word appears in the string.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-223">![실행 중인 앱을 보여 주는 Mac용 Visual Studio 콘솔 창](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-223">![Visual Studio for Mac console window showing your app running](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span></span>

1. <span data-ttu-id="fb0af-224">알아보려는 마지막 기능은 Visual Studio for Mac을 사용한 디버깅입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-224">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="fb0af-225">`Console.WriteLine` 문에서 중단점을 설정합니다. 줄 23의 왼쪽 여백을 선택하면 코드 줄 옆에 빨간색 원이 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-225">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="fb0af-226">또는 코드 줄의 아무 위치나 선택하고 메뉴에서 **실행** > **중단점 설정/해제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-226">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-227">![Mac용 Visual Studio 중단점 설정](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-227">![Visual Studio for Mac breakpoint set](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span></span>

1. <span data-ttu-id="fb0af-228">`WordCounterApp` 프로젝트를 Ctrl 키를 누른 채로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-228">ctrl-click the `WordCounterApp` project.</span></span> <span data-ttu-id="fb0af-229">상황에 맞는 메뉴에서 **프로젝트 디버깅 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-229">Select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="fb0af-230">앱이 실행될 때 검색 단어 "cat" 및 검색할 문자열 "The dog chased the cat, but the cat escaped."를</span><span class="sxs-lookup"><span data-stu-id="fb0af-230">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="fb0af-231">입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-231">for the string to search.</span></span> <span data-ttu-id="fb0af-232">`Console.WriteLine` 문에 도달하면 프로그램 실행이 중단된 후 해당 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-232">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="fb0af-233">**지역** 탭에 `searchWord`, `inputString`, `wordCount` 및 `pluralChar` 값이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-233">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-234">![Mac용 Visual Studio 디버거 프로그램 실행 중지됨](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-234">![Visual Studio for Mac debugger program execution stopped](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span></span>

1. <span data-ttu-id="fb0af-235">**직접 실행** 창에서 "wordCount = 999;"를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-235">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="fb0af-236">이 명령을 사용하면 의미 없는 값인 999가 `wordCount` 변수에 할당되면서 디버그 동안 변수 값을 바꿀 수 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-236">This command assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-237">![Mac용 Visual Studio 직접 실행 창에서 값 변경](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-237">![Visual Studio for Mac changing values in the immediate window](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span></span>

1. <span data-ttu-id="fb0af-238">도구 모음에서 *계속* 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-238">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="fb0af-239">콘솔 창에서 출력을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-239">Look at the output in the console window.</span></span> <span data-ttu-id="fb0af-240">앱을 디버그할 때 설정한 잘못된 값인 999가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-240">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-241">![Mac용 Visual Studio 도구 모음의 계속 단추](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-241">![Visual Studio for Mac continue button in the toolbar](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0af-242">![Mac용 Visual Studio 콘솔 창 출력](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span><span class="sxs-lookup"><span data-stu-id="fb0af-242">![Visual Studio for Mac console window output](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span></span>

<span data-ttu-id="fb0af-243">동일한 프로세스를 사용하여 단위 테스트 프로젝트를 사용하는 코드를 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-243">You can use the same process to debug code using your unit test project.</span></span> <span data-ttu-id="fb0af-244">WordCount 앱 프로젝트를 시작하는 대신 상황에 맞는 메뉴에서 **테스트 라이브러리** 프로젝트를 Ctrl 키를 누른 채 클릭하고 **프로젝트 디버그 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-244">Instead of starting the WordCount app project, ctrl-click the **Test Library** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="fb0af-245">Mac용 Visual Studio에서 디버거를 연결한 상태로 테스트 프로젝트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-245">Visual Studio for Mac starts your test project with the debugger attached.</span></span> <span data-ttu-id="fb0af-246">테스트 프로젝트에 추가한 중단점 또는 기본 라이브러리 코드에서 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0af-246">Execution will stop at any breakpoint you've added to the test project, or the underlying library code.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb0af-247">참조</span><span class="sxs-lookup"><span data-stu-id="fb0af-247">See also</span></span>

- [<span data-ttu-id="fb0af-248">Mac용 Visual Studio 2019 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="fb0af-248">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
