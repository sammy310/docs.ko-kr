---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157814"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="89fce-103">.NET Core 종속성 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="89fce-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="89fce-104">이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="89fce-105">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="89fce-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="89fce-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="89fce-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="89fce-107">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-108">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-109">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-109">OS</span></span>                            | <span data-ttu-id="89fce-110">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-110">Version</span></span>                        | <span data-ttu-id="89fce-111">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="89fce-112">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-112">Windows Client</span></span>                | <span data-ttu-id="89fce-113">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="89fce-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="89fce-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-114">x64, x86</span></span>        |
| <span data-ttu-id="89fce-115">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-115">Windows 10 Client</span></span>             | <span data-ttu-id="89fce-116">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="89fce-116">Version 1607+</span></span>                  | <span data-ttu-id="89fce-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-117">x64, x86</span></span>        |
| <span data-ttu-id="89fce-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="89fce-118">Windows Server</span></span>                | <span data-ttu-id="89fce-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="89fce-119">2012 R2+</span></span>                       | <span data-ttu-id="89fce-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-120">x64, x86</span></span>        |
| <span data-ttu-id="89fce-121">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="89fce-121">Nano Server</span></span>                   | <span data-ttu-id="89fce-122">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="89fce-122">Version 1803+</span></span>                  | <span data-ttu-id="89fce-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-123">x64, ARM32</span></span>      |

<span data-ttu-id="89fce-124">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="89fce-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="89fce-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="89fce-126">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-127">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-128">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-128">OS</span></span>                            | <span data-ttu-id="89fce-129">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-129">Version</span></span>                        | <span data-ttu-id="89fce-130">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="89fce-131">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-131">Windows Client</span></span>                | <span data-ttu-id="89fce-132">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="89fce-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="89fce-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-133">x64, x86</span></span>        |
| <span data-ttu-id="89fce-134">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-134">Windows 10 Client</span></span>             | <span data-ttu-id="89fce-135">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="89fce-135">Version 1607+</span></span>                  | <span data-ttu-id="89fce-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-136">x64, x86</span></span>        |
| <span data-ttu-id="89fce-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="89fce-137">Windows Server</span></span>                | <span data-ttu-id="89fce-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="89fce-138">2012 R2+</span></span>                       | <span data-ttu-id="89fce-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-139">x64, x86</span></span>        |
| <span data-ttu-id="89fce-140">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="89fce-140">Nano Server</span></span>                   | <span data-ttu-id="89fce-141">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="89fce-141">Version 1803+</span></span>                  | <span data-ttu-id="89fce-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-142">x64, ARM32</span></span>      |

<span data-ttu-id="89fce-143">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="89fce-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="89fce-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="89fce-145">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-146">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-147">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-147">OS</span></span>                            | <span data-ttu-id="89fce-148">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-148">Version</span></span>                        | <span data-ttu-id="89fce-149">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="89fce-150">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-150">Windows Client</span></span>                | <span data-ttu-id="89fce-151">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="89fce-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="89fce-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-152">x64, x86</span></span>        |
| <span data-ttu-id="89fce-153">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-153">Windows 10 Client</span></span>             | <span data-ttu-id="89fce-154">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="89fce-154">Version 1607+</span></span>                  | <span data-ttu-id="89fce-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-155">x64, x86</span></span>        |
| <span data-ttu-id="89fce-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="89fce-156">Windows Server</span></span>                | <span data-ttu-id="89fce-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="89fce-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="89fce-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-158">x64, x86</span></span>        |
| <span data-ttu-id="89fce-159">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="89fce-159">Nano Server</span></span>                   | <span data-ttu-id="89fce-160">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="89fce-160">Version 1803+</span></span>                   | <span data-ttu-id="89fce-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-161">x64, ARM32</span></span>      |

<span data-ttu-id="89fce-162">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="89fce-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89fce-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="89fce-164">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-165">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-166">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-166">OS</span></span>                            | <span data-ttu-id="89fce-167">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-167">Version</span></span>                        | <span data-ttu-id="89fce-168">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="89fce-169">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-169">Windows Client</span></span>                | <span data-ttu-id="89fce-170">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="89fce-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="89fce-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-171">x64, x86</span></span>        |
| <span data-ttu-id="89fce-172">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89fce-172">Windows 10 Client</span></span>             | <span data-ttu-id="89fce-173">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="89fce-173">Version 1607+</span></span>                  | <span data-ttu-id="89fce-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-174">x64, x86</span></span>        |
| <span data-ttu-id="89fce-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="89fce-175">Windows Server</span></span>                | <span data-ttu-id="89fce-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="89fce-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="89fce-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="89fce-177">x64, x86</span></span>        |
| <span data-ttu-id="89fce-178">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="89fce-178">Nano Server</span></span>                   | <span data-ttu-id="89fce-179">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="89fce-179">Version 1803+</span></span>                  | <span data-ttu-id="89fce-180">x64,</span><span class="sxs-lookup"><span data-stu-id="89fce-180">x64,</span></span>            |

<span data-ttu-id="89fce-181">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="89fce-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="89fce-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="89fce-183">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="89fce-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="89fce-184">Windows 7 SP1</span></span>
- <span data-ttu-id="89fce-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="89fce-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="89fce-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="89fce-186">Windows 8.1</span></span>
- <span data-ttu-id="89fce-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="89fce-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="89fce-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="89fce-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="89fce-189">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-189">Install the following:</span></span>

- <span data-ttu-id="89fce-190">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="89fce-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="89fce-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="89fce-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="89fce-192">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="89fce-193">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="89fce-194">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="89fce-195">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="89fce-195">\- or -</span></span>
>
> <span data-ttu-id="89fce-196">라이브러리 *hostfxr.dll*을 찾았으나 *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="89fce-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="89fce-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="89fce-198">.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="89fce-199">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="89fce-200">.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-201">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-202">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-202">OS</span></span>                             | <span data-ttu-id="89fce-203">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-203">Version</span></span>               | <span data-ttu-id="89fce-204">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="89fce-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="89fce-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="89fce-206">6, 7, 8</span></span>               | <span data-ttu-id="89fce-207">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-207">x64</span></span> |
| <span data-ttu-id="89fce-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="89fce-208">CentOS</span></span>                         | <span data-ttu-id="89fce-209">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-209">7+</span></span>                    | <span data-ttu-id="89fce-210">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-210">x64</span></span> |
| <span data-ttu-id="89fce-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-211">Oracle Linux</span></span>                   | <span data-ttu-id="89fce-212">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-212">7+</span></span>                    | <span data-ttu-id="89fce-213">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-213">x64</span></span> |
| <span data-ttu-id="89fce-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="89fce-214">Fedora</span></span>                         | <span data-ttu-id="89fce-215">29+</span><span class="sxs-lookup"><span data-stu-id="89fce-215">29+</span></span>                   | <span data-ttu-id="89fce-216">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-216">x64</span></span> |
| <span data-ttu-id="89fce-217">Debian</span><span class="sxs-lookup"><span data-stu-id="89fce-217">Debian</span></span>                         | <span data-ttu-id="89fce-218">9+</span><span class="sxs-lookup"><span data-stu-id="89fce-218">9+</span></span>                    | <span data-ttu-id="89fce-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="89fce-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="89fce-220">Ubuntu</span></span>                         | <span data-ttu-id="89fce-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="89fce-221">16.04+</span></span>                | <span data-ttu-id="89fce-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="89fce-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="89fce-223">Linux Mint</span></span>                     | <span data-ttu-id="89fce-224">18+</span><span class="sxs-lookup"><span data-stu-id="89fce-224">18+</span></span>                   | <span data-ttu-id="89fce-225">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-225">x64</span></span> |
| <span data-ttu-id="89fce-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="89fce-226">openSUSE</span></span>                       | <span data-ttu-id="89fce-227">15+</span><span class="sxs-lookup"><span data-stu-id="89fce-227">15+</span></span>                   | <span data-ttu-id="89fce-228">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-228">x64</span></span> |
| <span data-ttu-id="89fce-229">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="89fce-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="89fce-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="89fce-230">12 SP2+</span></span>               | <span data-ttu-id="89fce-231">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-231">x64</span></span> |
| <span data-ttu-id="89fce-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-232">Alpine Linux</span></span>                   | <span data-ttu-id="89fce-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="89fce-233">3.10+</span></span>                 | <span data-ttu-id="89fce-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-234">x64, ARM64</span></span> |

<span data-ttu-id="89fce-235">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="89fce-236">ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89fce-237">ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="89fce-238">몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="89fce-239">예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="89fce-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="89fce-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="89fce-241">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="89fce-242">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="89fce-243">.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-244">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-245">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-245">OS</span></span>                             | <span data-ttu-id="89fce-246">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-246">Version</span></span>               | <span data-ttu-id="89fce-247">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="89fce-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="89fce-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="89fce-249">6, 7, 8</span></span>               | <span data-ttu-id="89fce-250">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-250">x64</span></span> |
| <span data-ttu-id="89fce-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="89fce-251">CentOS</span></span>                         | <span data-ttu-id="89fce-252">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-252">7+</span></span>                    | <span data-ttu-id="89fce-253">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-253">x64</span></span> |
| <span data-ttu-id="89fce-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-254">Oracle Linux</span></span>                   | <span data-ttu-id="89fce-255">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-255">7+</span></span>                    | <span data-ttu-id="89fce-256">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-256">x64</span></span> |
| <span data-ttu-id="89fce-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="89fce-257">Fedora</span></span>                         | <span data-ttu-id="89fce-258">29+</span><span class="sxs-lookup"><span data-stu-id="89fce-258">29+</span></span>                   | <span data-ttu-id="89fce-259">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-259">x64</span></span> |
| <span data-ttu-id="89fce-260">Debian</span><span class="sxs-lookup"><span data-stu-id="89fce-260">Debian</span></span>                         | <span data-ttu-id="89fce-261">9+</span><span class="sxs-lookup"><span data-stu-id="89fce-261">9+</span></span>                    | <span data-ttu-id="89fce-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="89fce-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="89fce-263">Ubuntu</span></span>                         | <span data-ttu-id="89fce-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="89fce-264">16.04+</span></span>                | <span data-ttu-id="89fce-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="89fce-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="89fce-266">Linux Mint</span></span>                     | <span data-ttu-id="89fce-267">18+</span><span class="sxs-lookup"><span data-stu-id="89fce-267">18+</span></span>                   | <span data-ttu-id="89fce-268">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-268">x64</span></span> |
| <span data-ttu-id="89fce-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="89fce-269">openSUSE</span></span>                       | <span data-ttu-id="89fce-270">15+</span><span class="sxs-lookup"><span data-stu-id="89fce-270">15+</span></span>                   | <span data-ttu-id="89fce-271">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-271">x64</span></span> |
| <span data-ttu-id="89fce-272">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="89fce-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="89fce-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="89fce-273">12 SP2+</span></span>               | <span data-ttu-id="89fce-274">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-274">x64</span></span> |
| <span data-ttu-id="89fce-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-275">Alpine Linux</span></span>                   | <span data-ttu-id="89fce-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="89fce-276">3.8+</span></span>                  | <span data-ttu-id="89fce-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="89fce-277">x64, ARM64</span></span> |

<span data-ttu-id="89fce-278">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="89fce-279">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="89fce-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="89fce-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="89fce-281">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="89fce-282">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="89fce-283">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-284">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-285">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-285">OS</span></span>                             |  <span data-ttu-id="89fce-286">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-286">Version</span></span>                |  <span data-ttu-id="89fce-287">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="89fce-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="89fce-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="89fce-289">6, 7</span></span>                   | <span data-ttu-id="89fce-290">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-290">x64</span></span> |
| <span data-ttu-id="89fce-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="89fce-291">CentOS</span></span>                         |  <span data-ttu-id="89fce-292">7</span><span class="sxs-lookup"><span data-stu-id="89fce-292">7</span></span>                      | <span data-ttu-id="89fce-293">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-293">x64</span></span> |
| <span data-ttu-id="89fce-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-294">Oracle Linux</span></span>                   |  <span data-ttu-id="89fce-295">7</span><span class="sxs-lookup"><span data-stu-id="89fce-295">7</span></span>                      | <span data-ttu-id="89fce-296">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-296">x64</span></span> |
| <span data-ttu-id="89fce-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="89fce-297">Fedora</span></span>                         |  <span data-ttu-id="89fce-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="89fce-298">29, 30</span></span>                 | <span data-ttu-id="89fce-299">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-299">x64</span></span> |
| <span data-ttu-id="89fce-300">Debian</span><span class="sxs-lookup"><span data-stu-id="89fce-300">Debian</span></span>                         |  <span data-ttu-id="89fce-301">9</span><span class="sxs-lookup"><span data-stu-id="89fce-301">9</span></span>                      | <span data-ttu-id="89fce-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-302">x64, ARM32</span></span> |
| <span data-ttu-id="89fce-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="89fce-303">Ubuntu</span></span>                         |  <span data-ttu-id="89fce-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="89fce-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="89fce-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-305">x64, ARM32</span></span> |
| <span data-ttu-id="89fce-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="89fce-306">Linux Mint</span></span>                     |  <span data-ttu-id="89fce-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="89fce-307">17, 18</span></span>                 | <span data-ttu-id="89fce-308">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-308">x64</span></span> |
| <span data-ttu-id="89fce-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="89fce-309">openSUSE</span></span>                       |  <span data-ttu-id="89fce-310">15+</span><span class="sxs-lookup"><span data-stu-id="89fce-310">15+</span></span>                    | <span data-ttu-id="89fce-311">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-311">x64</span></span> |
| <span data-ttu-id="89fce-312">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="89fce-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="89fce-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="89fce-313">12 SP2+</span></span>                | <span data-ttu-id="89fce-314">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-314">x64</span></span> |
| <span data-ttu-id="89fce-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-315">Alpine Linux</span></span>                   |  <span data-ttu-id="89fce-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="89fce-316">3.8+</span></span>                   | <span data-ttu-id="89fce-317">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-317">x64</span></span> |

<span data-ttu-id="89fce-318">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="89fce-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89fce-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="89fce-320">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="89fce-321">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="89fce-322">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-323">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-324">OS</span><span class="sxs-lookup"><span data-stu-id="89fce-324">OS</span></span>                             |  <span data-ttu-id="89fce-325">버전</span><span class="sxs-lookup"><span data-stu-id="89fce-325">Version</span></span>                |  <span data-ttu-id="89fce-326">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="89fce-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="89fce-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="89fce-328">6, 7, 8</span></span>                | <span data-ttu-id="89fce-329">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-329">x64</span></span> |
| <span data-ttu-id="89fce-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="89fce-330">CentOS</span></span>                         |  <span data-ttu-id="89fce-331">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-331">7+</span></span>                     | <span data-ttu-id="89fce-332">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-332">x64</span></span> |
| <span data-ttu-id="89fce-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-333">Oracle Linux</span></span>                   |  <span data-ttu-id="89fce-334">7+</span><span class="sxs-lookup"><span data-stu-id="89fce-334">7+</span></span>                     | <span data-ttu-id="89fce-335">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-335">x64</span></span> |
| <span data-ttu-id="89fce-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="89fce-336">Fedora</span></span>                         |  <span data-ttu-id="89fce-337">29+</span><span class="sxs-lookup"><span data-stu-id="89fce-337">29+</span></span>                    | <span data-ttu-id="89fce-338">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-338">x64</span></span> |
| <span data-ttu-id="89fce-339">Debian</span><span class="sxs-lookup"><span data-stu-id="89fce-339">Debian</span></span>                         |  <span data-ttu-id="89fce-340">9</span><span class="sxs-lookup"><span data-stu-id="89fce-340">9</span></span>                      | <span data-ttu-id="89fce-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-341">x64, ARM32</span></span> |
| <span data-ttu-id="89fce-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="89fce-342">Ubuntu</span></span>                         |  <span data-ttu-id="89fce-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="89fce-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="89fce-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="89fce-344">x64, ARM32</span></span> |
| <span data-ttu-id="89fce-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="89fce-345">Linux Mint</span></span>                     |  <span data-ttu-id="89fce-346">17+</span><span class="sxs-lookup"><span data-stu-id="89fce-346">17+</span></span>                    | <span data-ttu-id="89fce-347">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-347">x64</span></span> |
| <span data-ttu-id="89fce-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="89fce-348">openSUSE</span></span>                       |  <span data-ttu-id="89fce-349">15+</span><span class="sxs-lookup"><span data-stu-id="89fce-349">15+</span></span>                    | <span data-ttu-id="89fce-350">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-350">x64</span></span> |
| <span data-ttu-id="89fce-351">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="89fce-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="89fce-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="89fce-352">12 SP2+</span></span>                | <span data-ttu-id="89fce-353">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-353">x64</span></span> |
| <span data-ttu-id="89fce-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="89fce-354">Alpine Linux</span></span>                   |  <span data-ttu-id="89fce-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="89fce-355">3.8+</span></span>                   | <span data-ttu-id="89fce-356">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-356">x64</span></span> |

<span data-ttu-id="89fce-357">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="89fce-358">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="89fce-358">Linux distribution dependencies</span></span>

<span data-ttu-id="89fce-359">Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89fce-360">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="89fce-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="89fce-361">Ubuntu</span></span>

<span data-ttu-id="89fce-362">Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="89fce-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="89fce-363">liblttng-ust0</span></span>
- <span data-ttu-id="89fce-364">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="89fce-365">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="89fce-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="89fce-366">libssl1.0.0</span></span>
- <span data-ttu-id="89fce-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="89fce-367">libkrb5-3</span></span>
- <span data-ttu-id="89fce-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="89fce-368">zlib1g</span></span>
- <span data-ttu-id="89fce-369">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="89fce-370">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="89fce-371">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="89fce-372">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="89fce-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="89fce-373">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="89fce-374">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="89fce-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="89fce-375">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="89fce-376">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="89fce-377">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="89fce-378">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="89fce-378">CentOS and Fedora</span></span>

<span data-ttu-id="89fce-379">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="89fce-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="89fce-380">lttng-ust</span></span>
- <span data-ttu-id="89fce-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="89fce-381">libcurl</span></span>
- <span data-ttu-id="89fce-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="89fce-382">openssl-libs</span></span>
- <span data-ttu-id="89fce-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="89fce-383">krb5-libs</span></span>
- <span data-ttu-id="89fce-384">libicu</span><span class="sxs-lookup"><span data-stu-id="89fce-384">libicu</span></span>
- <span data-ttu-id="89fce-385">zlib</span><span class="sxs-lookup"><span data-stu-id="89fce-385">zlib</span></span>

<span data-ttu-id="89fce-386">Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="89fce-387">.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="89fce-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="89fce-388">libunwind</span></span>
- <span data-ttu-id="89fce-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="89fce-389">libuuid</span></span>

<span data-ttu-id="89fce-390">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="89fce-391">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="89fce-392">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="89fce-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="89fce-393">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="89fce-394">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="89fce-395">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="89fce-396">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="89fce-397">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="89fce-398">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="89fce-398">.NET Core Version</span></span> | <span data-ttu-id="89fce-399">macOS</span><span class="sxs-lookup"><span data-stu-id="89fce-399">macOS</span></span>                 | <span data-ttu-id="89fce-400">아키텍처</span><span class="sxs-lookup"><span data-stu-id="89fce-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="89fce-401">3.1</span><span class="sxs-lookup"><span data-stu-id="89fce-401">3.1</span></span>               | <span data-ttu-id="89fce-402">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="89fce-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="89fce-403">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-403">x64</span></span> | [<span data-ttu-id="89fce-404">추가 정보</span><span class="sxs-lookup"><span data-stu-id="89fce-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="89fce-405">3.0</span><span class="sxs-lookup"><span data-stu-id="89fce-405">3.0</span></span>               | <span data-ttu-id="89fce-406">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="89fce-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="89fce-407">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-407">x64</span></span> | [<span data-ttu-id="89fce-408">추가 정보</span><span class="sxs-lookup"><span data-stu-id="89fce-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="89fce-409">2.2</span><span class="sxs-lookup"><span data-stu-id="89fce-409">2.2</span></span>               | <span data-ttu-id="89fce-410">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="89fce-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="89fce-411">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-411">x64</span></span> | [<span data-ttu-id="89fce-412">추가 정보</span><span class="sxs-lookup"><span data-stu-id="89fce-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="89fce-413">2.1</span><span class="sxs-lookup"><span data-stu-id="89fce-413">2.1</span></span>               | <span data-ttu-id="89fce-414">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="89fce-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="89fce-415">X64</span><span class="sxs-lookup"><span data-stu-id="89fce-415">x64</span></span> | [<span data-ttu-id="89fce-416">추가 정보</span><span class="sxs-lookup"><span data-stu-id="89fce-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="89fce-417">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="89fce-418">이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="89fce-419">.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="89fce-420">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="89fce-421">공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="89fce-423">공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="89fce-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="89fce-424">libgdiplus</span></span>

<span data-ttu-id="89fce-425">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="89fce-426">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="89fce-427">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="89fce-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="89fce-428">다음 단계</span><span class="sxs-lookup"><span data-stu-id="89fce-428">Next steps</span></span>

- <span data-ttu-id="89fce-429">앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="89fce-430">다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="89fce-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
