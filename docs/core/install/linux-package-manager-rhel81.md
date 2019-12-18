---
title: Linux RHEL 8.1에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 3ef639d5b76e81856ec8370d10e098c455ca8b3d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998914"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="bf8eb-103">RHEL 8.1 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="bf8eb-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="bf8eb-104">이 문서에서는 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="bf8eb-105">RHEL 8.1에서는 아직 .NET Core 3.1을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="bf8eb-106">RHEL 8.0은 .NET Core 3.0을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="bf8eb-107">명령 `yum upgrade`를 사용하여 RHEL 8.1로 업그레이드하세요.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="bf8eb-108">RHEL 8.0은 .NET Core 3.0을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-108">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="bf8eb-109">명령 `yum upgrade`를 사용하여 RHEL 8.1로 업그레이드하세요.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-109">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="bf8eb-110">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="bf8eb-110">Register your Red Hat subscription</span></span>

<span data-ttu-id="bf8eb-111">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-111">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="bf8eb-112">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-112">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="bf8eb-113">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="bf8eb-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="bf8eb-114">구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-114">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="bf8eb-115">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-115">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="bf8eb-116">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="bf8eb-116">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="bf8eb-117">구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-117">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="bf8eb-118">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-118">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="bf8eb-119">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="bf8eb-119">Install the .NET Core Runtime</span></span>

<span data-ttu-id="bf8eb-120">구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-120">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="bf8eb-121">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf8eb-121">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="bf8eb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf8eb-122">See also</span></span>

- <span data-ttu-id="bf8eb-123">[Using .NET Core 3.0 on Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)(Red Hat Enterprise Linux 8에서 .NET Core 3.0 사용)</span><span class="sxs-lookup"><span data-stu-id="bf8eb-123">[Using .NET Core 3.0 on Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)</span></span>
