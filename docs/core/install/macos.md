---
title: macOS에 .NET 설치
description: .NET을 설치할 수 있는 macOS 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 871263b820aaf4cc04e573dd4aa3022caa401857
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506307"
---
# <a name="install-net-on-macos"></a><span data-ttu-id="522cd-103">macOS에 .NET 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-103">Install .NET on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

<span data-ttu-id="522cd-107">이 문서에서는 macOS에 .NET을 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-107">In this article, you'll learn how to install .NET on macOS.</span></span> <span data-ttu-id="522cd-108">.NET은 런타임과 SDK로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="522cd-109">런타임은 .NET 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="522cd-110">SDK는 .NET 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="522cd-111">.NET 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="522cd-112">.NET의 최신 버전은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="522cd-113">.NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="522cd-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="522cd-114">지원되는 릴리스</span><span class="sxs-lookup"><span data-stu-id="522cd-114">Supported releases</span></span>

<span data-ttu-id="522cd-115">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 macOS 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-115">The following table is a list of currently supported .NET releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="522cd-116">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-116">These versions remain supported either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="522cd-117">✔️는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="522cd-118">❌️는 .NET Core 버전이 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="522cd-119">운영 체제</span><span class="sxs-lookup"><span data-stu-id="522cd-119">Operating System</span></span>          | <span data-ttu-id="522cd-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="522cd-120">.NET Core 2.1</span></span> | <span data-ttu-id="522cd-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="522cd-121">.NET Core 3.1</span></span> | <span data-ttu-id="522cd-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="522cd-122">.NET 5.0</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="522cd-123">macOS 11.0 “Big Sur”</span><span class="sxs-lookup"><span data-stu-id="522cd-123">macOS 11.0 "Big Sur"</span></span>        | <span data-ttu-id="522cd-124">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="522cd-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="522cd-125">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="522cd-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="522cd-126">✔️ 5.0([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="522cd-126">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="522cd-127">macOS 10.15 “Catalina”</span><span class="sxs-lookup"><span data-stu-id="522cd-127">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="522cd-128">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="522cd-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="522cd-129">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="522cd-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="522cd-130">✔️ 5.0([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="522cd-130">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="522cd-131">macOS 10.14 “Mojave”</span><span class="sxs-lookup"><span data-stu-id="522cd-131">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="522cd-132">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="522cd-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="522cd-133">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="522cd-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="522cd-134">✔️ 5.0([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="522cd-134">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="522cd-135">macOS 10.13 “High Sierra”</span><span class="sxs-lookup"><span data-stu-id="522cd-135">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="522cd-136">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="522cd-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="522cd-137">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="522cd-137">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="522cd-138">✔️ 5.0([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="522cd-138">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="522cd-139">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="522cd-139">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="522cd-140">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="522cd-140">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="522cd-141">❌ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="522cd-141">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="522cd-142">❌ 5.0([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="522cd-142">❌ 5.0 ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="522cd-143">지원되지 않는 릴리스</span><span class="sxs-lookup"><span data-stu-id="522cd-143">Unsupported releases</span></span>

<span data-ttu-id="522cd-144">다음 .NET 버전은 ❌로 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-144">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="522cd-145">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-145">The downloads for these still remain published:</span></span>

- <span data-ttu-id="522cd-146">3.0([릴리스 정보][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="522cd-146">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="522cd-147">2.2([릴리스 정보][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="522cd-147">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="522cd-148">2.0([릴리스 정보][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="522cd-148">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="522cd-149">런타임 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-149">Runtime information</span></span>

<span data-ttu-id="522cd-150">런타임은 .NET으로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-150">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="522cd-151">앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-151">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="522cd-152">앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-152">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="522cd-153">macOS에 설치할 수 있는 두 가지 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-153">There are two different runtimes you can install on macOS:</span></span>

- <span data-ttu-id="522cd-154">‘ASP.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="522cd-154">*ASP.NET Core runtime*</span></span>\
  <span data-ttu-id="522cd-155">ASP.NET Core 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-155">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="522cd-156">.NET 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-156">Includes the .NET runtime.</span></span>

- <span data-ttu-id="522cd-157">‘.NET 런타임’</span><span class="sxs-lookup"><span data-stu-id="522cd-157">*.NET runtime*</span></span>\
  <span data-ttu-id="522cd-158">이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-158">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="522cd-159">.NET 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-159">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="522cd-160">.NET 런타임 다운로드</span><span class="sxs-lookup"><span data-stu-id="522cd-160">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="522cd-161">SDK 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-161">SDK information</span></span>

<span data-ttu-id="522cd-162">SDK는 .NET 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-162">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="522cd-163">SDK를 설치하면 ASP.NET Core 및 .NET Core의 두 가지 [런타임](#runtime-information)이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-163">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="522cd-164">종속성</span><span class="sxs-lookup"><span data-stu-id="522cd-164">Dependencies</span></span>

<span data-ttu-id="522cd-165">.NET은 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-165">.NET is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="522cd-166">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-166">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="522cd-167">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="522cd-167">.NET Core Version</span></span> | <span data-ttu-id="522cd-168">macOS</span><span class="sxs-lookup"><span data-stu-id="522cd-168">macOS</span></span>                 | <span data-ttu-id="522cd-169">아키텍처</span><span class="sxs-lookup"><span data-stu-id="522cd-169">Architectures</span></span> | <span data-ttu-id="522cd-170">추가 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-170">More information</span></span>    |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="522cd-171">5.0</span><span class="sxs-lookup"><span data-stu-id="522cd-171">5.0</span></span>               | <span data-ttu-id="522cd-172">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="522cd-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="522cd-173">X64</span><span class="sxs-lookup"><span data-stu-id="522cd-173">x64</span></span> | [<span data-ttu-id="522cd-174">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) |
| <span data-ttu-id="522cd-175">3.1</span><span class="sxs-lookup"><span data-stu-id="522cd-175">3.1</span></span>               | <span data-ttu-id="522cd-176">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="522cd-176">High Sierra (10.13+)</span></span>  | <span data-ttu-id="522cd-177">X64</span><span class="sxs-lookup"><span data-stu-id="522cd-177">x64</span></span> | [<span data-ttu-id="522cd-178">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="522cd-179">3.0</span><span class="sxs-lookup"><span data-stu-id="522cd-179">3.0</span></span>               | <span data-ttu-id="522cd-180">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="522cd-180">High Sierra (10.13+)</span></span>  | <span data-ttu-id="522cd-181">X64</span><span class="sxs-lookup"><span data-stu-id="522cd-181">x64</span></span> | [<span data-ttu-id="522cd-182">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="522cd-183">2.2</span><span class="sxs-lookup"><span data-stu-id="522cd-183">2.2</span></span>               | <span data-ttu-id="522cd-184">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="522cd-184">Sierra (10.12+)</span></span>       | <span data-ttu-id="522cd-185">X64</span><span class="sxs-lookup"><span data-stu-id="522cd-185">x64</span></span> | [<span data-ttu-id="522cd-186">추가 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-186">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="522cd-187">2.1</span><span class="sxs-lookup"><span data-stu-id="522cd-187">2.1</span></span>               | <span data-ttu-id="522cd-188">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="522cd-188">Sierra (10.12+)</span></span>       | <span data-ttu-id="522cd-189">X64</span><span class="sxs-lookup"><span data-stu-id="522cd-189">x64</span></span> | [<span data-ttu-id="522cd-190">추가 정보</span><span class="sxs-lookup"><span data-stu-id="522cd-190">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="522cd-191">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-191">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="522cd-192">이 요구 사항은 .NET 런타임, .NET SDK, .NET으로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-192">This requirement applies to the .NET runtime, .NET SDK, and software created with .NET.</span></span>

<span data-ttu-id="522cd-193">.NET 5.0, .NET Core 3.1, 3.0, 2.1용 런타임 및 SDK 설치 관리자는 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-193">The runtime and SDK installers for .NET 5.0 and .NET Core 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="522cd-194">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-194">Prior released versions aren't notarized.</span></span> <span data-ttu-id="522cd-195">공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-195">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="522cd-197">공증 요구 사항이 적용됨에 따라 .NET(및 .NET 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="522cd-197">For more information about how enforced-notarization affects .NET (and your .NET apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="522cd-198">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="522cd-198">libgdiplus</span></span>

<span data-ttu-id="522cd-199">*System.Drawing.Common* 어셈블리를 사용하는 .NET 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-199">.NET applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="522cd-200">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-200">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="522cd-201">*brew* 를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-201">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="522cd-202">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-202">Install with an installer</span></span>

<span data-ttu-id="522cd-203">macOS에는 .NET 5.0 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 관리자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-203">macOS has standalone installers that can be used to install the .NET 5.0 SDK:</span></span>

- [<span data-ttu-id="522cd-204">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="522cd-204">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/5.0)

## <a name="download-and-manually-install"></a><span data-ttu-id="522cd-205">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-205">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="522cd-206">.NET용 macOS 설치 관리자 대신 SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-206">As an alternative to the macOS installers for .NET, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="522cd-207">수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-207">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="522cd-208">개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-208">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="522cd-209">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-209">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="522cd-210">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-210">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="522cd-211">✔️ [.NET 5.0 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="522cd-211">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="522cd-212">✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="522cd-212">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="522cd-213">✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="522cd-213">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="522cd-214">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="522cd-214">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="522cd-215">그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET에서 사용된 변수를 설정하고 .NET이 PATH에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-215">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="522cd-216">런타임을 추출하고 터미널에서 .NET CLI 명령을 사용할 수 있도록 하려면 먼저 .NET 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-216">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="522cd-217">그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-217">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="522cd-218">보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-218">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="522cd-219">**다음 명령을 사용하여 다운로드한 런타임 또는 SDK를 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="522cd-219">**Use the following commands to extract the runtime or SDK that you downloaded.**</span></span> <span data-ttu-id="522cd-220">`DOTNET_FILE` 값을 파일 이름으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-220">Remember to change the `DOTNET_FILE` value to your file name:</span></span>

```bash
DOTNET_FILE=dotnet-sdk-5.0.102-linux-x64.tar.gz
export DOTNET_ROOT=$HOME/dotnet

mkdir -p "$DOTNET_ROOT" && tar zxf "$DOTNET_FILE" -C "$DOTNET_ROOT"

export PATH=$PATH:$DOTNET_ROOT
```

> [!TIP]
> <span data-ttu-id="522cd-221">이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET CLI 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-221">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="522cd-222">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-222">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="522cd-223">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-223">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="522cd-224">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="522cd-224">For example:</span></span>
>
> - <span data-ttu-id="522cd-225">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="522cd-225">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="522cd-226">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="522cd-226">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="522cd-227">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="522cd-227">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="522cd-228">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-228">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="522cd-229">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-229">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="522cd-230">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-230">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="522cd-231">이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-231">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="522cd-232">Mac용 Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-232">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="522cd-233">Mac용 Visual Studio는 **.NET** 워크로드가 선택된 경우 .NET SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-233">Visual Studio for Mac installs the .NET SDK when the **.NET** workload is selected.</span></span> <span data-ttu-id="522cd-234">macOS에서 .NET 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="522cd-234">To get started with .NET development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

| <span data-ttu-id="522cd-235">.NET SDK 버전</span><span class="sxs-lookup"><span data-stu-id="522cd-235">.NET SDK version</span></span>      | <span data-ttu-id="522cd-236">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="522cd-236">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="522cd-237">5.0</span><span class="sxs-lookup"><span data-stu-id="522cd-237">5.0</span></span>                   | <span data-ttu-id="522cd-238">Mac용 Visual Studio 2019 버전 8.8 이상</span><span class="sxs-lookup"><span data-stu-id="522cd-238">Visual Studio 2019 for Mac version 8.8 or higher.</span></span> |
| <span data-ttu-id="522cd-239">3.1</span><span class="sxs-lookup"><span data-stu-id="522cd-239">3.1</span></span>                   | <span data-ttu-id="522cd-240">Mac용 Visual Studio 2019 버전 8.4 이상</span><span class="sxs-lookup"><span data-stu-id="522cd-240">Visual Studio 2019 for Mac version 8.4 or higher.</span></span> |
| <span data-ttu-id="522cd-241">2.1</span><span class="sxs-lookup"><span data-stu-id="522cd-241">2.1</span></span>                   | <span data-ttu-id="522cd-242">Mac용 Visual Studio 2019 버전 8.0 이상</span><span class="sxs-lookup"><span data-stu-id="522cd-242">Visual Studio 2019 for Mac version 8.0 or higher.</span></span> |

<span data-ttu-id="522cd-243">[![macOS .NET 워크로드 기능이 있는 Mac용 Visual Studio 2019](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="522cd-243">[![macOS Visual Studio 2019 for Mac with .NET workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="522cd-244">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-244">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="522cd-245">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-245">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="522cd-246">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-246">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="522cd-247">Visual Studio Code에 Visual Studio처럼 자동화된 .NET 설치 관리자가 포함되지 않은 경우 간편하게 .NET 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-247">While Visual Studio Code doesn't come with an automated .NET installer like Visual Studio does, adding .NET support is simple.</span></span>

01. <span data-ttu-id="522cd-248">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="522cd-248">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="522cd-249">[.NET SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="522cd-249">[Download and install the .NET SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="522cd-250">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="522cd-250">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="522cd-251">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="522cd-251">Install with bash automation</span></span>

<span data-ttu-id="522cd-252">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-252">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="522cd-253">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-253">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="522cd-254">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-254">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="522cd-255">`current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-255">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="522cd-256">런타임을 설치하려면 `runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-256">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="522cd-257">포함하지 않을 경우 스크립트가 [SDK](./windows.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-257">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 5.0 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="522cd-258">이전 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-258">The previous command installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="522cd-259">ASP.NET Core 런타임에는 표준 .NET 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-259">The ASP.NET Core runtime also includes the standard .NET runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="522cd-260">Docker</span><span class="sxs-lookup"><span data-stu-id="522cd-260">Docker</span></span>

<span data-ttu-id="522cd-261">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-261">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="522cd-262">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-262">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="522cd-263">.NET은 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-263">.NET can run in a Docker container.</span></span> <span data-ttu-id="522cd-264">공식 .NET Docker 이미지는 MCR(Microsoft Container Registry)에 게시되며 [Microsoft .NET Core Docker Hub 리포지토리](https://hub.docker.com/_/microsoft-dotnet/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-264">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet/).</span></span> <span data-ttu-id="522cd-265">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-265">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="522cd-266">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-266">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="522cd-267">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-aspnet)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="522cd-267">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="522cd-268">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="522cd-268">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="522cd-269">다음 단계</span><span class="sxs-lookup"><span data-stu-id="522cd-269">Next steps</span></span>

- <span data-ttu-id="522cd-270">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-macos)</span><span class="sxs-lookup"><span data-stu-id="522cd-270">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="522cd-271">[macOS Catalina 공증 관련 사항](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="522cd-271">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="522cd-272">[자습서: macOS에서 시작](../tutorials/with-visual-studio-mac.md)</span><span class="sxs-lookup"><span data-stu-id="522cd-272">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="522cd-273">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="522cd-273">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="522cd-274">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="522cd-274">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
