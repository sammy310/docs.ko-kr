---
title: Alpine에 .NET Core 설치 - .NET Core
description: Alpine에 .NET Core SDK 및 .NET Core 런타임을 설치하는 다양한 방법을 설명합니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324831"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="2e468-103">Alpine에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="2e468-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="2e468-104">이 문서에서는 Alpine에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="2e468-105">Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET Core가 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="2e468-106">그러나, 이 문서의 지침은 지원되지 않더라도 해당 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="2e468-107">Alpine용 설치 관리자는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-107">There are no installers for Alpine.</span></span> <span data-ttu-id="2e468-108">[설치 스크립트](#scripted-install)를 사용하거나 [수동 설치](#manual-install) 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="2e468-109">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="2e468-109">Supported distributions</span></span>

<span data-ttu-id="2e468-110">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Alpine 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="2e468-111">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Alpine 버전이 지원 종료에 도달](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="2e468-112">✔️는 Alpine 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="2e468-113">❌는 Alpine 또는 .NET Core 버전이 해당 Alpine 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="2e468-114">Alpine 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="2e468-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="2e468-115">Alpine</span></span>                   | <span data-ttu-id="2e468-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-116">.NET Core 2.1</span></span> | <span data-ttu-id="2e468-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-117">.NET Core 3.1</span></span> | <span data-ttu-id="2e468-118">.NET 5 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="2e468-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="2e468-119">✔️ 3.12</span></span>  | <span data-ttu-id="2e468-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-120">✔️ 2.1</span></span>        | <span data-ttu-id="2e468-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-121">✔️ 3.1</span></span>        | <span data-ttu-id="2e468-122">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="2e468-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="2e468-123">✔️ 3.11</span></span>  | <span data-ttu-id="2e468-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-124">✔️ 2.1</span></span>        | <span data-ttu-id="2e468-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-125">✔️ 3.1</span></span>        | <span data-ttu-id="2e468-126">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="2e468-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="2e468-127">✔️ 3.10</span></span>  | <span data-ttu-id="2e468-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-128">✔️ 2.1</span></span>        | <span data-ttu-id="2e468-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-129">✔️ 3.1</span></span>        | <span data-ttu-id="2e468-130">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="2e468-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="2e468-131">✔️ 3.9</span></span>   | <span data-ttu-id="2e468-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-132">✔️ 2.1</span></span>        | <span data-ttu-id="2e468-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-133">✔️ 3.1</span></span>        | <span data-ttu-id="2e468-134">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="2e468-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="2e468-135">❌ 3.8</span></span>   | <span data-ttu-id="2e468-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e468-136">✔️ 2.1</span></span>        | <span data-ttu-id="2e468-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e468-137">❌ 3.1</span></span>        | <span data-ttu-id="2e468-138">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2e468-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="2e468-139">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="2e468-140">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="2e468-141">3.0</span><span class="sxs-lookup"><span data-stu-id="2e468-141">3.0</span></span>
- <span data-ttu-id="2e468-142">2.2</span><span class="sxs-lookup"><span data-stu-id="2e468-142">2.2</span></span>
- <span data-ttu-id="2e468-143">2.0</span><span class="sxs-lookup"><span data-stu-id="2e468-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="2e468-144">종속성</span><span class="sxs-lookup"><span data-stu-id="2e468-144">Dependencies</span></span>

<span data-ttu-id="2e468-145">Alpine Linux에서 .NET Core를 사용하려면 다음 종속성이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e468-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="2e468-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="2e468-146">icu-libs</span></span>
- <span data-ttu-id="2e468-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="2e468-147">krb5-libs</span></span>
- <span data-ttu-id="2e468-148">libintl</span><span class="sxs-lookup"><span data-stu-id="2e468-148">libintl</span></span>
- <span data-ttu-id="2e468-149">libssl1.1(Alpine v3.9 이상)</span><span class="sxs-lookup"><span data-stu-id="2e468-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="2e468-150">libssl1.0(Alpine v3.8)</span><span class="sxs-lookup"><span data-stu-id="2e468-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="2e468-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="2e468-151">libstdc++</span></span>
- <span data-ttu-id="2e468-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="2e468-152">lttng-ust</span></span>
- <span data-ttu-id="2e468-153">numactl(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2e468-153">numactl (optional)</span></span>
- <span data-ttu-id="2e468-154">zlib</span><span class="sxs-lookup"><span data-stu-id="2e468-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="2e468-155">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="2e468-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="2e468-156">수동 설치</span><span class="sxs-lookup"><span data-stu-id="2e468-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="2e468-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2e468-157">Next steps</span></span>

- [<span data-ttu-id="2e468-158">자습서: Visual Studio Code를 사용하여 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="2e468-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
