---
title: Windows, Linux 및 macOS에 .NET Core 런타임 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 실행하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998890"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="562fe-104">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="562fe-105">이 문서에서는 .NET Core 런타임을 다운로드하고 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="562fe-106">.NET Core 런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="562fe-107">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-107">Install with an installer</span></span>

<span data-ttu-id="562fe-108">Windows에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="562fe-109">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="562fe-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="562fe-110">x86(32비트) CPU</span><span class="sxs-lookup"><span data-stu-id="562fe-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="562fe-111">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-111">Install with an installer</span></span>

<span data-ttu-id="562fe-112">macOS에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="562fe-113">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="562fe-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="562fe-114">패키지 관리자를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-114">Install with a package manager</span></span>

<span data-ttu-id="562fe-115">널리 사용되는 여러 Linux 패키지 관리자를 사용하여 .NET Core 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="562fe-116">자세한 내용은 [Linux 패키지 관리자 - .NET Core 설치](linux-package-manager-rhel7.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="562fe-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="562fe-117">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-117">Install with PowerShell automation</span></span>

<span data-ttu-id="562fe-118">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="562fe-119">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="562fe-120">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="562fe-121">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="562fe-122">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="562fe-123">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="562fe-124">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="562fe-125">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="562fe-126">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="562fe-126">Install with bash automation</span></span>

<span data-ttu-id="562fe-127">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="562fe-128">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="562fe-129">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="562fe-130">`current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="562fe-131">런타임을 설치하려면 `runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="562fe-132">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="562fe-133">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="562fe-134">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="562fe-135">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="562fe-135">All .NET Core downloads</span></span>

<span data-ttu-id="562fe-136">다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="562fe-137">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="562fe-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="562fe-138">.NET Core 3.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="562fe-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="562fe-139">.NET Core 2.2 다운로드</span><span class="sxs-lookup"><span data-stu-id="562fe-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="562fe-140">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="562fe-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="562fe-141">Docker</span><span class="sxs-lookup"><span data-stu-id="562fe-141">Docker</span></span>

<span data-ttu-id="562fe-142">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="562fe-143">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="562fe-144">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="562fe-145">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="562fe-146">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="562fe-147">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="562fe-148">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="562fe-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="562fe-149">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="562fe-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="562fe-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="562fe-150">Next steps</span></span>

- <span data-ttu-id="562fe-151">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="562fe-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
