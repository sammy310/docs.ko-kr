---
title: Alpine에 .NET 설치 - .NET
description: Alpine에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970852"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="31670-103">Alpine에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="31670-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="31670-104">이 문서에서는 Alpine에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31670-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="31670-105">Alpine 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31670-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="31670-106">그러나 이러한 지침은 지원되지 않더라도 해당 버전에서 .NET을 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31670-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a><span data-ttu-id="31670-107">설치</span><span class="sxs-lookup"><span data-stu-id="31670-107">Install</span></span>

<span data-ttu-id="31670-108">설치 프로그램은 Alpine Linux에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31670-108">Installers aren't available for Alpine Linux.</span></span> <span data-ttu-id="31670-109">다음 방법 중 하나를 사용하여 .NET을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31670-109">You must install .NET in one of the following ways:</span></span>

- [<span data-ttu-id="31670-110">Snap 패키지</span><span class="sxs-lookup"><span data-stu-id="31670-110">Snap package</span></span>](linux-snap.md)
- [<span data-ttu-id="31670-111">_install-dotnet.sh_ 스크립트를 통한 설치</span><span class="sxs-lookup"><span data-stu-id="31670-111">Scripted install with _install-dotnet.sh_</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="31670-112">수동 이진 추출</span><span class="sxs-lookup"><span data-stu-id="31670-112">Manual binary extraction</span></span>](linux-scripted-manual.md#manual-install)

## <a name="supported-distributions"></a><span data-ttu-id="31670-113">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="31670-113">Supported distributions</span></span>

<span data-ttu-id="31670-114">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Alpine 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="31670-114">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="31670-115">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Alpine 버전이 지원 종료에 도달](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="31670-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="31670-116">✔️는 Alpine 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31670-116">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="31670-117">❌는 Alpine 또는 .NET 버전이 해당 Alpine 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31670-117">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="31670-118">Alpine 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="31670-118">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="31670-119">Alpine</span><span class="sxs-lookup"><span data-stu-id="31670-119">Alpine</span></span>  | <span data-ttu-id="31670-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-120">.NET Core 2.1</span></span> | <span data-ttu-id="31670-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-121">.NET Core 3.1</span></span> | <span data-ttu-id="31670-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-122">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="31670-123">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="31670-123">✔️ 3.12</span></span> | <span data-ttu-id="31670-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-124">✔️ 2.1</span></span>        | <span data-ttu-id="31670-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-125">✔️ 3.1</span></span>        | <span data-ttu-id="31670-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-126">✔️ 5.0</span></span> |
| <span data-ttu-id="31670-127">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="31670-127">✔️ 3.11</span></span> | <span data-ttu-id="31670-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-128">✔️ 2.1</span></span>        | <span data-ttu-id="31670-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-129">✔️ 3.1</span></span>        | <span data-ttu-id="31670-130">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-130">✔️ 5.0</span></span> |
| <span data-ttu-id="31670-131">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="31670-131">✔️ 3.10</span></span> | <span data-ttu-id="31670-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-132">✔️ 2.1</span></span>        | <span data-ttu-id="31670-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-133">✔️ 3.1</span></span>        | <span data-ttu-id="31670-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-134">❌ 5.0</span></span> |
| <span data-ttu-id="31670-135">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="31670-135">❌ 3.9</span></span>  | <span data-ttu-id="31670-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-136">✔️ 2.1</span></span>        | <span data-ttu-id="31670-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-137">✔️ 3.1</span></span>        | <span data-ttu-id="31670-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-138">❌ 5.0</span></span> |
| <span data-ttu-id="31670-139">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="31670-139">❌ 3.8</span></span>  | <span data-ttu-id="31670-140">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31670-140">✔️ 2.1</span></span>        | <span data-ttu-id="31670-141">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31670-141">✔️ 3.1</span></span>        | <span data-ttu-id="31670-142">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="31670-142">❌ 5.0</span></span> |

<span data-ttu-id="31670-143">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31670-143">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="31670-144">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="31670-144">The downloads for these still remain published:</span></span>

- <span data-ttu-id="31670-145">3.0</span><span class="sxs-lookup"><span data-stu-id="31670-145">3.0</span></span>
- <span data-ttu-id="31670-146">2.2</span><span class="sxs-lookup"><span data-stu-id="31670-146">2.2</span></span>
- <span data-ttu-id="31670-147">2.0</span><span class="sxs-lookup"><span data-stu-id="31670-147">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="31670-148">종속성</span><span class="sxs-lookup"><span data-stu-id="31670-148">Dependencies</span></span>

<span data-ttu-id="31670-149">Alpine Linux에서 .NET을 사용하려면 다음 종속성이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31670-149">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="31670-150">icu-libs</span><span class="sxs-lookup"><span data-stu-id="31670-150">icu-libs</span></span>
- <span data-ttu-id="31670-151">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="31670-151">krb5-libs</span></span>
- <span data-ttu-id="31670-152">libgcc</span><span class="sxs-lookup"><span data-stu-id="31670-152">libgcc</span></span>
- <span data-ttu-id="31670-153">libintl</span><span class="sxs-lookup"><span data-stu-id="31670-153">libintl</span></span>
- <span data-ttu-id="31670-154">libssl1.1(Alpine v3.9 이상)</span><span class="sxs-lookup"><span data-stu-id="31670-154">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="31670-155">libssl1.0(Alpine v3.8 이하)</span><span class="sxs-lookup"><span data-stu-id="31670-155">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="31670-156">libstdc++</span><span class="sxs-lookup"><span data-stu-id="31670-156">libstdc++</span></span>
- <span data-ttu-id="31670-157">zlib</span><span class="sxs-lookup"><span data-stu-id="31670-157">zlib</span></span>

## <a name="next-steps"></a><span data-ttu-id="31670-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="31670-158">Next steps</span></span>

- [<span data-ttu-id="31670-159">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="31670-159">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="31670-160">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="31670-160">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
