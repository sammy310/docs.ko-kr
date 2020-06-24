---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 06/01/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 81f6ab436428d71f71d9fd0f560bd2b0512a519b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590762"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="9959c-103">.NET Core 종속성 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9959c-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="9959c-104">이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="9959c-105">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="9959c-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="9959c-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9959c-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="9959c-107">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-108">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-109">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-109">OS</span></span>                            | <span data-ttu-id="9959c-110">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-110">Version</span></span>                        | <span data-ttu-id="9959c-111">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9959c-112">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-112">Windows Client</span></span>                | <span data-ttu-id="9959c-113">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9959c-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9959c-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-114">x64, x86</span></span>        |
| <span data-ttu-id="9959c-115">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-115">Windows 10 Client</span></span>             | <span data-ttu-id="9959c-116">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9959c-116">Version 1607+</span></span>                  | <span data-ttu-id="9959c-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-117">x64, x86</span></span>        |
| <span data-ttu-id="9959c-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9959c-118">Windows Server</span></span>                | <span data-ttu-id="9959c-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="9959c-119">2012 R2+</span></span>                       | <span data-ttu-id="9959c-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-120">x64, x86</span></span>        |
| <span data-ttu-id="9959c-121">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9959c-121">Nano Server</span></span>                   | <span data-ttu-id="9959c-122">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9959c-122">Version 1803+</span></span>                  | <span data-ttu-id="9959c-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-123">x64, ARM32</span></span>      |

<span data-ttu-id="9959c-124">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="9959c-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9959c-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="9959c-126">*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="9959c-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="9959c-127">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-128">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-129">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-129">OS</span></span>                            | <span data-ttu-id="9959c-130">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-130">Version</span></span>                        | <span data-ttu-id="9959c-131">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9959c-132">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-132">Windows Client</span></span>                | <span data-ttu-id="9959c-133">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9959c-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9959c-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-134">x64, x86</span></span>        |
| <span data-ttu-id="9959c-135">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-135">Windows 10 Client</span></span>             | <span data-ttu-id="9959c-136">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9959c-136">Version 1607+</span></span>                  | <span data-ttu-id="9959c-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-137">x64, x86</span></span>        |
| <span data-ttu-id="9959c-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9959c-138">Windows Server</span></span>                | <span data-ttu-id="9959c-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="9959c-139">2012 R2+</span></span>                       | <span data-ttu-id="9959c-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-140">x64, x86</span></span>        |
| <span data-ttu-id="9959c-141">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9959c-141">Nano Server</span></span>                   | <span data-ttu-id="9959c-142">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9959c-142">Version 1803+</span></span>                  | <span data-ttu-id="9959c-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-143">x64, ARM32</span></span>      |

<span data-ttu-id="9959c-144">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="9959c-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9959c-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9959c-146">*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="9959c-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="9959c-147">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-148">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-149">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-149">OS</span></span>                            | <span data-ttu-id="9959c-150">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-150">Version</span></span>                        | <span data-ttu-id="9959c-151">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9959c-152">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-152">Windows Client</span></span>                | <span data-ttu-id="9959c-153">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9959c-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9959c-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-154">x64, x86</span></span>        |
| <span data-ttu-id="9959c-155">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-155">Windows 10 Client</span></span>             | <span data-ttu-id="9959c-156">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9959c-156">Version 1607+</span></span>                  | <span data-ttu-id="9959c-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-157">x64, x86</span></span>        |
| <span data-ttu-id="9959c-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9959c-158">Windows Server</span></span>                | <span data-ttu-id="9959c-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="9959c-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="9959c-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-160">x64, x86</span></span>        |
| <span data-ttu-id="9959c-161">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9959c-161">Nano Server</span></span>                   | <span data-ttu-id="9959c-162">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9959c-162">Version 1803+</span></span>                   | <span data-ttu-id="9959c-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-163">x64, ARM32</span></span>      |

<span data-ttu-id="9959c-164">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="9959c-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9959c-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9959c-166">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-167">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-168">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-168">OS</span></span>                            | <span data-ttu-id="9959c-169">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-169">Version</span></span>                        | <span data-ttu-id="9959c-170">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="9959c-171">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-171">Windows Client</span></span>                | <span data-ttu-id="9959c-172">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="9959c-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="9959c-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-173">x64, x86</span></span>        |
| <span data-ttu-id="9959c-174">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9959c-174">Windows 10 Client</span></span>             | <span data-ttu-id="9959c-175">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="9959c-175">Version 1607+</span></span>                  | <span data-ttu-id="9959c-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-176">x64, x86</span></span>        |
| <span data-ttu-id="9959c-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9959c-177">Windows Server</span></span>                | <span data-ttu-id="9959c-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="9959c-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="9959c-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="9959c-179">x64, x86</span></span>        |
| <span data-ttu-id="9959c-180">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="9959c-180">Nano Server</span></span>                   | <span data-ttu-id="9959c-181">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="9959c-181">Version 1803+</span></span>                  | <span data-ttu-id="9959c-182">x64,</span><span class="sxs-lookup"><span data-stu-id="9959c-182">x64,</span></span>            |

<span data-ttu-id="9959c-183">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="9959c-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9959c-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="9959c-185">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="9959c-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="9959c-186">Windows 7 SP1</span></span>
- <span data-ttu-id="9959c-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="9959c-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="9959c-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9959c-188">Windows 8.1</span></span>
- <span data-ttu-id="9959c-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9959c-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="9959c-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9959c-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="9959c-191">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-191">Install the following:</span></span>

- <span data-ttu-id="9959c-192">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="9959c-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="9959c-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="9959c-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="9959c-194">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="9959c-195">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="9959c-196">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="9959c-197">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="9959c-197">\- or -</span></span>
>
> <span data-ttu-id="9959c-198">컴퓨터에 *api-ms-win-cor-timezone-l1-1-0.dll*이 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="9959c-199">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="9959c-200">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="9959c-200">\- or -</span></span>
>
> <span data-ttu-id="9959c-201">라이브러리 *hostfxr.dll*을 찾았으나, *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="9959c-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9959c-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="9959c-203">.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="9959c-204">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9959c-205">.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-206">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-207">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-207">OS</span></span>                             | <span data-ttu-id="9959c-208">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-208">Version</span></span>               | <span data-ttu-id="9959c-209">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="9959c-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="9959c-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9959c-211">6, 7, 8</span></span>               | <span data-ttu-id="9959c-212">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-212">x64</span></span> |
| <span data-ttu-id="9959c-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="9959c-213">CentOS</span></span>                         | <span data-ttu-id="9959c-214">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-214">7+</span></span>                    | <span data-ttu-id="9959c-215">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-215">x64</span></span> |
| <span data-ttu-id="9959c-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-216">Oracle Linux</span></span>                   | <span data-ttu-id="9959c-217">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-217">7+</span></span>                    | <span data-ttu-id="9959c-218">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-218">x64</span></span> |
| <span data-ttu-id="9959c-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="9959c-219">Fedora</span></span>                         | <span data-ttu-id="9959c-220">30+</span><span class="sxs-lookup"><span data-stu-id="9959c-220">30+</span></span>                   | <span data-ttu-id="9959c-221">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-221">x64</span></span> |
| <span data-ttu-id="9959c-222">Debian</span><span class="sxs-lookup"><span data-stu-id="9959c-222">Debian</span></span>                         | <span data-ttu-id="9959c-223">9+</span><span class="sxs-lookup"><span data-stu-id="9959c-223">9+</span></span>                    | <span data-ttu-id="9959c-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9959c-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9959c-225">Ubuntu</span></span>                         | <span data-ttu-id="9959c-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="9959c-226">16.04+</span></span>                | <span data-ttu-id="9959c-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9959c-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9959c-228">Linux Mint</span></span>                     | <span data-ttu-id="9959c-229">18+</span><span class="sxs-lookup"><span data-stu-id="9959c-229">18+</span></span>                   | <span data-ttu-id="9959c-230">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-230">x64</span></span> |
| <span data-ttu-id="9959c-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9959c-231">openSUSE</span></span>                       | <span data-ttu-id="9959c-232">15+</span><span class="sxs-lookup"><span data-stu-id="9959c-232">15+</span></span>                   | <span data-ttu-id="9959c-233">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-233">x64</span></span> |
| <span data-ttu-id="9959c-234">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9959c-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="9959c-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9959c-235">12 SP2+</span></span>               | <span data-ttu-id="9959c-236">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-236">x64</span></span> |
| <span data-ttu-id="9959c-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-237">Alpine Linux</span></span>                   | <span data-ttu-id="9959c-238">3.10+</span><span class="sxs-lookup"><span data-stu-id="9959c-238">3.10+</span></span>                 | <span data-ttu-id="9959c-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-239">x64, ARM64</span></span> |

<span data-ttu-id="9959c-240">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="9959c-241">ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9959c-242">ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="9959c-243">몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="9959c-244">예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="9959c-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9959c-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="9959c-246">*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="9959c-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="9959c-247">.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="9959c-248">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9959c-249">.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-250">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-251">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-251">OS</span></span>                             | <span data-ttu-id="9959c-252">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-252">Version</span></span>               | <span data-ttu-id="9959c-253">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="9959c-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="9959c-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9959c-255">6, 7, 8</span></span>               | <span data-ttu-id="9959c-256">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-256">x64</span></span> |
| <span data-ttu-id="9959c-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="9959c-257">CentOS</span></span>                         | <span data-ttu-id="9959c-258">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-258">7+</span></span>                    | <span data-ttu-id="9959c-259">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-259">x64</span></span> |
| <span data-ttu-id="9959c-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-260">Oracle Linux</span></span>                   | <span data-ttu-id="9959c-261">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-261">7+</span></span>                    | <span data-ttu-id="9959c-262">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-262">x64</span></span> |
| <span data-ttu-id="9959c-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="9959c-263">Fedora</span></span>                         | <span data-ttu-id="9959c-264">29+</span><span class="sxs-lookup"><span data-stu-id="9959c-264">29+</span></span>                   | <span data-ttu-id="9959c-265">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-265">x64</span></span> |
| <span data-ttu-id="9959c-266">Debian</span><span class="sxs-lookup"><span data-stu-id="9959c-266">Debian</span></span>                         | <span data-ttu-id="9959c-267">9+</span><span class="sxs-lookup"><span data-stu-id="9959c-267">9+</span></span>                    | <span data-ttu-id="9959c-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9959c-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9959c-269">Ubuntu</span></span>                         | <span data-ttu-id="9959c-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="9959c-270">16.04+</span></span>                | <span data-ttu-id="9959c-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="9959c-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9959c-272">Linux Mint</span></span>                     | <span data-ttu-id="9959c-273">18+</span><span class="sxs-lookup"><span data-stu-id="9959c-273">18+</span></span>                   | <span data-ttu-id="9959c-274">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-274">x64</span></span> |
| <span data-ttu-id="9959c-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9959c-275">openSUSE</span></span>                       | <span data-ttu-id="9959c-276">15+</span><span class="sxs-lookup"><span data-stu-id="9959c-276">15+</span></span>                   | <span data-ttu-id="9959c-277">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-277">x64</span></span> |
| <span data-ttu-id="9959c-278">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9959c-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="9959c-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9959c-279">12 SP2+</span></span>               | <span data-ttu-id="9959c-280">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-280">x64</span></span> |
| <span data-ttu-id="9959c-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-281">Alpine Linux</span></span>                   | <span data-ttu-id="9959c-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="9959c-282">3.8+</span></span>                  | <span data-ttu-id="9959c-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="9959c-283">x64, ARM64</span></span> |

<span data-ttu-id="9959c-284">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="9959c-285">ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="9959c-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9959c-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9959c-287">*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="9959c-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="9959c-288">.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="9959c-289">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9959c-290">.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-291">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-292">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-292">OS</span></span>                             |  <span data-ttu-id="9959c-293">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-293">Version</span></span>                |  <span data-ttu-id="9959c-294">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="9959c-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="9959c-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="9959c-296">6, 7</span></span>                   | <span data-ttu-id="9959c-297">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-297">x64</span></span> |
| <span data-ttu-id="9959c-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="9959c-298">CentOS</span></span>                         |  <span data-ttu-id="9959c-299">7</span><span class="sxs-lookup"><span data-stu-id="9959c-299">7</span></span>                      | <span data-ttu-id="9959c-300">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-300">x64</span></span> |
| <span data-ttu-id="9959c-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-301">Oracle Linux</span></span>                   |  <span data-ttu-id="9959c-302">7</span><span class="sxs-lookup"><span data-stu-id="9959c-302">7</span></span>                      | <span data-ttu-id="9959c-303">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-303">x64</span></span> |
| <span data-ttu-id="9959c-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="9959c-304">Fedora</span></span>                         |  <span data-ttu-id="9959c-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="9959c-305">29, 30</span></span>                 | <span data-ttu-id="9959c-306">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-306">x64</span></span> |
| <span data-ttu-id="9959c-307">Debian</span><span class="sxs-lookup"><span data-stu-id="9959c-307">Debian</span></span>                         |  <span data-ttu-id="9959c-308">9</span><span class="sxs-lookup"><span data-stu-id="9959c-308">9</span></span>                      | <span data-ttu-id="9959c-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-309">x64, ARM32</span></span> |
| <span data-ttu-id="9959c-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9959c-310">Ubuntu</span></span>                         |  <span data-ttu-id="9959c-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="9959c-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="9959c-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-312">x64, ARM32</span></span> |
| <span data-ttu-id="9959c-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9959c-313">Linux Mint</span></span>                     |  <span data-ttu-id="9959c-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="9959c-314">17, 18</span></span>                 | <span data-ttu-id="9959c-315">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-315">x64</span></span> |
| <span data-ttu-id="9959c-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9959c-316">openSUSE</span></span>                       |  <span data-ttu-id="9959c-317">15+</span><span class="sxs-lookup"><span data-stu-id="9959c-317">15+</span></span>                    | <span data-ttu-id="9959c-318">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-318">x64</span></span> |
| <span data-ttu-id="9959c-319">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9959c-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="9959c-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9959c-320">12 SP2+</span></span>                | <span data-ttu-id="9959c-321">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-321">x64</span></span> |
| <span data-ttu-id="9959c-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-322">Alpine Linux</span></span>                   |  <span data-ttu-id="9959c-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="9959c-323">3.8+</span></span>                   | <span data-ttu-id="9959c-324">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-324">x64</span></span> |

<span data-ttu-id="9959c-325">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="9959c-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9959c-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9959c-327">.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="9959c-328">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="9959c-329">.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-330">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-331">OS</span><span class="sxs-lookup"><span data-stu-id="9959c-331">OS</span></span>                             |  <span data-ttu-id="9959c-332">버전</span><span class="sxs-lookup"><span data-stu-id="9959c-332">Version</span></span>                |  <span data-ttu-id="9959c-333">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="9959c-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="9959c-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="9959c-335">6, 7, 8</span></span>                | <span data-ttu-id="9959c-336">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-336">x64</span></span> |
| <span data-ttu-id="9959c-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="9959c-337">CentOS</span></span>                         |  <span data-ttu-id="9959c-338">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-338">7+</span></span>                     | <span data-ttu-id="9959c-339">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-339">x64</span></span> |
| <span data-ttu-id="9959c-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-340">Oracle Linux</span></span>                   |  <span data-ttu-id="9959c-341">7+</span><span class="sxs-lookup"><span data-stu-id="9959c-341">7+</span></span>                     | <span data-ttu-id="9959c-342">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-342">x64</span></span> |
| <span data-ttu-id="9959c-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="9959c-343">Fedora</span></span>                         |  <span data-ttu-id="9959c-344">30+</span><span class="sxs-lookup"><span data-stu-id="9959c-344">30+</span></span>                    | <span data-ttu-id="9959c-345">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-345">x64</span></span> |
| <span data-ttu-id="9959c-346">Debian</span><span class="sxs-lookup"><span data-stu-id="9959c-346">Debian</span></span>                         |  <span data-ttu-id="9959c-347">9</span><span class="sxs-lookup"><span data-stu-id="9959c-347">9</span></span>                      | <span data-ttu-id="9959c-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-348">x64, ARM32</span></span> |
| <span data-ttu-id="9959c-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9959c-349">Ubuntu</span></span>                         |  <span data-ttu-id="9959c-350">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="9959c-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="9959c-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="9959c-351">x64, ARM32</span></span> |
| <span data-ttu-id="9959c-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="9959c-352">Linux Mint</span></span>                     |  <span data-ttu-id="9959c-353">17+</span><span class="sxs-lookup"><span data-stu-id="9959c-353">17+</span></span>                    | <span data-ttu-id="9959c-354">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-354">x64</span></span> |
| <span data-ttu-id="9959c-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9959c-355">openSUSE</span></span>                       |  <span data-ttu-id="9959c-356">15+</span><span class="sxs-lookup"><span data-stu-id="9959c-356">15+</span></span>                    | <span data-ttu-id="9959c-357">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-357">x64</span></span> |
| <span data-ttu-id="9959c-358">SLES(SUSE Enterprise Linux)</span><span class="sxs-lookup"><span data-stu-id="9959c-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="9959c-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="9959c-359">12 SP2+</span></span>                | <span data-ttu-id="9959c-360">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-360">x64</span></span> |
| <span data-ttu-id="9959c-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="9959c-361">Alpine Linux</span></span>                   |  <span data-ttu-id="9959c-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="9959c-362">3.8+</span></span>                   | <span data-ttu-id="9959c-363">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-363">x64</span></span> |

<span data-ttu-id="9959c-364">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="9959c-365">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="9959c-365">Linux distribution dependencies</span></span>

<span data-ttu-id="9959c-366">Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9959c-367">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="9959c-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9959c-368">Ubuntu</span></span>

<span data-ttu-id="9959c-369">Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="9959c-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="9959c-370">liblttng-ust0</span></span>
- <span data-ttu-id="9959c-371">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="9959c-372">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="9959c-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="9959c-373">libssl1.0.0</span></span>
- <span data-ttu-id="9959c-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="9959c-374">libkrb5-3</span></span>
- <span data-ttu-id="9959c-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="9959c-375">zlib1g</span></span>
- <span data-ttu-id="9959c-376">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="9959c-377">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="9959c-378">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="9959c-379">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="9959c-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="9959c-380">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="9959c-381">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="9959c-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="9959c-382">대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="9959c-383">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="9959c-384">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="9959c-385">CentOS 및 Fedora</span><span class="sxs-lookup"><span data-stu-id="9959c-385">CentOS and Fedora</span></span>

<span data-ttu-id="9959c-386">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="9959c-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="9959c-387">lttng-ust</span></span>
- <span data-ttu-id="9959c-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="9959c-388">libcurl</span></span>
- <span data-ttu-id="9959c-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="9959c-389">openssl-libs</span></span>
- <span data-ttu-id="9959c-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="9959c-390">krb5-libs</span></span>
- <span data-ttu-id="9959c-391">libicu</span><span class="sxs-lookup"><span data-stu-id="9959c-391">libicu</span></span>
- <span data-ttu-id="9959c-392">zlib</span><span class="sxs-lookup"><span data-stu-id="9959c-392">zlib</span></span>

<span data-ttu-id="9959c-393">Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="9959c-394">.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="9959c-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="9959c-395">libunwind</span></span>
- <span data-ttu-id="9959c-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="9959c-396">libuuid</span></span>

<span data-ttu-id="9959c-397">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="9959c-398">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="9959c-399">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="9959c-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="9959c-400">CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="9959c-401">시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="9959c-402">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="9959c-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="9959c-403">Alpine</span></span>

<span data-ttu-id="9959c-404">Alpine 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="9959c-405">icu-libs(세계화를 사용하지 않도록 설정한 경우에는 필요하지 않음)</span><span class="sxs-lookup"><span data-stu-id="9959c-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="9959c-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="9959c-406">krb5-libs</span></span>
- <span data-ttu-id="9959c-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="9959c-407">libcurl</span></span>
- <span data-ttu-id="9959c-408">libintl</span><span class="sxs-lookup"><span data-stu-id="9959c-408">libintl</span></span>
- <span data-ttu-id="9959c-409">libssl1.1(Alpine 3.9 이상) 또는 libssl1.0(이전 버전)</span><span class="sxs-lookup"><span data-stu-id="9959c-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="9959c-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="9959c-410">libstdc++</span></span>
- <span data-ttu-id="9959c-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="9959c-411">lttng-ust</span></span>
- <span data-ttu-id="9959c-412">numactl(선택 사항. NUMA를 사용하는 디바이스에만 유용함)</span><span class="sxs-lookup"><span data-stu-id="9959c-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="9959c-413">zlib</span><span class="sxs-lookup"><span data-stu-id="9959c-413">zlib</span></span>

<span data-ttu-id="9959c-414">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="9959c-415">libgdiplus(에지/테스트 리포지토리에서만 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="9959c-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="9959c-416">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="9959c-417">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="9959c-418">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="9959c-418">.NET Core Version</span></span> | <span data-ttu-id="9959c-419">macOS</span><span class="sxs-lookup"><span data-stu-id="9959c-419">macOS</span></span>                 | <span data-ttu-id="9959c-420">아키텍처</span><span class="sxs-lookup"><span data-stu-id="9959c-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="9959c-421">3.1</span><span class="sxs-lookup"><span data-stu-id="9959c-421">3.1</span></span>               | <span data-ttu-id="9959c-422">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="9959c-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="9959c-423">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-423">x64</span></span> | [<span data-ttu-id="9959c-424">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9959c-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="9959c-425">3.0</span><span class="sxs-lookup"><span data-stu-id="9959c-425">3.0</span></span>               | <span data-ttu-id="9959c-426">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="9959c-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="9959c-427">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-427">x64</span></span> | [<span data-ttu-id="9959c-428">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9959c-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="9959c-429">2.2</span><span class="sxs-lookup"><span data-stu-id="9959c-429">2.2</span></span>               | <span data-ttu-id="9959c-430">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="9959c-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="9959c-431">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-431">x64</span></span> | [<span data-ttu-id="9959c-432">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9959c-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="9959c-433">2.1</span><span class="sxs-lookup"><span data-stu-id="9959c-433">2.1</span></span>               | <span data-ttu-id="9959c-434">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="9959c-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="9959c-435">X64</span><span class="sxs-lookup"><span data-stu-id="9959c-435">x64</span></span> | [<span data-ttu-id="9959c-436">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9959c-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="9959c-437">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="9959c-438">이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="9959c-439">.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="9959c-440">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="9959c-441">공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="9959c-443">공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="9959c-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="9959c-444">libgdiplus</span></span>

<span data-ttu-id="9959c-445">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="9959c-446">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="9959c-447">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9959c-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="9959c-448">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9959c-448">Next steps</span></span>

- <span data-ttu-id="9959c-449">앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="9959c-450">다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="9959c-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
