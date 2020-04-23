---
title: .NET Core 배포 패키징
description: 배포를 위해 .NET Core를 패키지하고 이름과 버전을 지정하는 방법에 관해 알아봅니다.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: a345aeded29b3058c6c56abbff439ea26cbc7afb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "81386641"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="e0e4a-103">.NET Core 배포 패키징</span><span class="sxs-lookup"><span data-stu-id="e0e4a-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="e0e4a-104">.NET Core를 점점 더 많은 플랫폼에서 사용할 수 있게 되므로 이를 패키지하고 이름과 버전을 지정하는 방법을 알아보는 것이 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="e0e4a-105">이를 통해 패키지 유지 관리자는 사용자가 .NET을 어디서 실행하든 상관없이 일관된 환경을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="e0e4a-106">이 문서는 다음에 해당하는 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="e0e4a-107">원본에서 .NET Core를 빌드하려는 사용자</span><span class="sxs-lookup"><span data-stu-id="e0e4a-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="e0e4a-108">결과 레이아웃 또는 생성된 패키지에 영향을 미칠 수 있는 .NET Core CLI 변경을 수행하려는 사용자</span><span class="sxs-lookup"><span data-stu-id="e0e4a-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="e0e4a-109">디스크 레이아웃</span><span class="sxs-lookup"><span data-stu-id="e0e4a-109">Disk layout</span></span>

<span data-ttu-id="e0e4a-110">설치하면 .NET Core는 파일 시스템에서 다음과 같이 배치된 여러 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="e0e4a-111">(1) **dotnet** 호스트("muxer"라고도 함)는 런타임을 활성화하여 애플리케이션을 시작하고 SDK를 활성화하여 명령을 보내는 두 가지의 고유한 역할을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="e0e4a-112">호스트는 네이티브 실행 파일(`dotnet.exe`)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="e0e4a-113">단일 호스트가 있지만 다른 구성 요소는 대부분 버전이 지정된 디렉터리(2,3,5,6)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="e0e4a-114">여러 버전이 나란히 설치되므로 시스템에 여러 버전이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="e0e4a-115">(2) **host/fxr/\<fxr 버전>** 에는 호스트에서 사용하는 프레임워크 확인 논리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="e0e4a-116">호스트는 설치된 최신 hostfxr을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="e0e4a-117">hostfxr는 .NET Core 애플리케이션을 실행할 때 적합한 런타임을 선택하는 일을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="e0e4a-118">예를 들어 .NET Core 2.0.0에 대해 빌드된 애플리케이션을 사용할 수 있는 경우 2.0.5 런타임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="e0e4a-119">마찬가지로 hostfxr은 개발 중에 적절한 SDK를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="e0e4a-120">(3) **sdk/\<sdk version>** SDK("도구"라고도 함)는 .NET Core 라이브러리 및 애플리케이션을 작성하고 빌드하는 데 사용할 수 있는 관리형 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="e0e4a-121">SDK는 .NET Core CLI, 관리형 언어 컴파일러, MSBuild 및 연결된 빌드 작업과 대상, NuGet, 새 프로젝트 템플릿 등을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="e0e4a-122">(4) **sdk/NuGetFallbackFolder**에는 `dotnet restore` 또는 `dotnet build` 실행처럼 복원 작업 중에 SDK에서 사용하는 NuGet 패키지의 캐시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="e0e4a-123">이 폴더는 .NET Core 3.0 이전에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="e0e4a-124">`nuget.org`에서 미리 빌드된 이진 자산을 포함하므로 소스에서 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="e0e4a-125">**공유** 폴더에는 프레임워크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="e0e4a-126">공유 프레임워크는 다른 애플리케이션에서 사용할 수 있도록 중앙 위치에 라이브러리의 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="e0e4a-127">(5) **shared/Microsoft.NETCore.App/\<runtime 버전>** 이 프레임워크에는 지원되는 .NET Core 런타임 및 관리 라이브러리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="e0e4a-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore 버전>** 에는 ASP.NET Core 라이브러리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="e0e4a-129">`Microsoft.AspNetCore.App`에서 라이브러리를 개발하고 .NET Core 프로젝트의 일부로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="e0e4a-130">`Microsoft.AspNetCore.All`의 라이브러리는 타사 라이브러리도 포함하는 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="e0e4a-131">(7) **shared/Microsoft.Desktop.App/\<데스크톱 앱 버전>** 은 Windows 데스크톱 라이브러리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="e0e4a-132">Windows 이외의 플랫폼에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="e0e4a-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**는 각각 .NET Core에서 사용되는 .NET Core 라이선스 및 타사 라이브러리의 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="e0e4a-134">(9, 10) **dotnet.1.gz, dotnet** `dotnet.1.gz`은 dotnet 설명서 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="e0e4a-135">`dotnet`은 dotnet 호스트(1)의 symlink입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="e0e4a-136">이러한 파일은 시스템 통합을 위해 잘 알려진 위치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="e0e4a-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref**는 .NET Core 및 ASP.NET Core의 `x.y` 버전의 API를 각각 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="e0e4a-138">이러한 팩은 이러한 대상 버전에 대해 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="e0e4a-139">(13) **Microsoft.NETCore.App.Host.\<rid>** 는 플랫폼 `rid`용 네이티브 이진을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="e0e4a-140">이 이진은 .NET Core 애플리케이션을 해당 플랫폼의 네이티브 이진으로 컴파일할 때의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="e0e4a-141">(14) **Microsoft.WindowsDesktop.App.Ref**는 Windows 데스크톱 애플리케이션의 `x.y` 버전의 API를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="e0e4a-142">이러한 파일은 해당 대상에 대해 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="e0e4a-143">이는 Windows 이외의 플랫폼에는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="e0e4a-144">(15) **NETStandard.Library.Ref**는 netstandard `x.y` API를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="e0e4a-145">이러한 파일은 해당 대상에 대해 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="e0e4a-146">(16) **/etc/dotnet/install_location**은 `{dotnet_root}`의 전체 경로를 포함하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-146">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="e0e4a-147">경로는 줄 바꿈으로 끝날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-147">The path may end with a newline.</span></span> <span data-ttu-id="e0e4a-148">루트가 `/usr/share/dotnet`인 경우에는 이 파일을 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="e0e4a-149">(17) **템플릿**은 SDK에서 사용하는 템플릿을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="e0e4a-150">예를 들어 `dotnet new`는 여기에서 프로젝트 템플릿을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-150">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="e0e4a-151">`(*)`로 표시된 폴더는 여러 패키지에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-151">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="e0e4a-152">일부 패키지 형식(예: `rpm`)에는 이러한 폴더에 대한 특별한 처리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-152">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="e0e4a-153">패키지 유지 관리자는 이를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-153">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="e0e4a-154">권장된 패키지</span><span class="sxs-lookup"><span data-stu-id="e0e4a-154">Recommended packages</span></span>

<span data-ttu-id="e0e4a-155">.NET Core 버전 관리는 런타임 구성 요소 `[major].[minor]` 버전 번호에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-155">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="e0e4a-156">SDK 버전은 동일한 `[major].[minor]`를 사용하고, SDK의 기능 및 패치 의미 체계를 결합한 독립 `[patch]`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-156">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="e0e4a-157">예를 들어: SDK 버전 2.2.302는 2.2 런타임을 지원하는 SDK의 세 번째 기능 릴리스의 두 번째 패치 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-157">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="e0e4a-158">버전 관리의 작동 방식에 대 한 자세한 내용은 [.NET Core 버전 관리 개요](./versions/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-158">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="e0e4a-159">일부 패키지에는 해당 이름의 버전 번호 일부가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-159">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="e0e4a-160">그러면 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-160">This allows you to install a specific version.</span></span>
<span data-ttu-id="e0e4a-161">버전의 나머지 부분은 버전 이름에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-161">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="e0e4a-162">이 때문에 OS 패키지 관리자가 패키지를 업데이트할 수 있습니다(예: 보안 해결을 자동으로 설치).</span><span class="sxs-lookup"><span data-stu-id="e0e4a-162">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="e0e4a-163">지원되는 패키지 관리자는 Linux 특정입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-163">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="e0e4a-164">다음은 권장되는 패키지 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-164">The following lists the recommended packages:</span></span>

- <span data-ttu-id="e0e4a-165">`dotnet-sdk-[major].[minor]` - 특정 런타임의 최신 sdk를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-165">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="e0e4a-166">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-166">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-167">**예:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="e0e4a-167">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="e0e4a-168">**포함:** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-168">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="e0e4a-169">**종속성:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e0e4a-169">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="e0e4a-170">`aspnetcore-runtime-[major].[minor]` - 특정 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-170">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="e0e4a-171">**버전:** \<aspnetcore 런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-171">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="e0e4a-172">**예:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="e0e4a-172">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="e0e4a-173">**포함:** (6)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-173">**Contains:** (6)</span></span>
  - <span data-ttu-id="e0e4a-174">**종속성:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e0e4a-174">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="e0e4a-175">`dotnet-runtime-deps-[major].[minor]` _(선택 사항)_ - 자체 포함 애플리케이션을 실행하기 위한 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-175">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="e0e4a-176">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-176">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-177">**예:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="e0e4a-177">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="e0e4a-178">**종속성:** _배포 관련 종속성_</span><span class="sxs-lookup"><span data-stu-id="e0e4a-178">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="e0e4a-179">`dotnet-runtime-[major].[minor]` - 특정 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-179">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="e0e4a-180">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-180">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-181">**예:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="e0e4a-181">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="e0e4a-182">**포함:** (5)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-182">**Contains:** (5)</span></span>
  - <span data-ttu-id="e0e4a-183">**종속성:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e0e4a-183">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="e0e4a-184">`dotnet-hostfxr-[major].[minor]` - 종속성</span><span class="sxs-lookup"><span data-stu-id="e0e4a-184">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="e0e4a-185">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-185">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-186">**예:** dotnet-hostfxr-3.0</span><span class="sxs-lookup"><span data-stu-id="e0e4a-186">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="e0e4a-187">**포함:** (2)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-187">**Contains:** (2)</span></span>
  - <span data-ttu-id="e0e4a-188">**종속성:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="e0e4a-188">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="e0e4a-189">`dotnet-host` - 종속성</span><span class="sxs-lookup"><span data-stu-id="e0e4a-189">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="e0e4a-190">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-190">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-191">**예:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="e0e4a-191">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="e0e4a-192">**포함:** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-192">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="e0e4a-193">`dotnet-apphost-pack-[major].[minor]` - 종속성</span><span class="sxs-lookup"><span data-stu-id="e0e4a-193">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="e0e4a-194">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-195">**포함:** (13)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-195">**Contains:** (13)</span></span>

- <span data-ttu-id="e0e4a-196">`dotnet-targeting-pack-[major].[minor]` - 최신이 아닌 런타임 대상 지정 허용</span><span class="sxs-lookup"><span data-stu-id="e0e4a-196">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="e0e4a-197">**버전:** \<런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-197">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e0e4a-198">**포함:** (12)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-198">**Contains:** (12)</span></span>

- <span data-ttu-id="e0e4a-199">`aspnetcore-targeting-pack-[major].[minor]` - 최신이 아닌 런타임 대상 지정 허용</span><span class="sxs-lookup"><span data-stu-id="e0e4a-199">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="e0e4a-200">**버전:** \<aspnetcore 런타임 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-200">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="e0e4a-201">**포함:** (11)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-201">**Contains:** (11)</span></span>

- <span data-ttu-id="e0e4a-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - netstandard 버전 대상 지정 허용</span><span class="sxs-lookup"><span data-stu-id="e0e4a-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="e0e4a-203">**버전:** \<sdk 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-203">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="e0e4a-204">**포함:** (15)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-204">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="e0e4a-205">**버전:** \<sdk 버전></span><span class="sxs-lookup"><span data-stu-id="e0e4a-205">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="e0e4a-206">**포함:** (15)</span><span class="sxs-lookup"><span data-stu-id="e0e4a-206">**Contains:** (15)</span></span>

<span data-ttu-id="e0e4a-207">`dotnet-runtime-deps-[major].[minor]`에서는 _배포판 특정 종속성_에 대해 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-207">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="e0e4a-208">배포판 빌드 시스템은 이를 자동으로 파생시킬 수도 있으므로 패키지는 선택 사항입니다. 이 경우 이러한 종속성은 `dotnet-runtime-[major].[minor]` 패키지에 직접 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-208">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="e0e4a-209">패키지 콘텐츠가 버전이 있는 폴더에 있는 경우 패키지 이름 `[major].[minor]`는 버전이 있는 폴더 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-209">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="e0e4a-210">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`를 제외한 모든 패키지에서 이는 .NET Core 버전과도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-210">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="e0e4a-211">패키지 간 종속성은 _동일하거나 더 큰_ 버전 요구 사항을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-211">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="e0e4a-212">예를 들어 `dotnet-sdk-2.2:2.2.401`에는 `aspnetcore-runtime-2.2 >= 2.2.6`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-212">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="e0e4a-213">그러면 사용자는 루트 패키지(예: `dnf update dotnet-sdk-2.2`)를 통해 설치를 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-213">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="e0e4a-214">대부분의 배포는 모든 아티팩트를 원본에서 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-214">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="e0e4a-215">그러면 패키지에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-215">This has some impact on the packages:</span></span>

- <span data-ttu-id="e0e4a-216">`shared/Microsoft.AspNetCore.All`의 타사 라이브러리는 원본에서 쉽게 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-216">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="e0e4a-217">따라서 `aspnetcore-runtime` 패키지에서 해당 폴더를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-217">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="e0e4a-218">`nuget.org`에서 이진 아티팩트를 사용하여 `NuGetFallbackFolder`를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-218">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="e0e4a-219">비워 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-219">It should remain empty.</span></span>

<span data-ttu-id="e0e4a-220">여러 `dotnet-sdk` 패키지는 `NuGetFallbackFolder`에 동일한 파일을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-220">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="e0e4a-221">패키지 관리자를 사용하여 문제를 방지하려면 이러한 파일이 동일해야 합니다(체크섬, 수정 날짜 등).</span><span class="sxs-lookup"><span data-stu-id="e0e4a-221">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="e0e4a-222">패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="e0e4a-222">Building packages</span></span>

<span data-ttu-id="e0e4a-223">[dotnet/source-build](https://github.com/dotnet/source-build) 리포지토리는 .NET Core SDK 및 모든 해당 구성 요소의 소스 Tarball을 빌드하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-223">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="e0e4a-224">원본 빌드 리포지토리의 출력은 이 아티클의 첫 번째 섹션에 설명된 레이아웃과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-224">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
