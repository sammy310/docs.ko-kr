---
title: C# 언어 버전 관리 - C# 가이드
description: C# 언어 버전은 프로젝트에 따라 결정된다는 사실과 그 이유를 알아봅니다. 기본값을 수동으로 재정의하는 방법을 알아봅니다.
ms.date: 05/20/2020
ms.openlocfilehash: bbe5b12e378cf47b7c9b2c8576088e949e526a9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803002"
---
# <a name="c-language-versioning"></a><span data-ttu-id="0c185-104">C# 언어 버전 관리</span><span class="sxs-lookup"><span data-stu-id="0c185-104">C# language versioning</span></span>

<span data-ttu-id="0c185-105">최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="0c185-106">Visual Studio는 이 값을 변경하는 UI를 제공하지 않지만, *csproj* 파일을 편집하여 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="0c185-107">기본값이 이렇게 선택되면 항상 대상 프레임워크와 호환되는 최신 언어 버전을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="0c185-108">프로젝트의 대상과 호환되는 최신 언어 기능을 이용할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="0c185-109">또한, 기본값이 이렇게 선택되면 대상 프레임워크에서 사용할 수 없는 형식이나 런타임 동작이 필요한 언어를 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="0c185-110">기본값보다 최신의 언어 버전을 선택할 경우 컴파일 시간 및 런타임 오류를 진단하기 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="0c185-111">이 문서의 규칙은 Visual Studio 2019 또는 .NET Core 3.0 SDK와 함께 제공되는 컴파일러에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="0c185-112">Visual Studio 2017 설치 또는 이전 .NET Core SDK 버전의 일부인 C# 컴파일러는 기본적으로 C# 7.0을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="0c185-113">C# 8.0(이상)은 .NET Core 3.x 및 이후 버전에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="0c185-114">대부분의 최신 기능에는 .NET Core 3.x에서 도입된 라이브러리 및 런타임 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="0c185-115">[기본 인터페이스 구현](../whats-new/csharp-8.md#default-interface-methods)에는 .NET Core 3.0 CLR의 새로운 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="0c185-116">[비동기 스트림](../whats-new/csharp-8.md#asynchronous-streams)에는 새로운 형식인 <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="0c185-117">[인덱스 및 범위](../whats-new/csharp-8.md#indices-and-ranges)에는 새로운 형식인 <xref:System.Index?displayProperty=nameWithType> 및 <xref:System.Range?displayProperty=nameWithType>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="0c185-118">[Nulle 허용 참조 형식](../whats-new/csharp-8.md#nullable-reference-types)은 더 효과적인 경고를 제공하기 위해 몇 가지 [특성](attributes/nullable-analysis.md)을 사용하는데,</span><span class="sxs-lookup"><span data-stu-id="0c185-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="0c185-119">이러한 특성은 .NET Core 3.0에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="0c185-120">다른 대상 프레임워크는 이러한 특성으로 주석이 추가되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="0c185-121">즉, null 허용 경고가 잠재적인 문제를 정확하게 반영하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="0c185-122">기본값</span><span class="sxs-lookup"><span data-stu-id="0c185-122">Defaults</span></span>

<span data-ttu-id="0c185-123">컴파일러는 다음 규칙에 따라 기본값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-123">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="0c185-124">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="0c185-124">Target framework</span></span> | <span data-ttu-id="0c185-125">버전</span><span class="sxs-lookup"><span data-stu-id="0c185-125">version</span></span> | <span data-ttu-id="0c185-126">C# 언어 버전 기본값</span><span class="sxs-lookup"><span data-stu-id="0c185-126">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="0c185-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0c185-127">.NET Core</span></span>        | <span data-ttu-id="0c185-128">3.x</span><span class="sxs-lookup"><span data-stu-id="0c185-128">3.x</span></span>     | <span data-ttu-id="0c185-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="0c185-129">C# 8.0</span></span>                      |
| <span data-ttu-id="0c185-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0c185-130">.NET Core</span></span>        | <span data-ttu-id="0c185-131">2.x</span><span class="sxs-lookup"><span data-stu-id="0c185-131">2.x</span></span>     | <span data-ttu-id="0c185-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="0c185-132">C# 7.3</span></span>                      |
| <span data-ttu-id="0c185-133">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="0c185-133">.NET Standard</span></span>    | <span data-ttu-id="0c185-134">2.1</span><span class="sxs-lookup"><span data-stu-id="0c185-134">2.1</span></span>     | <span data-ttu-id="0c185-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="0c185-135">C# 8.0</span></span>                      |
| <span data-ttu-id="0c185-136">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="0c185-136">.NET Standard</span></span>    | <span data-ttu-id="0c185-137">2.0</span><span class="sxs-lookup"><span data-stu-id="0c185-137">2.0</span></span>     | <span data-ttu-id="0c185-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="0c185-138">C# 7.3</span></span>                      |
| <span data-ttu-id="0c185-139">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="0c185-139">.NET Standard</span></span>    | <span data-ttu-id="0c185-140">1.x</span><span class="sxs-lookup"><span data-stu-id="0c185-140">1.x</span></span>     | <span data-ttu-id="0c185-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="0c185-141">C# 7.3</span></span>                      |
| <span data-ttu-id="0c185-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c185-142">.NET Framework</span></span>   | <span data-ttu-id="0c185-143">모두</span><span class="sxs-lookup"><span data-stu-id="0c185-143">all</span></span>     | <span data-ttu-id="0c185-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="0c185-144">C# 7.3</span></span>                      |

<span data-ttu-id="0c185-145">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="0c185-146">따라서 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않으면서 모든 환경에서 해당 미리 보기의 최신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="0c185-147">기본값 재정의</span><span class="sxs-lookup"><span data-stu-id="0c185-147">Override a default</span></span>

<span data-ttu-id="0c185-148">C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="0c185-149">[프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="0c185-150">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="0c185-151">[`-langversion` 컴파일러 옵션](compiler-options/langversion-compiler-option.md)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="0c185-152">프로젝트 파일 편집</span><span class="sxs-lookup"><span data-stu-id="0c185-152">Edit the project file</span></span>

<span data-ttu-id="0c185-153">프로젝트 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-153">You can set the language version in your project file.</span></span> <span data-ttu-id="0c185-154">예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="0c185-155">값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="0c185-156">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="0c185-156">Configure multiple projects</span></span>

<span data-ttu-id="0c185-157">여러 프로젝트를 구성하려면 `<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="0c185-158">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="0c185-159">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="0c185-160">해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="0c185-161">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c185-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="0c185-162">C# 언어 버전 참조</span><span class="sxs-lookup"><span data-stu-id="0c185-162">C# language version reference</span></span>

<span data-ttu-id="0c185-163">모든 표는 현재 C# 언어 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="0c185-164">컴파일러가 오래된 것이라면 일부 값을 파악하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="0c185-165">.NET Core 3.0 이상을 설치하면 나열된 모든 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="0c185-166">[Visual Studio용 개발자 명령 프롬프트](../../framework/tools/developer-command-prompt-for-vs.md)를 열고 다음 명령을 실행하여 컴퓨터에서 사용할 수 있는 언어 버전의 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-166">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="0c185-167">이와 같이 [-langversion](compiler-options/langversion-compiler-option.md) compile 옵션을 질문하면 다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c185-167">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
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
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
