---
title: RHEL에 .NET 설치 - .NET
description: RHEL에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 931cad51ff8e35ff16b67ff9b795feb36010a66b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031793"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="f6d76-103">RHEL에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="f6d76-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="f6d76-104">.NET은 RHEL에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="f6d76-105">이 문서에서는 RHEL에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="f6d76-106">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="f6d76-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="f6d76-107">RHEL의 Red Hat에서 .NET을 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="f6d76-108">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d76-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="f6d76-109">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="f6d76-109">Supported distributions</span></span>

<span data-ttu-id="f6d76-110">다음 표는 RHEL 7과 RHEL 8에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="f6d76-111">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 RHEL 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="f6d76-112">✔️는 RHEL 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="f6d76-113">❌는 RHEL 또는 .NET 버전이 해당 RHEL 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="f6d76-114">RHEL 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="f6d76-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="f6d76-115">RHEL</span></span>                     | <span data-ttu-id="f6d76-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-116">.NET Core 2.1</span></span> | <span data-ttu-id="f6d76-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-117">.NET Core 3.1</span></span> | <span data-ttu-id="f6d76-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f6d76-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="f6d76-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="f6d76-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="f6d76-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-120">✔️ 2.1</span></span>        | <span data-ttu-id="f6d76-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-121">✔️ 3.1</span></span>        | <span data-ttu-id="f6d76-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f6d76-122">✔️ 5.0</span></span> |
| <span data-ttu-id="f6d76-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="f6d76-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="f6d76-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-124">✔️ 2.1</span></span>        | <span data-ttu-id="f6d76-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="f6d76-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="f6d76-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="f6d76-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="f6d76-127">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="f6d76-128">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f6d76-129">3.0</span><span class="sxs-lookup"><span data-stu-id="f6d76-129">3.0</span></span>
- <span data-ttu-id="f6d76-130">2.2</span><span class="sxs-lookup"><span data-stu-id="f6d76-130">2.2</span></span>
- <span data-ttu-id="f6d76-131">2.0</span><span class="sxs-lookup"><span data-stu-id="f6d76-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="f6d76-132">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="f6d76-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f6d76-133">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="f6d76-133">How to install other versions</span></span>

<span data-ttu-id="f6d76-134">.NET의 다른 릴리스를 설치하는 데 필요한 단계에 대해서는 [.NET용 Red Hat 설명서](https://access.redhat.com/documentation/net/5.0/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d76-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="f6d76-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="f6d76-135">RHEL 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="f6d76-136">.NET 5.0은 AppStream 리포지토리에서 아직 사용할 수 없지만 .NET Core 3.1은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-136">.NET 5.0 isn't yet available in the AppStream repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="f6d76-137">.NET Core 3.1을 설치하려면 `aspnetcore-runtime-3.1` 또는 `dotnet-sdk-3.1`과 같은 적절한 패키지에서 `dnf install` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-137">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="f6d76-138">다음은 .NET 5.0에 대한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-138">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="f6d76-139">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f6d76-139">RHEL 7 ✔️ .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="f6d76-140">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f6d76-140">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="f6d76-141">다음 명령은 `scl-utils` 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-141">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="f6d76-142">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="f6d76-142">Install the SDK</span></span>

<span data-ttu-id="f6d76-143">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-143">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="f6d76-144">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-144">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f6d76-145">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-145">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="f6d76-146">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-146">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="f6d76-147">예를 들어 `rh-dotnet31`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-147">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="f6d76-148">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-148">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="f6d76-149">`rh-dotnet`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-149">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="f6d76-150">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="f6d76-150">Install the runtime</span></span>

<span data-ttu-id="f6d76-151">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-151">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="f6d76-152">아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-152">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="f6d76-153">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-153">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="f6d76-154">다른 프로그램에 영향을 줄 수 있으므로 Red Hat은 `rh-dotnet31-aspnetcore-runtime-3.1`을 영구적으로 사용 설정하는 것을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-154">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="f6d76-155">예를 들어 `rh-dotnet31-aspnetcore-runtime-3.1`에는 기본 RHEL 버전과 다른 `libcurl` 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-155">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="f6d76-156">이로 인해 다른 버전의 `libcurl`을 예상하지 않은 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-156">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="f6d76-157">`rh-dotnet31-aspnetcore-runtime-3.1`을 영구적으로 사용 설정하려면 다음 줄을 _~/.bashrc_ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-157">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="f6d76-158">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `rh-dotnet31-aspnetcore-runtime-3.1`을 `rh-dotnet31-dotnet-runtime-3.1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f6d76-158">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="f6d76-159">Snap</span><span class="sxs-lookup"><span data-stu-id="f6d76-159">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="f6d76-160">종속성</span><span class="sxs-lookup"><span data-stu-id="f6d76-160">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="f6d76-161">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="f6d76-161">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="f6d76-162">수동 설치</span><span class="sxs-lookup"><span data-stu-id="f6d76-162">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="f6d76-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f6d76-163">Next steps</span></span>

- [<span data-ttu-id="f6d76-164">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="f6d76-164">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
