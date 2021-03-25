---
title: C# 언어 버전 관리 - C# 가이드
description: C# 언어 버전은 프로젝트에 따라 결정된다는 사실과 그 이유를 알아봅니다. 기본값을 수동으로 재정의하는 방법을 알아봅니다.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: e1b5848f5cd589b0ea61518f0b19efb8fe801337
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477456"
---
# <a name="c-language-versioning"></a><span data-ttu-id="a97e3-104">C# 언어 버전 관리</span><span class="sxs-lookup"><span data-stu-id="a97e3-104">C# language versioning</span></span>

<span data-ttu-id="a97e3-105">최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="a97e3-106">Visual Studio는 이 값을 변경하는 UI를 제공하지 않지만, *csproj* 파일을 편집하여 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="a97e3-107">기본값이 이렇게 선택되면 항상 대상 프레임워크와 호환되는 최신 언어 버전을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="a97e3-108">프로젝트의 대상과 호환되는 최신 언어 기능을 이용할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="a97e3-109">또한, 기본값이 이렇게 선택되면 대상 프레임워크에서 사용할 수 없는 형식이나 런타임 동작이 필요한 언어를 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="a97e3-110">기본값보다 최신의 언어 버전을 선택할 경우 컴파일 시간 및 런타임 오류를 진단하기 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="a97e3-111">이 문서의 규칙은 Visual Studio 2019 또는 .NET SDK와 함께 제공되는 컴파일러에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET SDK.</span></span> <span data-ttu-id="a97e3-112">Visual Studio 2017 설치 또는 이전 .NET Core SDK 버전의 일부인 C# 컴파일러는 기본적으로 C# 7.0을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="a97e3-113">C# 8.0은 .NET Core 3.x 이상 버전에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-113">C# 8.0 is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="a97e3-114">대부분의 최신 기능에는 .NET Core 3.x에서 도입된 라이브러리 및 런타임 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="a97e3-115">[기본 인터페이스 구현](../whats-new/csharp-8.md#default-interface-methods)에는 .NET Core 3.0 CLR의 새로운 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="a97e3-116">[비동기 스트림](../whats-new/csharp-8.md#asynchronous-streams)에는 새로운 형식인 <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="a97e3-117">[인덱스 및 범위](../whats-new/csharp-8.md#indices-and-ranges)에는 새로운 형식인 <xref:System.Index?displayProperty=nameWithType> 및 <xref:System.Range?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="a97e3-118">[Nulle 허용 참조 형식](../whats-new/csharp-8.md#nullable-reference-types)은 더 효과적인 경고를 제공하기 위해 몇 가지 [특성](attributes/nullable-analysis.md)을 사용하는데,</span><span class="sxs-lookup"><span data-stu-id="a97e3-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="a97e3-119">이러한 특성은 .NET Core 3.0에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="a97e3-120">다른 대상 프레임워크는 이러한 특성으로 주석이 추가되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="a97e3-121">즉, null 허용 경고가 잠재적인 문제를 정확하게 반영하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

<span data-ttu-id="a97e3-122">C# 9.0은 .NET 5 이상 버전에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-122">C# 9.0 is supported only on .NET 5 and newer versions.</span></span>

## <a name="defaults"></a><span data-ttu-id="a97e3-123">기본값</span><span class="sxs-lookup"><span data-stu-id="a97e3-123">Defaults</span></span>

<span data-ttu-id="a97e3-124">컴파일러는 다음 규칙에 따라 기본값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-124">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="a97e3-125">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="a97e3-125">Target framework</span></span> | <span data-ttu-id="a97e3-126">버전</span><span class="sxs-lookup"><span data-stu-id="a97e3-126">version</span></span> | <span data-ttu-id="a97e3-127">C# 언어 버전 기본값</span><span class="sxs-lookup"><span data-stu-id="a97e3-127">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="a97e3-128">.NET</span><span class="sxs-lookup"><span data-stu-id="a97e3-128">.NET</span></span>             | <span data-ttu-id="a97e3-129">5.x</span><span class="sxs-lookup"><span data-stu-id="a97e3-129">5.x</span></span>     | <span data-ttu-id="a97e3-130">C# 9.0</span><span class="sxs-lookup"><span data-stu-id="a97e3-130">C# 9.0</span></span>                      |
| <span data-ttu-id="a97e3-131">.NET Core</span><span class="sxs-lookup"><span data-stu-id="a97e3-131">.NET Core</span></span>        | <span data-ttu-id="a97e3-132">3.x</span><span class="sxs-lookup"><span data-stu-id="a97e3-132">3.x</span></span>     | <span data-ttu-id="a97e3-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="a97e3-133">C# 8.0</span></span>                      |
| <span data-ttu-id="a97e3-134">.NET Core</span><span class="sxs-lookup"><span data-stu-id="a97e3-134">.NET Core</span></span>        | <span data-ttu-id="a97e3-135">2.x</span><span class="sxs-lookup"><span data-stu-id="a97e3-135">2.x</span></span>     | <span data-ttu-id="a97e3-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a97e3-136">C# 7.3</span></span>                      |
| <span data-ttu-id="a97e3-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a97e3-137">.NET Standard</span></span>    | <span data-ttu-id="a97e3-138">2.1</span><span class="sxs-lookup"><span data-stu-id="a97e3-138">2.1</span></span>     | <span data-ttu-id="a97e3-139">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="a97e3-139">C# 8.0</span></span>                      |
| <span data-ttu-id="a97e3-140">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a97e3-140">.NET Standard</span></span>    | <span data-ttu-id="a97e3-141">2.0</span><span class="sxs-lookup"><span data-stu-id="a97e3-141">2.0</span></span>     | <span data-ttu-id="a97e3-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a97e3-142">C# 7.3</span></span>                      |
| <span data-ttu-id="a97e3-143">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a97e3-143">.NET Standard</span></span>    | <span data-ttu-id="a97e3-144">1.x</span><span class="sxs-lookup"><span data-stu-id="a97e3-144">1.x</span></span>     | <span data-ttu-id="a97e3-145">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a97e3-145">C# 7.3</span></span>                      |
| <span data-ttu-id="a97e3-146">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a97e3-146">.NET Framework</span></span>   | <span data-ttu-id="a97e3-147">모두</span><span class="sxs-lookup"><span data-stu-id="a97e3-147">all</span></span>     | <span data-ttu-id="a97e3-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a97e3-148">C# 7.3</span></span>                      |

<span data-ttu-id="a97e3-149">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-149">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="a97e3-150">따라서 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않으면서 모든 환경에서 해당 미리 보기의 최신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-150">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a97e3-151">Visual Studio 2017은 만든 모든 프로젝트 파일에 `<LangVersion>latest</LangVersion>` 항목을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-151">Visual Studio 2017 added a `<LangVersion>latest</LangVersion>` entry to any project files it created.</span></span> <span data-ttu-id="a97e3-152">즉, *C# 7.0* 이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-152">That meant *C# 7.0* when it was added.</span></span> <span data-ttu-id="a97e3-153">하지만 Visual Studio 2019로 업그레이드하면 대상 프레임워크에 관계없이 릴리스된 최신 버전이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-153">However, once you upgrade to Visual Studio 2019, that means the latest released version, regardless of the target framework.</span></span> <span data-ttu-id="a97e3-154">이러한 프로젝트는 이제 [기본 동작을 재정의](#override-a-default)합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-154">These projects now [override the default behavior](#override-a-default).</span></span> <span data-ttu-id="a97e3-155">프로젝트 파일을 편집하여 해당 노드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-155">You should edit the project file and remove that node.</span></span> <span data-ttu-id="a97e3-156">그러면 프로젝트에서 대상 프레임워크에 권장되는 컴파일러 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-156">Then, your project will use the compiler version recommended for your target framework.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="a97e3-157">기본값 재정의</span><span class="sxs-lookup"><span data-stu-id="a97e3-157">Override a default</span></span>

<span data-ttu-id="a97e3-158">C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-158">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="a97e3-159">[프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-159">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="a97e3-160">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-160">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="a97e3-161">[**LangVersion** 컴파일러 옵션](compiler-options/language.md#langversion)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-161">Configure the [**LangVersion** compiler option](compiler-options/language.md#langversion).</span></span>

> [!TIP]
> <span data-ttu-id="a97e3-162">현재 사용 중인 언어 버전을 확인하려면 코드에 `#error version`(대/소문자 구분)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-162">To know what language version you're currently using, put `#error version` (case sensitive) in your code.</span></span> <span data-ttu-id="a97e3-163">이렇게 하면 컴파일러가 사용 중인 컴파일러 버전 및 현재 선택된 언어 버전을 포함하는 메시지가 있는 컴파일러 오류 CS8304를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-163">This makes the compiler report a compiler error, CS8304, with a message containing the compiler version being used and the current selected language version.</span></span> <span data-ttu-id="a97e3-164">자세한 내용은 [#error(C# 참조)](preprocessor-directives/preprocessor-error.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a97e3-164">See [#error (C# Reference)](preprocessor-directives/preprocessor-error.md) for more information.</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="a97e3-165">프로젝트 파일 편집</span><span class="sxs-lookup"><span data-stu-id="a97e3-165">Edit the project file</span></span>

<span data-ttu-id="a97e3-166">프로젝트 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-166">You can set the language version in your project file.</span></span> <span data-ttu-id="a97e3-167">예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-167">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a97e3-168">값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-168">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="a97e3-169">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="a97e3-169">Configure multiple projects</span></span>

<span data-ttu-id="a97e3-170">여러 프로젝트를 구성하려면 `<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-170">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="a97e3-171">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-171">You typically do that in your solution directory.</span></span> <span data-ttu-id="a97e3-172">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-172">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="a97e3-173">해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-173">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="a97e3-174">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a97e3-174">For more information, see [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="a97e3-175">C# 언어 버전 참조</span><span class="sxs-lookup"><span data-stu-id="a97e3-175">C# language version reference</span></span>

<span data-ttu-id="a97e3-176">모든 표는 현재 C# 언어 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-176">The following table shows all current C# language versions.</span></span> <span data-ttu-id="a97e3-177">컴파일러가 오래된 것이라면 일부 값을 파악하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-177">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="a97e3-178">최신 .NET SDK를 설치하는 경우 나열된 모든 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-178">If you install the latest .NET SDK, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="a97e3-179">[개발자 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 열고 다음 명령을 실행하여 머신에서 사용할 수 있는 언어 버전 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-179">Open a [developer command-line shell](/visualstudio/ide/reference/command-prompt-powershell), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="a97e3-180">이와 같이 [\*\*LangVersion](compiler-options/language.md#langversion) 컴파일 옵션을 쿼리하면 다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="a97e3-180">Querying the [\*\*LangVersion](compiler-options/language.md#langversion) compile option like this prints something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
