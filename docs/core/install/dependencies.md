---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a535048fc8756b55068098ad61fdc37fc8c1f04e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74999010"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="9ccff-103">.NET Core 종속성 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ccff-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="9ccff-104">이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="9ccff-105">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="9ccff-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31tabnetcore31"></a>[<span data-ttu-id="9ccff-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="9ccff-107">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-108">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-109">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-109">OS</span></span>                            | <span data-ttu-id="9ccff-110">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-110">Version</span></span>                        | <span data-ttu-id="9ccff-111">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9ccff-112">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-112">Windows Client</span></span>                | <span data-ttu-id="9ccff-113">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9ccff-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-114">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-115">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-115">Windows 10 Client</span></span>             | <span data-ttu-id="9ccff-116">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9ccff-116">Version 1607+</span></span>                  | <span data-ttu-id="9ccff-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-117">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9ccff-118">Windows Server</span></span>                | <span data-ttu-id="9ccff-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-119">2012 R2+</span></span>                       | <span data-ttu-id="9ccff-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-120">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-121">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9ccff-121">Nano Server</span></span>                   | <span data-ttu-id="9ccff-122">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9ccff-122">Version 1803+</span></span>                  | <span data-ttu-id="9ccff-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-123">x64, ARM32</span></span>      |

<span data-ttu-id="9ccff-124">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="9ccff-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9ccff-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="9ccff-126">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-127">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-128">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-128">OS</span></span>                            | <span data-ttu-id="9ccff-129">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-129">Version</span></span>                        | <span data-ttu-id="9ccff-130">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9ccff-131">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-131">Windows Client</span></span>                | <span data-ttu-id="9ccff-132">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9ccff-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-133">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-134">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-134">Windows 10 Client</span></span>             | <span data-ttu-id="9ccff-135">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9ccff-135">Version 1607+</span></span>                  | <span data-ttu-id="9ccff-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-136">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9ccff-137">Windows Server</span></span>                | <span data-ttu-id="9ccff-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-138">2012 R2+</span></span>                       | <span data-ttu-id="9ccff-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-139">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-140">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9ccff-140">Nano Server</span></span>                   | <span data-ttu-id="9ccff-141">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9ccff-141">Version 1803+</span></span>                  | <span data-ttu-id="9ccff-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-142">x64, ARM32</span></span>      |

<span data-ttu-id="9ccff-143">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ccff-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ccff-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9ccff-145">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-146">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-147">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-147">OS</span></span>                            | <span data-ttu-id="9ccff-148">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-148">Version</span></span>                        | <span data-ttu-id="9ccff-149">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9ccff-150">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-150">Windows Client</span></span>                | <span data-ttu-id="9ccff-151">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9ccff-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-152">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-153">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-153">Windows 10 Client</span></span>             | <span data-ttu-id="9ccff-154">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9ccff-154">Version 1607+</span></span>                  | <span data-ttu-id="9ccff-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-155">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9ccff-156">Windows Server</span></span>                | <span data-ttu-id="9ccff-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="9ccff-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="9ccff-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-158">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-159">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9ccff-159">Nano Server</span></span>                   | <span data-ttu-id="9ccff-160">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9ccff-160">Version 1803+</span></span>                   | <span data-ttu-id="9ccff-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-161">x64, ARM32</span></span>      |

<span data-ttu-id="9ccff-162">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ccff-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9ccff-164">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-165">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-166">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-166">OS</span></span>                            | <span data-ttu-id="9ccff-167">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-167">Version</span></span>                        | <span data-ttu-id="9ccff-168">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9ccff-169">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-169">Windows Client</span></span>                | <span data-ttu-id="9ccff-170">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9ccff-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-171">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-172">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9ccff-172">Windows 10 Client</span></span>             | <span data-ttu-id="9ccff-173">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9ccff-173">Version 1607+</span></span>                  | <span data-ttu-id="9ccff-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-174">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9ccff-175">Windows Server</span></span>                | <span data-ttu-id="9ccff-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="9ccff-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="9ccff-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9ccff-177">x64, x86</span></span>        |
| <span data-ttu-id="9ccff-178">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9ccff-178">Nano Server</span></span>                   | <span data-ttu-id="9ccff-179">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9ccff-179">Version 1803+</span></span>                  | <span data-ttu-id="9ccff-180">x64,</span><span class="sxs-lookup"><span data-stu-id="9ccff-180">x64,</span></span>            |

<span data-ttu-id="9ccff-181">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="9ccff-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9ccff-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="9ccff-183">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="9ccff-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="9ccff-184">Windows 7 SP1</span></span>
- <span data-ttu-id="9ccff-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="9ccff-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="9ccff-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-186">Windows 8.1</span></span>
- <span data-ttu-id="9ccff-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9ccff-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="9ccff-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9ccff-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="9ccff-189">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-189">Install the following:</span></span>

- <span data-ttu-id="9ccff-190">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="9ccff-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="9ccff-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="9ccff-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="9ccff-192">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="9ccff-193">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="9ccff-194">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="9ccff-195">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="9ccff-195">\- or -</span></span>
>
> <span data-ttu-id="9ccff-196">라이브러리 *hostfxr.dll*을 찾았으나 *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31tabnetcore31"></a>[<span data-ttu-id="9ccff-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="9ccff-198">.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="9ccff-199">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9ccff-200">.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-201">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-202">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-202">OS</span></span>                             | <span data-ttu-id="9ccff-203">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-203">Version</span></span>               | <span data-ttu-id="9ccff-204">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="9ccff-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="9ccff-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9ccff-206">6, 7, 8</span></span>               | <span data-ttu-id="9ccff-207">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-207">x64</span></span> |
| <span data-ttu-id="9ccff-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="9ccff-208">CentOS</span></span>                         | <span data-ttu-id="9ccff-209">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-209">7+</span></span>                    | <span data-ttu-id="9ccff-210">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-210">x64</span></span> |
| <span data-ttu-id="9ccff-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-211">Oracle Linux</span></span>                   | <span data-ttu-id="9ccff-212">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-212">7+</span></span>                    | <span data-ttu-id="9ccff-213">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-213">x64</span></span> |
| <span data-ttu-id="9ccff-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="9ccff-214">Fedora</span></span>                         | <span data-ttu-id="9ccff-215">29+</span><span class="sxs-lookup"><span data-stu-id="9ccff-215">29+</span></span>                   | <span data-ttu-id="9ccff-216">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-216">x64</span></span> |
| <span data-ttu-id="9ccff-217">Debian</span><span class="sxs-lookup"><span data-stu-id="9ccff-217">Debian</span></span>                         | <span data-ttu-id="9ccff-218">9+</span><span class="sxs-lookup"><span data-stu-id="9ccff-218">9+</span></span>                    | <span data-ttu-id="9ccff-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9ccff-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9ccff-220">Ubuntu</span></span>                         | <span data-ttu-id="9ccff-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="9ccff-221">16.04+</span></span>                | <span data-ttu-id="9ccff-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9ccff-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9ccff-223">Linux Mint</span></span>                     | <span data-ttu-id="9ccff-224">18+</span><span class="sxs-lookup"><span data-stu-id="9ccff-224">18+</span></span>                   | <span data-ttu-id="9ccff-225">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-225">x64</span></span> |
| <span data-ttu-id="9ccff-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9ccff-226">openSUSE</span></span>                       | <span data-ttu-id="9ccff-227">15+</span><span class="sxs-lookup"><span data-stu-id="9ccff-227">15+</span></span>                   | <span data-ttu-id="9ccff-228">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-228">x64</span></span> |
| <span data-ttu-id="9ccff-229">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9ccff-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="9ccff-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-230">12 SP2+</span></span>               | <span data-ttu-id="9ccff-231">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-231">x64</span></span> |
| <span data-ttu-id="9ccff-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-232">Alpine Linux</span></span>                   | <span data-ttu-id="9ccff-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="9ccff-233">3.10+</span></span>                 | <span data-ttu-id="9ccff-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-234">x64, ARM64</span></span> |

<span data-ttu-id="9ccff-235">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="9ccff-236">ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ccff-237">ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="9ccff-238">몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="9ccff-239">예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="9ccff-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9ccff-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="9ccff-241">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="9ccff-242">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9ccff-243">.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-244">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-245">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-245">OS</span></span>                             | <span data-ttu-id="9ccff-246">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-246">Version</span></span>               | <span data-ttu-id="9ccff-247">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="9ccff-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="9ccff-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9ccff-249">6, 7, 8</span></span>               | <span data-ttu-id="9ccff-250">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-250">x64</span></span> |
| <span data-ttu-id="9ccff-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="9ccff-251">CentOS</span></span>                         | <span data-ttu-id="9ccff-252">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-252">7+</span></span>                    | <span data-ttu-id="9ccff-253">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-253">x64</span></span> |
| <span data-ttu-id="9ccff-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-254">Oracle Linux</span></span>                   | <span data-ttu-id="9ccff-255">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-255">7+</span></span>                    | <span data-ttu-id="9ccff-256">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-256">x64</span></span> |
| <span data-ttu-id="9ccff-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="9ccff-257">Fedora</span></span>                         | <span data-ttu-id="9ccff-258">29+</span><span class="sxs-lookup"><span data-stu-id="9ccff-258">29+</span></span>                   | <span data-ttu-id="9ccff-259">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-259">x64</span></span> |
| <span data-ttu-id="9ccff-260">Debian</span><span class="sxs-lookup"><span data-stu-id="9ccff-260">Debian</span></span>                         | <span data-ttu-id="9ccff-261">9+</span><span class="sxs-lookup"><span data-stu-id="9ccff-261">9+</span></span>                    | <span data-ttu-id="9ccff-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9ccff-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9ccff-263">Ubuntu</span></span>                         | <span data-ttu-id="9ccff-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="9ccff-264">16.04+</span></span>                | <span data-ttu-id="9ccff-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9ccff-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9ccff-266">Linux Mint</span></span>                     | <span data-ttu-id="9ccff-267">18+</span><span class="sxs-lookup"><span data-stu-id="9ccff-267">18+</span></span>                   | <span data-ttu-id="9ccff-268">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-268">x64</span></span> |
| <span data-ttu-id="9ccff-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9ccff-269">openSUSE</span></span>                       | <span data-ttu-id="9ccff-270">15+</span><span class="sxs-lookup"><span data-stu-id="9ccff-270">15+</span></span>                   | <span data-ttu-id="9ccff-271">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-271">x64</span></span> |
| <span data-ttu-id="9ccff-272">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9ccff-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="9ccff-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-273">12 SP2+</span></span>               | <span data-ttu-id="9ccff-274">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-274">x64</span></span> |
| <span data-ttu-id="9ccff-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-275">Alpine Linux</span></span>                   | <span data-ttu-id="9ccff-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="9ccff-276">3.8+</span></span>                  | <span data-ttu-id="9ccff-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="9ccff-277">x64, ARM64</span></span> |

<span data-ttu-id="9ccff-278">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="9ccff-279">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ccff-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ccff-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9ccff-281">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="9ccff-282">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9ccff-283">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-284">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-285">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-285">OS</span></span>                             |  <span data-ttu-id="9ccff-286">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-286">Version</span></span>                |  <span data-ttu-id="9ccff-287">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="9ccff-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="9ccff-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="9ccff-289">6, 7</span></span>                   | <span data-ttu-id="9ccff-290">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-290">x64</span></span> |
| <span data-ttu-id="9ccff-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="9ccff-291">CentOS</span></span>                         |  <span data-ttu-id="9ccff-292">7</span><span class="sxs-lookup"><span data-stu-id="9ccff-292">7</span></span>                      | <span data-ttu-id="9ccff-293">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-293">x64</span></span> |
| <span data-ttu-id="9ccff-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-294">Oracle Linux</span></span>                   |  <span data-ttu-id="9ccff-295">7</span><span class="sxs-lookup"><span data-stu-id="9ccff-295">7</span></span>                      | <span data-ttu-id="9ccff-296">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-296">x64</span></span> |
| <span data-ttu-id="9ccff-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="9ccff-297">Fedora</span></span>                         |  <span data-ttu-id="9ccff-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="9ccff-298">29, 30</span></span>                 | <span data-ttu-id="9ccff-299">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-299">x64</span></span> |
| <span data-ttu-id="9ccff-300">Debian</span><span class="sxs-lookup"><span data-stu-id="9ccff-300">Debian</span></span>                         |  <span data-ttu-id="9ccff-301">9</span><span class="sxs-lookup"><span data-stu-id="9ccff-301">9</span></span>                      | <span data-ttu-id="9ccff-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-302">x64, ARM32</span></span> |
| <span data-ttu-id="9ccff-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9ccff-303">Ubuntu</span></span>                         |  <span data-ttu-id="9ccff-304">16.04, 18.04, 18.10, 19.04</span><span class="sxs-lookup"><span data-stu-id="9ccff-304">16.04, 18.04, 18.10, 19.04</span></span>    | <span data-ttu-id="9ccff-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-305">x64, ARM32</span></span> |
| <span data-ttu-id="9ccff-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9ccff-306">Linux Mint</span></span>                     |  <span data-ttu-id="9ccff-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="9ccff-307">17, 18</span></span>                 | <span data-ttu-id="9ccff-308">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-308">x64</span></span> |
| <span data-ttu-id="9ccff-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9ccff-309">openSUSE</span></span>                       |  <span data-ttu-id="9ccff-310">15+</span><span class="sxs-lookup"><span data-stu-id="9ccff-310">15+</span></span>                    | <span data-ttu-id="9ccff-311">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-311">x64</span></span> |
| <span data-ttu-id="9ccff-312">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9ccff-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="9ccff-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-313">12 SP2+</span></span>                | <span data-ttu-id="9ccff-314">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-314">x64</span></span> |
| <span data-ttu-id="9ccff-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-315">Alpine Linux</span></span>                   |  <span data-ttu-id="9ccff-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="9ccff-316">3.8+</span></span>                   | <span data-ttu-id="9ccff-317">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-317">x64</span></span> |

<span data-ttu-id="9ccff-318">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ccff-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9ccff-320">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="9ccff-321">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9ccff-322">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-323">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-324">OS</span><span class="sxs-lookup"><span data-stu-id="9ccff-324">OS</span></span>                             |  <span data-ttu-id="9ccff-325">버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-325">Version</span></span>                |  <span data-ttu-id="9ccff-326">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="9ccff-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="9ccff-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9ccff-328">6, 7, 8</span></span>                | <span data-ttu-id="9ccff-329">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-329">x64</span></span> |
| <span data-ttu-id="9ccff-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="9ccff-330">CentOS</span></span>                         |  <span data-ttu-id="9ccff-331">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-331">7+</span></span>                     | <span data-ttu-id="9ccff-332">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-332">x64</span></span> |
| <span data-ttu-id="9ccff-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-333">Oracle Linux</span></span>                   |  <span data-ttu-id="9ccff-334">7+</span><span class="sxs-lookup"><span data-stu-id="9ccff-334">7+</span></span>                     | <span data-ttu-id="9ccff-335">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-335">x64</span></span> |
| <span data-ttu-id="9ccff-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="9ccff-336">Fedora</span></span>                         |  <span data-ttu-id="9ccff-337">29+</span><span class="sxs-lookup"><span data-stu-id="9ccff-337">29+</span></span>                    | <span data-ttu-id="9ccff-338">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-338">x64</span></span> |
| <span data-ttu-id="9ccff-339">Debian</span><span class="sxs-lookup"><span data-stu-id="9ccff-339">Debian</span></span>                         |  <span data-ttu-id="9ccff-340">9</span><span class="sxs-lookup"><span data-stu-id="9ccff-340">9</span></span>                      | <span data-ttu-id="9ccff-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-341">x64, ARM32</span></span> |
| <span data-ttu-id="9ccff-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9ccff-342">Ubuntu</span></span>                         |  <span data-ttu-id="9ccff-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="9ccff-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="9ccff-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9ccff-344">x64, ARM32</span></span> |
| <span data-ttu-id="9ccff-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9ccff-345">Linux Mint</span></span>                     |  <span data-ttu-id="9ccff-346">17+</span><span class="sxs-lookup"><span data-stu-id="9ccff-346">17+</span></span>                    | <span data-ttu-id="9ccff-347">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-347">x64</span></span> |
| <span data-ttu-id="9ccff-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9ccff-348">openSUSE</span></span>                       |  <span data-ttu-id="9ccff-349">15+</span><span class="sxs-lookup"><span data-stu-id="9ccff-349">15+</span></span>                    | <span data-ttu-id="9ccff-350">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-350">x64</span></span> |
| <span data-ttu-id="9ccff-351">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9ccff-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="9ccff-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9ccff-352">12 SP2+</span></span>                | <span data-ttu-id="9ccff-353">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-353">x64</span></span> |
| <span data-ttu-id="9ccff-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9ccff-354">Alpine Linux</span></span>                   |  <span data-ttu-id="9ccff-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="9ccff-355">3.8+</span></span>                   | <span data-ttu-id="9ccff-356">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-356">x64</span></span> |

<span data-ttu-id="9ccff-357">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="9ccff-358">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="9ccff-358">Linux distribution dependencies</span></span>

<span data-ttu-id="9ccff-359">Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ccff-360">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="9ccff-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9ccff-361">Ubuntu</span></span>

<span data-ttu-id="9ccff-362">Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="9ccff-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="9ccff-363">liblttng-ust0</span></span>
- <span data-ttu-id="9ccff-364">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="9ccff-365">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="9ccff-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="9ccff-366">libssl1.0.0</span></span>
- <span data-ttu-id="9ccff-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="9ccff-367">libkrb5-3</span></span>
- <span data-ttu-id="9ccff-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="9ccff-368">zlib1g</span></span>
- <span data-ttu-id="9ccff-369">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="9ccff-370">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="9ccff-371">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="9ccff-372">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="9ccff-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="9ccff-373">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="9ccff-374">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="9ccff-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="9ccff-375">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="9ccff-376">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="9ccff-377">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="9ccff-378">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="9ccff-378">CentOS and Fedora</span></span>

<span data-ttu-id="9ccff-379">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="9ccff-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="9ccff-380">lttng-ust</span></span>
- <span data-ttu-id="9ccff-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="9ccff-381">libcurl</span></span>
- <span data-ttu-id="9ccff-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="9ccff-382">openssl-libs</span></span>
- <span data-ttu-id="9ccff-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="9ccff-383">krb5-libs</span></span>
- <span data-ttu-id="9ccff-384">libicu</span><span class="sxs-lookup"><span data-stu-id="9ccff-384">libicu</span></span>
- <span data-ttu-id="9ccff-385">zlib</span><span class="sxs-lookup"><span data-stu-id="9ccff-385">zlib</span></span>

<span data-ttu-id="9ccff-386">Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="9ccff-387">.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="9ccff-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="9ccff-388">libunwind</span></span>
- <span data-ttu-id="9ccff-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="9ccff-389">libuuid</span></span>

<span data-ttu-id="9ccff-390">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="9ccff-391">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="9ccff-392">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="9ccff-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="9ccff-393">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="9ccff-394">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="9ccff-395">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="9ccff-396">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="9ccff-397">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9ccff-398">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="9ccff-398">.NET Core Version</span></span> | <span data-ttu-id="9ccff-399">macOS</span><span class="sxs-lookup"><span data-stu-id="9ccff-399">macOS</span></span>                 | <span data-ttu-id="9ccff-400">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9ccff-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="9ccff-401">3.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-401">3.1</span></span>               | <span data-ttu-id="9ccff-402">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="9ccff-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="9ccff-403">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-403">x64</span></span> | [<span data-ttu-id="9ccff-404">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9ccff-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="9ccff-405">3.0</span><span class="sxs-lookup"><span data-stu-id="9ccff-405">3.0</span></span>               | <span data-ttu-id="9ccff-406">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="9ccff-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="9ccff-407">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-407">x64</span></span> | [<span data-ttu-id="9ccff-408">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9ccff-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="9ccff-409">2.2</span><span class="sxs-lookup"><span data-stu-id="9ccff-409">2.2</span></span>               | <span data-ttu-id="9ccff-410">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="9ccff-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="9ccff-411">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-411">x64</span></span> | [<span data-ttu-id="9ccff-412">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9ccff-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="9ccff-413">2.1</span><span class="sxs-lookup"><span data-stu-id="9ccff-413">2.1</span></span>               | <span data-ttu-id="9ccff-414">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="9ccff-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="9ccff-415">X64</span><span class="sxs-lookup"><span data-stu-id="9ccff-415">x64</span></span> | [<span data-ttu-id="9ccff-416">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9ccff-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="9ccff-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="9ccff-417">libgdiplus</span></span>

<span data-ttu-id="9ccff-418">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="9ccff-419">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="9ccff-420">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccff-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="9ccff-421">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9ccff-421">Next steps</span></span>

- <span data-ttu-id="9ccff-422">앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="9ccff-423">다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccff-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
