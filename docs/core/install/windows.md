---
title: Windows에 .NET 설치
description: .NET을 설치할 수 있는 Windows 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 55746b29b579a6d3aacb7d11c5604dc601440ab5
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506294"
---
# <a name="install-net-on-windows"></a><span data-ttu-id="a7869-103">Windows에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-103">Install .NET on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

<span data-ttu-id="a7869-107">이 문서에서는 Windows에 .NET을 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-107">In this article, you'll learn how to install .NET on Windows.</span></span> <span data-ttu-id="a7869-108">.NET은 런타임과 SDK로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="a7869-109">런타임은 .NET 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="a7869-110">SDK는 .NET 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="a7869-111">.NET 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="a7869-112">.NET의 최신 버전은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="a7869-113">.NET 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-113">Download .NET</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="a7869-114">지원되는 릴리스</span><span class="sxs-lookup"><span data-stu-id="a7869-114">Supported releases</span></span>

<span data-ttu-id="a7869-115">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Windows 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-115">The following table is a list of currently supported .NET releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="a7869-116">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Windows 버전이 지원 종료에 도달](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-116">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="a7869-117">Windows 10 버전의 서비스 종료 날짜는 버전별로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="a7869-118">**Home**, **Pro**, **Pro Education** 및 **Pro for Workstations** 버전만 다음 표에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="a7869-119">특정 세부 정보는 [Windows 수명 주기 팩트 시트](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

> [!TIP]
> <span data-ttu-id="a7869-120">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-120">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-121">운영 체제</span><span class="sxs-lookup"><span data-stu-id="a7869-121">Operating System</span></span>            | <span data-ttu-id="a7869-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a7869-122">.NET Core 2.1</span></span> | <span data-ttu-id="a7869-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a7869-123">.NET Core 3.1</span></span> | <span data-ttu-id="a7869-124">.NET 5</span><span class="sxs-lookup"><span data-stu-id="a7869-124">.NET 5</span></span> |
|-----------------------------|---------------|---------------|--------|
| <span data-ttu-id="a7869-125">Windows 10/Windows Server, 버전 20H2</span><span class="sxs-lookup"><span data-stu-id="a7869-125">Windows 10 / Windows Server, Version 20H2</span></span>    | <span data-ttu-id="a7869-126">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-126">✔️</span></span>           | <span data-ttu-id="a7869-127">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-127">✔️</span></span>            | <span data-ttu-id="a7869-128">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-128">✔️</span></span>    |
| <span data-ttu-id="a7869-129">Windows 10/Windows Server, 버전 2004</span><span class="sxs-lookup"><span data-stu-id="a7869-129">Windows 10 / Windows Server, Version 2004</span></span>    | <span data-ttu-id="a7869-130">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-130">✔️</span></span>           | <span data-ttu-id="a7869-131">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-131">✔️</span></span>            | <span data-ttu-id="a7869-132">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-132">✔️</span></span>    |
| <span data-ttu-id="a7869-133">Windows 10/Windows Server, 버전 1909</span><span class="sxs-lookup"><span data-stu-id="a7869-133">Windows 10 / Windows Server, Version 1909</span></span>    | <span data-ttu-id="a7869-134">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-134">✔️</span></span>           | <span data-ttu-id="a7869-135">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-135">✔️</span></span>            | <span data-ttu-id="a7869-136">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-136">✔️</span></span>    |
| <span data-ttu-id="a7869-137">Windows 10/Windows Server, 버전 1903</span><span class="sxs-lookup"><span data-stu-id="a7869-137">Windows 10 / Windows Server, Version 1903</span></span>    | <span data-ttu-id="a7869-138">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-138">✔️</span></span>           | <span data-ttu-id="a7869-139">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-139">✔️</span></span>            | <span data-ttu-id="a7869-140">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-140">✔️</span></span>    |
| <span data-ttu-id="a7869-141">Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="a7869-141">Windows 10, Version 1809</span></span>    | <span data-ttu-id="a7869-142">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-142">✔️</span></span>           | <span data-ttu-id="a7869-143">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-143">✔️</span></span>            | <span data-ttu-id="a7869-144">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-144">✔️</span></span>    |
| <span data-ttu-id="a7869-145"> Windows 10, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="a7869-145">Windows 10, Version 1803</span></span>    | <span data-ttu-id="a7869-146">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-146">✔️</span></span>           | <span data-ttu-id="a7869-147">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-147">✔️</span></span>            | <span data-ttu-id="a7869-148">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-148">✔️</span></span>    |
| <span data-ttu-id="a7869-149"> Windows 10, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="a7869-149">Windows 10, Version 1709</span></span>    | <span data-ttu-id="a7869-150">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-150">✔️</span></span>           | <span data-ttu-id="a7869-151">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-151">✔️</span></span>            | <span data-ttu-id="a7869-152">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-152">✔️</span></span>    |
| <span data-ttu-id="a7869-153"> Windows 10, 버전 1607</span><span class="sxs-lookup"><span data-stu-id="a7869-153">Windows 10, Version 1607</span></span>    | <span data-ttu-id="a7869-154">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-154">✔️</span></span>           | <span data-ttu-id="a7869-155">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-155">✔️</span></span>            | <span data-ttu-id="a7869-156">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-156">✔️</span></span>    |
| <span data-ttu-id="a7869-157">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-157">Windows 8.1</span></span>                 | <span data-ttu-id="a7869-158">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-158">✔️</span></span>           | <span data-ttu-id="a7869-159">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-159">✔️</span></span>            | <span data-ttu-id="a7869-160">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-160">✔️</span></span>    |
| <span data-ttu-id="a7869-161">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="a7869-161">Windows 7 SP1 [ESU][esu]</span></span>    | <span data-ttu-id="a7869-162">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-162">✔️</span></span>           | <span data-ttu-id="a7869-163">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-163">✔️</span></span>            | <span data-ttu-id="a7869-164">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-164">✔️</span></span>    |
| <span data-ttu-id="a7869-165">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a7869-165">Windows Server 2019</span></span><br><span data-ttu-id="a7869-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a7869-166">Windows Server 2016</span></span><br><span data-ttu-id="a7869-167">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a7869-167">Windows Server 2012 R2</span></span><br>      | <span data-ttu-id="a7869-168">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-168">✔️</span></span>           | <span data-ttu-id="a7869-169">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-169">✔️</span></span>            | <span data-ttu-id="a7869-170">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-170">✔️</span></span>    |
| <span data-ttu-id="a7869-171">Windows Server Core 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a7869-171">Windows Server Core 2012 R2</span></span> | <span data-ttu-id="a7869-172">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-172">✔️</span></span>           | <span data-ttu-id="a7869-173">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-173">✔️</span></span>            | <span data-ttu-id="a7869-174">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-174">✔️</span></span>    |
| <span data-ttu-id="a7869-175">Nano Server, 버전 1809+</span><span class="sxs-lookup"><span data-stu-id="a7869-175">Nano Server, Version 1809+</span></span>  | <span data-ttu-id="a7869-176">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-176">✔️</span></span>           | <span data-ttu-id="a7869-177">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-177">✔️</span></span>            | <span data-ttu-id="a7869-178">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-178">✔️</span></span>    |
| <span data-ttu-id="a7869-179">Nano Server, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="a7869-179">Nano Server, Version 1803</span></span>   | <span data-ttu-id="a7869-180">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-180">✔️</span></span>           | <span data-ttu-id="a7869-181">✔️</span><span class="sxs-lookup"><span data-stu-id="a7869-181">✔️</span></span>            | ❌    |

## <a name="unsupported-releases"></a><span data-ttu-id="a7869-182">지원되지 않는 릴리스</span><span class="sxs-lookup"><span data-stu-id="a7869-182">Unsupported releases</span></span>

<span data-ttu-id="a7869-183">다음 .NET 버전은 ❌ 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-183">The following versions of .NET are ❌ no longer supported:</span></span>

- <span data-ttu-id="a7869-184">3.0</span><span class="sxs-lookup"><span data-stu-id="a7869-184">3.0</span></span>
- <span data-ttu-id="a7869-185">2.2</span><span class="sxs-lookup"><span data-stu-id="a7869-185">2.2</span></span>
- <span data-ttu-id="a7869-186">2.0</span><span class="sxs-lookup"><span data-stu-id="a7869-186">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="a7869-187">런타임 정보</span><span class="sxs-lookup"><span data-stu-id="a7869-187">Runtime information</span></span>

<span data-ttu-id="a7869-188">런타임은 .NET으로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-188">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="a7869-189">앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-189">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="a7869-190">앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-190">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="a7869-191">Windows에 설치할 수 있는 세 가지 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-191">There are three different runtimes you can install on Windows:</span></span>

- <span data-ttu-id="a7869-192">‘ASP.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="a7869-192">*ASP.NET Core runtime*</span></span>\
  <span data-ttu-id="a7869-193">ASP.NET Core 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-193">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="a7869-194">.NET 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-194">Includes the .NET runtime.</span></span>

- <span data-ttu-id="a7869-195">‘데스크톱 런타임’</span><span class="sxs-lookup"><span data-stu-id="a7869-195">*Desktop runtime*</span></span>\
  <span data-ttu-id="a7869-196">Windows용 .NET WPF 및 Windows Forms 데스크톱 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-196">Runs .NET WPF and Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="a7869-197">.NET 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-197">Includes the .NET runtime.</span></span>

- <span data-ttu-id="a7869-198">‘.NET 런타임’</span><span class="sxs-lookup"><span data-stu-id="a7869-198">*.NET runtime*</span></span>\
  <span data-ttu-id="a7869-199">이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-199">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="a7869-200">.NET 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’과 ‘데스크톱 런타임’을 모두 설치하는 것이 좋습니다. </span><span class="sxs-lookup"><span data-stu-id="a7869-200">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="a7869-201">.NET 런타임 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-201">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="a7869-202">SDK 정보</span><span class="sxs-lookup"><span data-stu-id="a7869-202">SDK information</span></span>

<span data-ttu-id="a7869-203">SDK는 .NET 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-203">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="a7869-204">SDK를 설치하면 ASP.NET Core, 데스크톱 및 .NET Core의 세 가지 [런타임](#runtime-information)이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-204">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="a7869-205">종속성</span><span class="sxs-lookup"><span data-stu-id="a7869-205">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[<span data-ttu-id="a7869-206">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a7869-206">.NET 5.0</span></span>](#tab/net50)

<span data-ttu-id="a7869-207">.NET 5.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-207">The following Windows versions are supported with .NET 5.0:</span></span>

> [!NOTE]
> <span data-ttu-id="a7869-208">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-208">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-209">OS</span><span class="sxs-lookup"><span data-stu-id="a7869-209">OS</span></span>                  | <span data-ttu-id="a7869-210">버전</span><span class="sxs-lookup"><span data-stu-id="a7869-210">Version</span></span>       | <span data-ttu-id="a7869-211">아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7869-211">Architectures</span></span>   |
|---------------------|---------------|-----------------|
| <span data-ttu-id="a7869-212">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-212">Windows 10 Client</span></span>   | <span data-ttu-id="a7869-213">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="a7869-213">Version 1607+</span></span> | <span data-ttu-id="a7869-214">x64, x86, ARM64</span><span class="sxs-lookup"><span data-stu-id="a7869-214">x64, x86, ARM64</span></span> |
| <span data-ttu-id="a7869-215">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-215">Windows Client</span></span>      | <span data-ttu-id="a7869-216">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-216">7 SP1+, 8.1</span></span>   | <span data-ttu-id="a7869-217">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-217">x64, x86</span></span>        |
| <span data-ttu-id="a7869-218">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a7869-218">Windows Server</span></span>      | <span data-ttu-id="a7869-219">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a7869-219">2012 R2+</span></span>      | <span data-ttu-id="a7869-220">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-220">x64, x86</span></span>        |
| <span data-ttu-id="a7869-221">Windows Server Core</span><span class="sxs-lookup"><span data-stu-id="a7869-221">Windows Server Core</span></span> | <span data-ttu-id="a7869-222">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a7869-222">2012 R2+</span></span>      | <span data-ttu-id="a7869-223">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-223">x64, x86</span></span>        |
| <span data-ttu-id="a7869-224">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="a7869-224">Nano Server</span></span>         | <span data-ttu-id="a7869-225">버전 1809+</span><span class="sxs-lookup"><span data-stu-id="a7869-225">Version 1809+</span></span> | <span data-ttu-id="a7869-226">X64</span><span class="sxs-lookup"><span data-stu-id="a7869-226">x64</span></span>             |

<span data-ttu-id="a7869-227">.NET 5.0이 지원되는 운영 체제, 배포, 수명 주기 정책에 대한 자세한 내용은 [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md)(.NET 5.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-227">For more information about .NET 5.0 supported operating systems, distributions, and lifecycle policy, see [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).</span></span>

# <a name="net-core-31"></a>[<span data-ttu-id="a7869-228">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a7869-228">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="a7869-229">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-229">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a7869-230">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-230">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-231">OS</span><span class="sxs-lookup"><span data-stu-id="a7869-231">OS</span></span>                            | <span data-ttu-id="a7869-232">버전</span><span class="sxs-lookup"><span data-stu-id="a7869-232">Version</span></span>                        | <span data-ttu-id="a7869-233">아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7869-233">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a7869-234">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-234">Windows Client</span></span>                | <span data-ttu-id="a7869-235">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-235">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a7869-236">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-236">x64, x86</span></span>        |
| <span data-ttu-id="a7869-237">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-237">Windows 10 Client</span></span>             | <span data-ttu-id="a7869-238">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="a7869-238">Version 1607+</span></span>                  | <span data-ttu-id="a7869-239">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-239">x64, x86</span></span>        |
| <span data-ttu-id="a7869-240">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a7869-240">Windows Server</span></span>                | <span data-ttu-id="a7869-241">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a7869-241">2012 R2+</span></span>                       | <span data-ttu-id="a7869-242">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-242">x64, x86</span></span>        |
| <span data-ttu-id="a7869-243">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="a7869-243">Nano Server</span></span>                   | <span data-ttu-id="a7869-244">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="a7869-244">Version 1803+</span></span>                  | <span data-ttu-id="a7869-245">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a7869-245">x64, ARM32</span></span>      |

<span data-ttu-id="a7869-246">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-246">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="a7869-247">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a7869-247">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a7869-248">*.NET Core 3.0은 현재 ❌ 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="a7869-248">*.NET Core 3.0 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a7869-249">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-249">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="a7869-250">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-251">OS</span><span class="sxs-lookup"><span data-stu-id="a7869-251">OS</span></span>                            | <span data-ttu-id="a7869-252">버전</span><span class="sxs-lookup"><span data-stu-id="a7869-252">Version</span></span>                        | <span data-ttu-id="a7869-253">아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7869-253">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a7869-254">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-254">Windows Client</span></span>                | <span data-ttu-id="a7869-255">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-255">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a7869-256">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-256">x64, x86</span></span>        |
| <span data-ttu-id="a7869-257">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-257">Windows 10 Client</span></span>             | <span data-ttu-id="a7869-258">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="a7869-258">Version 1607+</span></span>                  | <span data-ttu-id="a7869-259">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-259">x64, x86</span></span>        |
| <span data-ttu-id="a7869-260">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a7869-260">Windows Server</span></span>                | <span data-ttu-id="a7869-261">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a7869-261">2012 R2+</span></span>                       | <span data-ttu-id="a7869-262">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-262">x64, x86</span></span>        |
| <span data-ttu-id="a7869-263">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="a7869-263">Nano Server</span></span>                   | <span data-ttu-id="a7869-264">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="a7869-264">Version 1803+</span></span>                  | <span data-ttu-id="a7869-265">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a7869-265">x64, ARM32</span></span>      |

<span data-ttu-id="a7869-266">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-266">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="a7869-267">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a7869-267">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a7869-268">*.NET Core 2.2는 현재 ❌ 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="a7869-268">*.NET Core 2.2 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a7869-269">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-269">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="a7869-270">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-270">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-271">OS</span><span class="sxs-lookup"><span data-stu-id="a7869-271">OS</span></span>                            | <span data-ttu-id="a7869-272">버전</span><span class="sxs-lookup"><span data-stu-id="a7869-272">Version</span></span>                        | <span data-ttu-id="a7869-273">아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7869-273">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a7869-274">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-274">Windows Client</span></span>                | <span data-ttu-id="a7869-275">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-275">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a7869-276">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-276">x64, x86</span></span>        |
| <span data-ttu-id="a7869-277">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-277">Windows 10 Client</span></span>             | <span data-ttu-id="a7869-278">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="a7869-278">Version 1607+</span></span>                  | <span data-ttu-id="a7869-279">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-279">x64, x86</span></span>        |
| <span data-ttu-id="a7869-280">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a7869-280">Windows Server</span></span>                | <span data-ttu-id="a7869-281">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="a7869-281">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a7869-282">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-282">x64, x86</span></span>        |
| <span data-ttu-id="a7869-283">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="a7869-283">Nano Server</span></span>                   | <span data-ttu-id="a7869-284">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="a7869-284">Version 1803+</span></span>                   | <span data-ttu-id="a7869-285">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a7869-285">x64, ARM32</span></span>      |

<span data-ttu-id="a7869-286">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-286">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a7869-287">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a7869-287">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a7869-288">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-288">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a7869-289">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-289">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a7869-290">OS</span><span class="sxs-lookup"><span data-stu-id="a7869-290">OS</span></span>                            | <span data-ttu-id="a7869-291">버전</span><span class="sxs-lookup"><span data-stu-id="a7869-291">Version</span></span>                        | <span data-ttu-id="a7869-292">아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7869-292">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a7869-293">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-293">Windows Client</span></span>                | <span data-ttu-id="a7869-294">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-294">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a7869-295">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-295">x64, x86</span></span>        |
| <span data-ttu-id="a7869-296">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7869-296">Windows 10 Client</span></span>             | <span data-ttu-id="a7869-297">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="a7869-297">Version 1607+</span></span>                  | <span data-ttu-id="a7869-298">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-298">x64, x86</span></span>        |
| <span data-ttu-id="a7869-299">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a7869-299">Windows Server</span></span>                | <span data-ttu-id="a7869-300">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="a7869-300">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a7869-301">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a7869-301">x64, x86</span></span>        |
| <span data-ttu-id="a7869-302">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="a7869-302">Nano Server</span></span>                   | <span data-ttu-id="a7869-303">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="a7869-303">Version 1803+</span></span>                  | <span data-ttu-id="a7869-304">x64,</span><span class="sxs-lookup"><span data-stu-id="a7869-304">x64,</span></span>            |

<span data-ttu-id="a7869-305">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-305">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

### <a name="offline-install-for-windows-7"></a><span data-ttu-id="a7869-306">Windows 7에 대한 오프라인 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-306">Offline install for Windows 7</span></span>

<span data-ttu-id="a7869-307">Windows 7에서 .NET Core 2.1의 오프라인 설치를 수행하려면 먼저 최신 [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm)이 대상 머신에 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-307">When doing an offline install for .NET Core 2.1 on Windows 7, you'll first need to make sure that the latest [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) has been installed on the target machine.</span></span>

<span data-ttu-id="a7869-308">_certmgr.exe_ 도구는 인증서 설치를 자동화할 수 있으며 Visual Studio 또는 Windows SDK에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-308">The _certmgr.exe_ tool can automate installing a certificate and is obtained from Visual Studio or the Windows SDK.</span></span> <span data-ttu-id="a7869-309">다음 명령은 .NET Core 2.1 설치 관리자를 실행하기 전에 인증서를 설치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-309">The following command is used to install the certificate before running the .NET Core 2.1 installer:</span></span>

```console
certmgr.exe /add MicRooCerAut2011_2011_03_22.crt /s /r localMachine root
```

<span data-ttu-id="a7869-310">[아래 Windows 7](#additional-deps)에 필요한 종속성을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-310">Be sure to review the dependencies required for [Windows 7 below](#additional-deps).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="a7869-311">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a7869-311">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="a7869-312">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 종속성이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-312">More dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

| <span data-ttu-id="a7869-313">운영 체제</span><span class="sxs-lookup"><span data-stu-id="a7869-313">Operating System</span></span>         | <span data-ttu-id="a7869-314">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7869-314">Prerequisites</span></span>                                                                    |
|--------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="a7869-315">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="a7869-315">Windows 7 SP1 [ESU][esu]</span></span> | <span data-ttu-id="a7869-316">- Microsoft Visual C++ 2015-2019 재배포 가능 [64비트][vcc64] / [32비트][vcc32]</span><span class="sxs-lookup"><span data-stu-id="a7869-316">- Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> <br> <span data-ttu-id="a7869-317">- KB3063858 [64비트][kb64] / [32비트][kb32]</span><span class="sxs-lookup"><span data-stu-id="a7869-317">- KB3063858 [64-bit][kb64] / [32-bit][kb32]</span></span> <br> <span data-ttu-id="a7869-318">- [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm)(.NET Core 2.1 오프라인 설치 관리자만 해당)</span><span class="sxs-lookup"><span data-stu-id="a7869-318">- [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) (.NET Core 2.1 offline installer only)</span></span> |
| <span data-ttu-id="a7869-319">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="a7869-319">Windows Vista SP 2</span></span>       | <span data-ttu-id="a7869-320">Microsoft Visual C++ 2015-2019 재배포 가능 [64비트][vcc64] / [32비트][vcc32]</span><span class="sxs-lookup"><span data-stu-id="a7869-320">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="a7869-321">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a7869-321">Windows 8.1</span></span>              | <span data-ttu-id="a7869-322">Microsoft Visual C++ 2015-2019 재배포 가능 [64비트][vcc64] / [32비트][vcc32]</span><span class="sxs-lookup"><span data-stu-id="a7869-322">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="a7869-323">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a7869-323">Windows Server 2008 R2</span></span>   | <span data-ttu-id="a7869-324">Microsoft Visual C++ 2015-2019 재배포 가능 [64비트][vcc64] / [32비트][vcc32]</span><span class="sxs-lookup"><span data-stu-id="a7869-324">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="a7869-325">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a7869-325">Windows Server 2012 R2</span></span>   | <span data-ttu-id="a7869-326">Microsoft Visual C++ 2015-2019 재배포 가능 [64비트][vcc64] / [32비트][vcc32]</span><span class="sxs-lookup"><span data-stu-id="a7869-326">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |

<span data-ttu-id="a7869-327">다음 dll 중 하나와 관련된 오류를 수신하는 경우에도 이전 요구 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-327">The previous requirements are also required if you receive an error related to either of the following dlls:</span></span>

- <span data-ttu-id="a7869-328">*api-ms-win-crt-runtime-l1-1-0.dll*</span><span class="sxs-lookup"><span data-stu-id="a7869-328">*api-ms-win-crt-runtime-l1-1-0.dll*</span></span>
- <span data-ttu-id="a7869-329">*api-ms-win-cor-timezone-l1-1-0.dll*</span><span class="sxs-lookup"><span data-stu-id="a7869-329">*api-ms-win-cor-timezone-l1-1-0.dll*</span></span>
- <span data-ttu-id="a7869-330">*hostfxr.dll*</span><span class="sxs-lookup"><span data-stu-id="a7869-330">*hostfxr.dll*</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="a7869-331">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-331">Install with PowerShell automation</span></span>

<span data-ttu-id="a7869-332">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 CI 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-332">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a7869-333">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-333">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a7869-334">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-334">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="a7869-335">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-335">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="a7869-336">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-336">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="a7869-337">포함하지 않을 경우 스크립트가 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-337">Otherwise, the script installs the SDK.</span></span>

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

<span data-ttu-id="a7869-338">`-Runtime` 스위치를 생략하여 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-338">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="a7869-339">이 예에서는 `-Channel` 스위치를 `Current`로 설정하여 최신 지원 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-339">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="a7869-340">Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-340">Install with Visual Studio</span></span>

<span data-ttu-id="a7869-341">Visual Studio를 사용하여 .NET 앱을 개발하는 경우 다음 표에서 대상 .NET SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-341">If you're using Visual Studio to develop .NET apps, the following table describes the minimum required version of Visual Studio based on the target .NET SDK version.</span></span>

| <span data-ttu-id="a7869-342">.NET SDK 버전</span><span class="sxs-lookup"><span data-stu-id="a7869-342">.NET SDK version</span></span>      | <span data-ttu-id="a7869-343">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="a7869-343">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="a7869-344">5.0</span><span class="sxs-lookup"><span data-stu-id="a7869-344">5.0</span></span>                   | <span data-ttu-id="a7869-345">Visual Studio 2019 버전 16.8 이상</span><span class="sxs-lookup"><span data-stu-id="a7869-345">Visual Studio 2019 version 16.8 or higher.</span></span> |
| <span data-ttu-id="a7869-346">3.1</span><span class="sxs-lookup"><span data-stu-id="a7869-346">3.1</span></span>                   | <span data-ttu-id="a7869-347">Visual Studio 2019 버전 16.4 이상</span><span class="sxs-lookup"><span data-stu-id="a7869-347">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="a7869-348">3.0</span><span class="sxs-lookup"><span data-stu-id="a7869-348">3.0</span></span>                   | <span data-ttu-id="a7869-349">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="a7869-349">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="a7869-350">2.2</span><span class="sxs-lookup"><span data-stu-id="a7869-350">2.2</span></span>                   | <span data-ttu-id="a7869-351">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="a7869-351">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="a7869-352">2.1</span><span class="sxs-lookup"><span data-stu-id="a7869-352">2.1</span></span>                   | <span data-ttu-id="a7869-353">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="a7869-353">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="a7869-354">Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-354">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="a7869-355">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-355">Open Visual Studio.</span></span>
01. <span data-ttu-id="a7869-356">**도움말** > **Microsoft Visual Studio 정보** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-356">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="a7869-357">**정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-357">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="a7869-358">Visual Studio가 최신 .NET SDK 및 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-358">Visual Studio can install the latest .NET SDK and runtime.</span></span>

> [!div class="button"]
> <span data-ttu-id="a7869-359">[Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-359">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="a7869-360">워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="a7869-360">Select a workload</span></span>

<span data-ttu-id="a7869-361">Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-361">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="a7869-362">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="a7869-362">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="a7869-363">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="a7869-363">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="a7869-364">**웹 및 클라우드** 섹션의 **Azure 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="a7869-364">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="a7869-365">**데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="a7869-365">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="a7869-366">[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a7869-366">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="a7869-367">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-367">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="a7869-368">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-368">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="a7869-369">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-369">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="a7869-370">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-370">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="a7869-371">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="a7869-371">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="a7869-372">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="a7869-372">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="a7869-373">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="a7869-373">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="a7869-374">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="a7869-374">Windows Installer</span></span>

<span data-ttu-id="a7869-375">Windows Installer 실행 파일은 .NET [다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core)에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-375">The [download page](https://dotnet.microsoft.com/download/dotnet-core) for .NET provides Windows Installer executables.</span></span>

<span data-ttu-id="a7869-376">Windows Installer를 사용하여 .NET을 설치하는 경우 `DOTNETHOME_X64` 및 `DOTNETHOME_X86` 매개 변수를 설정하여 설치 경로를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-376">When you use the Windows installers to install .NET, you can customize the installation path by setting the `DOTNETHOME_X64` and `DOTNETHOME_X86` parameters:</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe DOTNETHOME_X64="F:\dotnet\x64" DOTNETHOME_X86="F:\dotnet\x86"
```

<span data-ttu-id="a7869-377">프로덕션 환경에서처럼 .NET을 자동으로 설치하거나 연속 통합을 지원하려면 다음 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-377">If you want to install .NET silently, such as in a production environment or to support continuous integration, use the following switches:</span></span>

- `/install`\
<span data-ttu-id="a7869-378">.NET을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-378">Installs .NET.</span></span>

- `/quiet`\
<span data-ttu-id="a7869-379">UI와 프롬프트가 표시되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-379">Prevents any UI and prompts from displaying.</span></span>

- `norestart`\
<span data-ttu-id="a7869-380">다시 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-380">Suppresses any attempts to restart.</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe /install /quiet /norestart
```

<span data-ttu-id="a7869-381">자세한 내용은 [표준 설치 관리자 명령줄 옵션](/windows/win32/msi/standard-installer-command-line-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-381">For more information, see [Standard Installer Command-Line Options](/windows/win32/msi/standard-installer-command-line-options).</span></span>

> [!TIP]
> <span data-ttu-id="a7869-382">설치 관리자는 성공 시 종료 코드 0을 반환하고 다시 시작이 필요함을 나타내기 위해 종료 코드 3010을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-382">The installer returns an exit code of 0 for success and an exit code of 3010 to indicate that a restart is required.</span></span> <span data-ttu-id="a7869-383">다른 모든 값은 일반적으로 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-383">Any other value is generally an error code.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="a7869-384">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="a7869-384">Download and manually install</span></span>

<span data-ttu-id="a7869-385">.NET용 Windows 설치 관리자 대신 SDK나 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-385">As an alternative to the Windows installers for .NET, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="a7869-386">수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-386">Manual install is usually done as part of continuous integration testing.</span></span> <span data-ttu-id="a7869-387">개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-387">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="a7869-388">.NET SDK와 .NET 런타임 모두 다운로드한 후 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-388">Both .NET SDK and .NET Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="a7869-389">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-389">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a7869-390">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-390">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- [<span data-ttu-id="a7869-391">.NET 5.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-391">.NET 5.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- [<span data-ttu-id="a7869-392">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-392">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="a7869-393">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-393">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [<span data-ttu-id="a7869-394">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="a7869-394">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="a7869-395">.NET을 추출해서 넣을 디렉터리(예: `%USERPROFILE%\dotnet`)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-395">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="a7869-396">그런 다음, 다운로드한 zip 파일을 이 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-396">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="a7869-397">기본적으로 이런 방식으로 설치된 .NET은 .NET CLI 명령과 앱에서 사용되지 않으므로 사용하도록 명시적으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-397">By default, .NET CLI commands and apps won't use .NET installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="a7869-398">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-398">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="a7869-399">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-399">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="a7869-400">`DOTNET_MULTILEVEL_LOOKUP`을 `0`으로 설정하면 .NET에서는 전역적으로 설치된 .NET 버전을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-400">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET ignores any globally installed .NET version.</span></span> <span data-ttu-id="a7869-401">.NET에서 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 고려하도록 하려면 이러한 환경 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-401">Remove that environment setting to let .NET consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="a7869-402">기본값은 일반적으로 `C:\Program Files\dotnet`입니다. 이 경로는 설치 관리자가 .NET을 설치하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-402">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET.</span></span>

## <a name="docker"></a><span data-ttu-id="a7869-403">Docker</span><span class="sxs-lookup"><span data-stu-id="a7869-403">Docker</span></span>

<span data-ttu-id="a7869-404">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-404">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="a7869-405">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-405">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="a7869-406">.NET은 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-406">.NET can run in a Docker container.</span></span> <span data-ttu-id="a7869-407">공식 .NET Docker 이미지는 MCR(Microsoft Container Registry)에 게시되며 [Microsoft .NET Docker Hub 리포지토리](https://hub.docker.com/_/microsoft-dotnet)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-407">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet).</span></span> <span data-ttu-id="a7869-408">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-408">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="a7869-409">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-409">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="a7869-410">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-aspnet)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7869-410">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="a7869-411">Docker 컨테이너에서 .NET 사용에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7869-411">For more information about using .NET in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a7869-412">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a7869-412">Next steps</span></span>

- <span data-ttu-id="a7869-413">[.NET이 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="a7869-413">[How to check if .NET is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="a7869-414">[자습서: Hello World 자습서](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="a7869-414">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="a7869-415">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="a7869-415">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="a7869-416">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="a7869-416">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[esu]: /troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq
[vcc64]: https://aka.ms/vs/16/release/vc_redist.x64.exe
[vcc32]: https://aka.ms/vs/16/release/vc_redist.x86.exe
[kb64]: https://www.microsoft.com/download/details.aspx?id=47442
[kb32]: https://www.microsoft.com/download/details.aspx?id=47409
