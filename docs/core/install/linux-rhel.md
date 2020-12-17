---
title: RHEL에 .NET 설치 - .NET
description: RHEL에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851642"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="8718e-103">RHEL에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="8718e-104">.NET은 RHEL에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="8718e-105">이 문서에서는 RHEL에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="8718e-106">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="8718e-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="8718e-107">RHEL의 Red Hat에서 .NET을 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="8718e-108">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8718e-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="8718e-109">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="8718e-109">Supported distributions</span></span>

<span data-ttu-id="8718e-110">다음 표는 RHEL 7과 RHEL 8에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="8718e-111">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 RHEL 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="8718e-112">✔️는 RHEL 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="8718e-113">❌는 RHEL 또는 .NET 버전이 해당 RHEL 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="8718e-114">RHEL 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="8718e-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="8718e-115">RHEL</span></span>                     | <span data-ttu-id="8718e-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8718e-116">.NET Core 2.1</span></span> | <span data-ttu-id="8718e-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8718e-117">.NET Core 3.1</span></span> | <span data-ttu-id="8718e-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8718e-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="8718e-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="8718e-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="8718e-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="8718e-120">✔️ 2.1</span></span>        | <span data-ttu-id="8718e-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="8718e-121">✔️ 3.1</span></span>        | <span data-ttu-id="8718e-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="8718e-122">✔️ 5.0</span></span> |
| <span data-ttu-id="8718e-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="8718e-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="8718e-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="8718e-124">✔️ 2.1</span></span>        | <span data-ttu-id="8718e-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="8718e-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="8718e-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="8718e-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="8718e-127">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="8718e-128">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="8718e-129">3.0</span><span class="sxs-lookup"><span data-stu-id="8718e-129">3.0</span></span>
- <span data-ttu-id="8718e-130">2.2</span><span class="sxs-lookup"><span data-stu-id="8718e-130">2.2</span></span>
- <span data-ttu-id="8718e-131">2.0</span><span class="sxs-lookup"><span data-stu-id="8718e-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="8718e-132">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="8718e-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="8718e-133">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="8718e-133">How to install other versions</span></span>

<span data-ttu-id="8718e-134">.NET의 다른 릴리스를 설치하는 데 필요한 단계에 대해서는 [.NET용 Red Hat 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8718e-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="8718e-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="8718e-135">RHEL 8 ✔️</span></span>

<span data-ttu-id="8718e-136">.NET은 RHEL 8의 AppStream 리포지토리에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-136">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="8718e-137">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8718e-137">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="8718e-138">다음 명령은 `scl-utils` 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-138">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="8718e-139">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-139">Install the SDK</span></span>

<span data-ttu-id="8718e-140">.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-140">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="8718e-141">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-141">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="8718e-142">.NET SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-142">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="8718e-143">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet50`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-143">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="8718e-144">`rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-144">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="8718e-145">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-145">Install the runtime</span></span>

<span data-ttu-id="8718e-146">.NET 런타임을 사용하면 런타임을 포함하지 않았던 .NET으로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-146">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="8718e-147">아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-147">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="8718e-148">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-148">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="8718e-149">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet50`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-149">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="8718e-150">`rh-dotnet50`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-150">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="8718e-151">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet50-aspnetcore-runtime-5.0`을 `rh-dotnet50-dotnet-runtime-5.0`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-151">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="8718e-152">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8718e-152">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="8718e-153">다음 명령은 `scl-utils` 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-153">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="8718e-154">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-154">Install the SDK</span></span>

<span data-ttu-id="8718e-155">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-155">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="8718e-156">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-156">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="8718e-157">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-157">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="8718e-158">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-158">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="8718e-159">예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-159">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="8718e-160">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-160">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="8718e-161">`rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-161">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="8718e-162">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-162">Install the runtime</span></span>

<span data-ttu-id="8718e-163">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-163">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="8718e-164">아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-164">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="8718e-165">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-165">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="8718e-166">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-166">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="8718e-167">예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-167">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="8718e-168">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-168">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="8718e-169">`rh-dotnet31`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-169">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="8718e-170">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet31-aspnetcore-runtime-3.1`을 `rh-dotnet31-dotnet-runtime-3.1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8718e-170">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="8718e-171">Snap</span><span class="sxs-lookup"><span data-stu-id="8718e-171">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="8718e-172">종속성</span><span class="sxs-lookup"><span data-stu-id="8718e-172">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="8718e-173">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-173">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="8718e-174">수동 설치</span><span class="sxs-lookup"><span data-stu-id="8718e-174">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="8718e-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8718e-175">Next steps</span></span>

- [<span data-ttu-id="8718e-176">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8718e-176">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
