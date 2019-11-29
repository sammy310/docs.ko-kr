---
title: Mac용 Visual Studio를 사용하여 macOS에서 .NET Core 시작
description: 이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 애플리케이션을 빌드하는 과정을 안내합니다.
author: mairaw
ms.date: 07/11/2019
ms.custom: seodec18
ms.openlocfilehash: feaed88e902080c5c3b07578b78f8437489a690c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428590"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="4843c-103">Mac용 Visual Studio를 사용하여 macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="4843c-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="4843c-104">Visual Studio for Mac은 .NET Core 애플리케이션 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="4843c-105">이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 애플리케이션을 빌드하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="4843c-106">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-106">Your feedback is highly valued.</span></span> <span data-ttu-id="4843c-107">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="4843c-108">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="4843c-109">[Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="4843c-110">제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4843c-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4843c-111">Prerequisites</span></span>

<span data-ttu-id="4843c-112">[.NET Core 종속성 및 요구 사항](../install/dependencies.md?tabs=netcore30&pivots=os-macos) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4843c-112">See the [.NET Core dependencies and requirements](../install/dependencies.md?tabs=netcore30&pivots=os-macos) topic.</span></span>

<span data-ttu-id="4843c-113">[.NET Core 지원](/visualstudio/mac/net-core-support) 문서를 참조하여 지원되는 버전의 .NET Core를 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-113">Check the [.NET Core Support](/visualstudio/mac/net-core-support) article to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="4843c-114">시작</span><span class="sxs-lookup"><span data-stu-id="4843c-114">Get started</span></span>

<span data-ttu-id="4843c-115">필수 구성 요소와 Visual Studio for Mac을 이미 설치한 경우 이 섹션을 건너뛰고 [프로젝트 만들기](#creating-a-project)를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="4843c-116">다음 단계에 따라 필수 구성 요소 및 Visual Studio for Mac을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="4843c-117">[Visual Studio for Mac 설치 관리자](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="4843c-118">설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-118">Run the installer.</span></span> <span data-ttu-id="4843c-119">사용권 계약을 읽은 다음 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-119">Read and accept the license agreement.</span></span> <span data-ttu-id="4843c-120">설치하는 동안 .NET Core 설치 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="4843c-121">플랫폼 간 모바일 앱 개발 기술인 Xamarin을 설치할 기회가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="4843c-122">Xamarin 및 관련된 구성 요소의 설치는 .NET Core 개발에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="4843c-123">Mac용 Visual Studio 설치 프로세스에 대한 연습을 진행하려면 [Mac용 Visual Studio 설명서](/visualstudio/mac/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4843c-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="4843c-124">설치가 완료되면 Visual Studio for Mac IDE를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="4843c-125">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4843c-125">Creating a project</span></span>

1. <span data-ttu-id="4843c-126">[시작] 창에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-126">Select **New** on the Start Window.</span></span>

   ![Mac용 Visual Studio 시작 화면의 새로 만들기 단추](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="4843c-128">**새 프로젝트** 대화 상자에서 **.NET Core** 노드 아래에서 **앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="4843c-129">**콘솔 애플리케이션** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![새 프로젝트 템플릿 목록](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="4843c-131">여러 버전의 .NET Core가 설치된 경우 프로젝트의 대상 프레임워크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="4843c-132">**프로젝트 이름**으로 "HelloWorld"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="4843c-133">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-133">Select **Create**.</span></span>

   ![새 콘솔 애플리케이션 대화 상자 구성](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="4843c-135">프로젝트의 종속성이 복원되는 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="4843c-136">프로젝트에는 `Main` 메서드가 있는 `Program` 클래스를 포함하는 C# 파일 *Program.cs*가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="4843c-137">앱이 실행되면 `Console.WriteLine` 문은 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="4843c-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="4843c-138">콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-138">to the console when the app is run.</span></span>

   ![Program.cs 파일이 열려 있는 주 창](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="4843c-140">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="4843c-140">Run the application</span></span>

<span data-ttu-id="4843c-141">앱을 디버그 모드에서 실행하려면 ⌘ ↵(Command + Enter)를 사용하고 릴리스 모드에서 실행하려면 ⌥ ⌘ ↵(Option + Command + Enter)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![애플리케이션 출력 창에 Hello World!가 표시됩니다.](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="4843c-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4843c-143">Next step</span></span>

<span data-ttu-id="4843c-144">[Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드](using-on-mac-vs-full-solution.md) 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 전체 .NET Core 솔루션을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4843c-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
