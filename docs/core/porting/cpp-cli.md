---
title: C++/CLI 프로젝트를 .NET Core로 마이그레이션
description: C++/CLI 프로젝트를 .NET Core로 이식하는 방법에 대해 알아봅니다.
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964862"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a><span data-ttu-id="cd7b2-103">C++/CLI 프로젝트를 .NET Core로 이식하는 방법</span><span class="sxs-lookup"><span data-stu-id="cd7b2-103">How to port a C++/CLI project to .NET Core</span></span>

<span data-ttu-id="cd7b2-104">.NET Core 3.1 및 Visual Studio 2019 버전 16.4부터 시작하면 [C++/CLI 프로젝트](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp)는 .NET Core를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-104">Beginning with .NET Core 3.1 and Visual Studio 2019 version 16.4, [C++/CLI projects](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) can target .NET Core.</span></span> <span data-ttu-id="cd7b2-105">이 지원을 통해 C++/CLI interop 레이어가 있는 Windows 데스크톱 애플리케이션을 .NET Core로 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-105">This support makes it possible to port Windows desktop applications with C++/CLI interop layers to .NET Core.</span></span> <span data-ttu-id="cd7b2-106">이 문서에서는 C++/CLI 프로젝트를 .NET Framework에서 .NET Core 3.1로 이식하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-106">This article describes how to port C++/CLI projects from .NET Framework to .NET Core 3.1.</span></span>

## <a name="ccli-net-core-limitations"></a><span data-ttu-id="cd7b2-107">C++/CLI .NET Core 제한 사항</span><span class="sxs-lookup"><span data-stu-id="cd7b2-107">C++/CLI .NET Core limitations</span></span>

<span data-ttu-id="cd7b2-108">다른 언어에 비해 C++/CLI 프로젝트를 .NET Core로 이식하는 데는 몇 가지 중요한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-108">There are some important limitations to porting C++/CLI projects to .NET Core compared to other languages:</span></span>

* <span data-ttu-id="cd7b2-109">.NET Core에 대한 C++/CLI 지원은 Windows 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-109">C++/CLI support for .NET Core is Windows only.</span></span>
* <span data-ttu-id="cd7b2-110">C++/CLI 프로젝트는 .NET Standard를 대상으로 할 수 없습니다. .NET Core(또는 .NET Framework)만 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-110">C++/CLI projects can't target .NET Standard, only .NET Core (or .NET Framework).</span></span>
* <span data-ttu-id="cd7b2-111">C++/CLI 프로젝트는 새 SDK 스타일 프로젝트 파일 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-111">C++/CLI projects don't support the new SDK-style project file format.</span></span> <span data-ttu-id="cd7b2-112">대신 .NET Core를 대상으로 하는 경우에도 C++/CLI 프로젝트는 기존 vcxproj 파일 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-112">Instead, even when targeting .NET Core, C++/CLI projects use the existing vcxproj file format.</span></span>
* <span data-ttu-id="cd7b2-113">C++/CLI 프로젝트는 여러 .NET 플랫폼을 멀티 타기팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-113">C++/CLI projects can't multitarget multiple .NET platforms.</span></span> <span data-ttu-id="cd7b2-114">.NET Framework와 .NET Core 모두에 대해 C++/CLI 프로젝트를 빌드해야 하는 경우 별도의 프로젝트 파일을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-114">If you need to build a C++/CLI project for both .NET Framework and .NET Core, use separate project files.</span></span>
* <span data-ttu-id="cd7b2-115">.NET Core는 `-clr:pure` 또는 `-clr:safe` 컴파일을 지원하지 않습니다. 새 `-clr:netcore` 옵션(.NET Framework의 `-clr`와 동일)만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-115">.NET Core doesn't support `-clr:pure` or `-clr:safe` compilation, only the new `-clr:netcore` option (which is equivalent to `-clr` for .NET Framework).</span></span>

## <a name="port-a-ccli-project"></a><span data-ttu-id="cd7b2-116">C++/CLI 프로젝트 이식</span><span class="sxs-lookup"><span data-stu-id="cd7b2-116">Port a C++/CLI project</span></span>

<span data-ttu-id="cd7b2-117">C++/CLI 프로젝트를 .NET Core로 이식하려면 vcxproj 파일을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-117">To port a C++/CLI project to .NET Core, make the following changes to the vcxproj file.</span></span> <span data-ttu-id="cd7b2-118">C++/CLI 프로젝트가 SDK 스타일의 프로젝트 파일을 사용하지 않기 때문에 이 마이그레이션 단계는 다른 프로젝트 형식에 필요한 단계와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-118">These migration steps differ from the steps needed for other project types because C++/CLI projects don't use SDK-style project files.</span></span>

1. <span data-ttu-id="cd7b2-119">`<CLRSupport>true</CLRSupport>` 속성을 `<CLRSupport>NetCore</CLRSupport>`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-119">Replace `<CLRSupport>true</CLRSupport>` properties with `<CLRSupport>NetCore</CLRSupport>`.</span></span> <span data-ttu-id="cd7b2-120">이 속성은 주로 구성별 속성 그룹에 있으므로 여러 위치에서 바꿔야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-120">This property is often in configuration-specific property groups, so you may need to replace it in multiple places.</span></span>
2. <span data-ttu-id="cd7b2-121">`<TargetFrameworkVersion>` 속성을 `<TargetFramework>netcoreapp3.1</TargetFramework>`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-121">Replace `<TargetFrameworkVersion>` properties with `<TargetFramework>netcoreapp3.1</TargetFramework>`.</span></span>
3. <span data-ttu-id="cd7b2-122">모든 .NET Framework 참조(예: `<Reference Include="System" />`)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-122">Remove any .NET Framework references (like `<Reference Include="System" />`).</span></span> <span data-ttu-id="cd7b2-123">.NET Core SDK 어셈블리는 `<CLRSupport>NetCore</CLRSupport>`를 사용할 때 자동으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-123">.NET Core SDK assemblies are automatically referenced when using `<CLRSupport>NetCore</CLRSupport>`.</span></span>
4. <span data-ttu-id="cd7b2-124">.NET Core에서 사용할 수 없는 API를 제거하려면 필요에 따라 cpp 파일의 API 사용을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-124">Update API usage in cpp files, as necessary, to remove APIs unavailable to .NET Core.</span></span> <span data-ttu-id="cd7b2-125">C++/CLI 프로젝트는 상당히 얇은 interop 계층이기 때문에 필요한 변경 내용이 많지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-125">Because C++/CLI projects tend to be fairly thin interop layers, there are often not many changes needed.</span></span> <span data-ttu-id="cd7b2-126">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)는 전적으로 관리되는 이진 파일과 마찬가지로 C++/CLI 이진에서 사용하는 지원되지 않는 .NET API를 식별하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-126">The [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) can be used to identify unsupported .NET APIs used by C++/CLI binaries just as with purely managed binaries.</span></span> <span data-ttu-id="cd7b2-127">코드 이식성을 확인하고 .NET Core API와 함께 작동하도록 프로젝트를 업데이트하는 방법에 대한 지침은 [라이브러리 이식 지침](./libraries.md#determine-portability)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-127">Guidelines for determining code portability and updating projects to work with .NET Core APIs are available in the [library porting guidance](./libraries.md#determine-portability).</span></span>

### <a name="wpf-and-windows-forms-usage"></a><span data-ttu-id="cd7b2-128">WPF 및 Windows Forms 사용법</span><span class="sxs-lookup"><span data-stu-id="cd7b2-128">WPF and Windows Forms usage</span></span>

<span data-ttu-id="cd7b2-129">.NET Core C++/CLI 프로젝트는 Windows Forms 및 WPF API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-129">.NET Core C++/CLI projects can use Windows Forms and WPF APIs.</span></span> <span data-ttu-id="cd7b2-130">해당 Windows 데스크톱 API를 사용하려면 UI 라이브러리에 명시적 프레임워크 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-130">To use these Windows desktop APIs, you need to add explicit framework references to the UI libraries.</span></span> <span data-ttu-id="cd7b2-131">Windows 데스크톱 API를 사용하는 SDK 스타일 프로젝트는 `Microsoft.NET.Sdk.WindowsDesktop` SDK를 사용하여 필요한 프레임워크 라이브러리를 자동으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-131">SDK-style projects that use Windows desktop APIs reference the necessary framework libraries automatically by using the `Microsoft.NET.Sdk.WindowsDesktop` SDK.</span></span> <span data-ttu-id="cd7b2-132">C++/CLI 프로젝트는 SDK 스타일 프로젝트 형식을 사용하지 않으므로 .NET Core를 대상으로 할 때 명시적 프레임워크 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-132">Because C++/CLI projects don't use the SDK-style project format, they need to add explicit framework references when targeting .NET Core.</span></span>

<span data-ttu-id="cd7b2-133">Windows Forms API를 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-133">To use Windows Forms APIs, add this reference to the vcxproj file:</span></span>

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

<span data-ttu-id="cd7b2-134">WPF API를 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-134">To use WPF APIs, add this reference to the vcxproj file:</span></span>

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

<span data-ttu-id="cd7b2-135">Windows Forms 및 WPF API를 모두 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-135">To use both Windows Forms and WPF APIs, add this reference to the vcxproj file:</span></span>

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

<span data-ttu-id="cd7b2-136">현재는 Visual Studio의 참조 관리자를 사용하여 해당 참조를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-136">Currently, it's not possible to add these references using Visual Studio's reference manager.</span></span> <span data-ttu-id="cd7b2-137">대신 프로젝트 파일을 수동으로 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-137">Instead, update the project file manually.</span></span> <span data-ttu-id="cd7b2-138">이 업데이트는 Visual Studio에서 프로젝트를 언로드한 다음 프로젝트 파일을 편집하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-138">This update can be done in Visual Studio by unloading the project and then editing the project file.</span></span> <span data-ttu-id="cd7b2-139">VS Code 같은 다른 편집기를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-139">You can also use another editor like VS Code.</span></span>

## <a name="build-without-msbuild"></a><span data-ttu-id="cd7b2-140">MSBuild를 사용하지 않고 빌드</span><span class="sxs-lookup"><span data-stu-id="cd7b2-140">Build without MSBuild</span></span>

<span data-ttu-id="cd7b2-141">MSBuild를 사용하지 않고 C++/CLI 프로젝트를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-141">It's also possible to build C++/CLI projects without using MSBuild.</span></span> <span data-ttu-id="cd7b2-142">*cl.exe* 및 *link.exe*를 사용하여 .NET Core용 C++CLI 프로젝트를 직접 빌드하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-142">Follow these steps to build a C++/CLI project for .NET Core directly with *cl.exe* and *link.exe*:</span></span>

1. <span data-ttu-id="cd7b2-143">컴파일하는 경우 `-clr:netcore`를 *cl.exe*에 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-143">When compiling, pass `-clr:netcore` to *cl.exe*.</span></span>
2. <span data-ttu-id="cd7b2-144">필요한 .NET Core 참조 어셈블리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-144">Reference necessary .NET Core reference assemblies.</span></span>
3. <span data-ttu-id="cd7b2-145">연결할 때 *ijwhost*를 찾을 수 있도록 .NET Core 앱 호스트 디렉터리를 `LibPath`로 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-145">When linking, provide the .NET Core app host directory as a `LibPath` (so that *ijwhost.lib* can be found).</span></span>
4. <span data-ttu-id="cd7b2-146">.NET Core 앱 호스트 디렉터리에서 *ijwhost.dll*을 프로젝트의 출력 디렉터리로 복사하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-146">Copy *ijwhost.dll* (from the .NET Core app host directory) to the project's output directory.</span></span>
5. <span data-ttu-id="cd7b2-147">관리 코드를 실행할 애플리케이션의 첫 번째 구성 요소에 대한 [runtimeconfig.template.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) 파일이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-147">Make sure a [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) file exists for the first component of the application that will run managed code.</span></span> <span data-ttu-id="cd7b2-148">애플리케이션에 관리형 진입점이 있으면 `runtime.config` 파일이 자동으로 만들어지고 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-148">If the application has a managed entry point, a `runtime.config` file will be created and copied automatically.</span></span> <span data-ttu-id="cd7b2-149">그러나 애플리케이션에 네이티브 진입점이 있으면 .NET Core 런타임을 사용하기 위해 첫 번째 C++/CLI 라이브러리의 `runtimeconfig.json` 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-149">If the application has a native entry point, though, you need to create a `runtimeconfig.json` file for the first C++/CLI library to use the .NET Core runtime.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cd7b2-150">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="cd7b2-150">Known issues</span></span>

<span data-ttu-id="cd7b2-151">.NET Core를 대상으로 하는 C++/CLI 프로젝트로 작업할 때 살펴볼 몇 가지 알려진 이슈가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-151">There are a couple known issues to look out for when working with C++/CLI projects targeting .NET Core.</span></span>

* <span data-ttu-id="cd7b2-152">.NET Core C++/CLI 프로젝트의 WPF 프레임워크 참조는 현재 기호를 가져올 수 없다는 일부 불필요한 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-152">A WPF framework reference in .NET Core C++/CLI projects currently causes some extraneous warnings about being unable to import symbols.</span></span> <span data-ttu-id="cd7b2-153">해당 경고는 무시해주세요. 곧 해결될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-153">These warnings can be safely ignored and should be fixed soon.</span></span>
* <span data-ttu-id="cd7b2-154">애플리케이션에 네이티브 진입점이 있는 경우 관리 코드를 먼저 실행하는 C++/CLI 라이브러리에 [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-154">If the application has a native entry point, the C++/CLI library that first executes managed code needs a [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) file.</span></span> <span data-ttu-id="cd7b2-155">이 구성 파일은 .NET Core 런타임이 시작될 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-155">This config file is used when the .NET Core runtime starts.</span></span> <span data-ttu-id="cd7b2-156">C++/CLI 프로젝트는 빌드 시 `runtimeconfig.json` 파일을 자동으로 만들지 않으므로 파일을 수동으로 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-156">C++/CLI projects don't create `runtimeconfig.json` files automatically at build time yet, so the file must be generated manually.</span></span> <span data-ttu-id="cd7b2-157">관리형 진입점에서 C++/CLI 라이브러리를 호출하는 경우에는 진입점 어셈블리에 런타임을 시작할 때 사용하는 파일이 있으므로 C++/CLI 라이브러리에 `runtimeconfig.json` 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-157">If a C++/CLI library is called from a managed entry point, then the C++/CLI library doesn't need a `runtimeconfig.json` file (since the entry point assembly will have one that is used when starting the runtime).</span></span> <span data-ttu-id="cd7b2-158">다음은 간단한 샘플 `runtimeconfig.json` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-158">A simple sample `runtimeconfig.json` file is shown below.</span></span> <span data-ttu-id="cd7b2-159">자세한 내용은 [GitHub 사양](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd7b2-159">For more information, see the [spec on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

    ```json
    {
          "runtimeOptions": {
             "tfm": "netcoreapp3.1",
             "framework": {
                "name": "Microsoft.NETCore.App",
                "version": "3.1.0"
             }
          }
    }
    ```
