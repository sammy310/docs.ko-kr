---
title: .NET Core 3.0의 새로운 기능
description: .NET Core 3.0에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 9f553e9af16be0891f208832c5daa444a1b736e2
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281513"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="c2cc5-103">.NET Core 3.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="c2cc5-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="c2cc5-104">이 문서에서는 .NET Core 3.0의 새로운 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="c2cc5-105">가장 중요한 개선 사항 중 하나는 Windows 데스크톱 애플리케이션에 대한 지원(Windows만 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="c2cc5-106">.NET Core 3.0 SDK 구성 요소 Windows 데스크톱을 사용하여 Windows Forms 및 Windows Presentation Foundation(WPF) 애플리케이션을 포트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="c2cc5-107">분명히 말하지만, Windows 데스크톱 구성 요소는 Windows에서만 지원되고 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="c2cc5-108">자세한 내용은 이 문서 후반부의 [Windows 데스크톱](#windows-desktop) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="c2cc5-109">.NET Core 3.0에서는 C# 8.0에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="c2cc5-110">[Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상, [Mac용 Visual Studio 8.3](/visualstudio/mac/install-preview) 이상 또는 [Visual Studio Code](https://code.visualstudio.com/)를 최신 **C# 확장**과 함께 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="c2cc5-111">Windows, macOS 또는 Linux에서 지금 바로 [.NET Core 3.0을 다운로드하여 시작](https://aka.ms/netcore3download)하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="c2cc5-112">릴리스에 대한 자세한 내용은 [.NET Core 3.0 알림](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="c2cc5-113">.NET Core RC1은 Microsoft에서 프로덕션용으로 간주되었으며 완전히 지원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="c2cc5-114">미리 보기 릴리스를 사용하는 경우, 계속 지원을 받으려면 RTM 버전으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="c2cc5-115">언어 향상 C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c2cc5-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="c2cc5-116">[Null 허용 참조 형식](../../csharp/tutorials/nullable-reference-types.md) 기능,[ 비동기 스트림](../../csharp/tutorials/generate-consume-asynchronous-stream.md), [추가 패턴](../../csharp/tutorials/pattern-matching.md) 등을 포함하는 C# 8.0도 이 릴리스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="c2cc5-117">C# 8.0 기능에 대한 자세한 내용은 [C# 8.0의 새로운 기능](../../csharp/whats-new/csharp-8.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="c2cc5-118">아래에 설명된 다음 API 기능을 지원하기 위해 언어 향상 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="c2cc5-119">범위 및 인덱스</span><span class="sxs-lookup"><span data-stu-id="c2cc5-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="c2cc5-120">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="c2cc5-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="c2cc5-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="c2cc5-121">.NET Standard 2.1</span></span>

<span data-ttu-id="c2cc5-122">.NET Core 3.0에서는 **.NET Standard 2.1**을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="c2cc5-123">하지만 기본 `dotnet new classlib` 템플릿은 여전히 **.NET Standard 2.0**을 대상으로 하는 프로젝트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="c2cc5-124">**.NET 표준 2.1**을 대상으로 지정하려면 프로젝트 파일을 편집하고 `TargetFramework` 속성을 `netstandard2.1`로 변경하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="c2cc5-125">Visual Studio를 사용하고 있는 경우 Visual Studio 2017은 **.NET Standard 2.1** 또는 **.NET Core 3.0**을 지원하지 않으므로 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="c2cc5-126">컴파일/배포</span><span class="sxs-lookup"><span data-stu-id="c2cc5-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="c2cc5-127">기본 실행 파일</span><span class="sxs-lookup"><span data-stu-id="c2cc5-127">Default executables</span></span>

<span data-ttu-id="c2cc5-128">이제 .NET Core에서 기본적으로 [런타임 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-128">.NET Core now builds [runtime-dependent executables](../deploying/index.md#publish-runtime-dependent) by default.</span></span> <span data-ttu-id="c2cc5-129">이는 전역적으로 설치된 .NET Core 버전을 사용하는 애플리케이션을 위한 새로운 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="c2cc5-130">지금까지는 [자체 포함 배포](../deploying/index.md#publish-self-contained)만 실행 파일을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-130">Previously, only [self-contained deployments](../deploying/index.md#publish-self-contained) would produce an executable.</span></span>

<span data-ttu-id="c2cc5-131">`dotnet build` 또는 `dotnet publish` 중에 사용 중인 SDK의 환경 및 플랫폼과 일치하는 실행 파일(**appHost**)이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-131">During `dotnet build` or `dotnet publish`, an executable (known as the **appHost**) is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="c2cc5-132">다른 네이티브 실행 파일과 마찬가지로 이러한 실행 파일에서도 다음과 같은 동일한 기능을 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="c2cc5-133">실행 파일을 두 번 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="c2cc5-134">Windows의 `myapp.exe`, Linux 및 macOS의 `./myapp`과 같은 애플리케이션을 명령 프롬프트에서 직접 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="macos-apphost-and-notarization"></a><span data-ttu-id="c2cc5-135">macOS appHost 및 공증</span><span class="sxs-lookup"><span data-stu-id="c2cc5-135">macOS appHost and notarization</span></span>

<span data-ttu-id="c2cc5-136">‘macOS만 해당’</span><span class="sxs-lookup"><span data-stu-id="c2cc5-136">*macOS only*</span></span>

<span data-ttu-id="c2cc5-137">공증된 macOS용 .NET Core SDK 3.0부터, 기본 실행 파일(appHost)을 생성하는 설정이 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-137">Starting with the notarized .NET Core SDK 3.0 for macOS, the setting to produce a default executable (known as the appHost) is disabled by default.</span></span> <span data-ttu-id="c2cc5-138">자세한 내용은 [macOS Catalina 공증과 이것이 .NET Core 다운로드 및 프로젝트에 미치는 영향](../install/macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-138">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="c2cc5-139">appHost 설정이 사용하도록 설정된 경우, 빌드 또는 게시할 때 .NET Core가 네이티브 Mach-O 실행 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-139">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="c2cc5-140">앱을 `dotnet run` 명령을 사용하여 소스 코드에서 실행하거나 Mach-O 실행 파일을 직접 시작하면 앱이 appHost 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-140">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="c2cc5-141">사용자가 appHost 없이 [런타임 종속](../deploying/index.md#publish-runtime-dependent) 앱을 시작할 유일할 방법은 `dotnet <filename.dll>` 명령을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-141">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="c2cc5-142">appHost는 앱을 [자체 포함](../deploying/index.md#publish-self-contained) 방식으로 게시하면 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-142">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="c2cc5-143">appHost는 다음과 같이 프로젝트 수준에서 구성하거나 `-p:UseAppHost` 매개 변수를 사용하여 특정 `dotnet` 명령에 대해 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-143">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="c2cc5-144">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="c2cc5-144">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="c2cc5-145">명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2cc5-145">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="c2cc5-146">`UseAppHost` 설정에 대한 자세한 내용은 [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost)(Microsoft.NET.Sdk의 MSBuild 속성)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-146">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="c2cc5-147">단일 실행 파일</span><span class="sxs-lookup"><span data-stu-id="c2cc5-147">Single-file executables</span></span>

<span data-ttu-id="c2cc5-148">`dotnet publish` 명령은 플랫폼별 단일 실행 파일로 앱 패키징을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-148">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="c2cc5-149">실행 파일은 자동 압축 풀기 파일이며 앱을 실행하는 데 필요한 모든 종속 항목(네이티브 포함)을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-149">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="c2cc5-150">앱을 처음 실행하면 애플리케이션은 앱 이름과 빌드 식별자에 기반하여 디렉터리로 압축이 풀립니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-150">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="c2cc5-151">해당 애플리케이션을 다시 실행하면 시작이 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-151">Startup is faster when the application is run again.</span></span> <span data-ttu-id="c2cc5-152">새 버전을 사용한 경우가 아니라면 두 번째에는 애플리케이션의 압축을 풀 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-152">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="c2cc5-153">단일 실행 파일을 게시하려면 `dotnet publish` 명령을 사용하여 프로젝트 또는 명령줄에 `PublishSingleFile`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-153">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="c2cc5-154">또는</span><span class="sxs-lookup"><span data-stu-id="c2cc5-154">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="c2cc5-155">단일 파일 게시에 대한 자세한 내용은 [단일 파일 번들러 설계 문서](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-155">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="c2cc5-156">어셈블리 연결</span><span class="sxs-lookup"><span data-stu-id="c2cc5-156">Assembly linking</span></span>

<span data-ttu-id="c2cc5-157">.NET Core SDK 3.0에는 IL을 분석하고 사용되지 않는 어셈블리를 잘라내어 앱의 크기를 줄일 수 있는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-157">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="c2cc5-158">자체 포함 앱에는 호스트 컴퓨터에 .NET을 설치하지 않고도 코드를 실행하는 데 필요한 모든 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-158">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="c2cc5-159">그러나 앱을 실행하는 데 프레임워크의 작은 하위 집합만 필요한 경우가 많으므로 사용되지 않는 다른 라이브러리를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-159">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="c2cc5-160">이제 .NET Core에 [IL 링커](https://github.com/mono/linker) 도구를 사용하여 앱의 IL을 검사하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-160">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="c2cc5-161">이 도구는 필요한 코드를 검색한 다음, 사용되지 않는 라이브러리를 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-161">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="c2cc5-162">이 도구를 통해 일부 앱의 배포 크기를 훨씬 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-162">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="c2cc5-163">이 도구를 사용하려면 프로젝트에서 `<PublishTrimmed>` 설정을 추가하고 자체 포함 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-163">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="c2cc5-164">예를 들어 포함된 기본 “hello world” 새 콘솔 프로젝트 템플릿은 게시될 때 크기가 약 70MB입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-164">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="c2cc5-165">`<PublishTrimmed>`를 사용하면 크기가 약 30MB로 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-165">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="c2cc5-166">잘라낼 때 리플렉션이나 관련된 동적 기능을 사용하는 애플리케이션 또는 프레임워크 (ASP.NET Core, WPF 등)가 중단되는 경우가 많다는 것을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-166">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="c2cc5-167">이러한 중단은 링커에서 이 동적 동작을 알지 못하고 리플렉션에 필요한 프레임워크 유형을 확인할 수 없기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-167">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="c2cc5-168">이 시나리오를 인식하도록 IL 링커 도구를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-168">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="c2cc5-169">무엇보다도, 잘라낸 후 앱을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-169">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="c2cc5-170">IL 링커 도구에 대한 자세한 내용은 [문서](https://aka.ms/dotnet-illink)또는 [mono/linker]( https://github.com/mono/linker) 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-170">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="c2cc5-171">계층화된 컴파일</span><span class="sxs-lookup"><span data-stu-id="c2cc5-171">Tiered compilation</span></span>

<span data-ttu-id="c2cc5-172">[계층화된 컴파일](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)(TC)은 .NET Core 3.0에서 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-172">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="c2cc5-173">런타임 시 JIT(Just-In-Time) 컴파일러를 더욱 유연하게 사용하여 성능을 개선할 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-173">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="c2cc5-174">계층화된 컴파일의 주요 혜택은 품질은 낮지만 빠른 계층의 (재)JIT 메서드 또는 품질은 높지만 느린 계층의 (재)JIT 메서드의 두 가지 방법을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-174">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="c2cc5-175">품질은 메서드가 얼마나 제대로 최적화되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-175">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="c2cc5-176">TC는 시작에서 정적인 상태까지 다양한 실행 단계를 거치므로 애플리케이션의 성능을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-176">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="c2cc5-177">계층화된 컴파일을 사용하지 않도록 설정하는 경우 모든 메서드는 시작 성능보다 정적인 상태 성능에 편향된 단일 방식으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-177">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="c2cc5-178">TC를 사용하도록 설정하면 앱이 시작될 때 메서드 컴파일에 다음과 같은 동작이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-178">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="c2cc5-179">메서드에 Ahead Of Time 컴파일 코드([ReadyToRun](#readytorun-images))가 있는 경우 사전 생성된 코드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-179">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="c2cc5-180">그렇지 않으면 메서드가 JIT 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-180">Otherwise, the method is jitted.</span></span> <span data-ttu-id="c2cc5-181">일반적으로 이 메서드는 값 형식의 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-181">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="c2cc5-182">*빠른 JIT*은 품질이 더 낮거나 덜 최적화된 코드를 더욱 빠르게 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-182">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="c2cc5-183">.NET Core 3.0에서 빠른 JIT는 루프를 포함하지 않은 메서드에 기본적으로 사용하도록 설정되며, 시작하는 동안 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-183">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="c2cc5-184">완전히 최적화된 JIT는 품질이 더 높거나 더 최적화된 코드를 더욱 느리게 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-184">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="c2cc5-185">빠른 JIT를 사용하지 않는 메서드의 경우(예: 메서드가 <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>으로 특성이 지정된 경우) 완전히 최적화된 JIT가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-185">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="c2cc5-186">자주 호출되는 메서드의 경우 Just-In-Time 컴파일러는 결과적으로 백그라운드에서 완전히 최적화된 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-186">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="c2cc5-187">그런 다음, 최적화된 코드는 해당 메서드에 대해 미리 컴파일된 코드를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-187">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="c2cc5-188">빠른 JIT에 의해 생성된 코드는 실행 속도가 저하되거나, 더 많은 메모리를 할당하거나, 더 많은 스택 공간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-188">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="c2cc5-189">이슈가 있는 경우 프로젝트 파일에서 이 MSBuild 속성을 사용하여 빠른 JIT를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-189">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="c2cc5-190">TC를 완전히 사용하지 않도록 설정하려면 프로젝트 파일에서 이 MSBuild 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-190">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="c2cc5-191">프로젝트 파일에서 이러한 설정을 변경하는 경우 새 설정이 반영되도록 클린 빌드(`obj` 및 `bin` 디렉터리를 삭제한 후 다시 빌드)를 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-191">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="c2cc5-192">런타임에 컴파일을 구성하는 방법에 대한 자세한 내용은 [컴파일을 위한 런타임 구성 옵션](../run-time-config/compilation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-192">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="c2cc5-193">ReadyToRun 이미지</span><span class="sxs-lookup"><span data-stu-id="c2cc5-193">ReadyToRun images</span></span>

<span data-ttu-id="c2cc5-194">R2R(ReadyToRun) 형식으로 애플리케이션 어셈블리를 컴파일하면 .NET Core 애플리케이의 시작 시간을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-194">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="c2cc5-195">R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-195">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="c2cc5-196">R2R 이진 파일은 애플리케이션이 로드될 때 JIT(Just-In-Time) 컴파일러에서 수행해야 하는 작업량을 줄여 시작 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-196">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="c2cc5-197">이진 파일에는 JIT에서 생성되는 코드와 비슷한 네이티브 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-197">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="c2cc5-198">그러나 R2R 이진 파일은 일부 시나리오에서 필요한 IL(중간 언어) 코드와 동일한 코드의 네이티브 버전을 모두 포함하므로 크기가 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-198">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="c2cc5-199">R2R은 Linux x64 또는 Windows x64와 같은 특정 런타임 환경(RID)을 대상으로 하는 자체 포함 앱을 게시하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-199">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="c2cc5-200">프로젝트를 ReadyToRun으로 컴파일하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-200">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="c2cc5-201">프로젝트에 `<PublishReadyToRun>` 설정 추가:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-201">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="c2cc5-202">자체 포함 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-202">Publish a self-contained app.</span></span> <span data-ttu-id="c2cc5-203">예를 들어 이 명령은 Windows 64비트 버전용 자체 포함 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-203">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="c2cc5-204">교차 플랫폼/아키텍처 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c2cc5-204">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="c2cc5-205">현재 ReadyToRun 컴파일러는 교차 대상 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-205">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="c2cc5-206">지정된 대상에서 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-206">You must compile on a given target.</span></span> <span data-ttu-id="c2cc5-207">예를 들어 Windows x64용 R2R 이미지를 만들려는 경우 해당 환경에서 게시 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-207">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="c2cc5-208">교차 대상 지정 예외:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-208">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="c2cc5-209">Windows x64를 사용하여 Windows ARM32, ARM64 및 x86 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-209">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="c2cc5-210">Windows x86을 사용하여 Windows ARM32 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-210">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="c2cc5-211">Linux X64를 사용하여 Linux ARM32 및 ARM64 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-211">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="c2cc5-212">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="c2cc5-212">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="c2cc5-213">주 버전 런타임 롤포워드</span><span class="sxs-lookup"><span data-stu-id="c2cc5-213">Major-version runtime roll forward</span></span>

<span data-ttu-id="c2cc5-214">.NET Core 3.0은 애플리케이션을 .NET Core의 최신 주 버전으로 롤포워드할 수 있는 옵트인(opt-in) 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-214">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="c2cc5-215">또한, 롤포워드가 애플리케이션에 적용되는 방식을 제어하기 위해 새 설정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-215">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="c2cc5-216">이 설정은 다음과 같은 방법으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-216">This can be configured in the following ways:</span></span>

- <span data-ttu-id="c2cc5-217">프로젝트 파일 속성: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-217">Project file property: `RollForward`</span></span>
- <span data-ttu-id="c2cc5-218">런타임 구성 파일 속성: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-218">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="c2cc5-219">환경 변수: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-219">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="c2cc5-220">명령줄 인수: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-220">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="c2cc5-221">다음 값 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-221">One of the following values must be specified.</span></span> <span data-ttu-id="c2cc5-222">설정을 생략하면 **Minor**가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-222">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="c2cc5-223">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-223">**LatestPatch**</span></span>\
<span data-ttu-id="c2cc5-224">가장 높은 패치 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-224">Roll forward to the highest patch version.</span></span> <span data-ttu-id="c2cc5-225">부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-225">This disables minor version roll forward.</span></span>
- <span data-ttu-id="c2cc5-226">**Minor**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-226">**Minor**</span></span>\
<span data-ttu-id="c2cc5-227">요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-227">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="c2cc5-228">요청된 부 버전이 있다면 **LatestPatch** 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-228">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="c2cc5-229">**Major**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-229">**Major**</span></span>\
<span data-ttu-id="c2cc5-230">요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-230">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="c2cc5-231">요청된 주 버전이 있다면 **Minor** 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-231">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="c2cc5-232">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-232">**LatestMinor**</span></span>\
<span data-ttu-id="c2cc5-233">요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-233">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="c2cc5-234">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-234">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="c2cc5-235">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-235">**LatestMajor**</span></span>\
<span data-ttu-id="c2cc5-236">요청된 주 버전이 있는 경우에도 가장 높은 주, 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-236">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="c2cc5-237">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-237">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="c2cc5-238">**Disable**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-238">**Disable**</span></span>\
<span data-ttu-id="c2cc5-239">롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-239">Don't roll forward.</span></span> <span data-ttu-id="c2cc5-240">지정된 버전에만 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-240">Only bind to specified version.</span></span> <span data-ttu-id="c2cc5-241">이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-241">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="c2cc5-242">이 값은 테스트용으로만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-242">This value is only recommended for testing.</span></span>

<span data-ttu-id="c2cc5-243">**Disable** 설정 이외에도 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-243">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="c2cc5-244">기본적으로 요청된 버전(애플리케이션에 대한 `.runtimeconfig.json`에 지정됨)이 릴리스 버전인 경우에만 릴리스 버전이 롤포워드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-244">By default, if the requested version (as specified in `.runtimeconfig.json` for the application) is a release version, only release versions are considered for roll forward.</span></span> <span data-ttu-id="c2cc5-245">시험판 버전은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-245">Any pre-release versions are ignored.</span></span> <span data-ttu-id="c2cc5-246">일치하는 릴리스 버전이 없는 경우 시험판 버전이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-246">If there is no matching release version, then pre-release versions are taken into account.</span></span> <span data-ttu-id="c2cc5-247">이 동작은 `DOTNET_ROLL_FORWARD_TO_PRERELEASE=1`을 설정하여 변경할 수 있으며, 이 경우 모든 버전이 항상 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-247">This behavior can be changed by setting `DOTNET_ROLL_FORWARD_TO_PRERELEASE=1`, in which case all versions are always considered.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="c2cc5-248">빌드 복사본 종속성</span><span class="sxs-lookup"><span data-stu-id="c2cc5-248">Build copies dependencies</span></span>

<span data-ttu-id="c2cc5-249">`dotnet build` 명령은 이제 애플리케이션에 대한 NuGet 종속성을 NuGet 캐시에서 빌드 출력 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-249">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="c2cc5-250">이전에는 종속성이 `dotnet publish` 중에만 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-250">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="c2cc5-251">연결, Razor 페이지 게시 등 여전히 게시해야 하는 일부 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-251">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="c2cc5-252">로컬 도구</span><span class="sxs-lookup"><span data-stu-id="c2cc5-252">Local tools</span></span>

<span data-ttu-id="c2cc5-253">.NET core 3.0에서는 로컬 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-253">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="c2cc5-254">로컬 도구는 [전역 도구](../tools/global-tools.md)와 유사하지만 디스크의 특정 위치와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-254">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="c2cc5-255">로컬 도구는 전역적으로 사용할 수 없으며 NuGet 패키지로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-255">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="c2cc5-256">.NET Core 3.0 미리 보기 1에서 `dotnet tool restore` 또는 `dotnet tool install` 삭제와 같은 현지 도구를 사용했다면 로컬 도구 캐시 폴더를 삭제하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-256">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="c2cc5-257">그렇지 않으면 로컬 도구는 모든 최신 릴리스에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-257">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="c2cc5-258">이 폴더의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-258">This folder is located at:</span></span>
>
> <span data-ttu-id="c2cc5-259">macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-259">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="c2cc5-260">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="c2cc5-260">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="c2cc5-261">로컬 도구는 현재 디렉터리에 있는 매니페스트 파일 이름 `dotnet-tools.json`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-261">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="c2cc5-262">이 매니페스트 파일은 해당 폴더 및 그 아래에서 사용할 수 있는 도구를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-262">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="c2cc5-263">코드를 사용하는 누구나 동일한 도구를 복구하고 사용할 수 있도록 코드로 매니페스트 파일을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-263">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="c2cc5-264">전역 도구와 로컬 도구 둘 다, 호환되는 버전의 런타임이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-264">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="c2cc5-265">현재 NuGet.org의 많은 도구는 .NET Core 런타임 2.1을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-265">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="c2cc5-266">이러한 도구를 전역 또는 로컬로 설치하려면 여전히 [NET Core 2.1 런타임](https://dotnet.microsoft.com/download/dotnet-core/2.1)을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-266">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="c2cc5-267">새 global.json 옵션</span><span class="sxs-lookup"><span data-stu-id="c2cc5-267">New global.json options</span></span>

<span data-ttu-id="c2cc5-268">*global. json* 파일에는 사용되는 .NET Core SDK 버전을 정의하려고 할 때 더 많은 유연성을 제공하는 새로운 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-268">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="c2cc5-269">새 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-269">The new options are:</span></span>

- <span data-ttu-id="c2cc5-270">`allowPrerelease`: 사용할 SDK 버전을 선택할 때 SDK 확인자가 시험판 버전을 고려해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-270">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="c2cc5-271">`rollForward`: SDK 버전을 선택할 때, 특정 SDK 버전이 누락된 경우 대체하거나 상위 버전을 사용하기 위한 지시문으로 사용할 롤포워드 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-271">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="c2cc5-272">기본값, 지원되는 값, 새 일치 규칙을 비롯한 변경 내용에 대한 자세한 내용은 [global.json 개요](../tools/global-json.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-272">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="c2cc5-273">더 작은 가비지 수집 힙 크기</span><span class="sxs-lookup"><span data-stu-id="c2cc5-273">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="c2cc5-274">가비지 수집기의 기본 힙 크기가 감소되어 .NET Core에서 사용되는 메모리가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-274">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="c2cc5-275">이러한 변화는 최신 프로세서 캐시 크기의 생성 0 할당 예산과 부합됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-275">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="c2cc5-276">가비지 수집 Large Page 지원</span><span class="sxs-lookup"><span data-stu-id="c2cc5-276">Garbage Collection Large Page support</span></span>

<span data-ttu-id="c2cc5-277">Large Page(또는 Linux Huge Page)는 운영 체제가 이러한 큰 페이지를 요청하는 애플리케이션의 성능을 개선하기 위해 네이티브 페이지 크기(보통 4K)보다 더 큰 메모리 영역을 구축할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-277">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="c2cc5-278">이제 가비지 수집기는 Windows에서 큰 페이지를 할당하기 위해 선택할 수 있는 옵트인(opt-in) 기능으로 **GCLargePages** 설정을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-278">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="c2cc5-279">Windows 데스크톱 및 COM</span><span class="sxs-lookup"><span data-stu-id="c2cc5-279">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="c2cc5-280">.NET Core SDK Windows Installer</span><span class="sxs-lookup"><span data-stu-id="c2cc5-280">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="c2cc5-281">Windows용 MSI 설치 관리자는 .NET Core 3.0부터 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-281">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="c2cc5-282">이제 SDK 설치 관리자는 준비된 SDK 기반 밴드 릴리스를 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-282">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="c2cc5-283">기능 밴드는 번호 버전의 *패치* 섹션에서 *수백 개*의 그룹에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-283">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="c2cc5-284">예를 들어, **3.0._101_** 및 **3.0._201_** 은 두 가지 기능 밴드의 버전이며, **3.0._101_** 및 **3.0._199_** 는 동일한 기능 밴드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-284">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="c2cc5-285">그리고 .NET Core SDK **3.0._101_** 이 설치되어 있는 경우 .NET Core SDK**3.0._100_** 은 머신에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-285">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="c2cc5-286">.NET Core SDK **3.0._200_** 이 동일한 머신에 설치되어 있는 경우 .NET Core SDK **3.0._101_** 은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-286">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="c2cc5-287">버전 관리에 대한 자세한 내용은 [.NET Core의 버전 관리 방법](../versions/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-287">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="c2cc5-288">Windows 바탕 화면</span><span class="sxs-lookup"><span data-stu-id="c2cc5-288">Windows desktop</span></span>

<span data-ttu-id="c2cc5-289">.NET Core 3.0은 Windows Presentation Foundation(WPF) 및 Windows Forms를 사용하여 Windows 데스크톱 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-289">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="c2cc5-290">이러한 프레임워크는 [XAML 아일랜드](/windows/uwp/xaml-platform/xaml-host-controls)를 통해 Windows UI XAML 라이브러리(WinUI)의 최신 컨트롤 및 Fluent 스타일을 사용하는 것도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-290">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="c2cc5-291">Windows 데스크톱 구성 요소는 Windows .NET Core 3.0 SDK의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-291">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="c2cc5-292">다음 `dotnet` 명령을 사용하여 새 WPF 또는 Windows Forms 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-292">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="c2cc5-293">Visual Studio 2019에는 .NET Core 3.0 Windows Forms 및 WPF용 **새 프로젝트** 템플릿이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-293">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="c2cc5-294">기존 .NET Framework 애플리케이션을 포트하는 방법에 대한 자세한 내용은 [WPF 프로젝트 포트](../../desktop-wpf/migration/convert-project-from-net-framework.md) 및 [Windows Forms 프로젝트 포트](../porting/winforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-294">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="c2cc5-295">WinForms의 높은 DPI</span><span class="sxs-lookup"><span data-stu-id="c2cc5-295">WinForms high DPI</span></span>

<span data-ttu-id="c2cc5-296">.NET Core Windows Forms 애플리케이션은 <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>을(를) 사용하여 높은 DPI 모드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-296">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c2cc5-297">`SetHighDpiMode` 메서드는 해당 설정이 `Application.Run` 전에 `App.Manifest` 또는 P/Invoke와 같은 다른 수단으로 설정된 경우가 아니라면 해당하는 높은 DPI 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-297">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="c2cc5-298"><xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 열거형으로 표현되는 가능한 `highDpiMode` 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-298">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="c2cc5-299">높은 DPI 모드에 대한 자세한 내용은 [Windows에서 높은 DPI 데스크톱 애플리케이션 개발](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-299">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="c2cc5-300">COM 구성 요소 생성</span><span class="sxs-lookup"><span data-stu-id="c2cc5-300">Create COM components</span></span>

<span data-ttu-id="c2cc5-301">Windows에서 이제는 COM 호출 가능 관리형 구성 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-301">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="c2cc5-302">이 기능은 COM 추가 기능 모델을 통해 .NET Core를 사용할 뿐만 아니라 .NET Framework에 패리티를 제공하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-302">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="c2cc5-303">*mscoree.dll*이 COM 서버처럼 사용되는 .NET Framework와는 달리, .NET Core는 COM 구성 요소 빌드 시 네이티브 시작 관리자 dll을 *bin* 디렉터리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-303">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="c2cc5-304">COM 구성 요소를 만들고 사용하는 방법에 대한 예는 [COM 데모](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-304">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="c2cc5-305">Windows 네이티브 Interop</span><span class="sxs-lookup"><span data-stu-id="c2cc5-305">Windows Native Interop</span></span>

<span data-ttu-id="c2cc5-306">Windows는 플랫 C API, COM 및 WinRT의 형태로 다양한 네이티브 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-306">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="c2cc5-307">.NET Core에서는 **P/Invoke**를 지원하지만, .NET Core 3.0은 **CoCreate COM API** 및 **Activate WinRT API**에 대한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-307">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="c2cc5-308">코드 예제는 [Excel 데모](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-308">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="c2cc5-309">MSIX 배포</span><span class="sxs-lookup"><span data-stu-id="c2cc5-309">MSIX Deployment</span></span>

<span data-ttu-id="c2cc5-310">[MSIX](https://docs.microsoft.com/windows/msix/)는 새로운 Windows 애플리케이션 패키지 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-310">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="c2cc5-311">Windows 10에 .NET Core 3.0 데스크톱 애플리케이션을 배포하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-311">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="c2cc5-312">Visual Studio 2019에 제공되는 [Windows 애플리케이션 패키징 프로젝트](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)를 사용하면 [자체 포함](../deploying/index.md#publish-self-contained) .NET Core 애플리케이션을 사용하여 MSIX 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-312">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#publish-self-contained) .NET Core applications.</span></span>

<span data-ttu-id="c2cc5-313">NET Core 프로젝트 파일은 `<RuntimeIdentifiers>` 속성에 지원되는 런타임을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-313">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="c2cc5-314">Linux 기능 향상</span><span class="sxs-lookup"><span data-stu-id="c2cc5-314">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="c2cc5-315">Linux용 SerialPort</span><span class="sxs-lookup"><span data-stu-id="c2cc5-315">SerialPort for Linux</span></span>

<span data-ttu-id="c2cc5-316">.NET Core 3.0은 Linux에서 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>에 대한 기본 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-316">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="c2cc5-317">이전에는 .NET Core가 Windows에서만 `SerialPort` 사용을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-317">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="c2cc5-318">Linux의 제한적 직렬 포트 지원에 대한 자세한 내용은 [GitHub 이슈 #33146](https://github.com/dotnet/corefx/issues/33146)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-318">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="c2cc5-319">Docker 및 cgroup 메모리 한도</span><span class="sxs-lookup"><span data-stu-id="c2cc5-319">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="c2cc5-320">Docker를 사용하여 Linux에서 .NET Core 3.0을 실행하면 cgroup 메모리 한도에 훨씬 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-320">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="c2cc5-321">메모리 한도가 있는 Docker 컨테이너를 실행하면(`docker run -m` 사용) .NET Core 동작 방식이 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-321">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="c2cc5-322">기본 가비지 수집기(GC) 힙 크기: 최대 20mb 또는 컨테이너에서 75%의 메모리 한도</span><span class="sxs-lookup"><span data-stu-id="c2cc5-322">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="c2cc5-323">명시적 크기는 절대수 또는 cgroup 한도의 비율로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-323">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="c2cc5-324">GC 힙당 최소 예약된 세그먼트 크기는 16mb입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-324">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="c2cc5-325">이 크기는 머신에서 생성된 힙 수를 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-325">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="c2cc5-326">Raspberry Pi에 대한 GPIO 지원</span><span class="sxs-lookup"><span data-stu-id="c2cc5-326">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="c2cc5-327">GPIO 프로그래밍에 사용할 수 있는 두 개의 패키지가 NuGet에 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-327">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="c2cc5-328">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="c2cc5-328">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="c2cc5-329">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="c2cc5-329">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="c2cc5-330">GPIO 패키지에는 *GPIO*, *SPI*, *I2C* 및 *PWM*디바이스용 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-330">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="c2cc5-331">IoT 바인딩 패키지에 디바이스 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-331">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="c2cc5-332">자세한 내용은 [디바이스 GitHub 리포지토리](https://github.com/dotnet/iot/blob/master/src/devices/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-332">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="c2cc5-333">ARM64 Linux 지원</span><span class="sxs-lookup"><span data-stu-id="c2cc5-333">ARM64 Linux support</span></span>

<span data-ttu-id="c2cc5-334">.NET Core 3.0에서는 Linux용 ARM64에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-334">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="c2cc5-335">ARM64는 현재 IoT 시나리오에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-335">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="c2cc5-336">자세한 내용은 [.NET Core ARM64 상태](https://github.com/dotnet/announcements/issues/82)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-336">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="c2cc5-337">[ARM64의 .NET Core에 대한 Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/)를 Alpine, Debian 및 Ubuntu에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-337">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="c2cc5-338">**ARM64** Windows 지원은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-338">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="c2cc5-339">보안</span><span class="sxs-lookup"><span data-stu-id="c2cc5-339">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="c2cc5-340">Linux의 TLS 1.3 및 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="c2cc5-340">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="c2cc5-341">이제 .NET Core는 지정된 환경에서 사용 가능한 경우 [OpenSSL 1.1.1의 TLS 1.3 지원](https://www.openssl.org/blog/blog/2018/09/11/release111/)을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-341">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="c2cc5-342">TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-342">With TLS 1.3:</span></span>

- <span data-ttu-id="c2cc5-343">클라이언트와 서버 간에 필요한 왕복 횟수가 감소하여 연결 시간이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-343">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="c2cc5-344">더 이상 사용하지 않고 안전하지 않은 암호화 알고리즘을 제거하므로 보안이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-344">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="c2cc5-345">사용 가능한 경우 .NET Core 3.0은 Linux 시스템에서 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** 또는 **OpenSSL 1.0.2**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-345">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="c2cc5-346">**OpenSSL 1.1.1**이 사용 가능한 경우 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 **TLS 1.3**을 사용합니다(클라이언트와 서버 둘 다 **TLS 1.3**을 지원한다고 가정).</span><span class="sxs-lookup"><span data-stu-id="c2cc5-346">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2cc5-347">Windows 및 macOS에서는 아직 **TLS 1.3**을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-347">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="c2cc5-348">지원이 제공되면 .NET Core 3.0은 이러한 운영 체제에서 **TLS 1.3**을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-348">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="c2cc5-349">다음 C# 8.0 예제는 <https://www.cloudflare.com>에 연결하는 Ubuntu 18.10의 .NET Core 3.0을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-349">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](./snippets/dotnet-core-3-0/csharp/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="c2cc5-350">암호화 암호</span><span class="sxs-lookup"><span data-stu-id="c2cc5-350">Cryptography ciphers</span></span>

<span data-ttu-id="c2cc5-351">.NET 3.0은 각각 <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>으로 구현된 **AES-GCM** 및 **AES-CCM** 암호에 대한 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-351">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="c2cc5-352">이러한 알고리즘은 둘 다 [AEAD(Authenticated Encryption with Association Data) 알고리즘](https://en.wikipedia.org/wiki/Authenticated_encryption)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-352">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="c2cc5-353">다음 코드는 `AesGcm` 암호를 사용하여 임의 데이터를 암호화하고 암호를 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-353">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](./snippets/dotnet-core-3-0/csharp/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="c2cc5-354">암호화 키 가져오기/내보내기</span><span class="sxs-lookup"><span data-stu-id="c2cc5-354">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="c2cc5-355">.NET Core 3.0은 표준 형식에서 비대칭 퍼블릭 키와 프라이빗 키를 가져오고 내보낼 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-355">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="c2cc5-356">X.509 인증서를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-356">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="c2cc5-357">모든 키 형식(*RSA*, *DSA*, *ECDsa* 및 *ECDiffieHellman*)에서 다음 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-357">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="c2cc5-358">**공개 키**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-358">**Public Key**</span></span>
  - <span data-ttu-id="c2cc5-359">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="c2cc5-359">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="c2cc5-360">**프라이빗 키**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-360">**Private key**</span></span>
  - <span data-ttu-id="c2cc5-361">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="c2cc5-361">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="c2cc5-362">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="c2cc5-362">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="c2cc5-363">RSA 키는 다음도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-363">RSA keys also support:</span></span>

- <span data-ttu-id="c2cc5-364">**공개 키**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-364">**Public Key**</span></span>
  - <span data-ttu-id="c2cc5-365">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="c2cc5-365">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="c2cc5-366">**프라이빗 키**</span><span class="sxs-lookup"><span data-stu-id="c2cc5-366">**Private key**</span></span>
  - <span data-ttu-id="c2cc5-367">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="c2cc5-367">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="c2cc5-368">내보내기 메서드는 DER로 인코드된 이진 데이터를 생성하고, 가져오기 메서드도 동일한 동작을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-368">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="c2cc5-369">키가 텍스트에 편리한 PEM 형식으로 저장된 경우 호출자는 가져오기 메서드를 호출하기 전에 콘텐츠를 base64로 디코드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-369">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](./snippets/dotnet-core-3-0/csharp/RSA.cs#Rsa)]

<span data-ttu-id="c2cc5-370">**PKCS#8** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType>로 검사하고 **PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>로 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-370">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c2cc5-371">**PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-371">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="c2cc5-372">.NET Core 3.0 API 변경 내용</span><span class="sxs-lookup"><span data-stu-id="c2cc5-372">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="c2cc5-373">범위 및 인덱스</span><span class="sxs-lookup"><span data-stu-id="c2cc5-373">Ranges and indices</span></span>

<span data-ttu-id="c2cc5-374">새 <xref:System.Index?displayProperty=nameWithType> 형식을 인덱싱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-374">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="c2cc5-375">시작부터 계산되는 `int`의 인덱스를 만들거나, 접두사 `^` 연산자(C#)를 사용하여 끝부터 계산되는 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-375">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="c2cc5-376">시작 인덱스와 끝 인덱스의 두 `Index` 값으로 구성되고 `x..y` 범위 식(C#)으로 작성할 수 있는 <xref:System.Range?displayProperty=nameWithType> 유형도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-376">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="c2cc5-377">그런 다음, 조각을 생성하는 `Range`로 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-377">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="c2cc5-378">자세한 내용은 [범위 및 인덱스 자습서](../../csharp/tutorials/ranges-indexes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-378">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="c2cc5-379">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="c2cc5-379">Async streams</span></span>

<span data-ttu-id="c2cc5-380"><xref:System.Collections.Generic.IAsyncEnumerable%601> 형식은 <xref:System.Collections.Generic.IEnumerable%601>의 새로운 비동기 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-380">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="c2cc5-381">이 언어를 사용하면 `IAsyncEnumerable<T>`을 통해 `await foreach`를 수행하여 요소를 사용하고 `yield return`을 사용하여 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-381">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="c2cc5-382">다음 예제에서는 비동기 스트림의 생성 및 사용을 둘 다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-382">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="c2cc5-383">`foreach` 문은 비동기이며, `yield return`을 사용하여 호출자에 대한 비동기 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-383">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="c2cc5-384">이 패턴(`yield return` 사용)은 비동기 스트림 생성을 위한 권장 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-384">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="c2cc5-385">`await foreach`를 수행할 수 있을 뿐 아니라, 비동기 반복기(예: `await` 및 `yield`가 둘 다 가능한 `IAsyncEnumerable/IAsyncEnumerator`를 반환하는 반복기)를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-385">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="c2cc5-386">삭제해야 하는 개체의 경우 `Stream` 및 `Timer`와 같은 다양한 BCL 유형이 구현하는 `IAsyncDisposable`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-386">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="c2cc5-387">자세한 내용은 [비동기 스트림 자습서](../../csharp/tutorials/generate-consume-asynchronous-stream.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-387">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="c2cc5-388">IEEE 부동 소수점</span><span class="sxs-lookup"><span data-stu-id="c2cc5-388">IEEE Floating-point</span></span>

<span data-ttu-id="c2cc5-389">부동 소수점 API는 [IEEE 754-2008 개정판](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)을 준수하도록 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-389">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="c2cc5-390">이러한 변경의 목표는 **필요한** 모든 작업을 노출하고 이 작업이 IEEE 사양을 준수하는지 확인하는 것입니다. 부동 소수점 개선 사항에 대한 자세한 내용은 [.NET Core 3.0에서 부동 소수점 구문 분석 및 서식 지정 개선 사항](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-390">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="c2cc5-391">구문 분석 및 서식 지정 개선 사항:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-391">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="c2cc5-392">모든 길이의 입력을 올바르게 구문 분석하고 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-392">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="c2cc5-393">음수 0을 올바르게 구문 분석하고 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-393">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="c2cc5-394">대/소문자를 구분하지 않는 검사를 수행하여 `Infinity`와 `NaN`을 올바르게 구문 분석하고, 적용 가능한 경우 선행 `+` 옵션을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-394">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="c2cc5-395">새 <xref:System.Math?displayProperty=nameWithType> API의 구성 내용:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-395">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="c2cc5-396"><xref:System.Math.BitIncrement(System.Double)> 및 <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="c2cc5-396"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="c2cc5-397">`nextUp` 및 `nextDown` IEEE 연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-397">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="c2cc5-398">입력보다 크거나 작은 값을 각각 비교하는 최소 부동 소수점 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-398">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="c2cc5-399">예를 들어 `Math.BitIncrement(0.0)`는 `double.Epsilon`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-399">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="c2cc5-400"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> 및 <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="c2cc5-400"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="c2cc5-401">`maxNumMag` 및 `minNumMag` IEEE 연산에 해당하며 두 입력의 규모 중 더 크거나 작은 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-401">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="c2cc5-402">예를 들어 `Math.MaxMagnitude(2.0, -3.0)`는 `-3.0`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-402">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="c2cc5-403">`logB` IEEE 연산에 해당하며 정수값을 반환하고, 입력 매개 변수의 정수 이진 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-403">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="c2cc5-404">이 메서드는 `floor(log2(x))`와 사실상 동일하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-404">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="c2cc5-405">정수 값을 취하는 `scaleB` IEEE 연산에 해당하며 사실상 `x * pow(2, n)`을 반환하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-405">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="c2cc5-406">`log2` IEEE 연산에 해당하며, 기본-2 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-406">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="c2cc5-407">반올림 오류를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-407">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="c2cc5-408">`fma` IEEE 연산에 해당하며, 단일 곱셈 누산기(fused multiply add) 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-408">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="c2cc5-409">다시 말해, `(x * y) + z`을(를) 단일 연산으로 수행하기 때문에 반올림 오류가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-409">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="c2cc5-410">한 예로 `FusedMultiplyAdd(1e308, 2.0, -1e308)`는 `1e308`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-410">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="c2cc5-411">일반 `(1e308 * 2.0) - 1e308`은 `double.PositiveInfinity`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-411">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="c2cc5-412">`copySign` IEEE 연산에 해당하며, `x`의 값을 반환하지만 `y`의 부호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-412">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="c2cc5-413">.NET 플랫폼 종속 내장 함수</span><span class="sxs-lookup"><span data-stu-id="c2cc5-413">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="c2cc5-414">**SIMD** 또는 **비트 조작 명령어** 세트와 같은 특정 perf-oriented CPU 명령어에 대한 액세스를 허용하는 API가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-414">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="c2cc5-415">이러한 명령어를 사용하면 특정 시나리오(효율적인 데이터 병렬 처리)에서 성능을 크게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-415">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="c2cc5-416">적절한 경우 .NET 라이브러리는 성능을 개선하기 위해 이러한 명령을 사용하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-416">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="c2cc5-417">자세한 내용은 [.NET 플랫폼 종속 내장 함수](https://github.com/dotnet/designs/blob/master/accepted/2018/platform-intrinsics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-417">For more information, see [.NET Platform-Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/2018/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="c2cc5-418">향상된 .NET Core Version API</span><span class="sxs-lookup"><span data-stu-id="c2cc5-418">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="c2cc5-419">.NET Core 3.0부터 .NET Core에 제공된 버전 API가 이제 사용자가 예상하는 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-419">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="c2cc5-420">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-420">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="c2cc5-421">주요 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-421">Breaking change.</span></span> <span data-ttu-id="c2cc5-422">버전 관리 체계 변경되었기 때문에 엄밀히 따지면 주요 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-422">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="c2cc5-423">빠른 기본 제공 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="c2cc5-423">Fast built-in JSON support</span></span>

<span data-ttu-id="c2cc5-424">.NET 사용자는 [Newtonsoft.Json](https://www.newtonsoft.com/json) 및 여전히 유용한 기타 인기 있는 JSON 라이브러리를 많이 사용해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-424">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="c2cc5-425">`Newtonsoft.Json`은 내부적으로 UTF-16인 .NET 문자열을 기본 데이터 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-425">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="c2cc5-426">새로운 기본 제공 JSON 지원은 고성능, 낮은 할당이며 UTF-8로 인코딩된 JSON 텍스트와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-426">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="c2cc5-427"><xref:System.Text.Json> 네임스페이스 및 형식에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-427">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="c2cc5-428">.NET의 JSON serialization - 개요</span><span class="sxs-lookup"><span data-stu-id="c2cc5-428">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="c2cc5-429">[.NET에서 JSON을 직렬화 및 역직렬화하는 방법](../../standard/serialization/system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="c2cc5-429">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="c2cc5-430">Newtonsoft.json에서 System.Text.Json으로 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="c2cc5-430">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="c2cc5-431">HTTP/2 지원</span><span class="sxs-lookup"><span data-stu-id="c2cc5-431">HTTP/2 support</span></span>

<span data-ttu-id="c2cc5-432"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 HTTP/2 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-432">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="c2cc5-433">HTTP/2를 사용할 수 있는 경우 TLS/ALPN을 통해 HTTP 프로토콜 버전이 협상되며, 서버에서 사용하기로 선택하면 HTTP/2가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-433">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="c2cc5-434">기본 프로토콜은 여전히 HTTP/1.1이지만, 두 가지 방법으로 HTTP/2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-434">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="c2cc5-435">첫째, HTTP/2를 사용하도록 HTTP 요청 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-435">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](./snippets/dotnet-core-3-0/csharp/http.cs#Request)]

<span data-ttu-id="c2cc5-436">둘째, 기본적으로 HTTP/2를 사용하도록 <xref:System.Net.Http.HttpClient>를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-436">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](./snippets/dotnet-core-3-0/csharp/http.cs#Client)]

<span data-ttu-id="c2cc5-437">애플리케이션 개발 중에 암호화되지 않은 연결을 사용하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-437">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="c2cc5-438">대상 엔드포인트에서 HTTP/2를 사용할 것을 알고 있으면, HTTP/2에 대해 암호화되지 않은 연결을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-438">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="c2cc5-439">`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 환경 변수를 `1` 로 설정하거나 앱 컨텍스트에서 사용하도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-439">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](./snippets/dotnet-core-3-0/csharp/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="c2cc5-440">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c2cc5-440">Next steps</span></span>

- [<span data-ttu-id="c2cc5-441">.NET Core 2.2 및 3.0 간의 호환성이 손상되는 변경 검토</span><span class="sxs-lookup"><span data-stu-id="c2cc5-441">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="c2cc5-442">Windows Forms 앱용 .NET Core 3.0의 주요 변경 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-442">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
