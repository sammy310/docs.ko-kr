---
title: Linux RHEL 8에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 8에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: 8829e842e920e6abd4184b5140f80bb016acace2
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728237"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="024d4-103">RHEL 8 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="024d4-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="024d4-104">이 문서에서는 패키지 관리자를 사용하여 RHEL(Red Hat Enterprise Linux) 8에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-104">This article describes how to use a package manager to install .NET Core on Red Hat Enterprise Linux (RHEL) 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="024d4-105">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="024d4-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="024d4-106">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="024d4-107">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="024d4-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="024d4-108">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="024d4-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="024d4-109">구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="024d4-110">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="024d4-111">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="024d4-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="024d4-112">구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="024d4-113">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-113">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="024d4-114">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="024d4-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="024d4-115">구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="024d4-116">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="024d4-116">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="024d4-117">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="024d4-117">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="see-also"></a><span data-ttu-id="024d4-118">참조</span><span class="sxs-lookup"><span data-stu-id="024d4-118">See also</span></span>

- [<span data-ttu-id="024d4-119">Red Hat Enterprise Linux 8에서 .NET Core 3.1 사용</span><span class="sxs-lookup"><span data-stu-id="024d4-119">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
