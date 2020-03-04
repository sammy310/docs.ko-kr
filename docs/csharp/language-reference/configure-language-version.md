---
title: C# 언어 버전 관리 - C# 가이드
description: C# 언어 버전은 프로젝트에 따라 결정된다는 사실과 그 이유를 알아봅니다. 기본값을 수동으로 재정의하는 방법을 알아봅니다.
ms.date: 02/21/2020
ms.openlocfilehash: 2be76fdac471a7175b661d896b0da2910b3609f3
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626766"
---
# <a name="c-language-versioning"></a><span data-ttu-id="4921d-104">C# 언어 버전 관리</span><span class="sxs-lookup"><span data-stu-id="4921d-104">C# language versioning</span></span>

<span data-ttu-id="4921d-105">최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="4921d-106">Visual Studio는 이 값을 변경하는 UI를 제공하지 않지만, *csproj* 파일을 편집하여 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="4921d-107">기본값이 이렇게 선택되면 항상 대상 프레임워크와 호환되는 최신 언어 버전을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="4921d-108">프로젝트의 대상과 호환되는 최신 언어 기능을 이용할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="4921d-109">또한, 기본값이 이렇게 선택되면 대상 프레임워크에서 사용할 수 없는 형식이나 런타임 동작이 필요한 언어를 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="4921d-110">기본값보다 최신의 언어 버전을 선택할 경우 컴파일 시간 및 런타임 오류를 진단하기 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="4921d-111">C# 8.0(이상)은 .NET Core 3.x 및 이후 버전에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-111">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="4921d-112">대부분의 최신 기능에는 .NET Core 3.x에서 도입된 라이브러리 및 런타임 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-112">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="4921d-113">기본 인터페이스 멤버를 구현하려면 .NET Core 3.0 CLR의 새로운 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-113">Default interface member implementation requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="4921d-114">비동기 스트림에는 새로운 형식인 <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-114">Async streams require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="4921d-115">인덱스와 범위에는 새로운 형식인 <xref:System.Index?displayProperty=nameWithType> 및 <xref:System.Range?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-115">Indexes and Ranges require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="4921d-116">null 허용 참조 형식은 더 효과적인 경고를 제공하기 위해 몇 가지 [특성](../nullable-attributes.md)을 사용하는데,</span><span class="sxs-lookup"><span data-stu-id="4921d-116">Nullable reference types make use of several [attributes](../nullable-attributes.md) to provide better warnings.</span></span> <span data-ttu-id="4921d-117">이러한 특성은 .NET Core 3.0에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-117">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="4921d-118">다른 대상 프레임워크는 이러한 특성으로 주석이 추가되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-118">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="4921d-119">즉, null 허용 경고가 잠재적인 문제를 정확하게 반영하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-119">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="4921d-120">기본값</span><span class="sxs-lookup"><span data-stu-id="4921d-120">Defaults</span></span>

<span data-ttu-id="4921d-121">컴파일러는 다음 규칙에 따라 기본값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-121">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="4921d-122">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="4921d-122">Target framework</span></span>|<span data-ttu-id="4921d-123">버전</span><span class="sxs-lookup"><span data-stu-id="4921d-123">version</span></span>|<span data-ttu-id="4921d-124">C# 언어 버전 기본값</span><span class="sxs-lookup"><span data-stu-id="4921d-124">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="4921d-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="4921d-125">.NET Core</span></span>|<span data-ttu-id="4921d-126">3.x</span><span class="sxs-lookup"><span data-stu-id="4921d-126">3.x</span></span>|<span data-ttu-id="4921d-127">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="4921d-127">C# 8.0</span></span>|
|<span data-ttu-id="4921d-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="4921d-128">.NET Core</span></span>|<span data-ttu-id="4921d-129">2.x</span><span class="sxs-lookup"><span data-stu-id="4921d-129">2.x</span></span>|<span data-ttu-id="4921d-130">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="4921d-130">C# 7.3</span></span>|
|<span data-ttu-id="4921d-131">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="4921d-131">.NET Standard</span></span>|<span data-ttu-id="4921d-132">2.1</span><span class="sxs-lookup"><span data-stu-id="4921d-132">2.1</span></span>|<span data-ttu-id="4921d-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="4921d-133">C# 8.0</span></span>|
|<span data-ttu-id="4921d-134">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="4921d-134">.NET Standard</span></span>|<span data-ttu-id="4921d-135">2.0</span><span class="sxs-lookup"><span data-stu-id="4921d-135">2.0</span></span>|<span data-ttu-id="4921d-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="4921d-136">C# 7.3</span></span>|
|<span data-ttu-id="4921d-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="4921d-137">.NET Standard</span></span>|<span data-ttu-id="4921d-138">1.x</span><span class="sxs-lookup"><span data-stu-id="4921d-138">1.x</span></span>|<span data-ttu-id="4921d-139">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="4921d-139">C# 7.3</span></span>|
|<span data-ttu-id="4921d-140">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="4921d-140">.NET Framework</span></span>|<span data-ttu-id="4921d-141">모두</span><span class="sxs-lookup"><span data-stu-id="4921d-141">all</span></span>|<span data-ttu-id="4921d-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="4921d-142">C# 7.3</span></span>|

<span data-ttu-id="4921d-143">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-143">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="4921d-144">따라서 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않으면서 모든 환경에서 해당 미리 보기의 최신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-144">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="4921d-145">기본값 재정의</span><span class="sxs-lookup"><span data-stu-id="4921d-145">Override a default</span></span>

<span data-ttu-id="4921d-146">C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-146">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="4921d-147">[프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-147">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="4921d-148">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-148">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="4921d-149">[`-langversion` 컴파일러 옵션](compiler-options/langversion-compiler-option.md)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-149">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="4921d-150">프로젝트 파일 편집</span><span class="sxs-lookup"><span data-stu-id="4921d-150">Edit the project file</span></span>

<span data-ttu-id="4921d-151">프로젝트 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-151">You can set the language version in your project file.</span></span> <span data-ttu-id="4921d-152">예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-152">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="4921d-153">값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-153">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="4921d-154">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="4921d-154">Configure multiple projects</span></span>

<span data-ttu-id="4921d-155">여러 프로젝트를 구성하려면 `<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-155">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="4921d-156">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-156">You typically do that in your solution directory.</span></span> <span data-ttu-id="4921d-157">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-157">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="4921d-158">해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-158">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="4921d-159">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4921d-159">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="4921d-160">C# 언어 버전 참조</span><span class="sxs-lookup"><span data-stu-id="4921d-160">C# language version reference</span></span>

<span data-ttu-id="4921d-161">모든 표는 현재 C# 언어 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-161">The following table shows all current C# language versions.</span></span> <span data-ttu-id="4921d-162">컴파일러가 오래된 것이라면 일부 값을 파악하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-162">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="4921d-163">.NET Core 3.0 이상을 설치하면 나열된 모든 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-163">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

|<span data-ttu-id="4921d-164">값</span><span class="sxs-lookup"><span data-stu-id="4921d-164">Value</span></span>|<span data-ttu-id="4921d-165">의미</span><span class="sxs-lookup"><span data-stu-id="4921d-165">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="4921d-166">미리 보기</span><span class="sxs-lookup"><span data-stu-id="4921d-166">preview</span></span>|<span data-ttu-id="4921d-167">컴파일러가 최신 미리 보기 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-167">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="4921d-168">latest</span><span class="sxs-lookup"><span data-stu-id="4921d-168">latest</span></span>|<span data-ttu-id="4921d-169">컴파일러가 최신 릴리스 버전(부 버전 포함)의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-169">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="4921d-170">latestMajor</span><span class="sxs-lookup"><span data-stu-id="4921d-170">latestMajor</span></span>|<span data-ttu-id="4921d-171">컴파일러가 최신 릴리스 주 버전의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-171">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="4921d-172">8.0</span><span class="sxs-lookup"><span data-stu-id="4921d-172">8.0</span></span>|<span data-ttu-id="4921d-173">컴파일러는 C# 8.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-173">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="4921d-174">7.3</span><span class="sxs-lookup"><span data-stu-id="4921d-174">7.3</span></span>|<span data-ttu-id="4921d-175">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-175">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="4921d-176">7.2</span><span class="sxs-lookup"><span data-stu-id="4921d-176">7.2</span></span>|<span data-ttu-id="4921d-177">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-177">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="4921d-178">7.1</span><span class="sxs-lookup"><span data-stu-id="4921d-178">7.1</span></span>|<span data-ttu-id="4921d-179">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-179">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="4921d-180">7</span><span class="sxs-lookup"><span data-stu-id="4921d-180">7</span></span>|<span data-ttu-id="4921d-181">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-181">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="4921d-182">6</span><span class="sxs-lookup"><span data-stu-id="4921d-182">6</span></span>|<span data-ttu-id="4921d-183">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-183">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="4921d-184">5</span><span class="sxs-lookup"><span data-stu-id="4921d-184">5</span></span>|<span data-ttu-id="4921d-185">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-185">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="4921d-186">4</span><span class="sxs-lookup"><span data-stu-id="4921d-186">4</span></span>|<span data-ttu-id="4921d-187">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-187">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="4921d-188">3</span><span class="sxs-lookup"><span data-stu-id="4921d-188">3</span></span>|<span data-ttu-id="4921d-189">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-189">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="4921d-190">ISO-2</span><span class="sxs-lookup"><span data-stu-id="4921d-190">ISO-2</span></span>|<span data-ttu-id="4921d-191">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-191">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span> |
|<span data-ttu-id="4921d-192">ISO-1</span><span class="sxs-lookup"><span data-stu-id="4921d-192">ISO-1</span></span>|<span data-ttu-id="4921d-193">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4921d-193">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span> |
