---
title: macOS에 .NET Core 설치
description: .NET Core를 설치할 수 있는 macOS 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: f946759a57bf2eedd296ecbd55fd3a5a7560638d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538368"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="c5b0e-103">macOS에 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

<span data-ttu-id="c5b0e-107">이 문서에서는 macOS에 .NET Core를 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="c5b0e-108">.NET Core는 런타임과 SDK로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="c5b0e-109">런타임은 .NET Core 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="c5b0e-110">SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="c5b0e-111">.NET Core 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="c5b0e-112">최신 버전의 .NET Core는 3.1입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-112">The latest version of .NET Core is 3.1.</span></span>

> [!div class="button"]
> [<span data-ttu-id="c5b0e-113">.NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="c5b0e-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="c5b0e-114">지원되는 릴리스</span><span class="sxs-lookup"><span data-stu-id="c5b0e-114">Supported releases</span></span>

<span data-ttu-id="c5b0e-115">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 macOS 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="c5b0e-116">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="c5b0e-117">✔️는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="c5b0e-118">❌️는 .NET Core 버전이 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="c5b0e-119">운영 체제</span><span class="sxs-lookup"><span data-stu-id="c5b0e-119">Operating System</span></span>          | <span data-ttu-id="c5b0e-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5b0e-120">.NET Core 2.1</span></span> | <span data-ttu-id="c5b0e-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c5b0e-121">.NET Core 3.1</span></span> | <span data-ttu-id="c5b0e-122">.NET 5 미리 보기</span><span class="sxs-lookup"><span data-stu-id="c5b0e-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c5b0e-123">macOS 10.15 “Catalina”</span><span class="sxs-lookup"><span data-stu-id="c5b0e-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="c5b0e-124">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="c5b0e-125">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="c5b0e-126">✔️ 5.0 미리 보기([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="c5b0e-127">macOS 10.14 “Mojave”</span><span class="sxs-lookup"><span data-stu-id="c5b0e-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="c5b0e-128">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="c5b0e-129">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="c5b0e-130">✔️ 5.0 미리 보기([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="c5b0e-131">macOS 10.13 “High Sierra”</span><span class="sxs-lookup"><span data-stu-id="c5b0e-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="c5b0e-132">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="c5b0e-133">✔️ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="c5b0e-134">✔️ 5.0 미리 보기([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="c5b0e-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="c5b0e-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="c5b0e-136">✔️ 2.1([릴리스 정보][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="c5b0e-137">❌ 3.1([릴리스 정보][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="c5b0e-138">❌ 5.0 미리 보기([릴리스 정보][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="c5b0e-139">지원되지 않는 릴리스</span><span class="sxs-lookup"><span data-stu-id="c5b0e-139">Unsupported releases</span></span>

<span data-ttu-id="c5b0e-140">다음 .NET Core 버전은 ❌ 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="c5b0e-141">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c5b0e-142">3.0([릴리스 정보][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="c5b0e-143">2.2([릴리스 정보][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="c5b0e-144">2.0([릴리스 정보][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="c5b0e-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="c5b0e-145">런타임 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-145">Runtime information</span></span>

<span data-ttu-id="c5b0e-146">런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="c5b0e-147">앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="c5b0e-148">앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="c5b0e-149">macOS에 설치할 수 있는 세 가지 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="c5b0e-150">‘ASP.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="c5b0e-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="c5b0e-151">ASP.NET Core 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="c5b0e-152">.NET Core 런타임을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="c5b0e-153">‘.NET Core 런타임’</span><span class="sxs-lookup"><span data-stu-id="c5b0e-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="c5b0e-154">이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="c5b0e-155">.NET Core 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="c5b0e-156">.NET Core 런타임 다운로드</span><span class="sxs-lookup"><span data-stu-id="c5b0e-156">Download .NET Core Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="c5b0e-157">SDK 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-157">SDK information</span></span>

<span data-ttu-id="c5b0e-158">SDK는 .NET Core 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="c5b0e-159">SDK를 설치하면 ASP.NET Core 및 .NET Core의 두 가지 [런타임](#runtime-information)이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

> [!div class="button"]
> [<span data-ttu-id="c5b0e-160">.NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="c5b0e-160">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="c5b0e-161">종속성</span><span class="sxs-lookup"><span data-stu-id="c5b0e-161">Dependencies</span></span>

<span data-ttu-id="c5b0e-162">.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="c5b0e-163">`+` 기호는 최소 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c5b0e-164">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="c5b0e-164">.NET Core Version</span></span> | <span data-ttu-id="c5b0e-165">macOS</span><span class="sxs-lookup"><span data-stu-id="c5b0e-165">macOS</span></span>                 | <span data-ttu-id="c5b0e-166">아키텍처</span><span class="sxs-lookup"><span data-stu-id="c5b0e-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="c5b0e-167">3.1</span><span class="sxs-lookup"><span data-stu-id="c5b0e-167">3.1</span></span>               | <span data-ttu-id="c5b0e-168">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c5b0e-169">X64</span><span class="sxs-lookup"><span data-stu-id="c5b0e-169">x64</span></span> | [<span data-ttu-id="c5b0e-170">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="c5b0e-171">3.0</span><span class="sxs-lookup"><span data-stu-id="c5b0e-171">3.0</span></span>               | <span data-ttu-id="c5b0e-172">High Sierra(10.13+)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c5b0e-173">X64</span><span class="sxs-lookup"><span data-stu-id="c5b0e-173">x64</span></span> | [<span data-ttu-id="c5b0e-174">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="c5b0e-175">2.2</span><span class="sxs-lookup"><span data-stu-id="c5b0e-175">2.2</span></span>               | <span data-ttu-id="c5b0e-176">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="c5b0e-177">X64</span><span class="sxs-lookup"><span data-stu-id="c5b0e-177">x64</span></span> | [<span data-ttu-id="c5b0e-178">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="c5b0e-179">2.1</span><span class="sxs-lookup"><span data-stu-id="c5b0e-179">2.1</span></span>               | <span data-ttu-id="c5b0e-180">Sierra(10.12+)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="c5b0e-181">X64</span><span class="sxs-lookup"><span data-stu-id="c5b0e-181">x64</span></span> | [<span data-ttu-id="c5b0e-182">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5b0e-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="c5b0e-183">macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="c5b0e-184">이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="c5b0e-185">.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="c5b0e-186">그 전에 릴리스된 버전은 공증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="c5b0e-187">공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="c5b0e-189">공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="c5b0e-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="c5b0e-190">libgdiplus</span></span>

<span data-ttu-id="c5b0e-191">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="c5b0e-192">libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="c5b0e-193">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="c5b0e-194">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-194">Install with an installer</span></span>

<span data-ttu-id="c5b0e-195">macOS에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="c5b0e-196">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="c5b0e-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="c5b0e-197">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="c5b0e-198">.NET Core용 macOS 설치 프로그램의 대안으로, SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="c5b0e-199">수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="c5b0e-200">개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="c5b0e-201">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c5b0e-202">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="c5b0e-203">✔️ [.NET 5.0 미리보기 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="c5b0e-204">✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="c5b0e-205">✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="c5b0e-206">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="c5b0e-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="c5b0e-207">그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET Core에서 사용된 변수를 설정하고 .NET Core가 경로에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="c5b0e-208">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="c5b0e-209">그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="c5b0e-210">보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="c5b0e-211">**다음 명령을 사용하여 런타임을 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5b0e-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="c5b0e-212">**다음 명령을 사용하여 SDK를 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5b0e-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="c5b0e-213">이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET Core CLI 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="c5b0e-214">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="c5b0e-215">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="c5b0e-216">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="c5b0e-216">For example:</span></span>
>
> - <span data-ttu-id="c5b0e-217">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="c5b0e-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="c5b0e-218">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="c5b0e-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="c5b0e-219">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="c5b0e-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="c5b0e-220">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="c5b0e-221">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="c5b0e-222">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="c5b0e-223">이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="c5b0e-224">Mac용 Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="c5b0e-225">Mac용 Visual Studio는 **.NET Core** 워크로드가 선택된 경우 .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="c5b0e-226">macOS에서 .NET Core 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="c5b0e-227">최신 릴리스인 .NET Core 3.1의 경우 Mac용 Visual Studio 8.4를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="c5b0e-228">[![macOS Mac용 Visual Studio 2019 및 .NET Core 워크로드의 특징](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="c5b0e-229">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="c5b0e-230">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="c5b0e-231">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="c5b0e-232">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="c5b0e-233">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="c5b0e-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="c5b0e-234">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c5b0e-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="c5b0e-235">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="c5b0e-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="c5b0e-236">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c5b0e-236">Install with bash automation</span></span>

<span data-ttu-id="c5b0e-237">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c5b0e-238">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c5b0e-239">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c5b0e-240">`current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="c5b0e-241">런타임을 설치하려면 `runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="c5b0e-242">포함하지 않을 경우 스크립트가 [SDK](./windows.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-242">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c5b0e-243">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c5b0e-244">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="c5b0e-245">Docker</span><span class="sxs-lookup"><span data-stu-id="c5b0e-245">Docker</span></span>

<span data-ttu-id="c5b0e-246">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="c5b0e-247">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="c5b0e-248">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="c5b0e-249">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="c5b0e-250">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="c5b0e-251">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="c5b0e-252">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="c5b0e-253">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c5b0e-254">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c5b0e-254">Next steps</span></span>

- <span data-ttu-id="c5b0e-255">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-macos)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="c5b0e-256">[macOS Catalina 공증 관련 사항](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="c5b0e-257">[자습서: macOS에서 시작](../tutorials/with-visual-studio-mac.md)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-257">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="c5b0e-258">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="c5b0e-259">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="c5b0e-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
