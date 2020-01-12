---
title: Linux RHEL 8.1에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714385"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="86d38-103">RHEL 8.1 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="86d38-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="86d38-104">이 문서에서는 패키지 관리자를 사용하여 RHEL 8.1에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="86d38-105">RHEL 8.1에서는 아직 .NET Core 3.1을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="86d38-106">RHEL 8.0은 .NET Core 3.0을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="86d38-107">명령 `yum upgrade`를 사용하여 RHEL 8.1로 업그레이드하세요.</span><span class="sxs-lookup"><span data-stu-id="86d38-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="86d38-108">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="86d38-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="86d38-109">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="86d38-110">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86d38-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="86d38-111">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="86d38-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="86d38-112">구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="86d38-113">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="86d38-114">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="86d38-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="86d38-115">구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="86d38-116">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="86d38-117">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="86d38-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="86d38-118">구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="86d38-119">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86d38-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="86d38-120">참조</span><span class="sxs-lookup"><span data-stu-id="86d38-120">See also</span></span>

- <span data-ttu-id="86d38-121">[Using .NET Core 3.0 on Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)(Red Hat Enterprise Linux 8에서 .NET Core 3.0 사용)</span><span class="sxs-lookup"><span data-stu-id="86d38-121">[Using .NET Core 3.0 on Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)</span></span>
