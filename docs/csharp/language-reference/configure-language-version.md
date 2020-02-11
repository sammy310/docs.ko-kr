---
title: C# 언어 버전 관리 - C# 가이드
description: 프로젝트에 따라 C# 언어 버전이 결정되는 방법과 수동으로 조정할 수 있는 다양한 값에 대해 알아봅니다.
ms.date: 07/10/2019
ms.openlocfilehash: 3c1035d983660ea0a945e4d4b7b72c69736c90cb
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980134"
---
# <a name="c-language-versioning"></a><span data-ttu-id="f856d-103">C# 언어 버전 관리</span><span class="sxs-lookup"><span data-stu-id="f856d-103">C# language versioning</span></span>

<span data-ttu-id="f856d-104">최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="f856d-105">C# 언어는 모든 .NET 구현에서 사용할 수 없는 유형 또는 런타임 구성 요소를 사용하는 기능이 있을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="f856d-106">또한 프로젝트가 빌드된 대상에 상관없이 기본적으로 가장 호환성이 높은 언어 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="f856d-107">이 문서의 규칙은 Visual Studio 2019 또는 .NET Core 3.0 SDK와 함께 제공되는 컴파일러에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-107">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="f856d-108">Visual Studio 2017 설치 또는 이전 .NET Core SDK 버전의 일부인 C# 컴파일러는 기본적으로 C# 7.0을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="f856d-109">기본값</span><span class="sxs-lookup"><span data-stu-id="f856d-109">Defaults</span></span>

<span data-ttu-id="f856d-110">컴파일러는 다음 규칙에 따라 기본값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="f856d-111">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="f856d-111">Target framework</span></span>|<span data-ttu-id="f856d-112">버전</span><span class="sxs-lookup"><span data-stu-id="f856d-112">version</span></span>|<span data-ttu-id="f856d-113">C# 언어 버전 기본값</span><span class="sxs-lookup"><span data-stu-id="f856d-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="f856d-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="f856d-114">.NET Core</span></span>|<span data-ttu-id="f856d-115">3.x</span><span class="sxs-lookup"><span data-stu-id="f856d-115">3.x</span></span>|<span data-ttu-id="f856d-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="f856d-116">C# 8.0</span></span>|
|<span data-ttu-id="f856d-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="f856d-117">.NET Core</span></span>|<span data-ttu-id="f856d-118">2.x</span><span class="sxs-lookup"><span data-stu-id="f856d-118">2.x</span></span>|<span data-ttu-id="f856d-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="f856d-119">C# 7.3</span></span>|
|<span data-ttu-id="f856d-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="f856d-120">.NET Standard</span></span>|<span data-ttu-id="f856d-121">2.1</span><span class="sxs-lookup"><span data-stu-id="f856d-121">2.1</span></span>|<span data-ttu-id="f856d-122">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="f856d-122">C# 8.0</span></span>|
|<span data-ttu-id="f856d-123">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="f856d-123">.NET Standard</span></span>|<span data-ttu-id="f856d-124">2.0</span><span class="sxs-lookup"><span data-stu-id="f856d-124">2.0</span></span>|<span data-ttu-id="f856d-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="f856d-125">C# 7.3</span></span>|
|<span data-ttu-id="f856d-126">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="f856d-126">.NET Standard</span></span>|<span data-ttu-id="f856d-127">1.x</span><span class="sxs-lookup"><span data-stu-id="f856d-127">1.x</span></span>|<span data-ttu-id="f856d-128">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="f856d-128">C# 7.3</span></span>|
|<span data-ttu-id="f856d-129">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="f856d-129">.NET Framework</span></span>|<span data-ttu-id="f856d-130">모두</span><span class="sxs-lookup"><span data-stu-id="f856d-130">all</span></span>|<span data-ttu-id="f856d-131">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="f856d-131">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="f856d-132">미리 보기에 대한 기본값</span><span class="sxs-lookup"><span data-stu-id="f856d-132">Default for previews</span></span>

<span data-ttu-id="f856d-133">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-133">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="f856d-134">이렇게 하면 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않고 모든 환경에서 해당 미리 보기로 작업할 수 있는 최신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-134">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="f856d-135">기본값 재정의</span><span class="sxs-lookup"><span data-stu-id="f856d-135">Override a default</span></span>

<span data-ttu-id="f856d-136">C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-136">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="f856d-137">[프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-137">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="f856d-138">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-138">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="f856d-139">[`-langversion` 컴파일러 옵션](compiler-options/langversion-compiler-option.md)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-139">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="f856d-140">프로젝트 파일 편집</span><span class="sxs-lookup"><span data-stu-id="f856d-140">Edit the project file</span></span>

<span data-ttu-id="f856d-141">프로젝트 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-141">You can set the language version in your project file.</span></span> <span data-ttu-id="f856d-142">예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-142">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="f856d-143">값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-143">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="f856d-144">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="f856d-144">Configure multiple projects</span></span>

<span data-ttu-id="f856d-145">여러 프로젝트를 구성하려면 `<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-145">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="f856d-146">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-146">You typically do that in your solution directory.</span></span> <span data-ttu-id="f856d-147">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-147">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="f856d-148">이제 해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-148">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="f856d-149">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f856d-149">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="f856d-150">C# 언어 버전 참조</span><span class="sxs-lookup"><span data-stu-id="f856d-150">C# language version reference</span></span>

<span data-ttu-id="f856d-151">모든 표는 현재 C# 언어 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-151">The following table shows all current C# language versions.</span></span> <span data-ttu-id="f856d-152">컴파일러가 오래된 것이라면 모든 값을 반드시 파악하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-152">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="f856d-153">.NET Core 3.0을 설치하면 나열된 모든 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-153">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="f856d-154">값</span><span class="sxs-lookup"><span data-stu-id="f856d-154">Value</span></span>|<span data-ttu-id="f856d-155">의미</span><span class="sxs-lookup"><span data-stu-id="f856d-155">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="f856d-156">미리 보기</span><span class="sxs-lookup"><span data-stu-id="f856d-156">preview</span></span>|<span data-ttu-id="f856d-157">컴파일러가 최신 미리 보기 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-157">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="f856d-158">latest</span><span class="sxs-lookup"><span data-stu-id="f856d-158">latest</span></span>|<span data-ttu-id="f856d-159">컴파일러가 최신 릴리스 버전(부 버전 포함)의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-159">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="f856d-160">latestMajor</span><span class="sxs-lookup"><span data-stu-id="f856d-160">latestMajor</span></span>|<span data-ttu-id="f856d-161">컴파일러가 최신 릴리스 주 버전의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-161">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="f856d-162">8.0</span><span class="sxs-lookup"><span data-stu-id="f856d-162">8.0</span></span>|<span data-ttu-id="f856d-163">컴파일러는 C# 8.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-163">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="f856d-164">7.3</span><span class="sxs-lookup"><span data-stu-id="f856d-164">7.3</span></span>|<span data-ttu-id="f856d-165">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-165">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="f856d-166">7.2</span><span class="sxs-lookup"><span data-stu-id="f856d-166">7.2</span></span>|<span data-ttu-id="f856d-167">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-167">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="f856d-168">7.1</span><span class="sxs-lookup"><span data-stu-id="f856d-168">7.1</span></span>|<span data-ttu-id="f856d-169">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-169">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="f856d-170">7</span><span class="sxs-lookup"><span data-stu-id="f856d-170">7</span></span>|<span data-ttu-id="f856d-171">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-171">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="f856d-172">6</span><span class="sxs-lookup"><span data-stu-id="f856d-172">6</span></span>|<span data-ttu-id="f856d-173">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-173">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="f856d-174">5</span><span class="sxs-lookup"><span data-stu-id="f856d-174">5</span></span>|<span data-ttu-id="f856d-175">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-175">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="f856d-176">4</span><span class="sxs-lookup"><span data-stu-id="f856d-176">4</span></span>|<span data-ttu-id="f856d-177">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-177">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="f856d-178">3</span><span class="sxs-lookup"><span data-stu-id="f856d-178">3</span></span>|<span data-ttu-id="f856d-179">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-179">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="f856d-180">ISO-2</span><span class="sxs-lookup"><span data-stu-id="f856d-180">ISO-2</span></span>|<span data-ttu-id="f856d-181">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-181">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span> |
|<span data-ttu-id="f856d-182">ISO-1</span><span class="sxs-lookup"><span data-stu-id="f856d-182">ISO-1</span></span>|<span data-ttu-id="f856d-183">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f856d-183">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span> |
