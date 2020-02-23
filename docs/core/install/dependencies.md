---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448895"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="2ab0e-103">.NET Core 종속성 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ab0e-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="2ab0e-104">이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="2ab0e-105">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="2ab0e-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="2ab0e-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="2ab0e-107">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-108">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-109">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-109">OS</span></span>                            | <span data-ttu-id="2ab0e-110">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-110">Version</span></span>                        | <span data-ttu-id="2ab0e-111">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="2ab0e-112">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-112">Windows Client</span></span>                | <span data-ttu-id="2ab0e-113">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="2ab0e-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-114">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-115">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-115">Windows 10 Client</span></span>             | <span data-ttu-id="2ab0e-116">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-116">Version 1607+</span></span>                  | <span data-ttu-id="2ab0e-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-117">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ab0e-118">Windows Server</span></span>                | <span data-ttu-id="2ab0e-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-119">2012 R2+</span></span>                       | <span data-ttu-id="2ab0e-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-120">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-121">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="2ab0e-121">Nano Server</span></span>                   | <span data-ttu-id="2ab0e-122">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-122">Version 1803+</span></span>                  | <span data-ttu-id="2ab0e-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-123">x64, ARM32</span></span>      |

<span data-ttu-id="2ab0e-124">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="2ab0e-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2ab0e-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="2ab0e-126">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-127">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-128">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-128">OS</span></span>                            | <span data-ttu-id="2ab0e-129">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-129">Version</span></span>                        | <span data-ttu-id="2ab0e-130">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="2ab0e-131">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-131">Windows Client</span></span>                | <span data-ttu-id="2ab0e-132">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="2ab0e-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-133">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-134">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-134">Windows 10 Client</span></span>             | <span data-ttu-id="2ab0e-135">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-135">Version 1607+</span></span>                  | <span data-ttu-id="2ab0e-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-136">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ab0e-137">Windows Server</span></span>                | <span data-ttu-id="2ab0e-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-138">2012 R2+</span></span>                       | <span data-ttu-id="2ab0e-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-139">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-140">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="2ab0e-140">Nano Server</span></span>                   | <span data-ttu-id="2ab0e-141">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-141">Version 1803+</span></span>                  | <span data-ttu-id="2ab0e-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-142">x64, ARM32</span></span>      |

<span data-ttu-id="2ab0e-143">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="2ab0e-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="2ab0e-145">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-146">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-147">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-147">OS</span></span>                            | <span data-ttu-id="2ab0e-148">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-148">Version</span></span>                        | <span data-ttu-id="2ab0e-149">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="2ab0e-150">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-150">Windows Client</span></span>                | <span data-ttu-id="2ab0e-151">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="2ab0e-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-152">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-153">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-153">Windows 10 Client</span></span>             | <span data-ttu-id="2ab0e-154">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-154">Version 1607+</span></span>                  | <span data-ttu-id="2ab0e-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-155">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ab0e-156">Windows Server</span></span>                | <span data-ttu-id="2ab0e-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="2ab0e-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-158">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-159">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="2ab0e-159">Nano Server</span></span>                   | <span data-ttu-id="2ab0e-160">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-160">Version 1803+</span></span>                   | <span data-ttu-id="2ab0e-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-161">x64, ARM32</span></span>      |

<span data-ttu-id="2ab0e-162">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="2ab0e-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="2ab0e-164">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-165">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-166">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-166">OS</span></span>                            | <span data-ttu-id="2ab0e-167">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-167">Version</span></span>                        | <span data-ttu-id="2ab0e-168">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="2ab0e-169">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-169">Windows Client</span></span>                | <span data-ttu-id="2ab0e-170">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="2ab0e-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-171">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-172">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ab0e-172">Windows 10 Client</span></span>             | <span data-ttu-id="2ab0e-173">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-173">Version 1607+</span></span>                  | <span data-ttu-id="2ab0e-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-174">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ab0e-175">Windows Server</span></span>                | <span data-ttu-id="2ab0e-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="2ab0e-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="2ab0e-177">x64, x86</span></span>        |
| <span data-ttu-id="2ab0e-178">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="2ab0e-178">Nano Server</span></span>                   | <span data-ttu-id="2ab0e-179">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-179">Version 1803+</span></span>                  | <span data-ttu-id="2ab0e-180">x64,</span><span class="sxs-lookup"><span data-stu-id="2ab0e-180">x64,</span></span>            |

<span data-ttu-id="2ab0e-181">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="2ab0e-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="2ab0e-183">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="2ab0e-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-184">Windows 7 SP1</span></span>
- <span data-ttu-id="2ab0e-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="2ab0e-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-186">Windows 8.1</span></span>
- <span data-ttu-id="2ab0e-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="2ab0e-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="2ab0e-189">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-189">Install the following:</span></span>

- <span data-ttu-id="2ab0e-190">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="2ab0e-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="2ab0e-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="2ab0e-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="2ab0e-192">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="2ab0e-193">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="2ab0e-194">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="2ab0e-195">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="2ab0e-195">\- or -</span></span>
>
> <span data-ttu-id="2ab0e-196">라이브러리 *hostfxr.dll*을 찾았으나 *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="2ab0e-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="2ab0e-198">.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="2ab0e-199">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="2ab0e-200">.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-201">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-202">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-202">OS</span></span>                             | <span data-ttu-id="2ab0e-203">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-203">Version</span></span>               | <span data-ttu-id="2ab0e-204">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="2ab0e-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="2ab0e-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="2ab0e-206">6, 7, 8</span></span>               | <span data-ttu-id="2ab0e-207">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-207">x64</span></span> |
| <span data-ttu-id="2ab0e-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-208">CentOS</span></span>                         | <span data-ttu-id="2ab0e-209">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-209">7+</span></span>                    | <span data-ttu-id="2ab0e-210">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-210">x64</span></span> |
| <span data-ttu-id="2ab0e-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-211">Oracle Linux</span></span>                   | <span data-ttu-id="2ab0e-212">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-212">7+</span></span>                    | <span data-ttu-id="2ab0e-213">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-213">x64</span></span> |
| <span data-ttu-id="2ab0e-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="2ab0e-214">Fedora</span></span>                         | <span data-ttu-id="2ab0e-215">29+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-215">29+</span></span>                   | <span data-ttu-id="2ab0e-216">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-216">x64</span></span> |
| <span data-ttu-id="2ab0e-217">Debian</span><span class="sxs-lookup"><span data-stu-id="2ab0e-217">Debian</span></span>                         | <span data-ttu-id="2ab0e-218">9+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-218">9+</span></span>                    | <span data-ttu-id="2ab0e-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="2ab0e-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-220">Ubuntu</span></span>                         | <span data-ttu-id="2ab0e-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-221">16.04+</span></span>                | <span data-ttu-id="2ab0e-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="2ab0e-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="2ab0e-223">Linux Mint</span></span>                     | <span data-ttu-id="2ab0e-224">18+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-224">18+</span></span>                   | <span data-ttu-id="2ab0e-225">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-225">x64</span></span> |
| <span data-ttu-id="2ab0e-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2ab0e-226">openSUSE</span></span>                       | <span data-ttu-id="2ab0e-227">15+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-227">15+</span></span>                   | <span data-ttu-id="2ab0e-228">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-228">x64</span></span> |
| <span data-ttu-id="2ab0e-229">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="2ab0e-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-230">12 SP2+</span></span>               | <span data-ttu-id="2ab0e-231">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-231">x64</span></span> |
| <span data-ttu-id="2ab0e-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-232">Alpine Linux</span></span>                   | <span data-ttu-id="2ab0e-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-233">3.10+</span></span>                 | <span data-ttu-id="2ab0e-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-234">x64, ARM64</span></span> |

<span data-ttu-id="2ab0e-235">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="2ab0e-236">ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ab0e-237">ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="2ab0e-238">몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="2ab0e-239">예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="2ab0e-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2ab0e-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="2ab0e-241">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="2ab0e-242">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="2ab0e-243">.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-244">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-245">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-245">OS</span></span>                             | <span data-ttu-id="2ab0e-246">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-246">Version</span></span>               | <span data-ttu-id="2ab0e-247">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="2ab0e-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="2ab0e-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="2ab0e-249">6, 7, 8</span></span>               | <span data-ttu-id="2ab0e-250">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-250">x64</span></span> |
| <span data-ttu-id="2ab0e-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-251">CentOS</span></span>                         | <span data-ttu-id="2ab0e-252">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-252">7+</span></span>                    | <span data-ttu-id="2ab0e-253">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-253">x64</span></span> |
| <span data-ttu-id="2ab0e-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-254">Oracle Linux</span></span>                   | <span data-ttu-id="2ab0e-255">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-255">7+</span></span>                    | <span data-ttu-id="2ab0e-256">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-256">x64</span></span> |
| <span data-ttu-id="2ab0e-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="2ab0e-257">Fedora</span></span>                         | <span data-ttu-id="2ab0e-258">29+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-258">29+</span></span>                   | <span data-ttu-id="2ab0e-259">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-259">x64</span></span> |
| <span data-ttu-id="2ab0e-260">Debian</span><span class="sxs-lookup"><span data-stu-id="2ab0e-260">Debian</span></span>                         | <span data-ttu-id="2ab0e-261">9+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-261">9+</span></span>                    | <span data-ttu-id="2ab0e-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="2ab0e-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-263">Ubuntu</span></span>                         | <span data-ttu-id="2ab0e-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-264">16.04+</span></span>                | <span data-ttu-id="2ab0e-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="2ab0e-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="2ab0e-266">Linux Mint</span></span>                     | <span data-ttu-id="2ab0e-267">18+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-267">18+</span></span>                   | <span data-ttu-id="2ab0e-268">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-268">x64</span></span> |
| <span data-ttu-id="2ab0e-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2ab0e-269">openSUSE</span></span>                       | <span data-ttu-id="2ab0e-270">15+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-270">15+</span></span>                   | <span data-ttu-id="2ab0e-271">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-271">x64</span></span> |
| <span data-ttu-id="2ab0e-272">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="2ab0e-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-273">12 SP2+</span></span>               | <span data-ttu-id="2ab0e-274">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-274">x64</span></span> |
| <span data-ttu-id="2ab0e-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-275">Alpine Linux</span></span>                   | <span data-ttu-id="2ab0e-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-276">3.8+</span></span>                  | <span data-ttu-id="2ab0e-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-277">x64, ARM64</span></span> |

<span data-ttu-id="2ab0e-278">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="2ab0e-279">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="2ab0e-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="2ab0e-281">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="2ab0e-282">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="2ab0e-283">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-284">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-285">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-285">OS</span></span>                             |  <span data-ttu-id="2ab0e-286">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-286">Version</span></span>                |  <span data-ttu-id="2ab0e-287">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="2ab0e-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="2ab0e-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="2ab0e-289">6, 7</span></span>                   | <span data-ttu-id="2ab0e-290">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-290">x64</span></span> |
| <span data-ttu-id="2ab0e-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-291">CentOS</span></span>                         |  <span data-ttu-id="2ab0e-292">7</span><span class="sxs-lookup"><span data-stu-id="2ab0e-292">7</span></span>                      | <span data-ttu-id="2ab0e-293">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-293">x64</span></span> |
| <span data-ttu-id="2ab0e-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-294">Oracle Linux</span></span>                   |  <span data-ttu-id="2ab0e-295">7</span><span class="sxs-lookup"><span data-stu-id="2ab0e-295">7</span></span>                      | <span data-ttu-id="2ab0e-296">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-296">x64</span></span> |
| <span data-ttu-id="2ab0e-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="2ab0e-297">Fedora</span></span>                         |  <span data-ttu-id="2ab0e-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="2ab0e-298">29, 30</span></span>                 | <span data-ttu-id="2ab0e-299">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-299">x64</span></span> |
| <span data-ttu-id="2ab0e-300">Debian</span><span class="sxs-lookup"><span data-stu-id="2ab0e-300">Debian</span></span>                         |  <span data-ttu-id="2ab0e-301">9</span><span class="sxs-lookup"><span data-stu-id="2ab0e-301">9</span></span>                      | <span data-ttu-id="2ab0e-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-302">x64, ARM32</span></span> |
| <span data-ttu-id="2ab0e-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-303">Ubuntu</span></span>                         |  <span data-ttu-id="2ab0e-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="2ab0e-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="2ab0e-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-305">x64, ARM32</span></span> |
| <span data-ttu-id="2ab0e-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="2ab0e-306">Linux Mint</span></span>                     |  <span data-ttu-id="2ab0e-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="2ab0e-307">17, 18</span></span>                 | <span data-ttu-id="2ab0e-308">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-308">x64</span></span> |
| <span data-ttu-id="2ab0e-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2ab0e-309">openSUSE</span></span>                       |  <span data-ttu-id="2ab0e-310">15+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-310">15+</span></span>                    | <span data-ttu-id="2ab0e-311">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-311">x64</span></span> |
| <span data-ttu-id="2ab0e-312">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="2ab0e-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-313">12 SP2+</span></span>                | <span data-ttu-id="2ab0e-314">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-314">x64</span></span> |
| <span data-ttu-id="2ab0e-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-315">Alpine Linux</span></span>                   |  <span data-ttu-id="2ab0e-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-316">3.8+</span></span>                   | <span data-ttu-id="2ab0e-317">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-317">x64</span></span> |

<span data-ttu-id="2ab0e-318">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="2ab0e-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="2ab0e-320">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="2ab0e-321">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="2ab0e-322">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-323">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-324">OS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-324">OS</span></span>                             |  <span data-ttu-id="2ab0e-325">버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-325">Version</span></span>                |  <span data-ttu-id="2ab0e-326">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="2ab0e-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="2ab0e-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="2ab0e-328">6, 7, 8</span></span>                | <span data-ttu-id="2ab0e-329">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-329">x64</span></span> |
| <span data-ttu-id="2ab0e-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-330">CentOS</span></span>                         |  <span data-ttu-id="2ab0e-331">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-331">7+</span></span>                     | <span data-ttu-id="2ab0e-332">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-332">x64</span></span> |
| <span data-ttu-id="2ab0e-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-333">Oracle Linux</span></span>                   |  <span data-ttu-id="2ab0e-334">7+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-334">7+</span></span>                     | <span data-ttu-id="2ab0e-335">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-335">x64</span></span> |
| <span data-ttu-id="2ab0e-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="2ab0e-336">Fedora</span></span>                         |  <span data-ttu-id="2ab0e-337">29+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-337">29+</span></span>                    | <span data-ttu-id="2ab0e-338">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-338">x64</span></span> |
| <span data-ttu-id="2ab0e-339">Debian</span><span class="sxs-lookup"><span data-stu-id="2ab0e-339">Debian</span></span>                         |  <span data-ttu-id="2ab0e-340">9</span><span class="sxs-lookup"><span data-stu-id="2ab0e-340">9</span></span>                      | <span data-ttu-id="2ab0e-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-341">x64, ARM32</span></span> |
| <span data-ttu-id="2ab0e-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-342">Ubuntu</span></span>                         |  <span data-ttu-id="2ab0e-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="2ab0e-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="2ab0e-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="2ab0e-344">x64, ARM32</span></span> |
| <span data-ttu-id="2ab0e-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="2ab0e-345">Linux Mint</span></span>                     |  <span data-ttu-id="2ab0e-346">17+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-346">17+</span></span>                    | <span data-ttu-id="2ab0e-347">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-347">x64</span></span> |
| <span data-ttu-id="2ab0e-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2ab0e-348">openSUSE</span></span>                       |  <span data-ttu-id="2ab0e-349">15+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-349">15+</span></span>                    | <span data-ttu-id="2ab0e-350">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-350">x64</span></span> |
| <span data-ttu-id="2ab0e-351">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="2ab0e-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-352">12 SP2+</span></span>                | <span data-ttu-id="2ab0e-353">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-353">x64</span></span> |
| <span data-ttu-id="2ab0e-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="2ab0e-354">Alpine Linux</span></span>                   |  <span data-ttu-id="2ab0e-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="2ab0e-355">3.8+</span></span>                   | <span data-ttu-id="2ab0e-356">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-356">x64</span></span> |

<span data-ttu-id="2ab0e-357">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="2ab0e-358">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="2ab0e-358">Linux distribution dependencies</span></span>

<span data-ttu-id="2ab0e-359">Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ab0e-360">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="2ab0e-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-361">Ubuntu</span></span>

<span data-ttu-id="2ab0e-362">Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="2ab0e-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="2ab0e-363">liblttng-ust0</span></span>
- <span data-ttu-id="2ab0e-364">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="2ab0e-365">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="2ab0e-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="2ab0e-366">libssl1.0.0</span></span>
- <span data-ttu-id="2ab0e-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="2ab0e-367">libkrb5-3</span></span>
- <span data-ttu-id="2ab0e-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="2ab0e-368">zlib1g</span></span>
- <span data-ttu-id="2ab0e-369">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="2ab0e-370">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="2ab0e-371">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="2ab0e-372">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="2ab0e-373">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="2ab0e-374">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="2ab0e-375">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="2ab0e-376">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="2ab0e-377">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="2ab0e-378">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="2ab0e-378">CentOS and Fedora</span></span>

<span data-ttu-id="2ab0e-379">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="2ab0e-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="2ab0e-380">lttng-ust</span></span>
- <span data-ttu-id="2ab0e-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="2ab0e-381">libcurl</span></span>
- <span data-ttu-id="2ab0e-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="2ab0e-382">openssl-libs</span></span>
- <span data-ttu-id="2ab0e-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="2ab0e-383">krb5-libs</span></span>
- <span data-ttu-id="2ab0e-384">libicu</span><span class="sxs-lookup"><span data-stu-id="2ab0e-384">libicu</span></span>
- <span data-ttu-id="2ab0e-385">zlib</span><span class="sxs-lookup"><span data-stu-id="2ab0e-385">zlib</span></span>

<span data-ttu-id="2ab0e-386">Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="2ab0e-387">.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="2ab0e-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="2ab0e-388">libunwind</span></span>
- <span data-ttu-id="2ab0e-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="2ab0e-389">libuuid</span></span>

<span data-ttu-id="2ab0e-390">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="2ab0e-391">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="2ab0e-392">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="2ab0e-393">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="2ab0e-394">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="2ab0e-395">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="2ab0e-396">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="2ab0e-397">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="2ab0e-398">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="2ab0e-398">.NET Core Version</span></span> | <span data-ttu-id="2ab0e-399">macOS</span><span class="sxs-lookup"><span data-stu-id="2ab0e-399">macOS</span></span>                 | <span data-ttu-id="2ab0e-400">아키텍처</span><span class="sxs-lookup"><span data-stu-id="2ab0e-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="2ab0e-401">3.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-401">3.1</span></span>               | <span data-ttu-id="2ab0e-402">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="2ab0e-403">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-403">x64</span></span> | [<span data-ttu-id="2ab0e-404">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2ab0e-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="2ab0e-405">3.0</span><span class="sxs-lookup"><span data-stu-id="2ab0e-405">3.0</span></span>               | <span data-ttu-id="2ab0e-406">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="2ab0e-407">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-407">x64</span></span> | [<span data-ttu-id="2ab0e-408">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2ab0e-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="2ab0e-409">2.2</span><span class="sxs-lookup"><span data-stu-id="2ab0e-409">2.2</span></span>               | <span data-ttu-id="2ab0e-410">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="2ab0e-411">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-411">x64</span></span> | [<span data-ttu-id="2ab0e-412">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2ab0e-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="2ab0e-413">2.1</span><span class="sxs-lookup"><span data-stu-id="2ab0e-413">2.1</span></span>               | <span data-ttu-id="2ab0e-414">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="2ab0e-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="2ab0e-415">X64</span><span class="sxs-lookup"><span data-stu-id="2ab0e-415">x64</span></span> | [<span data-ttu-id="2ab0e-416">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2ab0e-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="2ab0e-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="2ab0e-417">libgdiplus</span></span>

<span data-ttu-id="2ab0e-418">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="2ab0e-419">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="2ab0e-420">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="2ab0e-421">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2ab0e-421">Next steps</span></span>

- <span data-ttu-id="2ab0e-422">앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="2ab0e-423">다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
