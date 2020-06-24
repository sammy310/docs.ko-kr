---
title: RHEL에 .NET Core 설치 - .NET Core
description: RHEL에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7ae55f881cd0c877cf1db24be7a4ee23320e21a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602797"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="31d21-103">RHEL에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="31d21-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="31d21-104">.NET Core는 RHEL에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="31d21-105">이 문서에서는 RHEL에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="31d21-106">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="31d21-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="31d21-107">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="31d21-108">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31d21-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="31d21-109">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="31d21-109">Supported distributions</span></span>

<span data-ttu-id="31d21-110">다음 표는 RHEL 7과 RHEL 8에서 현재 지원되는 .NET Core 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="31d21-111">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 RHEL 버전이 더 이상 지원되지 않을 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="31d21-112">✔️는 RHEL 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="31d21-113">❌는 RHEL 또는 .NET Core 버전이 해당 RHEL 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="31d21-114">RHEL 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="31d21-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="31d21-115">RHEL</span></span>                   | <span data-ttu-id="31d21-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="31d21-116">.NET Core 2.1</span></span> | <span data-ttu-id="31d21-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="31d21-117">.NET Core 3.1</span></span> | <span data-ttu-id="31d21-118">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="31d21-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="31d21-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="31d21-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="31d21-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31d21-120">✔️ 2.1</span></span>        | <span data-ttu-id="31d21-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31d21-121">✔️ 3.1</span></span>        | <span data-ttu-id="31d21-122">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="31d21-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="31d21-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="31d21-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="31d21-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="31d21-124">✔️ 2.1</span></span>        | <span data-ttu-id="31d21-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="31d21-125">✔️ 3.1</span></span>        | <span data-ttu-id="31d21-126">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="31d21-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="31d21-127">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="31d21-128">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="31d21-129">3.0</span><span class="sxs-lookup"><span data-stu-id="31d21-129">3.0</span></span>
- <span data-ttu-id="31d21-130">2.2</span><span class="sxs-lookup"><span data-stu-id="31d21-130">2.2</span></span>
- <span data-ttu-id="31d21-131">2.0</span><span class="sxs-lookup"><span data-stu-id="31d21-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="31d21-132">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="31d21-132">How to install other versions</span></span>

<span data-ttu-id="31d21-133">.NET Core의 다른 릴리스를 설치하는 데 필요한 단계에 대해서는 [.NET Core 관련 Red Hat 문서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31d21-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="31d21-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="31d21-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="31d21-135">.NET Core는 RHEL 8의 AppStream 리포지토리에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="31d21-136">RHEL 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="31d21-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="31d21-137">다음 명령은 `scl-utils` 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="31d21-138">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="31d21-138">Install the SDK</span></span>

<span data-ttu-id="31d21-139">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="31d21-140">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="31d21-141">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="31d21-142">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="31d21-143">예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="31d21-144">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="31d21-145">`rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="31d21-146">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="31d21-146">Install the runtime</span></span>

<span data-ttu-id="31d21-147">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="31d21-148">아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="31d21-149">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="31d21-150">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31-aspnetcore-runtime-3.1`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="31d21-151">예를 들어 `rh-dotnet31-aspnetcore-runtime-3.1`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="31d21-152">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="31d21-153">`rh-dotnet31-aspnetcore-runtime-3.1`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="31d21-154">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet31-aspnetcore-runtime-3.1`을 `rh-dotnet31-dotnet-runtime-3.1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="31d21-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="31d21-155">Snap</span><span class="sxs-lookup"><span data-stu-id="31d21-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="31d21-156">종속성</span><span class="sxs-lookup"><span data-stu-id="31d21-156">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="31d21-157">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="31d21-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="31d21-158">수동 설치</span><span class="sxs-lookup"><span data-stu-id="31d21-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="31d21-159">다음 단계</span><span class="sxs-lookup"><span data-stu-id="31d21-159">Next steps</span></span>

- <span data-ttu-id="31d21-160">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="31d21-160">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
