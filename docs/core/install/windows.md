---
title: Windows에 .NET Core 설치
description: .NET Core를 설치할 수 있는 Windows 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 06/22/2020
ms.openlocfilehash: 97f67d00b3eb4dafc55256aea51f4295bb0ef06a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308951"
---
# <a name="install-net-core-on-windows"></a><span data-ttu-id="6ba5e-103">Windows에 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="6ba5e-103">Install .NET Core on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

<span data-ttu-id="6ba5e-107">이 문서에서는 Windows에 .NET Core를 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-107">In this article, you'll learn how to install .NET Core on Windows.</span></span> <span data-ttu-id="6ba5e-108">.NET Core는 런타임과 SDK로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="6ba5e-109">런타임은 .NET Core 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="6ba5e-110">SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="6ba5e-111">.NET Core 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="6ba5e-112">최신 버전의 .NET Core는 3.1입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-112">The latest version of .NET Core is 3.1.</span></span>

> [!div class="button"]
> [<span data-ttu-id="6ba5e-113">.NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="6ba5e-114">지원되는 릴리스</span><span class="sxs-lookup"><span data-stu-id="6ba5e-114">Supported releases</span></span>

<span data-ttu-id="6ba5e-115">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Windows 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-115">The following table is a list of currently supported .NET Core releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="6ba5e-116">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 각 버전의 [Windows가 지원 종료에 도달](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-116">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="6ba5e-117">Windows 10 버전의 서비스 종료 날짜는 버전별로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="6ba5e-118">**Home**, **Pro**, **Pro Education** 및 **Pro for Workstations** 버전만 다음 표에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="6ba5e-119">특정 세부 정보는 [Windows 수명 주기 팩트 시트](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

- <span data-ttu-id="6ba5e-120">✔️는 버전의 Windows 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-120">A ✔️ indicates that the version of Windows or .NET Core is still supported.</span></span>
- <span data-ttu-id="6ba5e-121">❌는 Windows 또는 .NET Core 버전이 해당 Windows 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-121">A ❌ indicates that the version of Windows or .NET Core isn't supported on that Windows release.</span></span>
- <span data-ttu-id="6ba5e-122">Windows 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-122">When both a version of Windows and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="6ba5e-123">운영 체제</span><span class="sxs-lookup"><span data-stu-id="6ba5e-123">Operating System</span></span>                      | <span data-ttu-id="6ba5e-124">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-124">.NET Core 2.1</span></span> | <span data-ttu-id="6ba5e-125">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-125">.NET Core 3.1</span></span> | <span data-ttu-id="6ba5e-126">.NET 5 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-126">.NET 5 Preview</span></span> |
|-----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="6ba5e-127">✔️ Windows 10, 버전 2004</span><span class="sxs-lookup"><span data-stu-id="6ba5e-127">✔️ Windows 10, Version 2004</span></span> | <span data-ttu-id="6ba5e-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-128">✔️ 2.1</span></span>        | <span data-ttu-id="6ba5e-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-129">✔️ 3.1</span></span>        | <span data-ttu-id="6ba5e-130">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-131">✔️ Windows 10, 버전 1909</span><span class="sxs-lookup"><span data-stu-id="6ba5e-131">✔️ Windows 10, Version 1909</span></span> | <span data-ttu-id="6ba5e-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-132">✔️ 2.1</span></span>        | <span data-ttu-id="6ba5e-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-133">✔️ 3.1</span></span>        | <span data-ttu-id="6ba5e-134">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-135">✔️ Windows 10, 버전 1903</span><span class="sxs-lookup"><span data-stu-id="6ba5e-135">✔️ Windows 10, Version 1903</span></span> | <span data-ttu-id="6ba5e-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-136">✔️ 2.1</span></span>        | <span data-ttu-id="6ba5e-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-137">✔️ 3.1</span></span>        | <span data-ttu-id="6ba5e-138">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-138">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-139">✔️ Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="6ba5e-139">✔️ Windows 10, Version 1809</span></span> | <span data-ttu-id="6ba5e-140">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-140">✔️ 2.1</span></span>        | <span data-ttu-id="6ba5e-141">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-141">✔️ 3.1</span></span>        | <span data-ttu-id="6ba5e-142">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-142">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-143">❌ Windows 10, 버전 1803</span><span class="sxs-lookup"><span data-stu-id="6ba5e-143">❌ Windows 10, Version 1803</span></span> | <span data-ttu-id="6ba5e-144">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-144">✔️ 2.1</span></span>        | <span data-ttu-id="6ba5e-145">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-145">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-146">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-146">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-147">❌ Windows 10, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="6ba5e-147">❌ Windows 10, Version 1709</span></span> | <span data-ttu-id="6ba5e-148">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-148">❌ 2.1</span></span>        | <span data-ttu-id="6ba5e-149">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-149">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-150">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-150">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-151">❌ Windows 10, 버전 1703</span><span class="sxs-lookup"><span data-stu-id="6ba5e-151">❌ Windows 10, Version 1703</span></span> | <span data-ttu-id="6ba5e-152">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-152">❌ 2.1</span></span>        | <span data-ttu-id="6ba5e-153">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-153">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-154">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-154">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-155">❌ Windows 10, 버전 1607</span><span class="sxs-lookup"><span data-stu-id="6ba5e-155">❌ Windows 10, Version 1607</span></span> | <span data-ttu-id="6ba5e-156">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-156">❌ 2.1</span></span>        | <span data-ttu-id="6ba5e-157">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-157">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-158">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-158">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-159">❌ Windows 10, 버전 1511</span><span class="sxs-lookup"><span data-stu-id="6ba5e-159">❌ Windows 10, Version 1511</span></span> | <span data-ttu-id="6ba5e-160">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-160">❌ 2.1</span></span>        | <span data-ttu-id="6ba5e-161">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-161">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-162">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-162">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="6ba5e-163">❌ Windows 10, 버전 1507</span><span class="sxs-lookup"><span data-stu-id="6ba5e-163">❌ Windows 10, Version 1507</span></span> | <span data-ttu-id="6ba5e-164">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-164">❌ 2.1</span></span>        | <span data-ttu-id="6ba5e-165">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-165">❌ 3.1</span></span>        | <span data-ttu-id="6ba5e-166">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="6ba5e-166">❌ 5.0 Preview</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="6ba5e-167">지원되지 않는 릴리스</span><span class="sxs-lookup"><span data-stu-id="6ba5e-167">Unsupported releases</span></span>

<span data-ttu-id="6ba5e-168">다음 .NET Core 버전은 ❌ 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-168">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="6ba5e-169">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-169">The downloads for these still remain published:</span></span>

- <span data-ttu-id="6ba5e-170">3.0</span><span class="sxs-lookup"><span data-stu-id="6ba5e-170">3.0</span></span>
- <span data-ttu-id="6ba5e-171">2.2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-171">2.2</span></span>
- <span data-ttu-id="6ba5e-172">2.0</span><span class="sxs-lookup"><span data-stu-id="6ba5e-172">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="6ba5e-173">런타임 정보</span><span class="sxs-lookup"><span data-stu-id="6ba5e-173">Runtime information</span></span>

<span data-ttu-id="6ba5e-174">런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-174">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="6ba5e-175">앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-175">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="6ba5e-176">앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-176">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="6ba5e-177">Windows에 설치할 수 있는 세 가지 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-177">There are three different runtimes you can install on Windows:</span></span>

<span data-ttu-id="6ba5e-178">‘ASP.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="6ba5e-178">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="6ba5e-179">ASP.NET Core 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-179">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="6ba5e-180">.NET Core 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-180">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="6ba5e-181">‘데스크톱 런타임’</span><span class="sxs-lookup"><span data-stu-id="6ba5e-181">*Desktop runtime*</span></span>\
<span data-ttu-id="6ba5e-182">Windows용 .NET Core WPF 및 .NET Core Windows Forms 데스크톱 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-182">Runs .NET Core WPF and .NET Core Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="6ba5e-183">.NET Core 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-183">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="6ba5e-184">‘.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="6ba5e-184">*.NET Core runtime*</span></span>\
<span data-ttu-id="6ba5e-185">이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-185">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="6ba5e-186">.NET Core 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’과 ‘데스크톱 런타임’을 모두 설치하는 것이 좋습니다. </span><span class="sxs-lookup"><span data-stu-id="6ba5e-186">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET Core apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="6ba5e-187">.NET Core 런타임 다운로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-187">Download .NET Core Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="6ba5e-188">SDK 정보</span><span class="sxs-lookup"><span data-stu-id="6ba5e-188">SDK information</span></span>

<span data-ttu-id="6ba5e-189">SDK는 .NET Core 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-189">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="6ba5e-190">SDK를 설치하면 ASP.NET Core, 데스크톱 및 .NET Core의 세 가지 [런타임](#runtime-information)이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-190">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET Core.</span></span>

> [!div class="button"]
> [<span data-ttu-id="6ba5e-191">.NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-191">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="6ba5e-192">종속성</span><span class="sxs-lookup"><span data-stu-id="6ba5e-192">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="6ba5e-193">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-193">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="6ba5e-194">.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-194">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6ba5e-195">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-195">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6ba5e-196">OS</span><span class="sxs-lookup"><span data-stu-id="6ba5e-196">OS</span></span>                            | <span data-ttu-id="6ba5e-197">버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-197">Version</span></span>                        | <span data-ttu-id="6ba5e-198">아키텍처</span><span class="sxs-lookup"><span data-stu-id="6ba5e-198">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6ba5e-199">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-199">Windows Client</span></span>                | <span data-ttu-id="6ba5e-200">8.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-200">8.1</span></span>                            | <span data-ttu-id="6ba5e-201">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-201">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-202">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-202">Windows 10 Client</span></span>             | <span data-ttu-id="6ba5e-203">버전 1609+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-203">Version 1609+</span></span>                  | <span data-ttu-id="6ba5e-204">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-204">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-205">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6ba5e-205">Windows Server</span></span>                | <span data-ttu-id="6ba5e-206">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-206">2012 R2+</span></span>                       | <span data-ttu-id="6ba5e-207">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-207">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-208">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="6ba5e-208">Nano Server</span></span>                   | <span data-ttu-id="6ba5e-209">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-209">Version 1803+</span></span>                  | <span data-ttu-id="6ba5e-210">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6ba5e-210">x64, ARM32</span></span>      |

<span data-ttu-id="6ba5e-211">.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-211">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="6ba5e-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6ba5e-212">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="6ba5e-213">*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="6ba5e-213">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="6ba5e-214">.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-214">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="6ba5e-215">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-215">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6ba5e-216">OS</span><span class="sxs-lookup"><span data-stu-id="6ba5e-216">OS</span></span>                            | <span data-ttu-id="6ba5e-217">버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-217">Version</span></span>                        | <span data-ttu-id="6ba5e-218">아키텍처</span><span class="sxs-lookup"><span data-stu-id="6ba5e-218">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6ba5e-219">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-219">Windows Client</span></span>                | <span data-ttu-id="6ba5e-220">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-220">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6ba5e-221">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-221">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-222">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-222">Windows 10 Client</span></span>             | <span data-ttu-id="6ba5e-223">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-223">Version 1607+</span></span>                  | <span data-ttu-id="6ba5e-224">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-224">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-225">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6ba5e-225">Windows Server</span></span>                | <span data-ttu-id="6ba5e-226">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-226">2012 R2+</span></span>                       | <span data-ttu-id="6ba5e-227">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-227">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-228">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="6ba5e-228">Nano Server</span></span>                   | <span data-ttu-id="6ba5e-229">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-229">Version 1803+</span></span>                  | <span data-ttu-id="6ba5e-230">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6ba5e-230">x64, ARM32</span></span>      |

<span data-ttu-id="6ba5e-231">.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-231">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="6ba5e-232">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-232">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6ba5e-233">*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="6ba5e-233">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="6ba5e-234">.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-234">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="6ba5e-235">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-235">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6ba5e-236">OS</span><span class="sxs-lookup"><span data-stu-id="6ba5e-236">OS</span></span>                            | <span data-ttu-id="6ba5e-237">버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-237">Version</span></span>                        | <span data-ttu-id="6ba5e-238">아키텍처</span><span class="sxs-lookup"><span data-stu-id="6ba5e-238">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6ba5e-239">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-239">Windows Client</span></span>                | <span data-ttu-id="6ba5e-240">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-240">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6ba5e-241">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-241">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-242">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-242">Windows 10 Client</span></span>             | <span data-ttu-id="6ba5e-243">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-243">Version 1607+</span></span>                  | <span data-ttu-id="6ba5e-244">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-244">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-245">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6ba5e-245">Windows Server</span></span>                | <span data-ttu-id="6ba5e-246">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-246">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6ba5e-247">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-247">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-248">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="6ba5e-248">Nano Server</span></span>                   | <span data-ttu-id="6ba5e-249">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-249">Version 1803+</span></span>                   | <span data-ttu-id="6ba5e-250">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6ba5e-250">x64, ARM32</span></span>      |

<span data-ttu-id="6ba5e-251">.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-251">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="6ba5e-252">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-252">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6ba5e-253">.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-253">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6ba5e-254">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-254">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6ba5e-255">OS</span><span class="sxs-lookup"><span data-stu-id="6ba5e-255">OS</span></span>                            | <span data-ttu-id="6ba5e-256">버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-256">Version</span></span>                        | <span data-ttu-id="6ba5e-257">아키텍처</span><span class="sxs-lookup"><span data-stu-id="6ba5e-257">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6ba5e-258">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-258">Windows Client</span></span>                | <span data-ttu-id="6ba5e-259">7 SP1+, 8.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-259">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6ba5e-260">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-260">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-261">Windows 10 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ba5e-261">Windows 10 Client</span></span>             | <span data-ttu-id="6ba5e-262">버전 1607+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-262">Version 1607+</span></span>                  | <span data-ttu-id="6ba5e-263">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-263">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-264">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6ba5e-264">Windows Server</span></span>                | <span data-ttu-id="6ba5e-265">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-265">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6ba5e-266">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6ba5e-266">x64, x86</span></span>        |
| <span data-ttu-id="6ba5e-267">Nano 서버</span><span class="sxs-lookup"><span data-stu-id="6ba5e-267">Nano Server</span></span>                   | <span data-ttu-id="6ba5e-268">버전 1803+</span><span class="sxs-lookup"><span data-stu-id="6ba5e-268">Version 1803+</span></span>                  | <span data-ttu-id="6ba5e-269">x64,</span><span class="sxs-lookup"><span data-stu-id="6ba5e-269">x64,</span></span>            |

<span data-ttu-id="6ba5e-270">.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-270">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="6ba5e-271">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-271">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="6ba5e-272">다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-272">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="6ba5e-273">❌ Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-273">❌ Windows 7 SP1</span></span>
- <span data-ttu-id="6ba5e-274">❌ Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-274">❌ Windows Vista SP 2</span></span>
- <span data-ttu-id="6ba5e-275">✔️ Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-275">✔️ Windows 8.1</span></span>
- <span data-ttu-id="6ba5e-276">✔️ Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-276">✔️ Windows Server 2008 R2</span></span>
- <span data-ttu-id="6ba5e-277">✔️ Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-277">✔️ Windows Server 2012 R2</span></span>

<span data-ttu-id="6ba5e-278">다음을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-278">Install the following:</span></span>

- <span data-ttu-id="6ba5e-279">[Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="6ba5e-279">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="6ba5e-280">KB2533623</span><span class="sxs-lookup"><span data-stu-id="6ba5e-280">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="6ba5e-281">다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-281">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="6ba5e-282">컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-282">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="6ba5e-283">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-283">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="6ba5e-284">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="6ba5e-284">\- or -</span></span>
>
> <span data-ttu-id="6ba5e-285">컴퓨터에 *api-ms-win-cor-timezone-l1-1-0.dll*이 없어 프로그램을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-285">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="6ba5e-286">프로그램을 다시 설치하여 이 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-286">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="6ba5e-287">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="6ba5e-287">\- or -</span></span>
>
> <span data-ttu-id="6ba5e-288">라이브러리 *hostfxr.dll*을 찾았으나, *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-288">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="6ba5e-289">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="6ba5e-289">Install with PowerShell automation</span></span>

<span data-ttu-id="6ba5e-290">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 CI 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-290">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="6ba5e-291">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-291">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="6ba5e-292">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-292">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="6ba5e-293">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-293">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="6ba5e-294">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-294">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="6ba5e-295">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-295">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

<span data-ttu-id="6ba5e-296">`-Runtime` 스위치를 생략하여 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-296">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="6ba5e-297">이 예에서는 `-Channel` 스위치를 `Current`로 설정하여 최신 지원 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-297">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="6ba5e-298">Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="6ba5e-298">Install with Visual Studio</span></span>

<span data-ttu-id="6ba5e-299">Visual Studio를 사용하여 .NET Core 앱을 개발하는 경우, 다음 표에서 대상 .NET Core SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-299">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="6ba5e-300">.NET Core SDK 버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-300">.NET Core SDK version</span></span> | <span data-ttu-id="6ba5e-301">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="6ba5e-301">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="6ba5e-302">3.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-302">3.1</span></span>                   | <span data-ttu-id="6ba5e-303">Visual Studio 2019 버전 16.4 이상</span><span class="sxs-lookup"><span data-stu-id="6ba5e-303">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="6ba5e-304">3.0</span><span class="sxs-lookup"><span data-stu-id="6ba5e-304">3.0</span></span>                   | <span data-ttu-id="6ba5e-305">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="6ba5e-305">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="6ba5e-306">2.2</span><span class="sxs-lookup"><span data-stu-id="6ba5e-306">2.2</span></span>                   | <span data-ttu-id="6ba5e-307">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="6ba5e-307">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="6ba5e-308">2.1</span><span class="sxs-lookup"><span data-stu-id="6ba5e-308">2.1</span></span>                   | <span data-ttu-id="6ba5e-309">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="6ba5e-309">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="6ba5e-310">Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-310">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="6ba5e-311">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-311">Open Visual Studio.</span></span>
01. <span data-ttu-id="6ba5e-312">**도움말** > **Microsoft Visual Studio 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-312">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="6ba5e-313">**정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-313">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="6ba5e-314">Visual Studio가 최신 .NET Core SDK 및 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-314">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

> [!div class="button"]
> <span data-ttu-id="6ba5e-315">[Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-315">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="6ba5e-316">워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="6ba5e-316">Select a workload</span></span>

<span data-ttu-id="6ba5e-317">Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-317">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="6ba5e-318">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-318">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="6ba5e-319">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-319">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="6ba5e-320">**웹 및 클라우드** 섹션의 **Azure 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-320">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="6ba5e-321">**데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-321">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="6ba5e-322">[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-322">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="6ba5e-323">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="6ba5e-323">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="6ba5e-324">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-324">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="6ba5e-325">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-325">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="6ba5e-326">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-326">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="6ba5e-327">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="6ba5e-327">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="6ba5e-328">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="6ba5e-328">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="6ba5e-329">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="6ba5e-329">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="6ba5e-330">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="6ba5e-330">Download and manually install</span></span>

<span data-ttu-id="6ba5e-331">.NET Core용 Windows 설치 프로그램의 대안으로, SDK나 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-331">As an alternative to the Windows installers for .NET Core, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="6ba5e-332">수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-332">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="6ba5e-333">개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-333">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="6ba5e-334">.NET Core SDK와 .NET Core 런타임 모두 다운로드 후 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-334">Both .NET Core SDK and .NET Core Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="6ba5e-335">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-335">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="6ba5e-336">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-336">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="6ba5e-337">✔️ [.NET 5.0 미리보기 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-337">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="6ba5e-338">✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-338">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="6ba5e-339">✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-339">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="6ba5e-340">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="6ba5e-340">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="6ba5e-341">.NET을 추출해서 넣을 디렉터리(예: `%USERPROFILE%\dotnet`)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-341">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="6ba5e-342">그런 다음, 다운로드한 zip 파일을 이 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-342">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="6ba5e-343">기본적으로 .NET Core CLI 명령과 앱은 이런 방식으로 설치된 .NET Core를 사용하지 않으므로 명시적으로 사용을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-343">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="6ba5e-344">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-344">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="6ba5e-345">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-345">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="6ba5e-346">`DOTNET_MULTILEVEL_LOOKUP`을 `0`으로 설정하면 .NET Core에서는 전역적으로 설치된 .NET Core 버전을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-346">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET Core ignores any globally installed .NET Core version.</span></span> <span data-ttu-id="6ba5e-347">.NET Core에서 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 고려하도록 하려면 이러한 환경 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-347">Remove that environment setting to let .NET Core consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="6ba5e-348">기본값은 일반적으로 `C:\Program Files\dotnet`입니다. 이 경로는 설치 관리자가 .NET Core를 설치하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-348">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET Core.</span></span>

## <a name="docker"></a><span data-ttu-id="6ba5e-349">Docker</span><span class="sxs-lookup"><span data-stu-id="6ba5e-349">Docker</span></span>

<span data-ttu-id="6ba5e-350">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-350">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="6ba5e-351">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-351">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="6ba5e-352">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-352">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="6ba5e-353">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-353">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="6ba5e-354">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-354">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="6ba5e-355">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-355">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="6ba5e-356">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-356">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="6ba5e-357">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba5e-357">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ba5e-358">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6ba5e-358">Next steps</span></span>

- <span data-ttu-id="6ba5e-359">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-359">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="6ba5e-360">[자습서: Hello World 자습서](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-360">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="6ba5e-361">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-361">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="6ba5e-362">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="6ba5e-362">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>
