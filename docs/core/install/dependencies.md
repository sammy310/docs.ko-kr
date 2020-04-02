---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546564"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="d4677-103">.NET Core 종속성 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4677-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="d4677-104">이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="d4677-105">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="d4677-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="d4677-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d4677-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="d4677-107">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-108">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-109">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-109">OS</span></span>                            | <span data-ttu-id="d4677-110">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-110">Version</span></span>                        | <span data-ttu-id="d4677-111">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d4677-112">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-112">Windows Client</span></span>                | <span data-ttu-id="d4677-113">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="d4677-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d4677-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-114">x64, x86</span></span>        |
| <span data-ttu-id="d4677-115">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-115">Windows 10 Client</span></span>             | <span data-ttu-id="d4677-116">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="d4677-116">Version 1607+</span></span>                  | <span data-ttu-id="d4677-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-117">x64, x86</span></span>        |
| <span data-ttu-id="d4677-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d4677-118">Windows Server</span></span>                | <span data-ttu-id="d4677-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="d4677-119">2012 R2+</span></span>                       | <span data-ttu-id="d4677-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-120">x64, x86</span></span>        |
| <span data-ttu-id="d4677-121">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="d4677-121">Nano Server</span></span>                   | <span data-ttu-id="d4677-122">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="d4677-122">Version 1803+</span></span>                  | <span data-ttu-id="d4677-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-123">x64, ARM32</span></span>      |

<span data-ttu-id="d4677-124">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="d4677-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4677-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d4677-126">*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="d4677-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d4677-127">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-128">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-129">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-129">OS</span></span>                            | <span data-ttu-id="d4677-130">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-130">Version</span></span>                        | <span data-ttu-id="d4677-131">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d4677-132">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-132">Windows Client</span></span>                | <span data-ttu-id="d4677-133">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="d4677-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d4677-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-134">x64, x86</span></span>        |
| <span data-ttu-id="d4677-135">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-135">Windows 10 Client</span></span>             | <span data-ttu-id="d4677-136">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="d4677-136">Version 1607+</span></span>                  | <span data-ttu-id="d4677-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-137">x64, x86</span></span>        |
| <span data-ttu-id="d4677-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d4677-138">Windows Server</span></span>                | <span data-ttu-id="d4677-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="d4677-139">2012 R2+</span></span>                       | <span data-ttu-id="d4677-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-140">x64, x86</span></span>        |
| <span data-ttu-id="d4677-141">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="d4677-141">Nano Server</span></span>                   | <span data-ttu-id="d4677-142">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="d4677-142">Version 1803+</span></span>                  | <span data-ttu-id="d4677-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-143">x64, ARM32</span></span>      |

<span data-ttu-id="d4677-144">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="d4677-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="d4677-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="d4677-146">*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="d4677-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d4677-147">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-148">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-149">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-149">OS</span></span>                            | <span data-ttu-id="d4677-150">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-150">Version</span></span>                        | <span data-ttu-id="d4677-151">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d4677-152">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-152">Windows Client</span></span>                | <span data-ttu-id="d4677-153">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="d4677-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d4677-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-154">x64, x86</span></span>        |
| <span data-ttu-id="d4677-155">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-155">Windows 10 Client</span></span>             | <span data-ttu-id="d4677-156">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="d4677-156">Version 1607+</span></span>                  | <span data-ttu-id="d4677-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-157">x64, x86</span></span>        |
| <span data-ttu-id="d4677-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d4677-158">Windows Server</span></span>                | <span data-ttu-id="d4677-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="d4677-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="d4677-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-160">x64, x86</span></span>        |
| <span data-ttu-id="d4677-161">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="d4677-161">Nano Server</span></span>                   | <span data-ttu-id="d4677-162">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="d4677-162">Version 1803+</span></span>                   | <span data-ttu-id="d4677-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-163">x64, ARM32</span></span>      |

<span data-ttu-id="d4677-164">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="d4677-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d4677-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d4677-166">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-167">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-168">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-168">OS</span></span>                            | <span data-ttu-id="d4677-169">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-169">Version</span></span>                        | <span data-ttu-id="d4677-170">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d4677-171">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-171">Windows Client</span></span>                | <span data-ttu-id="d4677-172">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="d4677-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d4677-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-173">x64, x86</span></span>        |
| <span data-ttu-id="d4677-174">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d4677-174">Windows 10 Client</span></span>             | <span data-ttu-id="d4677-175">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="d4677-175">Version 1607+</span></span>                  | <span data-ttu-id="d4677-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-176">x64, x86</span></span>        |
| <span data-ttu-id="d4677-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d4677-177">Windows Server</span></span>                | <span data-ttu-id="d4677-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="d4677-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="d4677-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d4677-179">x64, x86</span></span>        |
| <span data-ttu-id="d4677-180">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="d4677-180">Nano Server</span></span>                   | <span data-ttu-id="d4677-181">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="d4677-181">Version 1803+</span></span>                  | <span data-ttu-id="d4677-182">x64,</span><span class="sxs-lookup"><span data-stu-id="d4677-182">x64,</span></span>            |

<span data-ttu-id="d4677-183">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="d4677-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d4677-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="d4677-185">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="d4677-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="d4677-186">Windows 7 SP1</span></span>
- <span data-ttu-id="d4677-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="d4677-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="d4677-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d4677-188">Windows 8.1</span></span>
- <span data-ttu-id="d4677-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d4677-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="d4677-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d4677-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="d4677-191">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-191">Install the following:</span></span>

- <span data-ttu-id="d4677-192">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="d4677-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="d4677-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="d4677-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="d4677-194">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="d4677-195">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="d4677-196">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="d4677-197">\- 또는-</span><span class="sxs-lookup"><span data-stu-id="d4677-197">\- or -</span></span>
>
> <span data-ttu-id="d4677-198">라이브러리 *hostfxr.dll*을 찾았으나 *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="d4677-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d4677-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="d4677-200">.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="d4677-201">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d4677-202">.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-203">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-204">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-204">OS</span></span>                             | <span data-ttu-id="d4677-205">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-205">Version</span></span>               | <span data-ttu-id="d4677-206">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="d4677-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="d4677-208">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="d4677-208">6, 7, 8</span></span>               | <span data-ttu-id="d4677-209">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-209">x64</span></span> |
| <span data-ttu-id="d4677-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="d4677-210">CentOS</span></span>                         | <span data-ttu-id="d4677-211">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-211">7+</span></span>                    | <span data-ttu-id="d4677-212">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-212">x64</span></span> |
| <span data-ttu-id="d4677-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-213">Oracle Linux</span></span>                   | <span data-ttu-id="d4677-214">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-214">7+</span></span>                    | <span data-ttu-id="d4677-215">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-215">x64</span></span> |
| <span data-ttu-id="d4677-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="d4677-216">Fedora</span></span>                         | <span data-ttu-id="d4677-217">30+</span><span class="sxs-lookup"><span data-stu-id="d4677-217">30+</span></span>                   | <span data-ttu-id="d4677-218">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-218">x64</span></span> |
| <span data-ttu-id="d4677-219">Debian</span><span class="sxs-lookup"><span data-stu-id="d4677-219">Debian</span></span>                         | <span data-ttu-id="d4677-220">9+</span><span class="sxs-lookup"><span data-stu-id="d4677-220">9+</span></span>                    | <span data-ttu-id="d4677-221">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d4677-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4677-222">Ubuntu</span></span>                         | <span data-ttu-id="d4677-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="d4677-223">16.04+</span></span>                | <span data-ttu-id="d4677-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d4677-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d4677-225">Linux Mint</span></span>                     | <span data-ttu-id="d4677-226">18+</span><span class="sxs-lookup"><span data-stu-id="d4677-226">18+</span></span>                   | <span data-ttu-id="d4677-227">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-227">x64</span></span> |
| <span data-ttu-id="d4677-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d4677-228">openSUSE</span></span>                       | <span data-ttu-id="d4677-229">15+</span><span class="sxs-lookup"><span data-stu-id="d4677-229">15+</span></span>                   | <span data-ttu-id="d4677-230">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-230">x64</span></span> |
| <span data-ttu-id="d4677-231">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d4677-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="d4677-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d4677-232">12 SP2+</span></span>               | <span data-ttu-id="d4677-233">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-233">x64</span></span> |
| <span data-ttu-id="d4677-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-234">Alpine Linux</span></span>                   | <span data-ttu-id="d4677-235">3.10+</span><span class="sxs-lookup"><span data-stu-id="d4677-235">3.10+</span></span>                 | <span data-ttu-id="d4677-236">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-236">x64, ARM64</span></span> |

<span data-ttu-id="d4677-237">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="d4677-238">ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4677-239">ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="d4677-240">몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="d4677-241">예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="d4677-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4677-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d4677-243">*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="d4677-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d4677-244">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="d4677-245">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d4677-246">.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-247">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-248">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-248">OS</span></span>                             | <span data-ttu-id="d4677-249">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-249">Version</span></span>               | <span data-ttu-id="d4677-250">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="d4677-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="d4677-252">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="d4677-252">6, 7, 8</span></span>               | <span data-ttu-id="d4677-253">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-253">x64</span></span> |
| <span data-ttu-id="d4677-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="d4677-254">CentOS</span></span>                         | <span data-ttu-id="d4677-255">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-255">7+</span></span>                    | <span data-ttu-id="d4677-256">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-256">x64</span></span> |
| <span data-ttu-id="d4677-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-257">Oracle Linux</span></span>                   | <span data-ttu-id="d4677-258">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-258">7+</span></span>                    | <span data-ttu-id="d4677-259">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-259">x64</span></span> |
| <span data-ttu-id="d4677-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="d4677-260">Fedora</span></span>                         | <span data-ttu-id="d4677-261">29+</span><span class="sxs-lookup"><span data-stu-id="d4677-261">29+</span></span>                   | <span data-ttu-id="d4677-262">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-262">x64</span></span> |
| <span data-ttu-id="d4677-263">Debian</span><span class="sxs-lookup"><span data-stu-id="d4677-263">Debian</span></span>                         | <span data-ttu-id="d4677-264">9+</span><span class="sxs-lookup"><span data-stu-id="d4677-264">9+</span></span>                    | <span data-ttu-id="d4677-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d4677-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4677-266">Ubuntu</span></span>                         | <span data-ttu-id="d4677-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="d4677-267">16.04+</span></span>                | <span data-ttu-id="d4677-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="d4677-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d4677-269">Linux Mint</span></span>                     | <span data-ttu-id="d4677-270">18+</span><span class="sxs-lookup"><span data-stu-id="d4677-270">18+</span></span>                   | <span data-ttu-id="d4677-271">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-271">x64</span></span> |
| <span data-ttu-id="d4677-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d4677-272">openSUSE</span></span>                       | <span data-ttu-id="d4677-273">15+</span><span class="sxs-lookup"><span data-stu-id="d4677-273">15+</span></span>                   | <span data-ttu-id="d4677-274">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-274">x64</span></span> |
| <span data-ttu-id="d4677-275">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d4677-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="d4677-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d4677-276">12 SP2+</span></span>               | <span data-ttu-id="d4677-277">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-277">x64</span></span> |
| <span data-ttu-id="d4677-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-278">Alpine Linux</span></span>                   | <span data-ttu-id="d4677-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="d4677-279">3.8+</span></span>                  | <span data-ttu-id="d4677-280">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="d4677-280">x64, ARM64</span></span> |

<span data-ttu-id="d4677-281">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="d4677-282">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="d4677-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="d4677-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="d4677-284">*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="d4677-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d4677-285">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="d4677-286">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d4677-287">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-288">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-289">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-289">OS</span></span>                             |  <span data-ttu-id="d4677-290">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-290">Version</span></span>                |  <span data-ttu-id="d4677-291">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="d4677-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="d4677-293">6, 7</span><span class="sxs-lookup"><span data-stu-id="d4677-293">6, 7</span></span>                   | <span data-ttu-id="d4677-294">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-294">x64</span></span> |
| <span data-ttu-id="d4677-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="d4677-295">CentOS</span></span>                         |  <span data-ttu-id="d4677-296">7</span><span class="sxs-lookup"><span data-stu-id="d4677-296">7</span></span>                      | <span data-ttu-id="d4677-297">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-297">x64</span></span> |
| <span data-ttu-id="d4677-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-298">Oracle Linux</span></span>                   |  <span data-ttu-id="d4677-299">7</span><span class="sxs-lookup"><span data-stu-id="d4677-299">7</span></span>                      | <span data-ttu-id="d4677-300">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-300">x64</span></span> |
| <span data-ttu-id="d4677-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="d4677-301">Fedora</span></span>                         |  <span data-ttu-id="d4677-302">29, 30</span><span class="sxs-lookup"><span data-stu-id="d4677-302">29, 30</span></span>                 | <span data-ttu-id="d4677-303">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-303">x64</span></span> |
| <span data-ttu-id="d4677-304">Debian</span><span class="sxs-lookup"><span data-stu-id="d4677-304">Debian</span></span>                         |  <span data-ttu-id="d4677-305">9</span><span class="sxs-lookup"><span data-stu-id="d4677-305">9</span></span>                      | <span data-ttu-id="d4677-306">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-306">x64, ARM32</span></span> |
| <span data-ttu-id="d4677-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4677-307">Ubuntu</span></span>                         |  <span data-ttu-id="d4677-308">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="d4677-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="d4677-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-309">x64, ARM32</span></span> |
| <span data-ttu-id="d4677-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d4677-310">Linux Mint</span></span>                     |  <span data-ttu-id="d4677-311">17, 18</span><span class="sxs-lookup"><span data-stu-id="d4677-311">17, 18</span></span>                 | <span data-ttu-id="d4677-312">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-312">x64</span></span> |
| <span data-ttu-id="d4677-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d4677-313">openSUSE</span></span>                       |  <span data-ttu-id="d4677-314">15+</span><span class="sxs-lookup"><span data-stu-id="d4677-314">15+</span></span>                    | <span data-ttu-id="d4677-315">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-315">x64</span></span> |
| <span data-ttu-id="d4677-316">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d4677-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="d4677-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d4677-317">12 SP2+</span></span>                | <span data-ttu-id="d4677-318">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-318">x64</span></span> |
| <span data-ttu-id="d4677-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-319">Alpine Linux</span></span>                   |  <span data-ttu-id="d4677-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="d4677-320">3.8+</span></span>                   | <span data-ttu-id="d4677-321">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-321">x64</span></span> |

<span data-ttu-id="d4677-322">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="d4677-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d4677-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d4677-324">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="d4677-325">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="d4677-326">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-327">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-328">OS</span><span class="sxs-lookup"><span data-stu-id="d4677-328">OS</span></span>                             |  <span data-ttu-id="d4677-329">버전</span><span class="sxs-lookup"><span data-stu-id="d4677-329">Version</span></span>                |  <span data-ttu-id="d4677-330">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="d4677-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="d4677-332">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="d4677-332">6, 7, 8</span></span>                | <span data-ttu-id="d4677-333">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-333">x64</span></span> |
| <span data-ttu-id="d4677-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="d4677-334">CentOS</span></span>                         |  <span data-ttu-id="d4677-335">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-335">7+</span></span>                     | <span data-ttu-id="d4677-336">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-336">x64</span></span> |
| <span data-ttu-id="d4677-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-337">Oracle Linux</span></span>                   |  <span data-ttu-id="d4677-338">7+</span><span class="sxs-lookup"><span data-stu-id="d4677-338">7+</span></span>                     | <span data-ttu-id="d4677-339">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-339">x64</span></span> |
| <span data-ttu-id="d4677-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="d4677-340">Fedora</span></span>                         |  <span data-ttu-id="d4677-341">30+</span><span class="sxs-lookup"><span data-stu-id="d4677-341">30+</span></span>                    | <span data-ttu-id="d4677-342">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-342">x64</span></span> |
| <span data-ttu-id="d4677-343">Debian</span><span class="sxs-lookup"><span data-stu-id="d4677-343">Debian</span></span>                         |  <span data-ttu-id="d4677-344">9</span><span class="sxs-lookup"><span data-stu-id="d4677-344">9</span></span>                      | <span data-ttu-id="d4677-345">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-345">x64, ARM32</span></span> |
| <span data-ttu-id="d4677-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4677-346">Ubuntu</span></span>                         |  <span data-ttu-id="d4677-347">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="d4677-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="d4677-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d4677-348">x64, ARM32</span></span> |
| <span data-ttu-id="d4677-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="d4677-349">Linux Mint</span></span>                     |  <span data-ttu-id="d4677-350">17+</span><span class="sxs-lookup"><span data-stu-id="d4677-350">17+</span></span>                    | <span data-ttu-id="d4677-351">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-351">x64</span></span> |
| <span data-ttu-id="d4677-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d4677-352">openSUSE</span></span>                       |  <span data-ttu-id="d4677-353">15+</span><span class="sxs-lookup"><span data-stu-id="d4677-353">15+</span></span>                    | <span data-ttu-id="d4677-354">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-354">x64</span></span> |
| <span data-ttu-id="d4677-355">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="d4677-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="d4677-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="d4677-356">12 SP2+</span></span>                | <span data-ttu-id="d4677-357">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-357">x64</span></span> |
| <span data-ttu-id="d4677-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="d4677-358">Alpine Linux</span></span>                   |  <span data-ttu-id="d4677-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="d4677-359">3.8+</span></span>                   | <span data-ttu-id="d4677-360">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-360">x64</span></span> |

<span data-ttu-id="d4677-361">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="d4677-362">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="d4677-362">Linux distribution dependencies</span></span>

<span data-ttu-id="d4677-363">Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4677-364">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="d4677-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4677-365">Ubuntu</span></span>

<span data-ttu-id="d4677-366">Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="d4677-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="d4677-367">liblttng-ust0</span></span>
- <span data-ttu-id="d4677-368">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="d4677-369">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="d4677-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="d4677-370">libssl1.0.0</span></span>
- <span data-ttu-id="d4677-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="d4677-371">libkrb5-3</span></span>
- <span data-ttu-id="d4677-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="d4677-372">zlib1g</span></span>
- <span data-ttu-id="d4677-373">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="d4677-374">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="d4677-375">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="d4677-376">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="d4677-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="d4677-377">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="d4677-378">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="d4677-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="d4677-379">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="d4677-380">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="d4677-381">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="d4677-382">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="d4677-382">CentOS and Fedora</span></span>

<span data-ttu-id="d4677-383">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="d4677-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="d4677-384">lttng-ust</span></span>
- <span data-ttu-id="d4677-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="d4677-385">libcurl</span></span>
- <span data-ttu-id="d4677-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="d4677-386">openssl-libs</span></span>
- <span data-ttu-id="d4677-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="d4677-387">krb5-libs</span></span>
- <span data-ttu-id="d4677-388">libicu</span><span class="sxs-lookup"><span data-stu-id="d4677-388">libicu</span></span>
- <span data-ttu-id="d4677-389">zlib</span><span class="sxs-lookup"><span data-stu-id="d4677-389">zlib</span></span>

<span data-ttu-id="d4677-390">Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="d4677-391">.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="d4677-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="d4677-392">libunwind</span></span>
- <span data-ttu-id="d4677-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="d4677-393">libuuid</span></span>

<span data-ttu-id="d4677-394">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="d4677-395">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="d4677-396">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="d4677-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="d4677-397">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="d4677-398">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="d4677-399">자세한 내용은 <https://www.mono-project.com/download/stable/>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="d4677-400">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="d4677-401">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d4677-402">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="d4677-402">.NET Core Version</span></span> | <span data-ttu-id="d4677-403">macOS</span><span class="sxs-lookup"><span data-stu-id="d4677-403">macOS</span></span>                 | <span data-ttu-id="d4677-404">아키텍처</span><span class="sxs-lookup"><span data-stu-id="d4677-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="d4677-405">3.1</span><span class="sxs-lookup"><span data-stu-id="d4677-405">3.1</span></span>               | <span data-ttu-id="d4677-406">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="d4677-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="d4677-407">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-407">x64</span></span> | [<span data-ttu-id="d4677-408">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d4677-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="d4677-409">3.0</span><span class="sxs-lookup"><span data-stu-id="d4677-409">3.0</span></span>               | <span data-ttu-id="d4677-410">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="d4677-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="d4677-411">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-411">x64</span></span> | [<span data-ttu-id="d4677-412">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d4677-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="d4677-413">2.2</span><span class="sxs-lookup"><span data-stu-id="d4677-413">2.2</span></span>               | <span data-ttu-id="d4677-414">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="d4677-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="d4677-415">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-415">x64</span></span> | [<span data-ttu-id="d4677-416">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d4677-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="d4677-417">2.1</span><span class="sxs-lookup"><span data-stu-id="d4677-417">2.1</span></span>               | <span data-ttu-id="d4677-418">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="d4677-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="d4677-419">x64</span><span class="sxs-lookup"><span data-stu-id="d4677-419">x64</span></span> | [<span data-ttu-id="d4677-420">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d4677-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="d4677-421">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="d4677-422">이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="d4677-423">.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="d4677-424">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="d4677-425">공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="d4677-427">공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="d4677-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="d4677-428">libgdiplus</span></span>

<span data-ttu-id="d4677-429">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="d4677-430">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="d4677-431">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d4677-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="d4677-432">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d4677-432">Next steps</span></span>

- <span data-ttu-id="d4677-433">앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="d4677-434">다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="d4677-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
