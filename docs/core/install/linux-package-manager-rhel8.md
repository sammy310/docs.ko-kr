---
title: Linux RHEL 8에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 8에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b564a386eb67b6e414a832ad3bca10d3d09022bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134189"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="26d25-103">RHEL 8 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="26d25-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="26d25-104">이 문서에서는 패키지 관리자를 사용하여 RHEL 8에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="26d25-105">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="26d25-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="26d25-106">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="26d25-107">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26d25-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="26d25-108">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="26d25-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="26d25-109">구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="26d25-110">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="26d25-111">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="26d25-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="26d25-112">구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="26d25-113">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="26d25-114">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="26d25-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="26d25-115">구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="26d25-116">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26d25-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="26d25-117">참조</span><span class="sxs-lookup"><span data-stu-id="26d25-117">See also</span></span>

- [<span data-ttu-id="26d25-118">Red Hat Enterprise Linux 8에서 .NET Core 3.1 사용</span><span class="sxs-lookup"><span data-stu-id="26d25-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
