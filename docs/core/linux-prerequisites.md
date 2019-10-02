---
title: Linux에서 .NET Core의 필수 구성 요소
description: Linux 컴퓨터에서 .NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다.
author: leecow
ms.author: leecow
ms.date: 09/25/2019
ms.openlocfilehash: 4c5d79459c9d69111ca6452d9305f0deb37212b8
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591694"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="231db-103">Linux에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="231db-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="231db-104">이 문서에서는 Linux에서 .NET Core 애플리케이션을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="231db-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="231db-105">다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="231db-106">즐겨 찾는 편집기를 사용하는 명령줄</span><span class="sxs-lookup"><span data-stu-id="231db-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="231db-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="231db-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="231db-108">.NET Core SDK 패키지는 프로덕션 서버/환경에서 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="231db-109">.NET Core 런타임 패키지만 프로덕션 환경에 배포된 앱에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="231db-110">NET Core 런타임은 자체 포함된 배포의 일부로 앱으로 배포되지만 프레임워크 종속 배포된 앱에 대해 별도로 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="231db-111">프레임워크 종속 및 자체 포함된 배포 형식에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](./deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="231db-112">또한 특정 지침은 [자체 포함된 Linux 애플리케이션](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="231db-113">지원되는 Linux 버전</span><span class="sxs-lookup"><span data-stu-id="231db-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="231db-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="231db-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="231db-115">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="231db-116">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="231db-117">다운로드 링크 및 자세한 내용은 [.NET Core 3.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="231db-118">.NET Core 3.0은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="231db-119">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="231db-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="231db-120">OS</span><span class="sxs-lookup"><span data-stu-id="231db-120">OS</span></span>                             | <span data-ttu-id="231db-121">버전</span><span class="sxs-lookup"><span data-stu-id="231db-121">Version</span></span>               | <span data-ttu-id="231db-122">아키텍처</span><span class="sxs-lookup"><span data-stu-id="231db-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="231db-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="231db-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="231db-124">6+, 7</span><span class="sxs-lookup"><span data-stu-id="231db-124">6+, 7</span></span>                 | <span data-ttu-id="231db-125">X64</span><span class="sxs-lookup"><span data-stu-id="231db-125">x64</span></span> |
| <span data-ttu-id="231db-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="231db-126">Oracle Linux</span></span>                   | <span data-ttu-id="231db-127">7</span><span class="sxs-lookup"><span data-stu-id="231db-127">7</span></span>                     | <span data-ttu-id="231db-128">X64</span><span class="sxs-lookup"><span data-stu-id="231db-128">x64</span></span> |
| <span data-ttu-id="231db-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="231db-129">CentOS</span></span>                         | <span data-ttu-id="231db-130">7</span><span class="sxs-lookup"><span data-stu-id="231db-130">7</span></span>                     | <span data-ttu-id="231db-131">X64</span><span class="sxs-lookup"><span data-stu-id="231db-131">x64</span></span> |
| <span data-ttu-id="231db-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="231db-132">Fedora</span></span>                         | <span data-ttu-id="231db-133">29+</span><span class="sxs-lookup"><span data-stu-id="231db-133">29+</span></span>                   | <span data-ttu-id="231db-134">X64</span><span class="sxs-lookup"><span data-stu-id="231db-134">x64</span></span> |
| <span data-ttu-id="231db-135">Debian</span><span class="sxs-lookup"><span data-stu-id="231db-135">Debian</span></span>                         | <span data-ttu-id="231db-136">9+</span><span class="sxs-lookup"><span data-stu-id="231db-136">9+</span></span>                    | <span data-ttu-id="231db-137">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="231db-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="231db-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="231db-138">Ubuntu</span></span>                         | <span data-ttu-id="231db-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="231db-139">16.04+</span></span>                | <span data-ttu-id="231db-140">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="231db-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="231db-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="231db-141">Linux Mint</span></span>                     | <span data-ttu-id="231db-142">18+</span><span class="sxs-lookup"><span data-stu-id="231db-142">18+</span></span>                   | <span data-ttu-id="231db-143">X64</span><span class="sxs-lookup"><span data-stu-id="231db-143">x64</span></span> |
| <span data-ttu-id="231db-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="231db-144">openSUSE</span></span>                       | <span data-ttu-id="231db-145">15+</span><span class="sxs-lookup"><span data-stu-id="231db-145">15+</span></span>                   | <span data-ttu-id="231db-146">X64</span><span class="sxs-lookup"><span data-stu-id="231db-146">x64</span></span> |
| <span data-ttu-id="231db-147">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="231db-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="231db-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="231db-148">12 SP2+</span></span>               | <span data-ttu-id="231db-149">X64</span><span class="sxs-lookup"><span data-stu-id="231db-149">x64</span></span> |
| <span data-ttu-id="231db-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="231db-150">Alpine Linux</span></span>                   | <span data-ttu-id="231db-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="231db-151">3.8+</span></span>                  | <span data-ttu-id="231db-152">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="231db-152">x64, ARM64</span></span> |

<span data-ttu-id="231db-153">지원 OS 버전 중 .NET Core 3.0이 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 3.0이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="231db-154">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="231db-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="231db-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="231db-156">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="231db-157">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="231db-158">다운로드 링크 및 자세한 내용은 [.NET Core 2.2 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="231db-159">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="231db-160">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="231db-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="231db-161">OS</span><span class="sxs-lookup"><span data-stu-id="231db-161">OS</span></span>                             |  <span data-ttu-id="231db-162">버전</span><span class="sxs-lookup"><span data-stu-id="231db-162">Version</span></span>                |  <span data-ttu-id="231db-163">아키텍처</span><span class="sxs-lookup"><span data-stu-id="231db-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="231db-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="231db-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="231db-165">6, 7</span><span class="sxs-lookup"><span data-stu-id="231db-165">6, 7</span></span>                   | <span data-ttu-id="231db-166">X64</span><span class="sxs-lookup"><span data-stu-id="231db-166">x64</span></span> |
| <span data-ttu-id="231db-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="231db-167">Oracle Linux</span></span>                   |  <span data-ttu-id="231db-168">7</span><span class="sxs-lookup"><span data-stu-id="231db-168">7</span></span>                      | <span data-ttu-id="231db-169">X64</span><span class="sxs-lookup"><span data-stu-id="231db-169">x64</span></span> |
| <span data-ttu-id="231db-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="231db-170">CentOS</span></span>                         |  <span data-ttu-id="231db-171">7</span><span class="sxs-lookup"><span data-stu-id="231db-171">7</span></span>                      | <span data-ttu-id="231db-172">X64</span><span class="sxs-lookup"><span data-stu-id="231db-172">x64</span></span> |
| <span data-ttu-id="231db-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="231db-173">Fedora</span></span>                         |  <span data-ttu-id="231db-174">29, 30</span><span class="sxs-lookup"><span data-stu-id="231db-174">29, 30</span></span>                 | <span data-ttu-id="231db-175">X64</span><span class="sxs-lookup"><span data-stu-id="231db-175">x64</span></span> |
| <span data-ttu-id="231db-176">Debian</span><span class="sxs-lookup"><span data-stu-id="231db-176">Debian</span></span>                         |  <span data-ttu-id="231db-177">9</span><span class="sxs-lookup"><span data-stu-id="231db-177">9</span></span>                      | <span data-ttu-id="231db-178">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="231db-178">x64, ARM32</span></span> |
| <span data-ttu-id="231db-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="231db-179">Ubuntu</span></span>                         |  <span data-ttu-id="231db-180">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="231db-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="231db-181">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="231db-181">x64, ARM32</span></span> |
| <span data-ttu-id="231db-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="231db-182">Linux Mint</span></span>                     |  <span data-ttu-id="231db-183">17, 18</span><span class="sxs-lookup"><span data-stu-id="231db-183">17, 18</span></span>                 | <span data-ttu-id="231db-184">X64</span><span class="sxs-lookup"><span data-stu-id="231db-184">x64</span></span> |
| <span data-ttu-id="231db-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="231db-185">openSUSE</span></span>                       |  <span data-ttu-id="231db-186">15+</span><span class="sxs-lookup"><span data-stu-id="231db-186">15+</span></span>                    | <span data-ttu-id="231db-187">X64</span><span class="sxs-lookup"><span data-stu-id="231db-187">x64</span></span> |
| <span data-ttu-id="231db-188">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="231db-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="231db-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="231db-189">12 SP2+</span></span>                | <span data-ttu-id="231db-190">X64</span><span class="sxs-lookup"><span data-stu-id="231db-190">x64</span></span> |
| <span data-ttu-id="231db-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="231db-191">Alpine Linux</span></span>                   |  <span data-ttu-id="231db-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="231db-192">3.7+</span></span>                   | <span data-ttu-id="231db-193">X64</span><span class="sxs-lookup"><span data-stu-id="231db-193">x64</span></span> |

<span data-ttu-id="231db-194">.NET Core 2.2 지원 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.2 지원 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="231db-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="231db-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="231db-196">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="231db-197">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="231db-198">다운로드 링크 및 자세한 내용은 [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="231db-199">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="231db-200">OS</span><span class="sxs-lookup"><span data-stu-id="231db-200">OS</span></span>                             |  <span data-ttu-id="231db-201">버전</span><span class="sxs-lookup"><span data-stu-id="231db-201">Version</span></span>                |  <span data-ttu-id="231db-202">아키텍처</span><span class="sxs-lookup"><span data-stu-id="231db-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="231db-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="231db-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="231db-204">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="231db-204">6, 7, 8</span></span>                | <span data-ttu-id="231db-205">X64</span><span class="sxs-lookup"><span data-stu-id="231db-205">x64</span></span> |
| <span data-ttu-id="231db-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="231db-206">Oracle Linux</span></span>                   |  <span data-ttu-id="231db-207">7</span><span class="sxs-lookup"><span data-stu-id="231db-207">7</span></span>                      | <span data-ttu-id="231db-208">X64</span><span class="sxs-lookup"><span data-stu-id="231db-208">x64</span></span> |
| <span data-ttu-id="231db-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="231db-209">CentOS</span></span>                         |  <span data-ttu-id="231db-210">7</span><span class="sxs-lookup"><span data-stu-id="231db-210">7</span></span>                      | <span data-ttu-id="231db-211">X64</span><span class="sxs-lookup"><span data-stu-id="231db-211">x64</span></span> |
| <span data-ttu-id="231db-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="231db-212">Fedora</span></span>                         |  <span data-ttu-id="231db-213">29, 30</span><span class="sxs-lookup"><span data-stu-id="231db-213">29, 30</span></span>                 | <span data-ttu-id="231db-214">X64</span><span class="sxs-lookup"><span data-stu-id="231db-214">x64</span></span> |
| <span data-ttu-id="231db-215">Debian</span><span class="sxs-lookup"><span data-stu-id="231db-215">Debian</span></span>                         |  <span data-ttu-id="231db-216">9</span><span class="sxs-lookup"><span data-stu-id="231db-216">9</span></span>                      | <span data-ttu-id="231db-217">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="231db-217">x64, ARM32</span></span> |
| <span data-ttu-id="231db-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="231db-218">Ubuntu</span></span>                         |  <span data-ttu-id="231db-219">16.04, 18.04, 19.04</span><span class="sxs-lookup"><span data-stu-id="231db-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="231db-220">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="231db-220">x64, ARM32</span></span> |
| <span data-ttu-id="231db-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="231db-221">Linux Mint</span></span>                     |  <span data-ttu-id="231db-222">17, 18</span><span class="sxs-lookup"><span data-stu-id="231db-222">17, 18</span></span>                 | <span data-ttu-id="231db-223">X64</span><span class="sxs-lookup"><span data-stu-id="231db-223">x64</span></span> |
| <span data-ttu-id="231db-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="231db-224">openSUSE</span></span>                       |  <span data-ttu-id="231db-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="231db-225">42.3+</span></span>                  | <span data-ttu-id="231db-226">X64</span><span class="sxs-lookup"><span data-stu-id="231db-226">x64</span></span> |
| <span data-ttu-id="231db-227">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="231db-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="231db-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="231db-228">12 SP2+</span></span>                | <span data-ttu-id="231db-229">X64</span><span class="sxs-lookup"><span data-stu-id="231db-229">x64</span></span> |
| <span data-ttu-id="231db-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="231db-230">Alpine Linux</span></span>                   |  <span data-ttu-id="231db-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="231db-231">3.7+</span></span>                   | <span data-ttu-id="231db-232">X64</span><span class="sxs-lookup"><span data-stu-id="231db-232">x64</span></span> |

<span data-ttu-id="231db-233">지원 OS 버전 중 .NET Core 2.1이 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.1이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="231db-234">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="231db-234">Linux distribution dependencies</span></span>

<span data-ttu-id="231db-235">다음은 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-235">The following are intended to be examples.</span></span> <span data-ttu-id="231db-236">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="231db-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="231db-237">Ubuntu</span></span>

<span data-ttu-id="231db-238">Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-238">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="231db-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="231db-239">liblttng-ust0</span></span>
* <span data-ttu-id="231db-240">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-240">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="231db-241">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-241">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="231db-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="231db-242">libssl1.0.0</span></span>
* <span data-ttu-id="231db-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="231db-243">libkrb5-3</span></span>
* <span data-ttu-id="231db-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="231db-244">zlib1g</span></span>
* <span data-ttu-id="231db-245">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-245">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="231db-246">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-246">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="231db-247">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-247">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="231db-248">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="231db-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="231db-249">.NET Core 2.1 이전 버전의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="231db-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="231db-250">libunwind8</span></span>
* <span data-ttu-id="231db-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="231db-251">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="231db-252">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="231db-252">CentOS and Fedora</span></span>

<span data-ttu-id="231db-253">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-253">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="231db-254">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="231db-254">lttng-ust</span></span>
* <span data-ttu-id="231db-255">libcurl</span><span class="sxs-lookup"><span data-stu-id="231db-255">libcurl</span></span>
* <span data-ttu-id="231db-256">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="231db-256">openssl-libs</span></span>
* <span data-ttu-id="231db-257">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="231db-257">krb5-libs</span></span>
* <span data-ttu-id="231db-258">libicu</span><span class="sxs-lookup"><span data-stu-id="231db-258">libicu</span></span>
* <span data-ttu-id="231db-259">zlib</span><span class="sxs-lookup"><span data-stu-id="231db-259">zlib</span></span>

<span data-ttu-id="231db-260">Fedora 사용자: openssl 버전 >= 1.1인 경우 compat-openssl10을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-260">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="231db-261">.NET Core 2.1 이전 버전의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-261">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="231db-262">libunwind</span><span class="sxs-lookup"><span data-stu-id="231db-262">libunwind</span></span>
* <span data-ttu-id="231db-263">libuuid</span><span class="sxs-lookup"><span data-stu-id="231db-263">libuuid</span></span>

<span data-ttu-id="231db-264">종속성에 대한 자세한 내용은 [자체 포함 Linux 애플리케이션](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-264">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="231db-265">기본 설치 관리자를 사용하여 .NET Core 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="231db-265">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="231db-266">.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-266">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="231db-267">기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-267">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="231db-268">기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="231db-268">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="231db-269">기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-269">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="231db-270">Linux에는 두 가지 패키지 선택 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-270">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="231db-271">피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).</span><span class="sxs-lookup"><span data-stu-id="231db-271">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="231db-272">패키지 자체 사용(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="231db-272">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="231db-273">.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅</span><span class="sxs-lookup"><span data-stu-id="231db-273">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="231db-274">[dotnet-install 스크립트](./tools/dotnet-install-script.md)는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-274">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="231db-275"><https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-275">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="231db-276">스크립트는 기본적으로 현재 .NET Core 1.1인 최신 "LTS" 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-276">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="231db-277">.NET Core 2.1을 설치하려면 다음 스위치를 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="231db-277">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="231db-278">설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="231db-278">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="231db-279">또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231db-279">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="231db-280">문제 해결</span><span class="sxs-lookup"><span data-stu-id="231db-280">Troubleshoot</span></span>

<span data-ttu-id="231db-281">지원되는 Linux 배포/버전에 .NET Core 설치에 문제가 있는 경우 설치된 배포/버전에 대한 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="231db-281">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="231db-282">.NET Core 3.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="231db-282">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="231db-283">.NET Core 2.2 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="231db-283">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="231db-284">.NET Core 2.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="231db-284">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="231db-285">.NET Core 1.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="231db-285">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="231db-286">.NET Core 1.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="231db-286">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
