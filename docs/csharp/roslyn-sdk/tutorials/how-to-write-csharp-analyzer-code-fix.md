---
title: '자습서: 첫 번째 분석기 및 코드 수정 작성'
description: 이 자습서에서는 .NET Complier SDK(Roslyn API)를 사용하여 분석기 및 코드 수정 사항을 빌드하는 단계별 지침을 제공합니다.
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: 7bd0fda9fb717a48c09aafde47f9b7f4f360c357
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837053"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="6df5d-103">자습서: 첫 번째 분석기 및 코드 수정 작성</span><span class="sxs-lookup"><span data-stu-id="6df5d-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="6df5d-104">.NET Compiler Platform SDK는 C# 또는 Visual Basic 코드를 대상으로 하는 사용자 지정 경고를 만드는 데 필요한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="6df5d-105">**분석기**에는 규칙 위반을 인식하는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="6df5d-106">**코드 수정 사항**에는 위반을 수정하는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="6df5d-107">구현하는 규칙은 코드 구조에서 코딩 스타일, 명명 규칙 등에 이를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="6df5d-108">.NET Compiler Platform은 개발자가 코드를 작성할 때 분석을 실행하기 위한 프레임워크와 코드를 수정하기 위한 모든 Visual Studio UI 기능(편집기에 물결선 표시, Visual Studio 오류 목록 채우기, “전구” 제안 만들기, 제안된 수정 사항의 다양한 미리 보기 표시)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="6df5d-109">이 자습서에서는 Roslyn API를 사용하여 **분석기** 및 함께 제공되는 **코드 수정 사항**을 만드는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="6df5d-110">분석기는 소스 코드 분석을 수행하고 사용자에게 문제를 보고하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="6df5d-111">필요한 경우 분석기는 사용자의 소스 코드에 대한 수정 사항을 나타내는 코드 수정 사항도 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="6df5d-112">이 자습서에서는 `const` 한정자를 사용하여 선언할 수 있는 지역 변수 선언을 찾는 분석기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="6df5d-113">함께 제공되는 코드 수정 사항은 해당 선언을 수정하여 `const` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6df5d-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="6df5d-114">Prerequisites</span></span>

- [<span data-ttu-id="6df5d-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6df5d-115">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="6df5d-116">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6df5d-116">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="6df5d-117">Visual Studio 설치 관리자를 통해 **.NET Compiler Platform SDK**를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-117">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="6df5d-118">분석기를 만들고 유효성 검사하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-118">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="6df5d-119">솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-119">Create the solution.</span></span>
1. <span data-ttu-id="6df5d-120">분석기 이름 및 설명을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-120">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="6df5d-121">분석기 경고 및 권장 사항을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-121">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="6df5d-122">권장 사항을 허용하도록 코드 수정 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-122">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="6df5d-123">단위 테스트를 통해 분석을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-123">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="6df5d-124">분석기 템플릿 살펴보기</span><span class="sxs-lookup"><span data-stu-id="6df5d-124">Explore the analyzer template</span></span>

<span data-ttu-id="6df5d-125">분석기는 지역 상수로 변환할 수 있는 모든 지역 변수 선언을 사용자에게 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-125">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="6df5d-126">예를 들어, 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="6df5d-126">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="6df5d-127">위의 코드에서 `x`는 상수 값이 할당되고 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-127">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="6df5d-128">`const` 한정자를 사용하여 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-128">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="6df5d-129">변수를 상수로 설정할 수 있는지 여부를 판별하기 위한 분석이 포함되며, 변수가 작성되지 않는지 확인하려면 구문 분석, 상수 분석, 이니셜라이저 식의 상수 분석 및 데이터 흐름 분석이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-129">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="6df5d-130">.NET Compiler Platform은 이 분석을 보다 쉽게 수행할 수 있는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-130">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="6df5d-131">첫 번째 단계는 새로운 C# **코드 수정 사항이 포함된 분석기** 프로젝트는 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-131">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="6df5d-132">Visual Studio에서 **파일 > 새로 만들기 > 프로젝트...** 를 선택하여 [새 프로젝트] 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-132">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="6df5d-133">**Visual C# > 확장성**에서 **코드 수정 사항이 포함된 분석기(.NET Standard)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-133">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="6df5d-134">프로젝트 이름을 “**MakeConst**”로 지정하고 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-134">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="6df5d-135">코드 수정 사항 템플릿이 포함된 분석기는 세 개의 프로젝트를 만듭니다. 하나에는 분석기 및 코드 수정 사항이 포함되고, 두 번째는 단위 테스트 프로젝트이고, 세 번째는 VSIX 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-135">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="6df5d-136">기본 시작 프로젝트는 VSIX 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-136">The default startup project is the VSIX project.</span></span> <span data-ttu-id="6df5d-137">**F5** 키를 눌러 VSIX 프로젝트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-137">Press **F5** to start the VSIX project.</span></span> <span data-ttu-id="6df5d-138">그러면 새 분석기를 로드한 Visual Studio의 두 번째 인스턴스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-138">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="6df5d-139">분석기를 실행할 때 Visual Studio의 두 번째 복사본을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-139">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="6df5d-140">이 두 번째 복사본은 다른 레지스트리 하이브를 사용하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-140">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="6df5d-141">이렇게 하면 Visual Studio의 두 복사본에서 시각적 설정을 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-141">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="6df5d-142">Visual Studio의 실험 실행에 서로 다른 테마를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-142">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="6df5d-143">또한 Visual Studio의 실험 실행을 사용하여 사용자 설정 또는 로그인을 Visual Studio 계정에 로밍하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6df5d-143">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="6df5d-144">이렇게 하면 설정이 다르게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-144">That keeps the settings different.</span></span>

<span data-ttu-id="6df5d-145">방금 시작한 두 번째 Visual Studio 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만듭니다(.NET Core 또는 .NET Framework 프로젝트가 작동함 - 분석기는 소스 수준에서 작동함). 물결 무늬 밑줄이 있는 토큰을 마우스로 가리키면 분석기가 제공하는 경고 텍스트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-145">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="6df5d-146">템플릿은 다음 그림에 표시된 대로 형식 이름에 소문자가 포함된 각 형식 선언에 대한 경고를 보고하는 분석기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-146">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![분석기 보고 경고](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="6df5d-148">또한 템플릿은 소문자를 포함하는 형식 이름을 모두 대문자로 변경하는 코드 수정 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-148">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="6df5d-149">경고와 함께 표시된 전구를 클릭하여 제안된 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-149">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="6df5d-150">제안된 변경 내용을 적용하면 솔루션에서 형식 이름과 해당 형식에 대한 모든 참조가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-150">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="6df5d-151">이제 초기 분석기가 작동 중임을 확인했으므로 두 번째 Visual Studio 인스턴스를 닫고 분석기 프로젝트로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-151">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="6df5d-152">분석기의 모든 변경 내용을 테스트하기 위해 Visual Studio의 두 번째 복사본을 시작하고 새 코드를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-152">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="6df5d-153">템플릿은 사용자 대신 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-153">The template also creates a unit test project for you.</span></span> <span data-ttu-id="6df5d-154">해당 프로젝트에는 두 개의 테스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-154">That project contains two tests.</span></span> <span data-ttu-id="6df5d-155">`TestMethod1`은 진단을 트리거하지 않고 코드를 분석하는 테스트의 일반적인 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-155">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="6df5d-156">`TestMethod2`는 진단을 트리거하는 테스트의 형식을 보여 준 후 제안된 코드 수정 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-156">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="6df5d-157">분석기 및 코드 수정 사항을 빌드할 때 여러 코드 구조에 대한 테스트를 작성하여 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-157">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="6df5d-158">분석기에 대한 단위 테스트는 Visual Studio와 대화형으로 테스트하는 것보다 훨씬 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-158">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="6df5d-159">분석기 단위 테스트는 분석기를 트리거해야 하는 코드 구문과 트리거하면 안 되는 코드 구문을 알고 있을 경우 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-159">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="6df5d-160">Visual Studio의 또 다른 복사본에서 분석기를 로드하는 기능은 아직 고려하지 않은 구문을 탐색하고 찾는 데 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-160">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="6df5d-161">분석기 등록 만들기</span><span class="sxs-lookup"><span data-stu-id="6df5d-161">Create analyzer registrations</span></span>

<span data-ttu-id="6df5d-162">템플릿은 **MakeConstAnalyzer.cs** 파일에서 초기 `DiagnosticAnalyzer` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-162">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="6df5d-163">이 초기 분석기는 모든 분석기의 두 가지 중요한 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-163">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="6df5d-164">모든 진단 분석기는 사용되는 언어를 설명하는 `[DiagnosticAnalyzer]` 특성을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-164">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="6df5d-165">모든 진단 분석기는 <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> 클래스에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-165">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="6df5d-166">템플릿은 분석기의 일부인 기본 기능도 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-166">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="6df5d-167">작업을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-167">Register actions.</span></span> <span data-ttu-id="6df5d-168">작업은 코드에서 위반을 검사하기 위해 분석기를 트리거해야 하는 코드 변경을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-168">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="6df5d-169">Visual Studio는 등록된 작업과 일치하는 코드 편집을 검색하면 분석기의 등록된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-169">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="6df5d-170">진단을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-170">Create diagnostics.</span></span> <span data-ttu-id="6df5d-171">분석기는 위반을 검색하면 Visual Studio가 사용자에게 위반 사실을 알리는 데 사용하는 진단 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-171">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="6df5d-172"><xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> 메서드의 재정의에 작업을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-172">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6df5d-173">이 자습서에서는 로컬 선언을 검색하는 **구문 노드**를 방문하고 그 중 상수 값이 있는 노드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-173">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="6df5d-174">선언이 상수일 수 있으면 분석기는 진단을 만들고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-174">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="6df5d-175">첫 번째 단계는 이러한 상수가 “Make Const” 분석기를 나타내도록 등록 상수 및 `Initialize` 메서드를 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-175">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="6df5d-176">대부분의 문자열 상수는 문자열 리소스 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-176">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="6df5d-177">더 쉽게 지역화하려면 해당 사례를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-177">You should follow that practice for easier localization.</span></span> <span data-ttu-id="6df5d-178">**MakeConst** 분석기 프로젝트에 대한 **Resources.resx** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-178">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="6df5d-179">리소스 편집기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-179">This displays the resource editor.</span></span> <span data-ttu-id="6df5d-180">다음과 같이 문자열 리소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-180">Update the string resources as follows:</span></span>

- <span data-ttu-id="6df5d-181">`AnalyzerTitle`을 “Variable can be made constant”(변수를 상수로 설정할 수 있음)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-181">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="6df5d-182">`AnalyzerMessageFormat`을 “Can be made constant”(상수로 설정할 수 있음)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-182">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="6df5d-183">`AnalyzerDescription`을 “Make Constant”(상수 만들기)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-183">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="6df5d-184">또한 **액세스 한정자** 드롭다운을 `public`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-184">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="6df5d-185">이렇게 하면 단위 테스트에서 이러한 상수를 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-185">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="6df5d-186">작업을 마치면 리소스 편집기가 다음 그림과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-186">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![문자열 리소스 업데이트](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="6df5d-188">나머지 변경 내용은 분석기 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-188">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="6df5d-189">Visual Studio에서 **MakeConstAnalyzer.cs**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-189">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="6df5d-190">등록된 작업을 기호에 적용되는 작업에서 구문에 적용되는 작업으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-190">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="6df5d-191">`MakeConstAnalyzerAnalyzer.Initialize` 메서드에서 기호에 대한 작업을 등록하는 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-191">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="6df5d-192">해당 줄을 다음 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-192">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="6df5d-193">변경한 후 `AnalyzeSymbol` 메서드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-193">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="6df5d-194">이 분석기는 <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> 문이 아니라 <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-194">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="6df5d-195">`AnalyzeNode` 아래에 빨간색 물결선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-195">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="6df5d-196">방금 추가한 코드는 선언되지 않은 `AnalyzeNode` 메서드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-196">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="6df5d-197">다음 코드를 사용하여 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-197">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="6df5d-198">다음 코드에 표시된 대로 **MakeConstAnalyzer.cs**에서 `Category`를 “Usage”(사용법)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-198">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="6df5d-199">const일 수 있는 로컬 선언 찾기</span><span class="sxs-lookup"><span data-stu-id="6df5d-199">Find local declarations that could be const</span></span>

<span data-ttu-id="6df5d-200">이제 `AnalyzeNode` 메서드의 첫 번째 버전을 작성하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-200">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="6df5d-201">다음 코드와 같이 `const`일 수 있지만 그렇지 않은 단일 로컬 선언을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-201">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="6df5d-202">첫 번째 단계는 로컬 선언을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-202">The first step is to find local declarations.</span></span> <span data-ttu-id="6df5d-203">**MakeConstAnalyzer.cs**에서 `AnalyzeNode`에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-203">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="6df5d-204">분석기는 로컬 선언의 변경 내용 및 로컬 선언만을 위해 등록되었으므로 이 캐스트는 항상 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-204">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="6df5d-205">다른 노드 형식은 `AnalyzeNode` 메서드 호출을 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-205">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="6df5d-206">그런 다음, 선언에서 `const` 한정자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-206">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="6df5d-207">한정자를 찾으면 즉시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-207">If you find them, return immediately.</span></span> <span data-ttu-id="6df5d-208">다음 코드는 로컬 선언에서 `const` 한정자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-208">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="6df5d-209">마지막으로 변수가 `const`일 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-209">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="6df5d-210">즉, 초기화된 후 절대 할당되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-210">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="6df5d-211"><xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>를 사용하여 몇 가지 의미 체계 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-211">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="6df5d-212">`context` 인수를 사용하여 지역 변수 선언을 `const`로 설정할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-212">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="6df5d-213"><xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType>은 단일 소스 파일에 있는 모든 의미 체계 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-213">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents of all semantic information in a single source file.</span></span> <span data-ttu-id="6df5d-214">[의미 체계 모델](../work-with-semantics.md)을 다루는 문서에서 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-214">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="6df5d-215"><xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType>을 사용하여 로컬 선언 문에 대한 데이터 흐름 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-215">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="6df5d-216">그런 다음, 이 데이터 흐름 분석의 결과를 사용하여 지역 변수가 다른 곳에서 새 값으로 작성되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-216">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="6df5d-217"><xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> 확장 메서드를 호출하여 변수의 <xref:Microsoft.CodeAnalysis.ILocalSymbol>을 검색하고 해당 변수가 데이터 흐름 분석의 <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> 컬렉션에 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-217">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="6df5d-218">`AnalyzeNode` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-218">Add the following code to the end of the `AnalyzeNode` method:</span></span>

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

<span data-ttu-id="6df5d-219">방금 추가된 코드는 변수가 수정되지 않았고 이에 따라 `const`로 설정될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-219">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="6df5d-220">이제 진단을 실행하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-220">It's time to raise the diagnostic.</span></span> <span data-ttu-id="6df5d-221">다음 코드를 `AnalyzeNode`의 마지막 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-221">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="6df5d-222">**F5** 키를 눌러 분석기를 실행하여 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-222">You can check your progress by pressing **F5** to run your analyzer.</span></span> <span data-ttu-id="6df5d-223">이전에 만든 콘솔 애플리케이션을 로드한 후 다음 테스트 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-223">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="6df5d-224">전구가 표시되고 분석기가 진단을 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-224">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="6df5d-225">그러나 전구는 템플릿에서 생성된 코드 수정 사항을 계속 사용하고 대문자로 설정될 수 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-225">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="6df5d-226">다음 섹션에서는 코드 수정 사항을 작성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-226">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="6df5d-227">코드 수정 사항 작성</span><span class="sxs-lookup"><span data-stu-id="6df5d-227">Write the code fix</span></span>

<span data-ttu-id="6df5d-228">분석기는 하나 이상의 코드 수정 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-228">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="6df5d-229">코드 수정 사항은 보고된 문제를 해결하는 편집을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-229">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="6df5d-230">직접 작성한 분석기의 경우 const 키워드를 삽입하는 코드 수정 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-230">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="6df5d-231">사용자가 편집기에서 전구 UI를 선택하면 Visual Studio가 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-231">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="6df5d-232">템플릿에서 추가된 **MakeConstCodeFixProvider.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-232">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="6df5d-233">이 코드 수정 사항은 진단 분석기에서 생성된 진단 ID에 연결되어 있지만 아직 적합한 코드 변환을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-233">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="6df5d-234">먼저 일부 템플릿 코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-234">First you should remove some of the template code.</span></span> <span data-ttu-id="6df5d-235">제목 문자열을 “Make constant”(상수 만들기)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-235">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="6df5d-236">그런 다음, `MakeUppercaseAsync` 메서드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-236">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="6df5d-237">코드가 더 이상 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-237">It no longer applies.</span></span>

<span data-ttu-id="6df5d-238">모든 코드 픽스 공급자는 <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-238">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="6df5d-239">모두 <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType>을 재정의하여 사용 가능한 코드 수정 사항을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-239">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="6df5d-240">`RegisterCodeFixesAsync`에서 진단과 일치하도록 검색 중인 상위 노드 형식을 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-240">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="6df5d-241">그런 다음, 마지막 줄을 변경하여 코드 수정 사항을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-241">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="6df5d-242">이 수정은 기존 선언에 `const` 한정자를 추가함으로써 생성되는 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-242">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="6df5d-243">방금 추가한 기호 `MakeConstAsync`에 대한 코드에 빨간색 물결선이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-243">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="6df5d-244">다음 코드와 같이 `MakeConstAsync`에 대한 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-244">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="6df5d-245">새 `MakeConstAsync` 메서드는 사용자의 소스 파일을 나타내는 <xref:Microsoft.CodeAnalysis.Document>를 현재 `const` 선언이 포함된 새 <xref:Microsoft.CodeAnalysis.Document>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-245">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="6df5d-246">선언 문 앞에 삽입할 새 `const` 키워드 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-246">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="6df5d-247">먼저 선언 문의 첫 번째 토큰에서 선행 trivia를 제거하고 이를 `const` 토큰에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-247">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="6df5d-248">`MakeConstAsync` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-248">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="6df5d-249">그런 다음, 다음 코드를 사용하여 `const` 토큰을 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-249">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="6df5d-250">그런 다음, C# 형식 지정 규칙과 일치하도록 새 선언의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-250">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="6df5d-251">기존 코드와 일치하도록 변경 내용의 형식을 지정하면 향상된 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-251">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="6df5d-252">기존 코드 바로 뒤에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-252">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="6df5d-253">이 코드에는 새 네임스페이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-253">A new namespace is required for this code.</span></span> <span data-ttu-id="6df5d-254">다음 `using` 문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-254">Add the following `using` statement to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="6df5d-255">마지막 단계는 편집을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-255">The final step is to make your edit.</span></span> <span data-ttu-id="6df5d-256">이 프로세스는 다음 3개 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-256">There are three steps to this process:</span></span>

1. <span data-ttu-id="6df5d-257">기존 문서에 대한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-257">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="6df5d-258">기존 선언을 새 선언으로 바꿔서 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-258">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="6df5d-259">새 문서를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-259">Return the new document.</span></span>

<span data-ttu-id="6df5d-260">`MakeConstAsync` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-260">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="6df5d-261">코드 수정 사항을 시도할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-261">Your code fix is ready to try.</span></span>  <span data-ttu-id="6df5d-262">F5 키를 눌러 Visual Studio의 두 번째 인스턴스에서 분석기 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-262">Press F5 to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="6df5d-263">Visual Studio의 두 번째 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만들고 상수 값으로 초기화된 몇 개의 지역 변수 선언을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-263">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="6df5d-264">아래와 같이 경고로 보고되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-264">You'll see that they are reported as warnings as below.</span></span>

![const 경고를 만들 수 있음](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="6df5d-266">많은 과정을 진행했습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-266">You've made a lot of progress.</span></span> <span data-ttu-id="6df5d-267">`const`로 설정될 수 있는 선언 아래에 물결선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-267">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="6df5d-268">그러나 아직 해야 할 일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-268">But there is still work to do.</span></span> <span data-ttu-id="6df5d-269">`i`, `j` 및 `k`로 시작하는 세 개의 선언에 순서대로 `const`를 추가하면 이 코드가 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-269">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="6df5d-270">그러나 `const` 한정자를 `k`부터 다른 순서로 추가하면 분석기에서 오류가 발생합니다. `i` 및 `j`가 둘 다 `const`가 될 때까지 `k`는 `const`로 선언될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-270">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="6df5d-271">변수를 선언하고 초기화할 수 있는 다양한 방법을 처리하도록 하려면 추가 분석을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-271">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="6df5d-272">데이터 기반 테스트 빌드</span><span class="sxs-lookup"><span data-stu-id="6df5d-272">Build data driven tests</span></span>

<span data-ttu-id="6df5d-273">분석기 및 코드 수정 사항은 const로 설정될 수 있는 단일 선언의 간단한 사례에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-273">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="6df5d-274">이 구현으로 인해 오류가 발생할 수 있는 많은 선언 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-274">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="6df5d-275">템플릿에서 작성된 단위 테스트 라이브러리를 사용하여 이러한 사례를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-275">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="6df5d-276">이 방법은 Visual Studio의 두 번째 복사본을 반복적으로 여는 것보다 훨씬 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-276">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="6df5d-277">단위 테스트 프로젝트에서 **MakeConstUnitTests.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-277">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="6df5d-278">템플릿은 분석기 및 코드 수정 사항 단위 테스트에 대한 두 개의 공통 패턴을 따르는 두 개의 테스트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-278">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="6df5d-279">`TestMethod1`은 분석기가 보고하면 안 될 때 진단을 보고하지 않는지 확인하는 테스트 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-279">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="6df5d-280">`TestMethod2`는 진단을 보고하고 코드 수정 사항을 실행하기 위한 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-280">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="6df5d-281">분석기의 거의 모든 테스트에 대한 코드는 이러한 두 패턴 중 하나를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-281">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="6df5d-282">첫 번째 단계에서는 이러한 테스트를 데이터 기반 테스트로 재작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-282">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="6df5d-283">그런 다음, 다른 테스트 입력을 나타내기 위한 새 문자열 상수를 추가하여 새 테스트를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-283">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="6df5d-284">효율성을 위해 첫 번째 단계는 두 테스트를 데이터 기반 테스트로 리팩터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-284">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="6df5d-285">그런 다음, 각각 새 테스트에 대한 두 개의 문자열 상수를 정의하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-285">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="6df5d-286">리팩터링하는 동안 두 메서드의 이름을 더 나은 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-286">While your refactoring, rename both methods to better names.</span></span> <span data-ttu-id="6df5d-287">`TestMethod1`을 진단이 실행되지 않는지 확인하는 이 테스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-287">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="6df5d-288">진단이 경고를 트리거하지 않도록 해야 하는 코드 조각을 정의하여 이 테스트에 대한 새 데이터 행을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-288">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="6df5d-289">`VerifyCSharpDiagnostic`의 이 오버로드는 소스 코드 조각에 대해 트리거된 진단이 없는 경우에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-289">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="6df5d-290">다음으로, `TestMethod2`를 진단이 실행되고 소스 코드 조각에 대한 코드 수정 사항이 적용되는지 확인하는 이 테스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-290">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

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

<span data-ttu-id="6df5d-291">이전 코드에서도 예상 진단 결과를 빌드하는 두 개의 변경 내용을 코드에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-291">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="6df5d-292">이전 코드는 `MakeConst` 분석기에 등록된 공용 상수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-292">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="6df5d-293">또한 입력 및 수정된 소스에 두 개의 문자열 상수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-293">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="6df5d-294">`UnitTest` 클래스에 다음 문자열 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-294">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="6df5d-295">이러한 두 테스트를 실행하여 성공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-295">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="6df5d-296">Visual Studio에서 **테스트** > **Windows** > **테스트 탐색기**를 선택하여 **테스트 탐색기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-296">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span>  <span data-ttu-id="6df5d-297">**모두 실행** 링크를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-297">The press the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="6df5d-298">유효한 선언에 대한 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="6df5d-298">Create tests for valid declarations</span></span>

<span data-ttu-id="6df5d-299">일반적으로 분석기는 가능한 한 빨리 종료되어야 하므로 최소한의 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-299">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="6df5d-300">Visual Studio는 등록된 분석기를 사용자 편집 코드로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-300">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="6df5d-301">응답은 키 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-301">Responsiveness is a key requirement.</span></span> <span data-ttu-id="6df5d-302">진단을 실행하지 않아야 하는 코드에 대한 여러 가지 테스트 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-302">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="6df5d-303">분석기가 이미 이러한 테스트 중 하나를 처리합니다. 이 경우 변수는 초기화된 후에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-303">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="6df5d-304">다음 문자열 상수를 테스트에 추가하여 해당 사례를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-304">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="6df5d-305">그런 다음, 아래 코드 조각에 표시된 대로 이 테스트의 데이터 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-305">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="6df5d-306">이 테스트도 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-306">This test passes as well.</span></span> <span data-ttu-id="6df5d-307">다음으로, 아직 처리하지 않은 조건에 대한 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-307">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="6df5d-308">이미 상수이므로 이미 `const`인 선언:</span><span class="sxs-lookup"><span data-stu-id="6df5d-308">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="6df5d-309">사용할 값이 없으므로 이니셜라이저가 없는 선언:</span><span class="sxs-lookup"><span data-stu-id="6df5d-309">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="6df5d-310">컴파일 시간 상수일 수 없으므로 이니셜라이저가 상수가 아닌 선언:</span><span class="sxs-lookup"><span data-stu-id="6df5d-310">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="6df5d-311">C#은 여러 선언을 하나의 문으로 허용하므로 훨씬 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-311">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="6df5d-312">다음 테스트 사례 문자열 상수를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-312">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="6df5d-313">`i` 변수는 상수로 설정될 수 있지만, `j` 변수는 상수로 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-313">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="6df5d-314">따라서 이 문은 const 선언으로 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-314">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="6df5d-315">다음 모든 테스트에 대한 `DataRow` 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-315">Add the `DataRow` declarations for all these tests:</span></span>

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

<span data-ttu-id="6df5d-316">테스트를 다시 실행하면 새 테스트 사례가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-316">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="6df5d-317">올바른 선언을 무시하도록 분석기 업데이트</span><span class="sxs-lookup"><span data-stu-id="6df5d-317">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="6df5d-318">이러한 조건과 일치하는 코드를 필터링하려면 분석기의 `AnalyzeNode` 메서드에 대한 몇 가지 개선 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-318">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="6df5d-319">개선 사항은 모두 관련된 조건이므로 유사한 변경 내용이 이러한 모든 조건을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-319">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="6df5d-320">`AnalyzeNode`에 다음 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-320">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="6df5d-321">의미 체계 분석이 단일 변수 선언을 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-321">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="6df5d-322">이 코드는 동일한 문에 선언된 모든 변수를 검사하는 `foreach` 루프에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-322">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="6df5d-323">선언된 각 변수에는 이니셜라이저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-323">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="6df5d-324">선언된 각 변수의 이니셜라이저는 컴파일 시간 상수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-324">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="6df5d-325">`AnalyzeNode` 메서드에서 다음 원래 의미 체계 분석을</span><span class="sxs-lookup"><span data-stu-id="6df5d-325">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

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

<span data-ttu-id="6df5d-326">다음 코드 조각으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-326">with the following code snippet:</span></span>

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

<span data-ttu-id="6df5d-327">첫 번째 `foreach` 루프는 구문 분석을 사용하여 각 변수 선언을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-327">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="6df5d-328">첫 번째 검사는 변수에 이니셜라이저가 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-328">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="6df5d-329">두 번째 검사는 이니셜라이저가 상수가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-329">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="6df5d-330">두 번째 루프에는 원래 의미 체계 분석이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-330">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="6df5d-331">의미 체계 검사는 성능에 더 큰 영향을 주므로 별도의 루프에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-331">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="6df5d-332">테스트를 다시 실행하면 테스트가 모두 성공으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-332">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="6df5d-333">최종 폴란드어 추가</span><span class="sxs-lookup"><span data-stu-id="6df5d-333">Add the final polish</span></span>

<span data-ttu-id="6df5d-334">거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-334">You're almost done.</span></span> <span data-ttu-id="6df5d-335">분석기가 처리할 몇 가지 추가 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-335">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="6df5d-336">사용자가 코드를 작성하는 동안 Visual Studio가 분석기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-336">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="6df5d-337">분석기가 컴파일되지 않는 코드를 위해 호출되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-337">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="6df5d-338">진단 분석기의 `AnalyzeNode` 메서드는 상수 값이 변수 형식으로 변환될 수 있는지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-338">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="6df5d-339">따라서 현재 구현은 int i = "abc"'와 같은 잘못된 선언을 로컬 상수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-339">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="6df5d-340">해당 조건에 대한 소스 문자열 상수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-340">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="6df5d-341">또한 참조 형식이 제대로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-341">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="6df5d-342">참조 형식에 허용되는 유일한 상수 값은 문자열 리터럴을 허용하는 <xref:System.String?displayProperty=nameWithType>의 이 경우를 제외하고 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-342">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="6df5d-343">즉, `const string s = "abc"`는 적합하지만 `const object s = "abc"`는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-343">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="6df5d-344">이 코드 조각은 해당 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-344">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="6df5d-345">철저하게 하려면 문자열에 대한 상수 선언을 만들 수 있는지 확인하는 또 다른 테스트를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-345">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="6df5d-346">다음 코드 조각은 진단을 실행하는 코드 및 수정 사항이 적용된 후의 코드를 둘 다 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-346">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="6df5d-347">마지막으로 변수가 `var` 키워드를 사용하여 선언된 경우 코드 수정 사항은 잘못된 작업을 수행하고 `const var` 선언을 생성하며, 이는 C# 언어에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-347">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="6df5d-348">이 버그를 수정하려면 코드 수정 사항이 `var` 키워드를 유추 형식 이름으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-348">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="6df5d-349">이러한 변경은 두 테스트에 대한 데이터 행 선언을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-349">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="6df5d-350">다음 코드는 모든 데이터 행 특성을 사용하여 이러한 테스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-350">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="6df5d-351">다행히도 위의 버그는 모두 방금 알아본 동일한 기술을 사용하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-351">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="6df5d-352">첫 번째 버그를 수정하려면 먼저 **DiagnosticAnalyzer.cs**를 열고 상수 값과 함께 할당되었는지 확인하기 위해 각 로컬 선언의 이니셜라이저가 검사되는 foreach 루프를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-352">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="6df5d-353">첫 번째 foreach 루프 바로 ‘앞’에서 `context.SemanticModel.GetTypeInfo()`를 호출하여 로컬 선언의 선언된 형식에 대한 자세한 정보를 검색합니다. </span><span class="sxs-lookup"><span data-stu-id="6df5d-353">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="6df5d-354">그런 다음, `foreach` 루프 내부에서 각 이니셜라이저를 검사하여 변수 형식으로 변환할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-354">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="6df5d-355">이니셜라이저가 상수인지 확인한 후 다음 검사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-355">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="6df5d-356">다음 변경은 마지막 항목을 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-356">The next change builds upon the last one.</span></span> <span data-ttu-id="6df5d-357">첫 번째 foreach 루프의 닫는 중괄호 앞에 다음 코드를 추가하여 상수가 문자열 또는 null일 때 로컬 선언의 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-357">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

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

<span data-ttu-id="6df5d-358">var' 키워드를 올바른 형식 이름으로 바꾸려면 코드 수정 사항 공급자에서 약간의 코드를 추가로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-358">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="6df5d-359">**CodeFixProvider.cs**로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-359">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="6df5d-360">추가할 코드는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-360">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="6df5d-361">선언이 `var` 선언인지, 그리고 다음과 같은지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-361">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="6df5d-362">유추 형식에 대한 새 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-362">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="6df5d-363">형식 선언이 별칭이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-363">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="6df5d-364">별칭이 아니면 `const var`을 선언하는 것이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-364">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="6df5d-365">`var`이 이 프로그램의 형식 이름이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-365">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="6df5d-366">아닌 경우 `const var`이 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-366">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="6df5d-367">전체 형식 이름 단순화</span><span class="sxs-lookup"><span data-stu-id="6df5d-367">Simplify the full type name</span></span>

<span data-ttu-id="6df5d-368">코드가 다소 많아 보이지만</span><span class="sxs-lookup"><span data-stu-id="6df5d-368">That sounds like a lot of code.</span></span> <span data-ttu-id="6df5d-369">그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-369">It's not.</span></span> <span data-ttu-id="6df5d-370">`newLocal`을 선언 및 초기화하는 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-370">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="6df5d-371">코드는 `newModifiers` 초기화 바로 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-371">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="6df5d-372"><xref:Microsoft.CodeAnalysis.Simplification.Simplifier> 형식을 사용하려면 하나의 `using` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-372">You'll need to add one `using` statement to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="6df5d-373">테스트를 실행하면 모두 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-373">Run your tests, and they should all pass.</span></span> <span data-ttu-id="6df5d-374">완료된 분석기를 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-374">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="6df5d-375">Ctrl+F5를 눌러 Roslyn 미리 보기 확장이 로드된 Visual Studio의 두 번째 인스턴스에서 분석기 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-375">Press Ctrl+F5 to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="6df5d-376">두 번째 Visual Studio 인스턴스에서 새 C# 콘솔 애플리케이션 프로젝트를 만들고 `int x = "abc";`을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-376">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="6df5d-377">첫 번째 버그 수정 덕분에 이 지역 변수 선언에 대한 경고가 보고되지 않습니다(컴파일러 오류는 예상대로 발생함).</span><span class="sxs-lookup"><span data-stu-id="6df5d-377">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="6df5d-378">그런 다음, `object s = "abc";`을 Main 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-378">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="6df5d-379">두 번째 버그 수정으로 인해 경고가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-379">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="6df5d-380">마지막으로 `var` 키워드를 사용하는 다른 지역 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-380">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="6df5d-381">경고가 보고되고 제안이 왼쪽 바로 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-381">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="6df5d-382">편집기 캐럿을 물결선 위로 이동하고 Ctrl+.를 눌러</span><span class="sxs-lookup"><span data-stu-id="6df5d-382">Move the editor caret over the squiggly underline and press Ctrl+.</span></span> <span data-ttu-id="6df5d-383">제안된 코드 수정 사항을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-383">to display the suggested code fix.</span></span> <span data-ttu-id="6df5d-384">코드 수정 사항을 선택하면 var' 키워드가 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-384">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="6df5d-385">마지막으로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-385">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="6df5d-386">이러한 변경 후에는 처음 두 개의 변수에만 빨간색 물결선이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-386">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="6df5d-387">`i` 및 `j`에 `const`를 추가합니다. `const`일 수 있으므로 `k`에 새 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-387">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="6df5d-388">지금까지</span><span class="sxs-lookup"><span data-stu-id="6df5d-388">Congratulations!</span></span> <span data-ttu-id="6df5d-389">신속한 코드 분석을 수행하여 문제를 검색하고 수정하기 위한 빠른 수정 사항을 제공하는 첫 번째 .NET Compiler Platform 확장을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-389">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="6df5d-390">또한 .NET Compiler Platform SDK(Roslyn API)의 일부인 많은 코드 API를 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-390">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="6df5d-391">샘플 GitHub 리포지토리의 [완료된 샘플](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst)을 기준으로 작업을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-391">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span> <span data-ttu-id="6df5d-392">또는 [완료된 프로젝트의 zip 파일](https://github.com/dotnet/samples/blob/master/csharp/roslyn-sdk/Tutorials/MakeConst.zip)을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df5d-392">Or you can download [zip file of the completed project](https://github.com/dotnet/samples/blob/master/csharp/roslyn-sdk/Tutorials/MakeConst.zip)</span></span>

## <a name="other-resources"></a><span data-ttu-id="6df5d-393">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="6df5d-393">Other resources</span></span>

- [<span data-ttu-id="6df5d-394">구문 분석 시작</span><span class="sxs-lookup"><span data-stu-id="6df5d-394">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="6df5d-395">의미 체계 분석 시작</span><span class="sxs-lookup"><span data-stu-id="6df5d-395">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
