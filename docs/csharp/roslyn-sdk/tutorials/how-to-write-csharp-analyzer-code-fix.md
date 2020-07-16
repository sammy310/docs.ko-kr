---
title: '자습서: 첫 번째 분석기 및 코드 수정 작성'
description: 이 자습서에서는 .NET Complier SDK(Roslyn API)를 사용하여 분석기 및 코드 수정 사항을 빌드하는 단계별 지침을 제공합니다.
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: c70fcacc6cb30969e5c69ffd0954ac52e637a915
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100940"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="85651-103">자습서: 첫 번째 분석기 및 코드 수정 작성</span><span class="sxs-lookup"><span data-stu-id="85651-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="85651-104">.NET Compiler Platform SDK는 C# 또는 Visual Basic 코드를 대상으로 하는 사용자 지정 경고를 만드는 데 필요한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="85651-105">**분석기**에는 규칙 위반을 인식하는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="85651-106">**코드 수정 사항**에는 위반을 수정하는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="85651-107">구현하는 규칙은 코드 구조에서 코딩 스타일, 명명 규칙 등에 이를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="85651-108">.NET Compiler Platform은 개발자가 코드를 작성할 때 분석을 실행하기 위한 프레임워크와 코드를 수정하기 위한 모든 Visual Studio UI 기능(편집기에 물결선 표시, Visual Studio 오류 목록 채우기, “전구” 제안 만들기, 제안된 수정 사항의 다양한 미리 보기 표시)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="85651-109">이 자습서에서는 Roslyn API를 사용하여 **분석기** 및 함께 제공되는 **코드 수정 사항**을 만드는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="85651-110">분석기는 소스 코드 분석을 수행하고 사용자에게 문제를 보고하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="85651-111">필요한 경우 분석기는 사용자의 소스 코드에 대한 수정 사항을 나타내는 코드 수정 사항도 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="85651-112">이 자습서에서는 `const` 한정자를 사용하여 선언할 수 있는 지역 변수 선언을 찾는 분석기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="85651-113">함께 제공되는 코드 수정 사항은 해당 선언을 수정하여 `const` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85651-114">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85651-114">Prerequisites</span></span>

> [!NOTE]
> <span data-ttu-id="85651-115">현재 Visual Studio **코드 수정 사항이 포함된 분석기(.NET Standard)** 템플릿에는 알려진 버그가 있으며 Visual Studio 2019 버전 16.7에서 수정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-115">The current Visual Studio **Analyzer with code fix (.NET Standard)** template has a known bug in it and should be fixed in Visual Studio 2019 version 16.7.</span></span> <span data-ttu-id="85651-116">다음과 같이 변경되어야 템플릿의 프로젝트가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-116">The projects in the template will not compile unless the following changes are made:</span></span>
>
> 1. <span data-ttu-id="85651-117">**도구** > **옵션** > **NuGet 패키지 관리자** > **패키지 소스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-117">Select **Tools** > **Options** > **NuGet Package Manager** > **Package Sources**</span></span>
>    - <span data-ttu-id="85651-118">더하기 단추를 선택하여 새 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-118">Select the plus button, to add a new source:</span></span>
>    - <span data-ttu-id="85651-119">**소스**를 `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json`으로 설정하고 **업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-119">Set the **Source** to `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` and select **Update**</span></span>
> 1. <span data-ttu-id="85651-120">**솔루션 탐색기**에서 **MakeConst.Vsix** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **프로젝트 파일 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-120">From the **Solution Explorer**, right-click on the **MakeConst.Vsix** project, and select **Edit Project File**</span></span>
>    - <span data-ttu-id="85651-121">`<AssemblyName>` 노드를 업데이트하여 `.Visx` 접미사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-121">Update the `<AssemblyName>` node to add the `.Visx` suffix:</span></span>
>      - `<AssemblyName>MakeConst.Vsix</AssemblyName>`
>    - <span data-ttu-id="85651-122">줄 41의 `<ProjectReference>` 노드를 업데이트하여 `TargetFramework` 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-122">Update the `<ProjectReference>` node on line 41 to alter the `TargetFramework` value:</span></span>
>      - `<ProjectReference Update="@(ProjectReference)" AdditionalProperties="TargetFramework=netstandard2.0" />`
> 1. <span data-ttu-id="85651-123">*MakeConst.Test* 프로젝트에서 *MakeConstUnitTests.cs* 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-123">Update the *MakeConstUnitTests.cs* file, in the *MakeConst.Test* project:</span></span>
>    - <span data-ttu-id="85651-124">줄 9를 다음으로 변경하고 네임스페이스 변경을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-124">Change line 9 to the following, notice namespace alteration:</span></span>
>      - `using Verify = Microsoft.CodeAnalysis.CSharp.Testing.MSTest.CodeFixVerifier<`
>    - <span data-ttu-id="85651-125">줄 24를 다음 메서드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-125">Change line 24 to the following method:</span></span>
>      - `await Verify.VerifyAnalyzerAsync(test);`
>    - <span data-ttu-id="85651-126">줄 62를 다음 메서드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-126">Change line 62 to the following method:</span></span>
>      - `await Verify.VerifyCodeFixAsync(test, expected, fixtest);`

- [<span data-ttu-id="85651-127">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="85651-127">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="85651-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="85651-128">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="85651-129">Visual Studio 설치 관리자를 통해 **.NET Compiler Platform SDK**를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-129">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="85651-130">분석기를 만들고 유효성 검사하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-130">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="85651-131">솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-131">Create the solution.</span></span>
1. <span data-ttu-id="85651-132">분석기 이름 및 설명을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-132">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="85651-133">분석기 경고 및 권장 사항을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-133">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="85651-134">권장 사항을 허용하도록 코드 수정 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-134">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="85651-135">단위 테스트를 통해 분석을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-135">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="85651-136">분석기 템플릿 살펴보기</span><span class="sxs-lookup"><span data-stu-id="85651-136">Explore the analyzer template</span></span>

<span data-ttu-id="85651-137">분석기는 지역 상수로 변환할 수 있는 모든 지역 변수 선언을 사용자에게 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-137">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="85651-138">예를 들어, 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="85651-138">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="85651-139">위의 코드에서 `x`는 상수 값이 할당되고 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-139">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="85651-140">`const` 한정자를 사용하여 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-140">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="85651-141">변수를 상수로 설정할 수 있는지 여부를 판별하기 위한 분석이 포함되며, 변수가 작성되지 않는지 확인하려면 구문 분석, 상수 분석, 이니셜라이저 식의 상수 분석 및 데이터 흐름 분석이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-141">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="85651-142">.NET Compiler Platform은 이 분석을 보다 쉽게 수행할 수 있는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-142">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="85651-143">첫 번째 단계는 새로운 C# **코드 수정 사항이 포함된 분석기** 프로젝트는 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-143">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="85651-144">Visual Studio에서 **파일 > 새로 만들기 > 프로젝트...** 를 선택하여 [새 프로젝트] 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-144">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="85651-145">**Visual C# > 확장성**에서 **코드 수정 사항이 포함된 분석기(.NET Standard)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-145">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="85651-146">프로젝트 이름을 “**MakeConst**”로 지정하고 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-146">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="85651-147">코드 수정 사항 템플릿이 포함된 분석기는 세 개의 프로젝트를 만듭니다. 하나에는 분석기 및 코드 수정 사항이 포함되고, 두 번째는 단위 테스트 프로젝트이고, 세 번째는 VSIX 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-147">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="85651-148">기본 시작 프로젝트는 VSIX 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-148">The default startup project is the VSIX project.</span></span> <span data-ttu-id="85651-149"><kbd>F5</kbd> 키를 눌러 VSIX 프로젝트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-149">Press <kbd>F5</kbd> to start the VSIX project.</span></span> <span data-ttu-id="85651-150">그러면 새 분석기를 로드한 Visual Studio의 두 번째 인스턴스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-150">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="85651-151">분석기를 실행할 때 Visual Studio의 두 번째 복사본을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-151">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="85651-152">이 두 번째 복사본은 다른 레지스트리 하이브를 사용하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-152">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="85651-153">이렇게 하면 Visual Studio의 두 복사본에서 시각적 설정을 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-153">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="85651-154">Visual Studio의 실험 실행에 서로 다른 테마를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-154">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="85651-155">또한 Visual Studio의 실험 실행을 사용하여 사용자 설정 또는 로그인을 Visual Studio 계정에 로밍하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="85651-155">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="85651-156">이렇게 하면 설정이 다르게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-156">That keeps the settings different.</span></span>

<span data-ttu-id="85651-157">방금 시작한 두 번째 Visual Studio 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만듭니다(.NET Core 또는 .NET Framework 프로젝트가 작동함 - 분석기는 소스 수준에서 작동함). 물결 무늬 밑줄이 있는 토큰을 마우스로 가리키면 분석기가 제공하는 경고 텍스트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="85651-157">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="85651-158">템플릿은 다음 그림에 표시된 대로 형식 이름에 소문자가 포함된 각 형식 선언에 대한 경고를 보고하는 분석기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-158">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![분석기 보고 경고](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="85651-160">또한 템플릿은 소문자를 포함하는 형식 이름을 모두 대문자로 변경하는 코드 수정 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-160">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="85651-161">경고와 함께 표시된 전구를 클릭하여 제안된 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-161">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="85651-162">제안된 변경 내용을 적용하면 솔루션에서 형식 이름과 해당 형식에 대한 모든 참조가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-162">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="85651-163">이제 초기 분석기가 작동 중임을 확인했으므로 두 번째 Visual Studio 인스턴스를 닫고 분석기 프로젝트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="85651-163">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="85651-164">분석기의 모든 변경 내용을 테스트하기 위해 Visual Studio의 두 번째 복사본을 시작하고 새 코드를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-164">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="85651-165">템플릿은 사용자 대신 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-165">The template also creates a unit test project for you.</span></span> <span data-ttu-id="85651-166">해당 프로젝트에는 두 개의 테스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-166">That project contains two tests.</span></span> <span data-ttu-id="85651-167">`TestMethod1`은 진단을 트리거하지 않고 코드를 분석하는 테스트의 일반적인 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85651-167">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="85651-168">`TestMethod2`는 진단을 트리거하는 테스트의 형식을 보여 준 후 제안된 코드 수정 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-168">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="85651-169">분석기 및 코드 수정 사항을 빌드할 때 여러 코드 구조에 대한 테스트를 작성하여 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-169">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="85651-170">분석기에 대한 단위 테스트는 Visual Studio와 대화형으로 테스트하는 것보다 훨씬 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-170">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="85651-171">분석기 단위 테스트는 분석기를 트리거해야 하는 코드 구문과 트리거하면 안 되는 코드 구문을 알고 있을 경우 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-171">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="85651-172">Visual Studio의 또 다른 복사본에서 분석기를 로드하는 기능은 아직 고려하지 않은 구문을 탐색하고 찾는 데 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-172">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="85651-173">분석기 등록 만들기</span><span class="sxs-lookup"><span data-stu-id="85651-173">Create analyzer registrations</span></span>

<span data-ttu-id="85651-174">템플릿은 **MakeConstAnalyzer.cs** 파일에서 초기 `DiagnosticAnalyzer` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-174">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="85651-175">이 초기 분석기는 모든 분석기의 두 가지 중요한 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-175">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="85651-176">모든 진단 분석기는 사용되는 언어를 설명하는 `[DiagnosticAnalyzer]` 특성을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-176">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="85651-177">모든 진단 분석기는 <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> 클래스에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-177">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="85651-178">템플릿은 분석기의 일부인 기본 기능도 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-178">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="85651-179">작업을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-179">Register actions.</span></span> <span data-ttu-id="85651-180">작업은 코드에서 위반을 검사하기 위해 분석기를 트리거해야 하는 코드 변경을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-180">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="85651-181">Visual Studio는 등록된 작업과 일치하는 코드 편집을 검색하면 분석기의 등록된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-181">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="85651-182">진단을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-182">Create diagnostics.</span></span> <span data-ttu-id="85651-183">분석기는 위반을 검색하면 Visual Studio가 사용자에게 위반 사실을 알리는 데 사용하는 진단 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-183">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="85651-184"><xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> 메서드의 재정의에 작업을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-184">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="85651-185">이 자습서에서는 로컬 선언을 검색하는 **구문 노드**를 방문하고 그 중 상수 값이 있는 노드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-185">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="85651-186">선언이 상수일 수 있으면 분석기는 진단을 만들고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-186">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="85651-187">첫 번째 단계는 이러한 상수가 “Make Const” 분석기를 나타내도록 등록 상수 및 `Initialize` 메서드를 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-187">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="85651-188">대부분의 문자열 상수는 문자열 리소스 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-188">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="85651-189">더 쉽게 지역화하려면 해당 사례를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-189">You should follow that practice for easier localization.</span></span> <span data-ttu-id="85651-190">**MakeConst** 분석기 프로젝트에 대한 **Resources.resx** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85651-190">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="85651-191">리소스 편집기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-191">This displays the resource editor.</span></span> <span data-ttu-id="85651-192">다음과 같이 문자열 리소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-192">Update the string resources as follows:</span></span>

- <span data-ttu-id="85651-193">`AnalyzerTitle`을 “Variable can be made constant”(변수를 상수로 설정할 수 있음)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-193">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="85651-194">`AnalyzerMessageFormat`을 “Can be made constant”(상수로 설정할 수 있음)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-194">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="85651-195">`AnalyzerDescription`을 “Make Constant”(상수 만들기)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-195">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="85651-196">또한 **액세스 한정자** 드롭다운을 `public`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-196">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="85651-197">이렇게 하면 단위 테스트에서 이러한 상수를 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-197">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="85651-198">작업을 마치면 리소스 편집기가 다음 그림과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-198">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![문자열 리소스 업데이트](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="85651-200">나머지 변경 내용은 분석기 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-200">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="85651-201">Visual Studio에서 **MakeConstAnalyzer.cs**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85651-201">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="85651-202">등록된 작업을 기호에 적용되는 작업에서 구문에 적용되는 작업으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-202">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="85651-203">`MakeConstAnalyzerAnalyzer.Initialize` 메서드에서 기호에 대한 작업을 등록하는 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-203">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="85651-204">해당 줄을 다음 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-204">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="85651-205">변경한 후 `AnalyzeSymbol` 메서드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-205">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="85651-206">이 분석기는 <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> 문이 아니라 <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-206">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="85651-207">`AnalyzeNode` 아래에 빨간색 물결선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-207">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="85651-208">방금 추가한 코드는 선언되지 않은 `AnalyzeNode` 메서드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-208">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="85651-209">다음 코드를 사용하여 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-209">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="85651-210">다음 코드에 표시된 대로 **MakeConstAnalyzer.cs**에서 `Category`를 “Usage”(사용법)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-210">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="85651-211">const일 수 있는 로컬 선언 찾기</span><span class="sxs-lookup"><span data-stu-id="85651-211">Find local declarations that could be const</span></span>

<span data-ttu-id="85651-212">이제 `AnalyzeNode` 메서드의 첫 번째 버전을 작성하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-212">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="85651-213">다음 코드와 같이 `const`일 수 있지만 그렇지 않은 단일 로컬 선언을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-213">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="85651-214">첫 번째 단계는 로컬 선언을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-214">The first step is to find local declarations.</span></span> <span data-ttu-id="85651-215">**MakeConstAnalyzer.cs**에서 `AnalyzeNode`에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-215">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="85651-216">분석기는 로컬 선언의 변경 내용 및 로컬 선언만을 위해 등록되었으므로 이 캐스트는 항상 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-216">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="85651-217">다른 노드 형식은 `AnalyzeNode` 메서드 호출을 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-217">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="85651-218">그런 다음, 선언에서 `const` 한정자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-218">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="85651-219">한정자를 찾으면 즉시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-219">If you find them, return immediately.</span></span> <span data-ttu-id="85651-220">다음 코드는 로컬 선언에서 `const` 한정자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-220">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="85651-221">마지막으로 변수가 `const`일 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-221">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="85651-222">즉, 초기화된 후 절대 할당되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-222">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="85651-223"><xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>를 사용하여 몇 가지 의미 체계 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-223">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="85651-224">`context` 인수를 사용하여 지역 변수 선언을 `const`로 설정할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-224">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="85651-225"><xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType>은 단일 소스 파일에 있는 모든 의미론적 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-225">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents all of semantic information in a single source file.</span></span> <span data-ttu-id="85651-226">[의미 체계 모델](../work-with-semantics.md)을 다루는 문서에서 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-226">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="85651-227"><xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType>을 사용하여 로컬 선언 문에 대한 데이터 흐름 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-227">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="85651-228">그런 다음, 이 데이터 흐름 분석의 결과를 사용하여 지역 변수가 다른 곳에서 새 값으로 작성되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-228">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="85651-229"><xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> 확장 메서드를 호출하여 변수의 <xref:Microsoft.CodeAnalysis.ILocalSymbol>을 검색하고 해당 변수가 데이터 흐름 분석의 <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> 컬렉션에 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-229">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="85651-230">`AnalyzeNode` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-230">Add the following code to the end of the `AnalyzeNode` method:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="85651-231">방금 추가된 코드는 변수가 수정되지 않았고 이에 따라 `const`로 설정될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-231">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="85651-232">이제 진단을 실행하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-232">It's time to raise the diagnostic.</span></span> <span data-ttu-id="85651-233">다음 코드를 `AnalyzeNode`의 마지막 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-233">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="85651-234"><kbd>F5</kbd> 키를 눌러 분석기를 실행하여 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-234">You can check your progress by pressing <kbd>F5</kbd> to run your analyzer.</span></span> <span data-ttu-id="85651-235">이전에 만든 콘솔 애플리케이션을 로드한 후 다음 테스트 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-235">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="85651-236">전구가 표시되고 분석기가 진단을 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-236">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="85651-237">그러나 전구는 템플릿에서 생성된 코드 수정 사항을 계속 사용하고 대문자로 설정될 수 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85651-237">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="85651-238">다음 섹션에서는 코드 수정 사항을 작성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-238">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="85651-239">코드 수정 사항 작성</span><span class="sxs-lookup"><span data-stu-id="85651-239">Write the code fix</span></span>

<span data-ttu-id="85651-240">분석기는 하나 이상의 코드 수정 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-240">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="85651-241">코드 수정 사항은 보고된 문제를 해결하는 편집을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-241">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="85651-242">직접 작성한 분석기의 경우 const 키워드를 삽입하는 코드 수정 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-242">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="85651-243">사용자가 편집기에서 전구 UI를 선택하면 Visual Studio가 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-243">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="85651-244">템플릿에서 추가된 **MakeConstCodeFixProvider.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85651-244">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="85651-245">이 코드 수정 사항은 진단 분석기에서 생성된 진단 ID에 연결되어 있지만 아직 적합한 코드 변환을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-245">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="85651-246">먼저 일부 템플릿 코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-246">First you should remove some of the template code.</span></span> <span data-ttu-id="85651-247">제목 문자열을 “Make constant”(상수 만들기)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-247">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="85651-248">그런 다음, `MakeUppercaseAsync` 메서드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-248">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="85651-249">코드가 더 이상 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-249">It no longer applies.</span></span>

<span data-ttu-id="85651-250">모든 코드 픽스 공급자는 <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-250">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="85651-251">모두 <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType>을 재정의하여 사용 가능한 코드 수정 사항을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-251">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="85651-252">`RegisterCodeFixesAsync`에서 진단과 일치하도록 검색 중인 상위 노드 형식을 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-252">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="85651-253">그런 다음, 마지막 줄을 변경하여 코드 수정 사항을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-253">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="85651-254">이 수정은 기존 선언에 `const` 한정자를 추가함으로써 생성되는 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-254">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="85651-255">방금 추가한 기호 `MakeConstAsync`에 대한 코드에 빨간색 물결선이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-255">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="85651-256">다음 코드와 같이 `MakeConstAsync`에 대한 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-256">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="85651-257">새 `MakeConstAsync` 메서드는 사용자의 소스 파일을 나타내는 <xref:Microsoft.CodeAnalysis.Document>를 현재 `const` 선언이 포함된 새 <xref:Microsoft.CodeAnalysis.Document>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-257">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="85651-258">선언 문 앞에 삽입할 새 `const` 키워드 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-258">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="85651-259">먼저 선언 문의 첫 번째 토큰에서 선행 trivia를 제거하고 이를 `const` 토큰에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-259">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="85651-260">`MakeConstAsync` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-260">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="85651-261">그런 다음, 다음 코드를 사용하여 `const` 토큰을 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-261">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="85651-262">그런 다음, C# 형식 지정 규칙과 일치하도록 새 선언의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-262">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="85651-263">기존 코드와 일치하도록 변경 내용의 형식을 지정하면 향상된 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-263">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="85651-264">기존 코드 바로 뒤에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-264">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="85651-265">이 코드에는 새 네임스페이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-265">A new namespace is required for this code.</span></span> <span data-ttu-id="85651-266">다음 `using` 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-266">Add the following `using` directive to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="85651-267">마지막 단계는 편집을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-267">The final step is to make your edit.</span></span> <span data-ttu-id="85651-268">이 프로세스는 다음 3개 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-268">There are three steps to this process:</span></span>

1. <span data-ttu-id="85651-269">기존 문서에 대한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85651-269">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="85651-270">기존 선언을 새 선언으로 바꿔서 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-270">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="85651-271">새 문서를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-271">Return the new document.</span></span>

<span data-ttu-id="85651-272">`MakeConstAsync` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-272">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="85651-273">코드 수정 사항을 시도할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-273">Your code fix is ready to try.</span></span>  <span data-ttu-id="85651-274"><kbd>F5</kbd> 키를 눌러 Visual Studio의 두 번째 인스턴스에서 분석기 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-274">Press <kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="85651-275">Visual Studio의 두 번째 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만들고 상수 값으로 초기화된 몇 개의 지역 변수 선언을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-275">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="85651-276">아래와 같이 경고로 보고되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-276">You'll see that they are reported as warnings as below.</span></span>

![const 경고를 만들 수 있음](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="85651-278">많은 과정을 진행했습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-278">You've made a lot of progress.</span></span> <span data-ttu-id="85651-279">`const`로 설정될 수 있는 선언 아래에 물결선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-279">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="85651-280">그러나 아직 해야 할 일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-280">But there is still work to do.</span></span> <span data-ttu-id="85651-281">`i`, `j` 및 `k`로 시작하는 세 개의 선언에 순서대로 `const`를 추가하면 이 코드가 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-281">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="85651-282">그러나 `const` 한정자를 `k`부터 다른 순서로 추가하면 분석기에서 오류가 발생합니다. `i` 및 `j`가 둘 다 `const`가 될 때까지 `k`는 `const`로 선언될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-282">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="85651-283">변수를 선언하고 초기화할 수 있는 다양한 방법을 처리하도록 하려면 추가 분석을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-283">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="85651-284">데이터 기반 테스트 빌드</span><span class="sxs-lookup"><span data-stu-id="85651-284">Build data driven tests</span></span>

<span data-ttu-id="85651-285">분석기 및 코드 수정 사항은 const로 설정될 수 있는 단일 선언의 간단한 사례에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-285">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="85651-286">이 구현으로 인해 오류가 발생할 수 있는 많은 선언 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-286">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="85651-287">템플릿에서 작성된 단위 테스트 라이브러리를 사용하여 이러한 사례를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-287">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="85651-288">이 방법은 Visual Studio의 두 번째 복사본을 반복적으로 여는 것보다 훨씬 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-288">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="85651-289">단위 테스트 프로젝트에서 **MakeConstUnitTests.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85651-289">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="85651-290">템플릿은 분석기 및 코드 수정 사항 단위 테스트에 대한 두 개의 공통 패턴을 따르는 두 개의 테스트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-290">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="85651-291">`TestMethod1`은 분석기가 보고하면 안 될 때 진단을 보고하지 않는지 확인하는 테스트 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85651-291">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="85651-292">`TestMethod2`는 진단을 보고하고 코드 수정 사항을 실행하기 위한 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85651-292">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="85651-293">분석기의 거의 모든 테스트에 대한 코드는 이러한 두 패턴 중 하나를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-293">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="85651-294">첫 번째 단계에서는 이러한 테스트를 데이터 기반 테스트로 재작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-294">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="85651-295">그런 다음, 다른 테스트 입력을 나타내기 위한 새 문자열 상수를 추가하여 새 테스트를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-295">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="85651-296">효율성을 위해 첫 번째 단계는 두 테스트를 데이터 기반 테스트로 리팩터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-296">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="85651-297">그런 다음, 각각 새 테스트에 대한 두 개의 문자열 상수를 정의하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-297">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="85651-298">리팩터링하는 동안 두 메서드의 이름을 더 나은 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-298">While you are refactoring, rename both methods to better names.</span></span> <span data-ttu-id="85651-299">`TestMethod1`을 진단이 실행되지 않는지 확인하는 이 테스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-299">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="85651-300">진단이 경고를 트리거하지 않도록 해야 하는 코드 조각을 정의하여 이 테스트에 대한 새 데이터 행을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-300">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="85651-301">`VerifyCSharpDiagnostic`의 이 오버로드는 소스 코드 조각에 대해 트리거된 진단이 없는 경우에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-301">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="85651-302">다음으로, `TestMethod2`를 진단이 실행되고 소스 코드 조각에 대한 코드 수정 사항이 적용되는지 확인하는 이 테스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-302">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

<span data-ttu-id="85651-303">이전 코드에서도 예상 진단 결과를 빌드하는 두 개의 변경 내용을 코드에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-303">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="85651-304">이전 코드는 `MakeConst` 분석기에 등록된 공용 상수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-304">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="85651-305">또한 입력 및 수정된 소스에 두 개의 문자열 상수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-305">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="85651-306">`UnitTest` 클래스에 다음 문자열 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-306">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="85651-307">이러한 두 테스트를 실행하여 성공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-307">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="85651-308">Visual Studio에서 **테스트** > **Windows** > **테스트 탐색기**를 선택하여 **테스트 탐색기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85651-308">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span> <span data-ttu-id="85651-309">그런 다음, **모두 실행** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-309">Then select the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="85651-310">유효한 선언에 대한 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="85651-310">Create tests for valid declarations</span></span>

<span data-ttu-id="85651-311">일반적으로 분석기는 가능한 한 빨리 종료되어야 하므로 최소한의 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-311">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="85651-312">Visual Studio는 등록된 분석기를 사용자 편집 코드로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-312">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="85651-313">응답은 키 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-313">Responsiveness is a key requirement.</span></span> <span data-ttu-id="85651-314">진단을 실행하지 않아야 하는 코드에 대한 여러 가지 테스트 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-314">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="85651-315">분석기가 이미 이러한 테스트 중 하나를 처리합니다. 이 경우 변수는 초기화된 후에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-315">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="85651-316">다음 문자열 상수를 테스트에 추가하여 해당 사례를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85651-316">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="85651-317">그런 다음, 아래 코드 조각에 표시된 대로 이 테스트의 데이터 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-317">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="85651-318">이 테스트도 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-318">This test passes as well.</span></span> <span data-ttu-id="85651-319">다음으로, 아직 처리하지 않은 조건에 대한 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-319">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="85651-320">이미 상수이므로 이미 `const`인 선언:</span><span class="sxs-lookup"><span data-stu-id="85651-320">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="85651-321">사용할 값이 없으므로 이니셜라이저가 없는 선언:</span><span class="sxs-lookup"><span data-stu-id="85651-321">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="85651-322">컴파일 시간 상수일 수 없으므로 이니셜라이저가 상수가 아닌 선언:</span><span class="sxs-lookup"><span data-stu-id="85651-322">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="85651-323">C#은 여러 선언을 하나의 문으로 허용하므로 훨씬 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-323">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="85651-324">다음 테스트 사례 문자열 상수를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-324">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="85651-325">`i` 변수는 상수로 설정될 수 있지만, `j` 변수는 상수로 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-325">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="85651-326">따라서 이 문은 const 선언으로 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-326">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="85651-327">다음 모든 테스트에 대한 `DataRow` 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-327">Add the `DataRow` declarations for all these tests:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="85651-328">테스트를 다시 실행하면 새 테스트 사례가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-328">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="85651-329">올바른 선언을 무시하도록 분석기 업데이트</span><span class="sxs-lookup"><span data-stu-id="85651-329">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="85651-330">이러한 조건과 일치하는 코드를 필터링하려면 분석기의 `AnalyzeNode` 메서드에 대한 몇 가지 개선 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-330">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="85651-331">개선 사항은 모두 관련된 조건이므로 유사한 변경 내용이 이러한 모든 조건을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-331">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="85651-332">`AnalyzeNode`에 다음 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-332">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="85651-333">의미 체계 분석이 단일 변수 선언을 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-333">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="85651-334">이 코드는 동일한 문에 선언된 모든 변수를 검사하는 `foreach` 루프에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-334">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="85651-335">선언된 각 변수에는 이니셜라이저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-335">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="85651-336">선언된 각 변수의 이니셜라이저는 컴파일 시간 상수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-336">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="85651-337">`AnalyzeNode` 메서드에서 다음 원래 의미 체계 분석을</span><span class="sxs-lookup"><span data-stu-id="85651-337">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="85651-338">다음 코드 조각으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-338">with the following code snippet:</span></span>

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

<span data-ttu-id="85651-339">첫 번째 `foreach` 루프는 구문 분석을 사용하여 각 변수 선언을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-339">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="85651-340">첫 번째 검사는 변수에 이니셜라이저가 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-340">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="85651-341">두 번째 검사는 이니셜라이저가 상수가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-341">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="85651-342">두 번째 루프에는 원래 의미 체계 분석이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-342">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="85651-343">의미 체계 검사는 성능에 더 큰 영향을 주므로 별도의 루프에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-343">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="85651-344">테스트를 다시 실행하면 테스트가 모두 성공으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-344">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="85651-345">최종 폴란드어 추가</span><span class="sxs-lookup"><span data-stu-id="85651-345">Add the final polish</span></span>

<span data-ttu-id="85651-346">거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-346">You're almost done.</span></span> <span data-ttu-id="85651-347">분석기가 처리할 몇 가지 추가 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-347">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="85651-348">사용자가 코드를 작성하는 동안 Visual Studio가 분석기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-348">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="85651-349">분석기가 컴파일되지 않는 코드를 위해 호출되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-349">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="85651-350">진단 분석기의 `AnalyzeNode` 메서드는 상수 값이 변수 형식으로 변환될 수 있는지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-350">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="85651-351">따라서 현재 구현은 int i = "abc"'와 같은 잘못된 선언을 로컬 상수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-351">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="85651-352">해당 조건에 대한 소스 문자열 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-352">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="85651-353">또한 참조 형식이 제대로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-353">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="85651-354">참조 형식에 허용되는 유일한 상수 값은 문자열 리터럴을 허용하는 <xref:System.String?displayProperty=nameWithType>의 이 경우를 제외하고 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="85651-354">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="85651-355">즉, `const string s = "abc"`는 적합하지만 `const object s = "abc"`는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-355">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="85651-356">이 코드 조각은 해당 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-356">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="85651-357">철저하게 하려면 문자열에 대한 상수 선언을 만들 수 있는지 확인하는 또 다른 테스트를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-357">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="85651-358">다음 코드 조각은 진단을 실행하는 코드 및 수정 사항이 적용된 후의 코드를 둘 다 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-358">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="85651-359">마지막으로 변수가 `var` 키워드를 사용하여 선언된 경우 코드 수정 사항은 잘못된 작업을 수행하고 `const var` 선언을 생성하며, 이는 C# 언어에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-359">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="85651-360">이 버그를 수정하려면 코드 수정 사항이 `var` 키워드를 유추 형식 이름으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-360">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="85651-361">이러한 변경은 두 테스트에 대한 데이터 행 선언을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-361">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="85651-362">다음 코드는 모든 데이터 행 특성을 사용하여 이러한 테스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85651-362">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="85651-363">다행히도 위의 버그는 모두 방금 알아본 동일한 기술을 사용하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-363">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="85651-364">첫 번째 버그를 수정하려면 먼저 **DiagnosticAnalyzer.cs**를 열고 상수 값과 함께 할당되었는지 확인하기 위해 각 로컬 선언의 이니셜라이저가 검사되는 foreach 루프를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-364">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="85651-365">첫 번째 foreach 루프 바로 ‘앞’에서 `context.SemanticModel.GetTypeInfo()`를 호출하여 로컬 선언의 선언된 형식에 대한 자세한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-365">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="85651-366">그런 다음, `foreach` 루프 내부에서 각 이니셜라이저를 검사하여 변수 형식으로 변환할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-366">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="85651-367">이니셜라이저가 상수인지 확인한 후 다음 검사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-367">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="85651-368">다음 변경은 마지막 항목을 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-368">The next change builds upon the last one.</span></span> <span data-ttu-id="85651-369">첫 번째 foreach 루프의 닫는 중괄호 앞에 다음 코드를 추가하여 상수가 문자열 또는 null일 때 로컬 선언의 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-369">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

<span data-ttu-id="85651-370">var' 키워드를 올바른 형식 이름으로 바꾸려면 코드 수정 사항 공급자에서 약간의 코드를 추가로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-370">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="85651-371">**CodeFixProvider.cs**로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="85651-371">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="85651-372">추가할 코드는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-372">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="85651-373">선언이 `var` 선언인지, 그리고 다음과 같은지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-373">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="85651-374">유추 형식에 대한 새 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85651-374">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="85651-375">형식 선언이 별칭이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-375">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="85651-376">별칭이 아니면 `const var`을 선언하는 것이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-376">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="85651-377">`var`이 이 프로그램의 형식 이름이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-377">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="85651-378">아닌 경우 `const var`이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-378">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="85651-379">전체 형식 이름 단순화</span><span class="sxs-lookup"><span data-stu-id="85651-379">Simplify the full type name</span></span>

<span data-ttu-id="85651-380">코드가 다소 많아 보이지만</span><span class="sxs-lookup"><span data-stu-id="85651-380">That sounds like a lot of code.</span></span> <span data-ttu-id="85651-381">그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-381">It's not.</span></span> <span data-ttu-id="85651-382">`newLocal`을 선언 및 초기화하는 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85651-382">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="85651-383">코드는 `newModifiers` 초기화 바로 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="85651-383">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="85651-384"><xref:Microsoft.CodeAnalysis.Simplification.Simplifier> 형식을 사용하려면 `using` 지시문을 하나 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-384">You'll need to add one `using` directive to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="85651-385">테스트를 실행하면 모두 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-385">Run your tests, and they should all pass.</span></span> <span data-ttu-id="85651-386">완료된 분석기를 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-386">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="85651-387"><kbd>Ctrl+F5</kbd>를 눌러 Roslyn 미리 보기 확장이 로드된 Visual Studio의 두 번째 인스턴스에서 분석기 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-387">Press <kbd>Ctrl+F5</kbd> to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="85651-388">두 번째 Visual Studio 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만들고 `int x = "abc";`을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-388">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="85651-389">첫 번째 버그 수정 덕분에 이 지역 변수 선언에 대한 경고가 보고되지 않습니다(컴파일러 오류는 예상대로 발생함).</span><span class="sxs-lookup"><span data-stu-id="85651-389">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="85651-390">그런 다음, `object s = "abc";`을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-390">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="85651-391">두 번째 버그 수정으로 인해 경고가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-391">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="85651-392">마지막으로 `var` 키워드를 사용하는 다른 지역 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-392">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="85651-393">경고가 보고되고 제안이 왼쪽 바로 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-393">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="85651-394">편집기 캐럿을 물결선 위로 이동하고 <kbd>Ctrl+</kbd>를 눌러</span><span class="sxs-lookup"><span data-stu-id="85651-394">Move the editor caret over the squiggly underline and press <kbd>Ctrl+</kbd>.</span></span> <span data-ttu-id="85651-395">제안된 코드 수정 사항을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-395">to display the suggested code fix.</span></span> <span data-ttu-id="85651-396">코드 수정 사항을 선택하면 var' 키워드가 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-396">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="85651-397">마지막으로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85651-397">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="85651-398">이러한 변경 후에는 처음 두 개의 변수에만 빨간색 물결선이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-398">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="85651-399">`i` 및 `j`에 `const`를 추가합니다. `const`일 수 있으므로 `k`에 새 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85651-399">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="85651-400">지금까지</span><span class="sxs-lookup"><span data-stu-id="85651-400">Congratulations!</span></span> <span data-ttu-id="85651-401">신속한 코드 분석을 수행하여 문제를 검색하고 수정하기 위한 빠른 수정 사항을 제공하는 첫 번째 .NET Compiler Platform 확장을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-401">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="85651-402">또한 .NET Compiler Platform SDK(Roslyn API)의 일부인 많은 코드 API를 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-402">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="85651-403">샘플 GitHub 리포지토리의 [완료된 샘플](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst)을 기준으로 작업을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85651-403">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="85651-404">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="85651-404">Other resources</span></span>

- [<span data-ttu-id="85651-405">구문 분석 시작</span><span class="sxs-lookup"><span data-stu-id="85651-405">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="85651-406">의미 체계 분석 시작</span><span class="sxs-lookup"><span data-stu-id="85651-406">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
