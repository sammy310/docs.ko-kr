---
title: C# 언어 버전 선택 - C# 가이드
description: 특정 컴파일러 버전을 사용하여 구문 유효성 검사를 수행하도록 컴파일러 구성
ms.date: 02/28/2019
ms.openlocfilehash: feb3e51a107f9830071b55c7985f202edc842f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770882"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="fa8d1-103">C# 언어 버전 선택</span><span class="sxs-lookup"><span data-stu-id="fa8d1-103">Select the C# language version</span></span>

<span data-ttu-id="fa8d1-104">C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="fa8d1-105">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-105">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="fa8d1-106">프로젝트가 미리 보기 프레임워크를 대상으로 하지 않는 경우 사용되는 언어 버전은 최신 부 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-106">When your project doesn't target a preview framework, the language version used is the latest minor version.</span></span>

<span data-ttu-id="fa8d1-107">예를 들어 .NET Core 3.0의 미리 보기 기간에 `netcoreapp3.0` 또는 `netstandard2.1`(둘 다 미리 보기)을 대상으로 하는 모든 프로젝트는 C# 8.0 언어(미리 보기)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-107">For example, during the preview period for .NET Core 3.0, any project that targets `netcoreapp3.0` or `netstandard2.1` (both in preview) will use the C# 8.0 language (also in preview).</span></span> <span data-ttu-id="fa8d1-108">릴리스 버전을 대상으로 하는 프로젝트는 C# 7.3(최신 릴리스 버전)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-108">Projects targeting any released version will use C# 7.3 (the latest released version).</span></span> <span data-ttu-id="fa8d1-109">이 동작은 .NET Framework를 대상으로 하는 모든 프로젝트에서 최신 버전(C# 7.3)을 사용함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-109">This behavior means that any project targeting .NET Framework will use latest (C# 7.3).</span></span> 

<span data-ttu-id="fa8d1-110">이 기능은 개발 환경에서 SDK 및 도구의 새 버전을 설치하는 결정과 프로젝트의 새 언어 기능을 통합하는 결정을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-110">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="fa8d1-111">빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-111">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="fa8d1-112">각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-112">Each project can be configured to use a specific version of the language for its build.</span></span> <span data-ttu-id="fa8d1-113">기본 동작은 프로젝트가 해당 프레임워크를 대상으로 할 경우에만 새 형식 또는 새 CLR 동작을 기반으로 하는 언어 기능을 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-113">The default behavior means that any language features that rely on new types or new CLR behavior are enabled only when projects target those frameworks.</span></span>

<span data-ttu-id="fa8d1-114">언어 버전을 지정하여 기본 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-114">You can override the default behavior by specifying a language version.</span></span> <span data-ttu-id="fa8d1-115">언어 버전을 설정하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-115">There are several ways to set the language version:</span></span>

- <span data-ttu-id="fa8d1-116">[Visual Studio 빠른 작업](#visual-studio-quick-action)에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-116">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="fa8d1-117">[Visual Studio UI](#set-the-language-version-in-visual-studio)에서 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-117">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="fa8d1-118">[**.csproj** 파일](#edit-the-csproj-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-118">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="fa8d1-119">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-119">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="fa8d1-120">[`-langversion` 컴파일러 옵션](#set-the-langversion-compiler-option)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-120">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="fa8d1-121">Visual Studio 빠른 작업</span><span class="sxs-lookup"><span data-stu-id="fa8d1-121">Visual Studio quick action</span></span>

<span data-ttu-id="fa8d1-122">Visual Studio를 사용하면 필요한 언어 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-122">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="fa8d1-123">현재 구성된 버전에 사용할 수 없는 언어 기능을 사용하는 경우, Visual Studio는 프로젝트의 언어 버전을 업데이트하는 잠재적 수정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-123">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="fa8d1-124">Visual Studio에서 언어 버전 설정</span><span class="sxs-lookup"><span data-stu-id="fa8d1-124">Set the language version in Visual Studio</span></span>

<span data-ttu-id="fa8d1-125">Visual Studio에서 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-125">You can set the version in Visual Studio.</span></span> <span data-ttu-id="fa8d1-126">솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-126">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="fa8d1-127">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-127">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="fa8d1-128">드롭다운에서 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-128">In the dropdown, select the version.</span></span> <span data-ttu-id="fa8d1-129">다음 이미지는 "최신" 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-129">The following image shows the "latest" setting:</span></span>

![언어 버전을 지정할 수 있는 고급 빌드 설정의 스크린샷](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="fa8d1-131">Visual Studio IDE를 사용하여 csproj 파일을 업데이트하는 경우 IDE는 각 빌드 구성에 대한 별도 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-131">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="fa8d1-132">일반적으로 모든 빌드 구성에서 값을 동일하게 설정하지만 각 빌드 구성에 대해 명시적으로 설정하거나 이 설정을 수정하는 경우 "모든 구성"을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-132">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="fa8d1-133">csproj 파일에 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-133">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="fa8d1-134">csproj 파일 편집</span><span class="sxs-lookup"><span data-stu-id="fa8d1-134">Edit the csproj file</span></span>

<span data-ttu-id="fa8d1-135">**.csproj** 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-135">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="fa8d1-136">다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-136">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="fa8d1-137">`latest` 값은 C# 언어의 최신 부 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-137">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="fa8d1-138">올바른 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-138">Valid values are:</span></span>

|<span data-ttu-id="fa8d1-139">값</span><span class="sxs-lookup"><span data-stu-id="fa8d1-139">Value</span></span>|<span data-ttu-id="fa8d1-140">의미</span><span class="sxs-lookup"><span data-stu-id="fa8d1-140">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="fa8d1-141">미리 보기</span><span class="sxs-lookup"><span data-stu-id="fa8d1-141">preview</span></span>|<span data-ttu-id="fa8d1-142">컴파일러가 최신 미리 보기 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-142">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="fa8d1-143">latest</span><span class="sxs-lookup"><span data-stu-id="fa8d1-143">latest</span></span>|<span data-ttu-id="fa8d1-144">컴파일러가 최신 릴리스 버전(부 버전 포함)의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-144">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="fa8d1-145">latestMajor</span><span class="sxs-lookup"><span data-stu-id="fa8d1-145">latestMajor</span></span>|<span data-ttu-id="fa8d1-146">컴파일러가 최신 릴리스 주 버전의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-146">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="fa8d1-147">8.0</span><span class="sxs-lookup"><span data-stu-id="fa8d1-147">8.0</span></span>|<span data-ttu-id="fa8d1-148">컴파일러는 C# 8.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-148">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-149">7.3</span><span class="sxs-lookup"><span data-stu-id="fa8d1-149">7.3</span></span>|<span data-ttu-id="fa8d1-150">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-150">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="fa8d1-151">7.2</span><span class="sxs-lookup"><span data-stu-id="fa8d1-151">7.2</span></span>|<span data-ttu-id="fa8d1-152">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-152">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="fa8d1-153">7.1</span><span class="sxs-lookup"><span data-stu-id="fa8d1-153">7.1</span></span>|<span data-ttu-id="fa8d1-154">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="fa8d1-155">7</span><span class="sxs-lookup"><span data-stu-id="fa8d1-155">7</span></span>|<span data-ttu-id="fa8d1-156">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-156">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-157">6</span><span class="sxs-lookup"><span data-stu-id="fa8d1-157">6</span></span>|<span data-ttu-id="fa8d1-158">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-158">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-159">5</span><span class="sxs-lookup"><span data-stu-id="fa8d1-159">5</span></span>|<span data-ttu-id="fa8d1-160">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-160">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-161">4</span><span class="sxs-lookup"><span data-stu-id="fa8d1-161">4</span></span>|<span data-ttu-id="fa8d1-162">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-162">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-163">3</span><span class="sxs-lookup"><span data-stu-id="fa8d1-163">3</span></span>|<span data-ttu-id="fa8d1-164">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-164">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="fa8d1-165">ISO-2</span><span class="sxs-lookup"><span data-stu-id="fa8d1-165">ISO-2</span></span>|<span data-ttu-id="fa8d1-166">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-166">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="fa8d1-167">ISO-1</span><span class="sxs-lookup"><span data-stu-id="fa8d1-167">ISO-1</span></span>|<span data-ttu-id="fa8d1-168">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-168">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |

## <a name="configure-multiple-projects"></a><span data-ttu-id="fa8d1-169">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="fa8d1-169">Configure multiple projects</span></span>

<span data-ttu-id="fa8d1-170">`<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들어 여러 디렉터리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-170">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="fa8d1-171">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-171">You typically do that in your solution directory.</span></span> <span data-ttu-id="fa8d1-172">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-172">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="fa8d1-173">이제 해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 C# 버전 7.3 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-173">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="fa8d1-174">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-174">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="fa8d1-175">langversion 컴파일러 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="fa8d1-175">Set the langversion compiler option</span></span>

<span data-ttu-id="fa8d1-176">`-langversion` 명령줄 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-176">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="fa8d1-177">자세한 내용은 [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) 컴파일러 옵션에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-177">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="fa8d1-178">`csc -langversion:?`을 입력하면 유효한 값 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8d1-178">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
