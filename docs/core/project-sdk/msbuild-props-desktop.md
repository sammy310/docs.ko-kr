---
title: Microsoft.NET.Sdk.Desktop의 MSBuild 속성
description: WPF 및 WinForms가 포함된 .NET 데스크톱 SDK에서 이해하는 MSBuild 속성 및 항목의 참조입니다.
ms.date: 02/04/2021
ms.topic: reference
author: adegeo
ms.author: adegeo
ms.custom: updateeachrelease
no-loc:
- App.xaml
- Application.xaml
- ApplicationDefinition
- Page
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: 6d1903558dd03776a72eb6ee56ddae09fb66615b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488248"
---
# <a name="msbuild-reference-for-net-desktop-sdk-projects"></a><span data-ttu-id="34f69-103">.NET 데스크톱 SDK 프로젝트의 MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="34f69-103">MSBuild reference for .NET Desktop SDK projects</span></span>

<span data-ttu-id="34f69-104">이 페이지는 .NET 데스크톱 SDK를 사용하여 WinForms(Windows Forms) 및 WPF(Windows Presentation Foundation) 프로젝트를 구성하는 데 사용하는 MSBuild 속성 및 항목의 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-104">This page is a reference for the MSBuild properties and items that you use to configure Windows Forms (WinForms) and Windows Presentation Foundation (WPF) projects with the .NET Desktop SDK.</span></span>

> [!NOTE]
> <span data-ttu-id="34f69-105">이 문서에서는 데스크톱 앱과 관련된 .NET SDK의 MSBuild 속성 하위 집합을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-105">This article documents a subset of the MSBuild properties for the .NET SDK as it relates to desktop apps.</span></span> <span data-ttu-id="34f69-106">일반적인 .NET SDK 관련 MSBuild 속성 목록은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-106">For a list of common .NET SDK-specific MSBuild properties, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span> <span data-ttu-id="34f69-107">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="enable-net-desktop-sdk"></a><span data-ttu-id="34f69-108">.NET 데스크톱 SDK 사용</span><span class="sxs-lookup"><span data-stu-id="34f69-108">Enable .NET Desktop SDK</span></span>

<span data-ttu-id="34f69-109">WinForms 또는 WPF를 사용하려면 프로젝트 파일을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-109">To use WinForms or WPF, configure your project file.</span></span>

### <a name="net-50"></a><span data-ttu-id="34f69-110">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="34f69-110">.NET 5.0</span></span>

<span data-ttu-id="34f69-111">WinForms 또는 WPF 프로젝트의 프로젝트 파일에서 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-111">Specify the following settings in the project file of your WinForms or WPF project:</span></span>

- <span data-ttu-id="34f69-112">.NET SDK `Microsoft.NET.Sdk`를 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-112">Target the .NET SDK `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="34f69-113">자세한 내용은 [프로젝트 파일](overview.md#project-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-113">For more information, see [Project files](overview.md#project-files).</span></span>
- <span data-ttu-id="34f69-114">[`TargetFramework`](msbuild-props.md#targetframework)를 `net5.0-windows`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-114">Set [`TargetFramework`](msbuild-props.md#targetframework) to `net5.0-windows`.</span></span>
- <span data-ttu-id="34f69-115">UI 프레임워크 속성(또는 필요한 경우 둘 다)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-115">Add a UI framework property (or both, if necessary):</span></span>
  - <span data-ttu-id="34f69-116">[`UseWPF`](#usewpf)를 `true`로 설정하여 WPF를 가져오고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-116">Set [`UseWPF`](#usewpf) to `true` to import and use WPF.</span></span>
  - <span data-ttu-id="34f69-117">[`UseWindowsForms`](#usewindowsforms)를 `true`로 설정하여 WinForms를 가져오고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-117">Set [`UseWindowsForms`](#usewindowsforms) to `true` to import and use WinForms.</span></span>
- <span data-ttu-id="34f69-118">(선택 사항) `OutputType`을 `WinExe`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-118">(Optional) Set `OutputType` to `WinExe`.</span></span> <span data-ttu-id="34f69-119">이렇게 하면 라이브러리가 아닌 앱이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-119">This produces an app as opposed to a library.</span></span> <span data-ttu-id="34f69-120">라이브러리를 생성하려면 해당 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-120">To produce a library, omit this property.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

### <a name="net-core-31"></a><span data-ttu-id="34f69-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="34f69-121">.NET Core 3.1</span></span>

<span data-ttu-id="34f69-122">WinForms 또는 WPF 프로젝트의 프로젝트 파일에서 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-122">Specify the following settings in the project file of your WinForms or WPF project:</span></span>

- <span data-ttu-id="34f69-123">.NET SDK `Microsoft.NET.Sdk.WindowsDesktop`을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-123">Target the .NET SDK `Microsoft.NET.Sdk.WindowsDesktop`.</span></span> <span data-ttu-id="34f69-124">자세한 내용은 [프로젝트 파일](overview.md#project-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-124">For more information, see [Project files](overview.md#project-files).</span></span>
- <span data-ttu-id="34f69-125">[`TargetFramework`](msbuild-props.md#targetframework)를 `netcoreapp3.1`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-125">Set [`TargetFramework`](msbuild-props.md#targetframework) to `netcoreapp3.1`.</span></span>
- <span data-ttu-id="34f69-126">UI 프레임워크 속성(또는 필요한 경우 둘 다)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-126">Add a UI framework property (or both, if necessary):</span></span>
  - <span data-ttu-id="34f69-127">[`UseWPF`](#usewpf)를 `true`로 설정하여 WPF를 가져오고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-127">Set [`UseWPF`](#usewpf) to `true` to import and use WPF.</span></span>
  - <span data-ttu-id="34f69-128">[`UseWindowsForms`](#usewindowsforms)를 `true`로 설정하여 WinForms를 가져오고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-128">Set [`UseWindowsForms`](#usewindowsforms) to `true` to import and use WinForms.</span></span>
- <span data-ttu-id="34f69-129">(선택 사항) `OutputType`을 `WinExe`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-129">(Optional) Set `OutputType` to `WinExe`.</span></span> <span data-ttu-id="34f69-130">이렇게 하면 라이브러리가 아닌 앱이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-130">This produces an app as opposed to a library.</span></span> <span data-ttu-id="34f69-131">라이브러리를 생성하려면 해당 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-131">To produce a library, omit this property.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

## <a name="wpf-default-includes-and-excludes"></a><span data-ttu-id="34f69-132">WPF 기본 포함 및 제외</span><span class="sxs-lookup"><span data-stu-id="34f69-132">WPF default includes and excludes</span></span>

<span data-ttu-id="34f69-133">SDK 프로젝트는 프로젝트의 파일을 암시적으로 포함하거나 제외하는 규칙 세트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-133">SDK projects define a set of rules to implicitly include or exclude files from the project.</span></span> <span data-ttu-id="34f69-134">해당 규칙은 파일의 빌드 작업도 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-134">These rules also automatically set the file's build action.</span></span> <span data-ttu-id="34f69-135">이는 기본 포함 또는 제외 규칙이 없는 이전 비 SDK .NET Framework 프로젝트와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-135">This is unlike the older non-SDK .NET Framework projects, which have no default include or exclude rules.</span></span> <span data-ttu-id="34f69-136">.NET Framework 프로젝트에서는 프로젝트에 포함할 파일을 명시적으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-136">.NET Framework projects require you to explicitly declare which files to include in the project.</span></span>

<span data-ttu-id="34f69-137">.NET 프로젝트 파일에는 파일을 자동으로 처리하는 [표준 규칙 세트](overview.md#default-includes-and-excludes)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-137">.NET project files include a [standard set of rules](overview.md#default-includes-and-excludes) for automatically processing files.</span></span> <span data-ttu-id="34f69-138">WPF 프로젝트는 다른 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-138">WPF projects add additional rules.</span></span>

<span data-ttu-id="34f69-139">다음 표에서는 [`UseWPF`](#usewpf) 프로젝트 속성이 `true`로 설정된 경우 .NET 데스크톱 SDK에서 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-139">The following table shows which elements and [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Desktop SDK when the [`UseWPF`](#usewpf) project property is set to `true`:</span></span>

| <span data-ttu-id="34f69-140">요소</span><span class="sxs-lookup"><span data-stu-id="34f69-140">Element</span></span>               | <span data-ttu-id="34f69-141">GLOB 포함</span><span class="sxs-lookup"><span data-stu-id="34f69-141">Include glob</span></span>                 | <span data-ttu-id="34f69-142">GLOB 제외</span><span class="sxs-lookup"><span data-stu-id="34f69-142">Exclude glob</span></span>                                                                                           | <span data-ttu-id="34f69-143">GLOB 제거</span><span class="sxs-lookup"><span data-stu-id="34f69-143">Remove glob</span></span>  |
|-----------------------|------------------------------|--------------------------------------------------------------------|--------------|
| ApplicationDefinition | <span data-ttu-id="34f69-144">App.xaml 또는 Application.xaml</span><span class="sxs-lookup"><span data-stu-id="34f69-144">App.xaml or Application.xaml</span></span> | <span data-ttu-id="34f69-145">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-145">N/A</span></span>                                                                | <span data-ttu-id="34f69-146">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-146">N/A</span></span>          |
| Page                  | <span data-ttu-id="34f69-147">\*\*/\*.xaml</span><span class="sxs-lookup"><span data-stu-id="34f69-147">\*\*/\*.xaml</span></span>                 | <span data-ttu-id="34f69-148">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="34f69-148">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span><br><span data-ttu-id="34f69-149">*ApplicationDefinition* 에서 정의된 모든 XAML</span><span class="sxs-lookup"><span data-stu-id="34f69-149">Any XAML defined by *ApplicationDefinition*</span></span> | <span data-ttu-id="34f69-150">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-150">N/A</span></span>          |
| None                  | <span data-ttu-id="34f69-151">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-151">N/A</span></span>                          | <span data-ttu-id="34f69-152">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-152">N/A</span></span>                                                                | <span data-ttu-id="34f69-153">\*\*/\*.xaml</span><span class="sxs-lookup"><span data-stu-id="34f69-153">\*\*/\*.xaml</span></span> |

<span data-ttu-id="34f69-154">모든 프로젝트 형식의 기본 포함 및 제외 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-154">Here are the default include and exclude settings for all project types.</span></span> <span data-ttu-id="34f69-155">자세한 내용은 [기본 포함 및 제외](overview.md#default-includes-and-excludes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-155">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

| <span data-ttu-id="34f69-156">요소</span><span class="sxs-lookup"><span data-stu-id="34f69-156">Element</span></span>           | <span data-ttu-id="34f69-157">GLOB 포함</span><span class="sxs-lookup"><span data-stu-id="34f69-157">Include glob</span></span>                              | <span data-ttu-id="34f69-158">GLOB 제외</span><span class="sxs-lookup"><span data-stu-id="34f69-158">Exclude glob</span></span>                                                  | <span data-ttu-id="34f69-159">GLOB 제거</span><span class="sxs-lookup"><span data-stu-id="34f69-159">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | <span data-ttu-id="34f69-160">\*\*/\*.cs, \*\*/\*.vb(또는 기타 언어 확장)</span><span class="sxs-lookup"><span data-stu-id="34f69-160">\*\*/\*.cs; \*\*/\*.vb (or other language extensions)</span></span> | <span data-ttu-id="34f69-161">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="34f69-161">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="34f69-162">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-162">N/A</span></span>          |
| EmbeddedResource  | <span data-ttu-id="34f69-163">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="34f69-163">\*\*/\*.resx</span></span>                              | <span data-ttu-id="34f69-164">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="34f69-164">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="34f69-165">N/A</span><span class="sxs-lookup"><span data-stu-id="34f69-165">N/A</span></span>                      |
| None              | \*\*/\*                                   | <span data-ttu-id="34f69-166">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="34f69-166">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="34f69-167">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="34f69-167">\*\*/\*.cs; \*\*/\*.resx</span></span> |

### <a name="errors-related-to-duplicate-items"></a><span data-ttu-id="34f69-168">“중복” 항목 관련 오류</span><span class="sxs-lookup"><span data-stu-id="34f69-168">Errors related to "duplicate" items</span></span>

<span data-ttu-id="34f69-169">프로젝트에 파일을 명시적으로 추가했거나 XAML GLOB가 프로젝트에 파일을 자동으로 포함하도록 하려면 다음 오류 중 하나가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-169">If you explicitly added files to your project, or have XAML globs to automatically include files in your project, you might get one of the following errors:</span></span>

* <span data-ttu-id="34f69-170">중복 ‘ApplicationDefinition’ 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-170">Duplicate 'ApplicationDefinition' items were included.</span></span>
* <span data-ttu-id="34f69-171">중복 ‘Page’ 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-171">Duplicate 'Page' items were included.</span></span>

<span data-ttu-id="34f69-172">해당 오류는 설정과 충돌하는 암시적 *Include* GLOB의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-172">These errors are a result of the implicit *Include* globs conflicting with your settings.</span></span> <span data-ttu-id="34f69-173">이 문제를 해결하려면 [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) 또는 [`EnableDefaultPageItems`](#enabledefaultpageitems)를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-173">To work around this problem, set either [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) or [`EnableDefaultPageItems`](#enabledefaultpageitems) to `false`.</span></span> <span data-ttu-id="34f69-174">해당 값을 `false`로 설정하면 프로젝트에서 기본 GLOB를 명시적으로 정의하거나 프로젝트에 포함할 파일을 명시적으로 정의해야 했던 이전 SDK의 동작으로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-174">Setting these values to `false` reverts to the behavior of previous SDKs where you had to explicitly define the default globs in your project, or explicitly define the files to include in the project.</span></span>

<span data-ttu-id="34f69-175">[`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 `false`로 설정하여 모든 암시적 포함을 완전히 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-175">You can completely disable all implicit includes by setting the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) to `false`.</span></span>

## <a name="wpf-settings"></a><span data-ttu-id="34f69-176">WPF 설정</span><span class="sxs-lookup"><span data-stu-id="34f69-176">WPF settings</span></span>

- [<span data-ttu-id="34f69-177">UseWPF</span><span class="sxs-lookup"><span data-stu-id="34f69-177">UseWPF</span></span>](#usewpf)
- [<span data-ttu-id="34f69-178">EnableDefaultApplicationDefinition</span><span class="sxs-lookup"><span data-stu-id="34f69-178">EnableDefaultApplicationDefinition</span></span>](#enabledefaultapplicationdefinition)
- [<span data-ttu-id="34f69-179">EnableDefaultPageItems</span><span class="sxs-lookup"><span data-stu-id="34f69-179">EnableDefaultPageItems</span></span>](#enabledefaultpageitems)

<span data-ttu-id="34f69-180">비 WPF 관련 프로젝트 설정에 관한 자세한 내용은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-180">For information about non-WPF-specific project settings, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="usewpf"></a><span data-ttu-id="34f69-181">UseWPF</span><span class="sxs-lookup"><span data-stu-id="34f69-181">UseWPF</span></span>

<span data-ttu-id="34f69-182">`UseWPF` 속성은 WPF 라이브러리에 대한 참조를 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-182">The `UseWPF` property controls whether or not to include references to WPF libraries.</span></span> <span data-ttu-id="34f69-183">또한 MSBuild 파이프라인을 변경하여 WPF 프로젝트 및 관련 파일을 올바르게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-183">This also alters the MSBuild pipeline to correctly process a WPF project and related files.</span></span> <span data-ttu-id="34f69-184">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-184">The default value is `false`.</span></span> <span data-ttu-id="34f69-185">`UseWPF` 속성을 `true`로 설정하여 WPF 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-185">Set the `UseWPF` property to `true` to enable WPF support.</span></span> <span data-ttu-id="34f69-186">해당 속성을 사용하는 경우 Windows 플랫폼만 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-186">You can only target the Windows platform when this property is enabled.</span></span>

```xml
<PropertyGroup>
  <UseWPF>true</UseWPF>
</PropertyGroup>
```

<span data-ttu-id="34f69-187">해당 속성을 `true`로 설정하면 .NET 5.0 이상 프로젝트는 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 자동으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-187">When this property is set to `true`, .NET 5.0+ projects will automatically import the [.NET Desktop SDK](#enable-net-desktop-sdk).</span></span>

<span data-ttu-id="34f69-188">.NET Core 3.1 프로젝트는 해당 속성을 사용하려면 명시적으로 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-188">.NET Core 3.1 projects need to explicitly target the [.NET Desktop SDK](#enable-net-desktop-sdk) to use this property.</span></span>

### <a name="enabledefaultapplicationdefinition"></a><span data-ttu-id="34f69-189">EnableDefaultApplicationDefinition</span><span class="sxs-lookup"><span data-stu-id="34f69-189">EnableDefaultApplicationDefinition</span></span>

<span data-ttu-id="34f69-190">`EnableDefaultApplicationDefinition` 속성은 `ApplicationDefinition` 항목을 프로젝트에 암시적으로 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-190">The `EnableDefaultApplicationDefinition` property controls whether `ApplicationDefinition` items are implicitly included in the project.</span></span> <span data-ttu-id="34f69-191">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-191">The default value is `true`.</span></span> <span data-ttu-id="34f69-192">`EnableDefaultApplicationDefinition` 속성을 `false`로 설정하여 암시적 파일 포함을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-192">Set the `EnableDefaultApplicationDefinition` property to `false` to disable the implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultApplicationDefinition>false</EnableDefaultApplicationDefinition>
</PropertyGroup>
```

<span data-ttu-id="34f69-193">해당 속성을 사용하려면 [`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 기본 설정인 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-193">This property requires that the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) property is set to `true`, which is the default setting.</span></span>

### <a name="enabledefaultpageitems"></a><span data-ttu-id="34f69-194">EnableDefaultPageItems</span><span class="sxs-lookup"><span data-stu-id="34f69-194">EnableDefaultPageItems</span></span>

<span data-ttu-id="34f69-195">`EnableDefaultPageItems` 속성은 _.xaml_ 파일인 `Page` 항목이 프로젝트에 암시적으로 포함되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-195">The `EnableDefaultPageItems` property controls whether `Page` items, which are _.xaml_ files, are implicitly included in the project.</span></span> <span data-ttu-id="34f69-196">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-196">The default value is `true`.</span></span> <span data-ttu-id="34f69-197">`EnableDefaultPageItems` 속성을 `false`로 설정하여 암시적 파일 포함을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-197">Set the `EnableDefaultPageItems` property to `false` to disable the implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultPageItems>false</EnableDefaultPageItems>
</PropertyGroup>
```

<span data-ttu-id="34f69-198">해당 속성을 사용하려면 [`EnableDefaultItems` 속성](msbuild-props.md#enabledefaultitems)을 기본 설정인 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-198">This property requires that the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) property is set to `true`, which is the default setting.</span></span>

## <a name="windows-forms-settings"></a><span data-ttu-id="34f69-199">Windows Forms 설정</span><span class="sxs-lookup"><span data-stu-id="34f69-199">Windows Forms settings</span></span>

- [<span data-ttu-id="34f69-200">UseWindowsForms</span><span class="sxs-lookup"><span data-stu-id="34f69-200">UseWindowsForms</span></span>](#usewindowsforms)

<span data-ttu-id="34f69-201">비 WinForms 관련 프로젝트 속성에 관한 자세한 내용은 [.NET SDK 프로젝트의 MSBuild 참조](msbuild-props.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f69-201">For information about non-WinForms-specific project properties, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="usewindowsforms"></a><span data-ttu-id="34f69-202">UseWindowsForms</span><span class="sxs-lookup"><span data-stu-id="34f69-202">UseWindowsForms</span></span>

<span data-ttu-id="34f69-203">`UseWindowsForms` 속성은 애플리케이션이 Windows Forms를 대상으로 하도록 빌드되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-203">The `UseWindowsForms` property controls whether or not your application is built to target Windows Forms.</span></span> <span data-ttu-id="34f69-204">해당 속성은 MSBuild 파이프라인을 변경하여 Windows Forms 프로젝트 및 관련 파일을 올바르게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-204">This property alters the MSBuild pipeline to correctly process a Windows Forms project and related files.</span></span> <span data-ttu-id="34f69-205">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-205">The default value is `false`.</span></span> <span data-ttu-id="34f69-206">`UseWindowsForms` 속성을 `true`로 설정하여 Windows Forms 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-206">Set the `UseWindowsForms` property to `true` to enable Windows Forms support.</span></span> <span data-ttu-id="34f69-207">해당 설정을 사용하는 경우 Windows 플랫폼만 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-207">You can only target the Windows platform when this setting is enabled.</span></span>

```xml
<PropertyGroup>
  <UseWindowsForms>true</UseWindowsForms>
</PropertyGroup>
```

<span data-ttu-id="34f69-208">해당 속성을 `true`로 설정하면 .NET 5.0 이상 프로젝트는 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 자동으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-208">When this property is set to `true`, .NET 5.0+ projects will automatically import the [.NET Desktop SDK](#enable-net-desktop-sdk).</span></span>

<span data-ttu-id="34f69-209">.NET Core 3.1 프로젝트는 해당 속성을 사용하려면 명시적으로 [.NET 데스크톱 SDK](#enable-net-desktop-sdk)를 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-209">.NET Core 3.1 projects need to explicitly target the [.NET Desktop SDK](#enable-net-desktop-sdk) to use this property.</span></span>

## <a name="shared-settings"></a><span data-ttu-id="34f69-210">공유 설정</span><span class="sxs-lookup"><span data-stu-id="34f69-210">Shared settings</span></span>

- [<span data-ttu-id="34f69-211">DisableWinExeOutputInference</span><span class="sxs-lookup"><span data-stu-id="34f69-211">DisableWinExeOutputInference</span></span>](#disablewinexeoutputinference)

### <a name="disablewinexeoutputinference"></a><span data-ttu-id="34f69-212">DisableWinExeOutputInference</span><span class="sxs-lookup"><span data-stu-id="34f69-212">DisableWinExeOutputInference</span></span>

<span data-ttu-id="34f69-213">.NET 5.0 SDK 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-213">Applies to .NET 5.0 SDK and later.</span></span>

<span data-ttu-id="34f69-214">앱에서 `OutputType` 속성에 `Exe` 값이 설정되어 있을 때 앱이 콘솔에서 실행되고 있지 않으면 콘솔 창이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-214">When an app has the `Exe` value set for the `OutputType` property, a console window is created if the app isn't running from a console.</span></span> <span data-ttu-id="34f69-215">이는 일반적으로 Windows 데스크톱 앱의 필요한 동작이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-215">This is generally not the desired behavior of a Windows Desktop app.</span></span> <span data-ttu-id="34f69-216">`WinExe` 값을 사용하면 콘솔 창이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-216">With the `WinExe` value, a console window isn't created.</span></span> <span data-ttu-id="34f69-217">.NET 5.0 SDK부터는 `Exe` 값이 `WinExe`로 자동으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-217">Starting with the .NET 5.0 SDK, the `Exe` value is automatically transformed to `WinExe`.</span></span>

<span data-ttu-id="34f69-218">`DisableWinExeOutputInference` 속성은 `Exe`를 `WinExe`로 처리하는 동작을 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-218">The `DisableWinExeOutputInference` property reverts the behavior of treating `Exe` as `WinExe`.</span></span> <span data-ttu-id="34f69-219">해당 값을 `true`로 설정하여 `Exe`의 `OutputType` 속성 값 동작을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-219">Set this value to `true` to restore the behavior of the `OutputType` property value of `Exe`.</span></span> <span data-ttu-id="34f69-220">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="34f69-220">The default value is `false`.</span></span>

```xml
<PropertyGroup>
  <DisableWinExeOutputInference>true</DisableWinExeOutputInference>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="34f69-221">참조</span><span class="sxs-lookup"><span data-stu-id="34f69-221">See also</span></span>

- [<span data-ttu-id="34f69-222">.NET 프로젝트 SDK</span><span class="sxs-lookup"><span data-stu-id="34f69-222">.NET project SDKs</span></span>](overview.md)
- [<span data-ttu-id="34f69-223">.NET SDK 프로젝트용 MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="34f69-223">MSBuild reference for .NET SDK projects</span></span>](msbuild-props.md)
- [<span data-ttu-id="34f69-224">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="34f69-224">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="34f69-225">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="34f69-225">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="34f69-226">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="34f69-226">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
