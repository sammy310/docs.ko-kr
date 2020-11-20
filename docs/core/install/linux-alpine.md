---
title: Alpine에 .NET 설치 - .NET
description: Alpine에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506837"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="15ce4-103">Alpine에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="15ce4-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="15ce4-104">이 문서에서는 Alpine에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="15ce4-105">Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="15ce4-106">그러나 이러한 지침은 지원되지 않더라도 해당 버전에서 .NET을 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="15ce4-107">Alpine용 설치 관리자는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-107">There are no installers for Alpine.</span></span> <span data-ttu-id="15ce4-108">[설치 스크립트](#scripted-install)를 사용하거나 [수동 설치](#manual-install) 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="15ce4-109">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="15ce4-109">Supported distributions</span></span>

<span data-ttu-id="15ce4-110">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Alpine 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-110">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="15ce4-111">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Alpine 버전이 지원 종료에 도달](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="15ce4-112">✔️는 Alpine 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-112">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="15ce4-113">❌는 Alpine 또는 .NET 버전이 해당 Alpine 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-113">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="15ce4-114">Alpine 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-114">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="15ce4-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="15ce4-115">Alpine</span></span>  | <span data-ttu-id="15ce4-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-116">.NET Core 2.1</span></span> | <span data-ttu-id="15ce4-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-117">.NET Core 3.1</span></span> | <span data-ttu-id="15ce4-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-118">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="15ce4-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="15ce4-119">✔️ 3.12</span></span> | <span data-ttu-id="15ce4-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-120">✔️ 2.1</span></span>        | <span data-ttu-id="15ce4-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-121">✔️ 3.1</span></span>        | <span data-ttu-id="15ce4-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-122">✔️ 5.0</span></span> |
| <span data-ttu-id="15ce4-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="15ce4-123">✔️ 3.11</span></span> | <span data-ttu-id="15ce4-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-124">✔️ 2.1</span></span>        | <span data-ttu-id="15ce4-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-125">✔️ 3.1</span></span>        | <span data-ttu-id="15ce4-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-126">✔️ 5.0</span></span> |
| <span data-ttu-id="15ce4-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="15ce4-127">✔️ 3.10</span></span> | <span data-ttu-id="15ce4-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-128">✔️ 2.1</span></span>        | <span data-ttu-id="15ce4-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-129">✔️ 3.1</span></span>        | <span data-ttu-id="15ce4-130">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-130">❌ 5.0</span></span> |
| <span data-ttu-id="15ce4-131">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="15ce4-131">❌ 3.9</span></span>  | <span data-ttu-id="15ce4-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-132">✔️ 2.1</span></span>        | <span data-ttu-id="15ce4-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-133">✔️ 3.1</span></span>        | <span data-ttu-id="15ce4-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-134">❌ 5.0</span></span> |
| <span data-ttu-id="15ce4-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="15ce4-135">❌ 3.8</span></span>  | <span data-ttu-id="15ce4-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-136">✔️ 2.1</span></span>        | <span data-ttu-id="15ce4-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="15ce4-137">✔️ 3.1</span></span>        | <span data-ttu-id="15ce4-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-138">❌ 5.0</span></span> |

<span data-ttu-id="15ce4-139">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-139">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="15ce4-140">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="15ce4-141">3.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-141">3.0</span></span>
- <span data-ttu-id="15ce4-142">2.2</span><span class="sxs-lookup"><span data-stu-id="15ce4-142">2.2</span></span>
- <span data-ttu-id="15ce4-143">2.0</span><span class="sxs-lookup"><span data-stu-id="15ce4-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="15ce4-144">종속성</span><span class="sxs-lookup"><span data-stu-id="15ce4-144">Dependencies</span></span>

<span data-ttu-id="15ce4-145">Alpine Linux에서 .NET을 사용하려면 다음 종속성이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ce4-145">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="15ce4-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="15ce4-146">icu-libs</span></span>
- <span data-ttu-id="15ce4-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="15ce4-147">krb5-libs</span></span>
- <span data-ttu-id="15ce4-148">libgcc</span><span class="sxs-lookup"><span data-stu-id="15ce4-148">libgcc</span></span>
- <span data-ttu-id="15ce4-149">libintl</span><span class="sxs-lookup"><span data-stu-id="15ce4-149">libintl</span></span>
- <span data-ttu-id="15ce4-150">libssl1.1(Alpine v3.9 이상)</span><span class="sxs-lookup"><span data-stu-id="15ce4-150">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="15ce4-151">libssl1.0(Alpine v3.8 이하)</span><span class="sxs-lookup"><span data-stu-id="15ce4-151">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="15ce4-152">libstdc++</span><span class="sxs-lookup"><span data-stu-id="15ce4-152">libstdc++</span></span>
- <span data-ttu-id="15ce4-153">zlib</span><span class="sxs-lookup"><span data-stu-id="15ce4-153">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="15ce4-154">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="15ce4-154">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="15ce4-155">수동 설치</span><span class="sxs-lookup"><span data-stu-id="15ce4-155">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="15ce4-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="15ce4-156">Next steps</span></span>

- [<span data-ttu-id="15ce4-157">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="15ce4-157">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
