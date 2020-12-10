---
title: Windows에 .NET 설치
description: .NET을 설치할 수 있는 Windows 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 786814549724948fa69b18a05cee966e0940aaf4
ms.sourcegitcommit: c6de55556add9f92af17e0f8d1da8f356a19a03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96549347"
---
# <a name="install-net-on-windows"></a><span data-ttu-id="ba1a7-103">Windows에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="ba1a7-103">Install .NET on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

<span data-ttu-id="ba1a7-107">이 문서에서는 Windows에 .NET을 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-107">In this article, you'll learn how to install .NET on Windows.</span></span> <span data-ttu-id="ba1a7-108">.NET은 런타임과 SDK로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="ba1a7-109">런타임은 .NET 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="ba1a7-110">SDK는 .NET 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="ba1a7-111">.NET 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="ba1a7-112">.NET의 최신 버전은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="ba1a7-113">.NET 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-113">Download .NET</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="ba1a7-114">지원되는 릴리스</span><span class="sxs-lookup"><span data-stu-id="ba1a7-114">Supported releases</span></span>

<span data-ttu-id="ba1a7-115">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Windows 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-115">The following table is a list of currently supported .NET releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="ba1a7-116">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Windows 버전이 지원 종료에 도달](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-116">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="ba1a7-117">Windows 10 버전의 서비스 종료 날짜는 버전별로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="ba1a7-118">**Home**, **Pro**, **Pro Education** 및 **Pro for Workstations** 버전만 다음 표에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="ba1a7-119">특정 세부 정보는 [Windows 수명 주기 팩트 시트](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

> [!TIP]
> <span data-ttu-id="ba1a7-120">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-120">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-121">운영 체제</span><span class="sxs-lookup"><span data-stu-id="ba1a7-121">Operating System</span></span>            | <span data-ttu-id="ba1a7-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-122">.NET Core 2.1</span></span> | <span data-ttu-id="ba1a7-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-123">.NET Core 3.1</span></span> | <span data-ttu-id="ba1a7-124">.NET 5</span><span class="sxs-lookup"><span data-stu-id="ba1a7-124">.NET 5</span></span> |
|-----------------------------|---------------|---------------|--------|
| <span data-ttu-id="ba1a7-125">Windows 10, 버전 2004</span><span class="sxs-lookup"><span data-stu-id="ba1a7-125">Windows 10, Version 2004</span></span>    | <span data-ttu-id="ba1a7-126">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-126">✔️</span></span>           | <span data-ttu-id="ba1a7-127">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-127">✔️</span></span>            | <span data-ttu-id="ba1a7-128">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-128">✔️</span></span>    |
| <span data-ttu-id="ba1a7-129">Windows 10, 버전 1909</span><span class="sxs-lookup"><span data-stu-id="ba1a7-129">Windows 10, Version 1909</span></span>    | <span data-ttu-id="ba1a7-130">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-130">✔️</span></span>           | <span data-ttu-id="ba1a7-131">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-131">✔️</span></span>            | <span data-ttu-id="ba1a7-132">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-132">✔️</span></span>    |
| <span data-ttu-id="ba1a7-133">Windows 10, 버전 1903</span><span class="sxs-lookup"><span data-stu-id="ba1a7-133">Windows 10, Version 1903</span></span>    | <span data-ttu-id="ba1a7-134">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-134">✔️</span></span>           | <span data-ttu-id="ba1a7-135">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-135">✔️</span></span>            | <span data-ttu-id="ba1a7-136">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-136">✔️</span></span>    |
| <span data-ttu-id="ba1a7-137">Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="ba1a7-137">Windows 10, Version 1809</span></span>    | <span data-ttu-id="ba1a7-138">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-138">✔️</span></span>           | <span data-ttu-id="ba1a7-139">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-139">✔️</span></span>            | <span data-ttu-id="ba1a7-140">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-140">✔️</span></span>    |
| <span data-ttu-id="ba1a7-141"> Windows 10, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="ba1a7-141">Windows 10, Version 1803</span></span>    | <span data-ttu-id="ba1a7-142">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-142">✔️</span></span>           | <span data-ttu-id="ba1a7-143">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-143">✔️</span></span>            | <span data-ttu-id="ba1a7-144">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-144">✔️</span></span>    |
| <span data-ttu-id="ba1a7-145"> Windows 10, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="ba1a7-145">Windows 10, Version 1709</span></span>    | <span data-ttu-id="ba1a7-146">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-146">✔️</span></span>           | <span data-ttu-id="ba1a7-147">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-147">✔️</span></span>            | <span data-ttu-id="ba1a7-148">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-148">✔️</span></span>    |
| <span data-ttu-id="ba1a7-149"> Windows 10, 버전 1607</span><span class="sxs-lookup"><span data-stu-id="ba1a7-149">Windows 10, Version 1607</span></span>    | <span data-ttu-id="ba1a7-150">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-150">✔️</span></span>           | <span data-ttu-id="ba1a7-151">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-151">✔️</span></span>            | <span data-ttu-id="ba1a7-152">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-152">✔️</span></span>    |
| <span data-ttu-id="ba1a7-153">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-153">Windows 8.1</span></span>                 | <span data-ttu-id="ba1a7-154">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-154">✔️</span></span>           | <span data-ttu-id="ba1a7-155">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-155">✔️</span></span>            | <span data-ttu-id="ba1a7-156">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-156">✔️</span></span>    |
| <span data-ttu-id="ba1a7-157">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="ba1a7-157">Windows 7 SP1 [ESU][esu]</span></span>    | <span data-ttu-id="ba1a7-158">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-158">✔️</span></span>           | <span data-ttu-id="ba1a7-159">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-159">✔️</span></span>            | <span data-ttu-id="ba1a7-160">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-160">✔️</span></span>    |
| <span data-ttu-id="ba1a7-161"> Windows 10, 버전 1607</span><span class="sxs-lookup"><span data-stu-id="ba1a7-161">Windows 10, Version 1607</span></span>    | <span data-ttu-id="ba1a7-162">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-162">✔️</span></span>           | <span data-ttu-id="ba1a7-163">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-163">✔️</span></span>            | <span data-ttu-id="ba1a7-164">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-164">✔️</span></span>    |
| <span data-ttu-id="ba1a7-165"> Windows 10, 버전 1607</span><span class="sxs-lookup"><span data-stu-id="ba1a7-165">Windows 10, Version 1607</span></span>    | <span data-ttu-id="ba1a7-166">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-166">✔️</span></span>           | <span data-ttu-id="ba1a7-167">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-167">✔️</span></span>            | <span data-ttu-id="ba1a7-168">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-168">✔️</span></span>    |
| <span data-ttu-id="ba1a7-169">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-169">Windows Server 2012 R2</span></span>      | <span data-ttu-id="ba1a7-170">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-170">✔️</span></span>           | <span data-ttu-id="ba1a7-171">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-171">✔️</span></span>            | <span data-ttu-id="ba1a7-172">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-172">✔️</span></span>    |
| <span data-ttu-id="ba1a7-173">Windows Server Core 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-173">Windows Server Core 2012 R2</span></span> | <span data-ttu-id="ba1a7-174">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-174">✔️</span></span>           | <span data-ttu-id="ba1a7-175">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-175">✔️</span></span>            | <span data-ttu-id="ba1a7-176">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-176">✔️</span></span>    |
| <span data-ttu-id="ba1a7-177">Nano Server, 버전 1809+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-177">Nano Server, Version 1809+</span></span>  | <span data-ttu-id="ba1a7-178">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-178">✔️</span></span>           | <span data-ttu-id="ba1a7-179">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-179">✔️</span></span>            | <span data-ttu-id="ba1a7-180">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-180">✔️</span></span>    |
| <span data-ttu-id="ba1a7-181">Nano Server, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="ba1a7-181">Nano Server, Version 1803</span></span>   | <span data-ttu-id="ba1a7-182">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-182">✔️</span></span>           | <span data-ttu-id="ba1a7-183">✔️</span><span class="sxs-lookup"><span data-stu-id="ba1a7-183">✔️</span></span>            | ❌    |

## <a name="unsupported-releases"></a><span data-ttu-id="ba1a7-184">지원되지 않는 릴리스</span><span class="sxs-lookup"><span data-stu-id="ba1a7-184">Unsupported releases</span></span>

<span data-ttu-id="ba1a7-185">다음 .NET 버전은 ❌로 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-185">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="ba1a7-186">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-186">The downloads for these still remain published:</span></span>

- <span data-ttu-id="ba1a7-187">3.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-187">3.0</span></span>
- <span data-ttu-id="ba1a7-188">2.2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-188">2.2</span></span>
- <span data-ttu-id="ba1a7-189">2.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-189">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="ba1a7-190">런타임 정보</span><span class="sxs-lookup"><span data-stu-id="ba1a7-190">Runtime information</span></span>

<span data-ttu-id="ba1a7-191">런타임은 .NET으로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-191">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="ba1a7-192">앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-192">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="ba1a7-193">앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-193">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="ba1a7-194">Windows에 설치할 수 있는 세 가지 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-194">There are three different runtimes you can install on Windows:</span></span>

<span data-ttu-id="ba1a7-195">‘ASP.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="ba1a7-195">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="ba1a7-196">ASP.NET Core 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-196">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="ba1a7-197">.NET 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-197">Includes the .NET runtime.</span></span>

<span data-ttu-id="ba1a7-198">‘데스크톱 런타임’</span><span class="sxs-lookup"><span data-stu-id="ba1a7-198">*Desktop runtime*</span></span>\
<span data-ttu-id="ba1a7-199">Windows용 .NET WPF 및 Windows Forms 데스크톱 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-199">Runs .NET WPF and Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="ba1a7-200">.NET 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-200">Includes the .NET runtime.</span></span>

<span data-ttu-id="ba1a7-201">‘.NET 런타임’</span><span class="sxs-lookup"><span data-stu-id="ba1a7-201">*.NET runtime*</span></span>\
<span data-ttu-id="ba1a7-202">이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-202">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="ba1a7-203">.NET 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’과 ‘데스크톱 런타임’을 모두 설치하는 것이 좋습니다. </span><span class="sxs-lookup"><span data-stu-id="ba1a7-203">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="ba1a7-204">.NET 런타임 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-204">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="ba1a7-205">SDK 정보</span><span class="sxs-lookup"><span data-stu-id="ba1a7-205">SDK information</span></span>

<span data-ttu-id="ba1a7-206">SDK는 .NET 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-206">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="ba1a7-207">SDK를 설치하면 ASP.NET Core, 데스크톱 및 .NET Core의 세 가지 [런타임](#runtime-information)이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-207">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="ba1a7-208">종속성</span><span class="sxs-lookup"><span data-stu-id="ba1a7-208">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[<span data-ttu-id="ba1a7-209">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-209">.NET 5.0</span></span>](#tab/net50)

<span data-ttu-id="ba1a7-210">.NET 5.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-210">The following Windows versions are supported with .NET 5.0:</span></span>

> [!NOTE]
> <span data-ttu-id="ba1a7-211">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-211">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-212">OS</span><span class="sxs-lookup"><span data-stu-id="ba1a7-212">OS</span></span>                  | <span data-ttu-id="ba1a7-213">버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-213">Version</span></span>       | <span data-ttu-id="ba1a7-214">아키텍처</span><span class="sxs-lookup"><span data-stu-id="ba1a7-214">Architectures</span></span>   |
|---------------------|---------------|-----------------|
| <span data-ttu-id="ba1a7-215">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-215">Windows 10 Client</span></span>   | <span data-ttu-id="ba1a7-216">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-216">Version 1607+</span></span> | <span data-ttu-id="ba1a7-217">x64, x86, ARM64</span><span class="sxs-lookup"><span data-stu-id="ba1a7-217">x64, x86, ARM64</span></span> |
| <span data-ttu-id="ba1a7-218">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-218">Windows Client</span></span>      | <span data-ttu-id="ba1a7-219">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-219">7 SP1+, 8.1</span></span>   | <span data-ttu-id="ba1a7-220">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-220">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-221">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ba1a7-221">Windows Server</span></span>      | <span data-ttu-id="ba1a7-222">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-222">2012 R2+</span></span>      | <span data-ttu-id="ba1a7-223">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-223">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-224">Windows Server Core</span><span class="sxs-lookup"><span data-stu-id="ba1a7-224">Windows Server Core</span></span> | <span data-ttu-id="ba1a7-225">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-225">2012 R2+</span></span>      | <span data-ttu-id="ba1a7-226">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-226">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-227">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="ba1a7-227">Nano Server</span></span>         | <span data-ttu-id="ba1a7-228">버전 1809+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-228">Version 1809+</span></span> | <span data-ttu-id="ba1a7-229">X64</span><span class="sxs-lookup"><span data-stu-id="ba1a7-229">x64</span></span>             |

<span data-ttu-id="ba1a7-230">.NET 5.0이 지원되는 운영 체제, 배포, 수명 주기 정책에 대한 자세한 내용은 [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md)(.NET 5.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-230">For more information about .NET 5.0 supported operating systems, distributions, and lifecycle policy, see [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).</span></span>

# <a name="net-core-31"></a>[<span data-ttu-id="ba1a7-231">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-231">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="ba1a7-232">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-232">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="ba1a7-233">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-233">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-234">OS</span><span class="sxs-lookup"><span data-stu-id="ba1a7-234">OS</span></span>                            | <span data-ttu-id="ba1a7-235">버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-235">Version</span></span>                        | <span data-ttu-id="ba1a7-236">아키텍처</span><span class="sxs-lookup"><span data-stu-id="ba1a7-236">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ba1a7-237">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-237">Windows Client</span></span>                | <span data-ttu-id="ba1a7-238">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-238">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ba1a7-239">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-239">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-240">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-240">Windows 10 Client</span></span>             | <span data-ttu-id="ba1a7-241">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-241">Version 1607+</span></span>                  | <span data-ttu-id="ba1a7-242">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-242">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-243">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ba1a7-243">Windows Server</span></span>                | <span data-ttu-id="ba1a7-244">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-244">2012 R2+</span></span>                       | <span data-ttu-id="ba1a7-245">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-245">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-246">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="ba1a7-246">Nano Server</span></span>                   | <span data-ttu-id="ba1a7-247">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-247">Version 1803+</span></span>                  | <span data-ttu-id="ba1a7-248">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ba1a7-248">x64, ARM32</span></span>      |

<span data-ttu-id="ba1a7-249">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-249">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="ba1a7-250">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-250">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="ba1a7-251">*.NET Core 3.0은 현재 ❌ 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="ba1a7-251">*.NET Core 3.0 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ba1a7-252">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-252">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="ba1a7-253">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-253">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-254">OS</span><span class="sxs-lookup"><span data-stu-id="ba1a7-254">OS</span></span>                            | <span data-ttu-id="ba1a7-255">버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-255">Version</span></span>                        | <span data-ttu-id="ba1a7-256">아키텍처</span><span class="sxs-lookup"><span data-stu-id="ba1a7-256">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ba1a7-257">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-257">Windows Client</span></span>                | <span data-ttu-id="ba1a7-258">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-258">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ba1a7-259">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-259">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-260">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-260">Windows 10 Client</span></span>             | <span data-ttu-id="ba1a7-261">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-261">Version 1607+</span></span>                  | <span data-ttu-id="ba1a7-262">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-262">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-263">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ba1a7-263">Windows Server</span></span>                | <span data-ttu-id="ba1a7-264">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-264">2012 R2+</span></span>                       | <span data-ttu-id="ba1a7-265">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-265">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-266">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="ba1a7-266">Nano Server</span></span>                   | <span data-ttu-id="ba1a7-267">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-267">Version 1803+</span></span>                  | <span data-ttu-id="ba1a7-268">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ba1a7-268">x64, ARM32</span></span>      |

<span data-ttu-id="ba1a7-269">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-269">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="ba1a7-270">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-270">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="ba1a7-271">*.NET Core 2.2는 현재 ❌ 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="ba1a7-271">*.NET Core 2.2 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ba1a7-272">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-272">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="ba1a7-273">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-273">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-274">OS</span><span class="sxs-lookup"><span data-stu-id="ba1a7-274">OS</span></span>                            | <span data-ttu-id="ba1a7-275">버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-275">Version</span></span>                        | <span data-ttu-id="ba1a7-276">아키텍처</span><span class="sxs-lookup"><span data-stu-id="ba1a7-276">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ba1a7-277">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-277">Windows Client</span></span>                | <span data-ttu-id="ba1a7-278">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-278">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ba1a7-279">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-279">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-280">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-280">Windows 10 Client</span></span>             | <span data-ttu-id="ba1a7-281">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-281">Version 1607+</span></span>                  | <span data-ttu-id="ba1a7-282">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-282">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-283">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ba1a7-283">Windows Server</span></span>                | <span data-ttu-id="ba1a7-284">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-284">2008 R2 SP1+</span></span>                   | <span data-ttu-id="ba1a7-285">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-285">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-286">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="ba1a7-286">Nano Server</span></span>                   | <span data-ttu-id="ba1a7-287">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-287">Version 1803+</span></span>                   | <span data-ttu-id="ba1a7-288">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ba1a7-288">x64, ARM32</span></span>      |

<span data-ttu-id="ba1a7-289">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-289">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="ba1a7-290">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-290">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="ba1a7-291">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-291">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="ba1a7-292">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-292">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ba1a7-293">OS</span><span class="sxs-lookup"><span data-stu-id="ba1a7-293">OS</span></span>                            | <span data-ttu-id="ba1a7-294">버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-294">Version</span></span>                        | <span data-ttu-id="ba1a7-295">아키텍처</span><span class="sxs-lookup"><span data-stu-id="ba1a7-295">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ba1a7-296">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-296">Windows Client</span></span>                | <span data-ttu-id="ba1a7-297">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-297">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ba1a7-298">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-298">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-299">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ba1a7-299">Windows 10 Client</span></span>             | <span data-ttu-id="ba1a7-300">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-300">Version 1607+</span></span>                  | <span data-ttu-id="ba1a7-301">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-301">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-302">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ba1a7-302">Windows Server</span></span>                | <span data-ttu-id="ba1a7-303">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-303">2008 R2 SP1+</span></span>                   | <span data-ttu-id="ba1a7-304">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ba1a7-304">x64, x86</span></span>        |
| <span data-ttu-id="ba1a7-305">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="ba1a7-305">Nano Server</span></span>                   | <span data-ttu-id="ba1a7-306">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="ba1a7-306">Version 1803+</span></span>                  | <span data-ttu-id="ba1a7-307">x64,</span><span class="sxs-lookup"><span data-stu-id="ba1a7-307">x64,</span></span>            |

<span data-ttu-id="ba1a7-308">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-308">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="ba1a7-309">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-309">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="ba1a7-310">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-310">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="ba1a7-311">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="ba1a7-311">Windows 7 SP1 [ESU][esu]</span></span>
- <span data-ttu-id="ba1a7-312">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-312">Windows Vista SP 2</span></span>
- <span data-ttu-id="ba1a7-313">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-313">Windows 8.1</span></span>
- <span data-ttu-id="ba1a7-314">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-314">Windows Server 2008 R2</span></span>
- <span data-ttu-id="ba1a7-315">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-315">Windows Server 2012 R2</span></span>

<span data-ttu-id="ba1a7-316">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-316">Install the following:</span></span>

- <span data-ttu-id="ba1a7-317">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="ba1a7-317">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="ba1a7-318">KB2533623</span><span class="sxs-lookup"><span data-stu-id="ba1a7-318">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="ba1a7-319">다음과 같은 오류가 발생할 경우에도 이전 요구 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-319">The previous requirements are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="ba1a7-320">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll* 이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-320">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="ba1a7-321">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-321">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="ba1a7-322">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="ba1a7-322">\- or -</span></span>
>
> <span data-ttu-id="ba1a7-323">컴퓨터에 *api-ms-win-cor-timezone-l1-1-0.dll* 이 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-323">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="ba1a7-324">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-324">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="ba1a7-325">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="ba1a7-325">\- or -</span></span>
>
> <span data-ttu-id="ba1a7-326">라이브러리 *hostfxr.dll* 을 찾았으나, *C:\\\<path_to_app>\\hostfxr.dll* 에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-326">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="ba1a7-327">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="ba1a7-327">Install with PowerShell automation</span></span>

<span data-ttu-id="ba1a7-328">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 CI 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-328">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="ba1a7-329">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-329">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="ba1a7-330">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-330">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="ba1a7-331">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-331">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="ba1a7-332">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-332">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="ba1a7-333">포함하지 않을 경우 스크립트가 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-333">Otherwise, the script installs the SDK.</span></span>

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

<span data-ttu-id="ba1a7-334">`-Runtime` 스위치를 생략하여 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-334">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="ba1a7-335">이 예에서는 `-Channel` 스위치를 `Current`로 설정하여 최신 지원 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-335">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="ba1a7-336">Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="ba1a7-336">Install with Visual Studio</span></span>

<span data-ttu-id="ba1a7-337">Visual Studio를 사용하여 .NET 앱을 개발하는 경우 다음 표에서 대상 .NET SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-337">If you're using Visual Studio to develop .NET apps, the following table describes the minimum required version of Visual Studio based on the target .NET SDK version.</span></span>

| <span data-ttu-id="ba1a7-338">.NET SDK 버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-338">.NET SDK version</span></span>      | <span data-ttu-id="ba1a7-339">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="ba1a7-339">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="ba1a7-340">5.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-340">5.0</span></span>                   | <span data-ttu-id="ba1a7-341">Visual Studio 2019 버전 16.8 이상</span><span class="sxs-lookup"><span data-stu-id="ba1a7-341">Visual Studio 2019 version 16.8 or higher.</span></span> |
| <span data-ttu-id="ba1a7-342">3.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-342">3.1</span></span>                   | <span data-ttu-id="ba1a7-343">Visual Studio 2019 버전 16.4 이상</span><span class="sxs-lookup"><span data-stu-id="ba1a7-343">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="ba1a7-344">3.0</span><span class="sxs-lookup"><span data-stu-id="ba1a7-344">3.0</span></span>                   | <span data-ttu-id="ba1a7-345">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="ba1a7-345">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="ba1a7-346">2.2</span><span class="sxs-lookup"><span data-stu-id="ba1a7-346">2.2</span></span>                   | <span data-ttu-id="ba1a7-347">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="ba1a7-347">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="ba1a7-348">2.1</span><span class="sxs-lookup"><span data-stu-id="ba1a7-348">2.1</span></span>                   | <span data-ttu-id="ba1a7-349">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="ba1a7-349">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="ba1a7-350">Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-350">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="ba1a7-351">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-351">Open Visual Studio.</span></span>
01. <span data-ttu-id="ba1a7-352">**도움말** > **Microsoft Visual Studio 정보** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-352">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="ba1a7-353">**정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-353">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="ba1a7-354">Visual Studio가 최신 .NET SDK 및 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-354">Visual Studio can install the latest .NET SDK and runtime.</span></span>

> [!div class="button"]
> <span data-ttu-id="ba1a7-355">[Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-355">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="ba1a7-356">워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="ba1a7-356">Select a workload</span></span>

<span data-ttu-id="ba1a7-357">Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-357">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="ba1a7-358">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-358">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="ba1a7-359">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-359">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="ba1a7-360">**웹 및 클라우드** 섹션의 **Azure 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-360">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="ba1a7-361">**데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-361">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="ba1a7-362">[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ba1a7-362">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="ba1a7-363">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="ba1a7-363">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="ba1a7-364">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-364">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="ba1a7-365">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-365">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="ba1a7-366">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-366">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="ba1a7-367">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="ba1a7-367">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="ba1a7-368">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="ba1a7-368">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="ba1a7-369">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="ba1a7-369">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="ba1a7-370">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="ba1a7-370">Windows Installer</span></span>

<span data-ttu-id="ba1a7-371">Windows Installer 실행 파일은 .NET [다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core)에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-371">The [download page](https://dotnet.microsoft.com/download/dotnet-core) for .NET provides Windows Installer executables.</span></span>

<span data-ttu-id="ba1a7-372">MSI 파일을 사용하여 .NET을 설치하는 경우 `DOTNETHOME_X64` 및 `DOTNETHOME_X86` 매개 변수를 설정하여 설치 경로를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-372">When you use the MSI files to install .NET< you can customize the installation path by setting the `DOTNETHOME_X64` and `DOTNETHOME_X86` parameters:</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe DOTNETHOME_X64="F:\dotnet\x64" DOTNETHOME_X86="F:\dotnet\x86"
```

## <a name="download-and-manually-install"></a><span data-ttu-id="ba1a7-373">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="ba1a7-373">Download and manually install</span></span>

<span data-ttu-id="ba1a7-374">.NET용 Windows 설치 관리자 대신 SDK나 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-374">As an alternative to the Windows installers for .NET, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="ba1a7-375">수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-375">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="ba1a7-376">개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-376">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="ba1a7-377">.NET SDK와 .NET 런타임 모두 다운로드한 후 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-377">Both .NET SDK and .NET Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="ba1a7-378">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-378">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="ba1a7-379">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-379">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- [<span data-ttu-id="ba1a7-380">.NET 5.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-380">.NET 5.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- [<span data-ttu-id="ba1a7-381">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-381">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="ba1a7-382">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-382">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [<span data-ttu-id="ba1a7-383">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="ba1a7-383">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="ba1a7-384">.NET을 추출해서 넣을 디렉터리(예: `%USERPROFILE%\dotnet`)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-384">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="ba1a7-385">그런 다음, 다운로드한 zip 파일을 이 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-385">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="ba1a7-386">기본적으로 이런 방식으로 설치된 .NET은 .NET CLI 명령과 앱에서 사용되지 않으므로 사용하도록 명시적으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-386">By default, .NET CLI commands and apps won't use .NET installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="ba1a7-387">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-387">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="ba1a7-388">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-388">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="ba1a7-389">`DOTNET_MULTILEVEL_LOOKUP`을 `0`으로 설정하면 .NET에서는 전역적으로 설치된 .NET 버전을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-389">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET ignores any globally installed .NET version.</span></span> <span data-ttu-id="ba1a7-390">.NET에서 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 고려하도록 하려면 이러한 환경 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-390">Remove that environment setting to let .NET consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="ba1a7-391">기본값은 일반적으로 `C:\Program Files\dotnet`입니다. 이 경로는 설치 관리자가 .NET을 설치하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-391">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET.</span></span>

## <a name="docker"></a><span data-ttu-id="ba1a7-392">Docker</span><span class="sxs-lookup"><span data-stu-id="ba1a7-392">Docker</span></span>

<span data-ttu-id="ba1a7-393">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-393">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="ba1a7-394">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-394">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="ba1a7-395">.NET은 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-395">.NET can run in a Docker container.</span></span> <span data-ttu-id="ba1a7-396">공식 .NET Docker 이미지는 MCR(Microsoft Container Registry)에 게시되며 [Microsoft .NET Docker Hub 리포지토리](https://hub.docker.com/_/microsoft-dotnet)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-396">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet).</span></span> <span data-ttu-id="ba1a7-397">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-397">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="ba1a7-398">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-398">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="ba1a7-399">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-aspnet)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-399">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="ba1a7-400">Docker 컨테이너에서 .NET 사용에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba1a7-400">For more information about using .NET in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba1a7-401">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ba1a7-401">Next steps</span></span>

- <span data-ttu-id="ba1a7-402">[.NET이 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="ba1a7-402">[How to check if .NET is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="ba1a7-403">[자습서: Hello World 자습서](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="ba1a7-403">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="ba1a7-404">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="ba1a7-404">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="ba1a7-405">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="ba1a7-405">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[esu]: /troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq
