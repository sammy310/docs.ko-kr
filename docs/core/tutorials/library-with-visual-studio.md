---
title: Visual Studio에서 .NET Standard 클래스 라이브러리 빌드
description: Visual Studio를 사용하여 C# 또는 Visual Basic으로 작성된 .NET Standard 클래스 라이브러리를 빌드하는 방법 알아보기
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714014"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="03798-103">Visual Studio에서 .NET Standard 라이브러리 빌드</span><span class="sxs-lookup"><span data-stu-id="03798-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="03798-104">*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="03798-105">.NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="03798-106">클래스 라이브러리를 마칠 때 타사 구성 요소로 배포할지 또는 하나 이상의 애플리케이션과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="03798-107">.NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03798-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="03798-108">이 항목에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="03798-109">[ 클래스의 멤버인 것처럼 호출할 수 있도록 ](../../csharp/programming-guide/classes-and-structs/extension-methods.md)확장 메서드<xref:System.String>로 구현하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="03798-110">Visual Studio 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="03798-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="03798-111">먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03798-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="03798-112">Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="03798-113">자습서 시리즈를 계속 학습하는 경우 동일한 솔루션에 관련 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="03798-114">빈 솔루션을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-114">To create the blank solution:</span></span>

1. <span data-ttu-id="03798-115">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03798-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="03798-116">시작 창에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="03798-117">**새 프로젝트 만들기** 페이지의 검색 상자에 **solution**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="03798-118">**빈 솔루션** 템플릿을 선택한 후, **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio의 빈 솔루션 템플릿](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="03798-120">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ClassLibraryProjects**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="03798-121">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="03798-122">이 단계를 건너뛰고 다음 단계에서 프로젝트를 만들 때 Visual Studio에서 솔루션을 만들도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="03798-123">**새 프로젝트 구성** 페이지에서 솔루션 옵션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="03798-124">클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="03798-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="03798-125">C#</span><span class="sxs-lookup"><span data-stu-id="03798-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="03798-126">“StringLibrary”라는 새로운 C# .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="03798-127">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="03798-128">**새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="03798-129">언어 목록에서 **C#** 을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="03798-130">**클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="03798-131">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="03798-132">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="03798-133">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="03798-134">**솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="03798-135">**대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03798-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="03798-137">코드 창의 코드를 다음 코드로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="03798-138">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="03798-139">이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="03798-140">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="03798-141"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="03798-142">메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="03798-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="03798-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="03798-144">“StringLibrary”라는 새로운 Visual Basic .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="03798-145">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="03798-146">**새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="03798-147">언어 목록에서 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="03798-148">**클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="03798-149">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="03798-150">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="03798-151">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="03798-152">**솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="03798-153">**대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03798-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="03798-155">**속성** 대화 상자에서 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="03798-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="03798-156">각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03798-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="03798-157">이 자습서에서는 코드 파일의 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="03798-158">코드 창의 코드를 다음 코드로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="03798-159">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="03798-160">이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="03798-161">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="03798-162"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="03798-163">메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="03798-164">프로젝트가 오류 없이 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03798-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="03798-165">Next steps</span></span>

<span data-ttu-id="03798-166">라이브러리를 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="03798-166">You've successfully built the library.</span></span> <span data-ttu-id="03798-167">해당 메서드를 호출하지 않았으므로 예상대로 작동하는지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="03798-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="03798-168">라이브러리 개발의 다음 단계는 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03798-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="03798-169">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="03798-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
