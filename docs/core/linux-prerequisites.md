---
title: Linux에서 .NET Core의 필수 구성 요소
description: Linux 컴퓨터에서 .NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다.
author: leecow
ms.author: leecow
ms.date: 10/11/2019
ms.openlocfilehash: 0e798e86fcf88a1b7a67f50c2301e10ad725fad8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521494"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="d8539-103">Linux에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d8539-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="d8539-104">이 문서에서는 Linux에서 .NET Core 애플리케이션을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="d8539-105">다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

- [<span data-ttu-id="d8539-106">즐겨 찾는 편집기를 사용하는 명령줄</span><span class="sxs-lookup"><span data-stu-id="d8539-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
- [<span data-ttu-id="d8539-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d8539-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="d8539-108">.NET Core SDK 패키지는 프로덕션 서버/환경에서 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="d8539-109">.NET Core 런타임 패키지만 프로덕션 환경에 배포된 앱에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="d8539-110">NET Core 런타임은 자체 포함된 배포의 일부로 앱으로 배포되지만 프레임워크 종속 배포된 앱에 대해 별도로 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="d8539-111">프레임워크 종속 및 자체 포함된 배포 형식에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](./deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="d8539-112">또한 특정 지침은 [자체 포함된 Linux 애플리케이션](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="d8539-113">지원되는 Linux 버전</span><span class="sxs-lookup"><span data-stu-id="d8539-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="d8539-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d8539-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d8539-115">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="d8539-116">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="d8539-117">다운로드 링크 및 자세한 내용은 [.NET Core 3.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="d8539-118">.NET Core 3.0은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="d8539-119">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d8539-120">OS</span><span class="sxs-lookup"><span data-stu-id="d8539-120">OS</span></span>                             | <span data-ttu-id="d8539-121">버전</span><span class="sxs-lookup"><span data-stu-id="d8539-121">Version</span></span>               | <span data-ttu-id="d8539-122">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d8539-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="d8539-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="d8539-124">6+, 7</span><span class="sxs-lookup"><span data-stu-id="d8539-124">6+, 7</span></span>                 | <span data-ttu-id="d8539-125">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-125">x64</span></span> |
| <span data-ttu-id="d8539-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-126">Oracle Linux</span></span>                   | <span data-ttu-id="d8539-127">7</span><span class="sxs-lookup"><span data-stu-id="d8539-127">7</span></span>                     | <span data-ttu-id="d8539-128">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-128">x64</span></span> |
| <span data-ttu-id="d8539-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="d8539-129">CentOS</span></span>                         | <span data-ttu-id="d8539-130">7</span><span class="sxs-lookup"><span data-stu-id="d8539-130">7</span></span>                     | <span data-ttu-id="d8539-131">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-131">x64</span></span> |
| <span data-ttu-id="d8539-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="d8539-132">Fedora</span></span>                         | <span data-ttu-id="d8539-133">29+</span><span class="sxs-lookup"><span data-stu-id="d8539-133">29+</span></span>                   | <span data-ttu-id="d8539-134">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-134">x64</span></span> |
| <span data-ttu-id="d8539-135">Debian</span><span class="sxs-lookup"><span data-stu-id="d8539-135">Debian</span></span>                         | <span data-ttu-id="d8539-136">9+</span><span class="sxs-lookup"><span data-stu-id="d8539-136">9+</span></span>                    | <span data-ttu-id="d8539-137">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d8539-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d8539-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d8539-138">Ubuntu</span></span>                         | <span data-ttu-id="d8539-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="d8539-139">16.04+</span></span>                | <span data-ttu-id="d8539-140">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d8539-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d8539-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d8539-141">Linux Mint</span></span>                     | <span data-ttu-id="d8539-142">18+</span><span class="sxs-lookup"><span data-stu-id="d8539-142">18+</span></span>                   | <span data-ttu-id="d8539-143">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-143">x64</span></span> |
| <span data-ttu-id="d8539-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d8539-144">openSUSE</span></span>                       | <span data-ttu-id="d8539-145">15+</span><span class="sxs-lookup"><span data-stu-id="d8539-145">15+</span></span>                   | <span data-ttu-id="d8539-146">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-146">x64</span></span> |
| <span data-ttu-id="d8539-147">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d8539-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="d8539-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d8539-148">12 SP2+</span></span>               | <span data-ttu-id="d8539-149">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-149">x64</span></span> |
| <span data-ttu-id="d8539-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-150">Alpine Linux</span></span>                   | <span data-ttu-id="d8539-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="d8539-151">3.8+</span></span>                  | <span data-ttu-id="d8539-152">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="d8539-152">x64, ARM64</span></span> |

<span data-ttu-id="d8539-153">지원 OS 버전 중 .NET Core 3.0이 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 3.0이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d8539-154">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="d8539-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="d8539-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="d8539-156">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="d8539-157">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d8539-158">다운로드 링크 및 자세한 내용은 [.NET Core 2.2 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="d8539-159">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="d8539-160">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d8539-161">OS</span><span class="sxs-lookup"><span data-stu-id="d8539-161">OS</span></span>                             |  <span data-ttu-id="d8539-162">버전</span><span class="sxs-lookup"><span data-stu-id="d8539-162">Version</span></span>                |  <span data-ttu-id="d8539-163">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d8539-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="d8539-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="d8539-165">6, 7</span><span class="sxs-lookup"><span data-stu-id="d8539-165">6, 7</span></span>                   | <span data-ttu-id="d8539-166">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-166">x64</span></span> |
| <span data-ttu-id="d8539-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-167">Oracle Linux</span></span>                   |  <span data-ttu-id="d8539-168">7</span><span class="sxs-lookup"><span data-stu-id="d8539-168">7</span></span>                      | <span data-ttu-id="d8539-169">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-169">x64</span></span> |
| <span data-ttu-id="d8539-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="d8539-170">CentOS</span></span>                         |  <span data-ttu-id="d8539-171">7</span><span class="sxs-lookup"><span data-stu-id="d8539-171">7</span></span>                      | <span data-ttu-id="d8539-172">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-172">x64</span></span> |
| <span data-ttu-id="d8539-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="d8539-173">Fedora</span></span>                         |  <span data-ttu-id="d8539-174">29, 30</span><span class="sxs-lookup"><span data-stu-id="d8539-174">29, 30</span></span>                 | <span data-ttu-id="d8539-175">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-175">x64</span></span> |
| <span data-ttu-id="d8539-176">Debian</span><span class="sxs-lookup"><span data-stu-id="d8539-176">Debian</span></span>                         |  <span data-ttu-id="d8539-177">9</span><span class="sxs-lookup"><span data-stu-id="d8539-177">9</span></span>                      | <span data-ttu-id="d8539-178">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d8539-178">x64, ARM32</span></span> |
| <span data-ttu-id="d8539-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d8539-179">Ubuntu</span></span>                         |  <span data-ttu-id="d8539-180">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="d8539-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="d8539-181">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d8539-181">x64, ARM32</span></span> |
| <span data-ttu-id="d8539-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d8539-182">Linux Mint</span></span>                     |  <span data-ttu-id="d8539-183">17, 18</span><span class="sxs-lookup"><span data-stu-id="d8539-183">17, 18</span></span>                 | <span data-ttu-id="d8539-184">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-184">x64</span></span> |
| <span data-ttu-id="d8539-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d8539-185">openSUSE</span></span>                       |  <span data-ttu-id="d8539-186">15+</span><span class="sxs-lookup"><span data-stu-id="d8539-186">15+</span></span>                    | <span data-ttu-id="d8539-187">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-187">x64</span></span> |
| <span data-ttu-id="d8539-188">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d8539-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="d8539-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d8539-189">12 SP2+</span></span>                | <span data-ttu-id="d8539-190">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-190">x64</span></span> |
| <span data-ttu-id="d8539-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-191">Alpine Linux</span></span>                   |  <span data-ttu-id="d8539-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="d8539-192">3.7+</span></span>                   | <span data-ttu-id="d8539-193">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-193">x64</span></span> |

<span data-ttu-id="d8539-194">.NET Core 2.2 지원 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.2 지원 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d8539-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d8539-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d8539-196">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="d8539-197">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처마다)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d8539-198">다운로드 링크 및 자세한 내용은 [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="d8539-199">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="d8539-200">OS</span><span class="sxs-lookup"><span data-stu-id="d8539-200">OS</span></span>                             |  <span data-ttu-id="d8539-201">버전</span><span class="sxs-lookup"><span data-stu-id="d8539-201">Version</span></span>                |  <span data-ttu-id="d8539-202">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d8539-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="d8539-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="d8539-204">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="d8539-204">6, 7, 8</span></span>                | <span data-ttu-id="d8539-205">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-205">x64</span></span> |
| <span data-ttu-id="d8539-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-206">Oracle Linux</span></span>                   |  <span data-ttu-id="d8539-207">7</span><span class="sxs-lookup"><span data-stu-id="d8539-207">7</span></span>                      | <span data-ttu-id="d8539-208">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-208">x64</span></span> |
| <span data-ttu-id="d8539-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="d8539-209">CentOS</span></span>                         |  <span data-ttu-id="d8539-210">7</span><span class="sxs-lookup"><span data-stu-id="d8539-210">7</span></span>                      | <span data-ttu-id="d8539-211">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-211">x64</span></span> |
| <span data-ttu-id="d8539-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="d8539-212">Fedora</span></span>                         |  <span data-ttu-id="d8539-213">29, 30</span><span class="sxs-lookup"><span data-stu-id="d8539-213">29, 30</span></span>                 | <span data-ttu-id="d8539-214">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-214">x64</span></span> |
| <span data-ttu-id="d8539-215">Debian</span><span class="sxs-lookup"><span data-stu-id="d8539-215">Debian</span></span>                         |  <span data-ttu-id="d8539-216">9</span><span class="sxs-lookup"><span data-stu-id="d8539-216">9</span></span>                      | <span data-ttu-id="d8539-217">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d8539-217">x64, ARM32</span></span> |
| <span data-ttu-id="d8539-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d8539-218">Ubuntu</span></span>                         |  <span data-ttu-id="d8539-219">16.04, 18.04, 19.04</span><span class="sxs-lookup"><span data-stu-id="d8539-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="d8539-220">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d8539-220">x64, ARM32</span></span> |
| <span data-ttu-id="d8539-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d8539-221">Linux Mint</span></span>                     |  <span data-ttu-id="d8539-222">17, 18</span><span class="sxs-lookup"><span data-stu-id="d8539-222">17, 18</span></span>                 | <span data-ttu-id="d8539-223">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-223">x64</span></span> |
| <span data-ttu-id="d8539-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d8539-224">openSUSE</span></span>                       |  <span data-ttu-id="d8539-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="d8539-225">42.3+</span></span>                  | <span data-ttu-id="d8539-226">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-226">x64</span></span> |
| <span data-ttu-id="d8539-227">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d8539-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="d8539-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d8539-228">12 SP2+</span></span>                | <span data-ttu-id="d8539-229">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-229">x64</span></span> |
| <span data-ttu-id="d8539-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d8539-230">Alpine Linux</span></span>                   |  <span data-ttu-id="d8539-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="d8539-231">3.7+</span></span>                   | <span data-ttu-id="d8539-232">X64</span><span class="sxs-lookup"><span data-stu-id="d8539-232">x64</span></span> |

<span data-ttu-id="d8539-233">지원 OS 버전 중 .NET Core 2.1이 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.1이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="d8539-234">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="d8539-234">Linux distribution dependencies</span></span>

<span data-ttu-id="d8539-235">다음은 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-235">The following are intended to be examples.</span></span> <span data-ttu-id="d8539-236">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="d8539-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d8539-237">Ubuntu</span></span>

<span data-ttu-id="d8539-238">Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-238">Ubuntu distributions require the following libraries installed:</span></span>

- <span data-ttu-id="d8539-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="d8539-239">liblttng-ust0</span></span>
- <span data-ttu-id="d8539-240">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-240">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="d8539-241">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-241">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="d8539-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="d8539-242">libssl1.0.0</span></span>
- <span data-ttu-id="d8539-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="d8539-243">libkrb5-3</span></span>
- <span data-ttu-id="d8539-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="d8539-244">zlib1g</span></span>
- <span data-ttu-id="d8539-245">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-245">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="d8539-246">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-246">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="d8539-247">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-247">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="d8539-248">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="d8539-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="d8539-249">.NET Core 2.1 이전 버전의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="d8539-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="d8539-250">libunwind8</span></span>
- <span data-ttu-id="d8539-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="d8539-251">libuuid1</span></span>

<span data-ttu-id="d8539-252">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-252">For .NET Core applications that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

* <span data-ttu-id="d8539-253">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="d8539-253">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="d8539-254">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-254">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="d8539-255">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-255">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="d8539-256">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-256">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="d8539-257">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="d8539-257">CentOS and Fedora</span></span>

<span data-ttu-id="d8539-258">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-258">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="d8539-259">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="d8539-259">lttng-ust</span></span>
- <span data-ttu-id="d8539-260">libcurl</span><span class="sxs-lookup"><span data-stu-id="d8539-260">libcurl</span></span>
- <span data-ttu-id="d8539-261">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="d8539-261">openssl-libs</span></span>
- <span data-ttu-id="d8539-262">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="d8539-262">krb5-libs</span></span>
- <span data-ttu-id="d8539-263">libicu</span><span class="sxs-lookup"><span data-stu-id="d8539-263">libicu</span></span>
- <span data-ttu-id="d8539-264">zlib</span><span class="sxs-lookup"><span data-stu-id="d8539-264">zlib</span></span>

<span data-ttu-id="d8539-265">Fedora 사용자: openssl 버전 >= 1.1인 경우 compat-openssl10을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-265">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="d8539-266">.NET Core 2.1 이전 버전의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-266">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="d8539-267">libunwind</span><span class="sxs-lookup"><span data-stu-id="d8539-267">libunwind</span></span>
- <span data-ttu-id="d8539-268">libuuid</span><span class="sxs-lookup"><span data-stu-id="d8539-268">libuuid</span></span>

<span data-ttu-id="d8539-269">종속성에 대한 자세한 내용은 [자체 포함 Linux 애플리케이션](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-269">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="d8539-270">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션의 경우 다음 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-270">For .NET Core applications that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

* <span data-ttu-id="d8539-271">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="d8539-271">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="d8539-272">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-272">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="d8539-273">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-273">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="d8539-274">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-274">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="d8539-275">기본 설치 관리자를 사용하여 .NET Core 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="d8539-275">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="d8539-276">.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-276">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="d8539-277">기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-277">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="d8539-278">기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-278">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="d8539-279">기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-279">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="d8539-280">Linux에는 두 가지 패키지 선택 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-280">On Linux, there are two installer package choices:</span></span>

- <span data-ttu-id="d8539-281">피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).</span><span class="sxs-lookup"><span data-stu-id="d8539-281">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
- <span data-ttu-id="d8539-282">패키지 자체 사용(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="d8539-282">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="d8539-283">.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅</span><span class="sxs-lookup"><span data-stu-id="d8539-283">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="d8539-284">[dotnet-install 스크립트](./tools/dotnet-install-script.md)는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-284">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="d8539-285"><https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-285">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="d8539-286">스크립트는 기본적으로 현재 .NET Core 1.1인 최신 "LTS" 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-286">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="d8539-287">.NET Core 2.1을 설치하려면 다음 스위치를 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-287">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="d8539-288">설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-288">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="d8539-289">또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8539-289">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="d8539-290">문제 해결</span><span class="sxs-lookup"><span data-stu-id="d8539-290">Troubleshoot</span></span>

<span data-ttu-id="d8539-291">지원되는 Linux 배포/버전에 .NET Core 설치에 문제가 있는 경우 설치된 배포/버전에 대한 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8539-291">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

- [<span data-ttu-id="d8539-292">.NET Core 3.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d8539-292">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
- [<span data-ttu-id="d8539-293">.NET Core 2.2 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d8539-293">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
- [<span data-ttu-id="d8539-294">.NET Core 2.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d8539-294">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
- [<span data-ttu-id="d8539-295">.NET Core 1.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d8539-295">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
- [<span data-ttu-id="d8539-296">.NET Core 1.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d8539-296">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
