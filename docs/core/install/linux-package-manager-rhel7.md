---
title: Linux RHEL 7에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 RHEL 7에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: f17a410ccea1ef4dec32de1d80ef6aac889aa6f3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998908"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="b61e9-103">RHEL 7 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="b61e9-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="b61e9-104">이 문서에서는 패키지 관리자를 사용하여 RHEL 7에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="b61e9-105">RHEL 7에서는 아직 .NET Core 3.1을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="b61e9-106">Red Hat 구독 등록</span><span class="sxs-lookup"><span data-stu-id="b61e9-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="b61e9-107">RHEL의 Red Hat에서 .NET Core를 설치하려면 먼저 Red Hat 구독 관리자를 사용하여 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="b61e9-108">아직 시스템에서 등록하지 않았거나 등록 여부가 확실하지 않다면 [.NET Core용 Red Hat 제품 설명서](https://access.redhat.com/documentation/net_core/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b61e9-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b61e9-109">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="b61e9-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="b61e9-110">구독 관리자를 사용하여 등록했다면 .NET Core SDK를 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="b61e9-111">터미널에서 다음 명령을 실행하여 RHEL 7 dotnet 채널을 사용하도록 설정하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b61e9-112">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="b61e9-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="b61e9-113">구독 관리자를 사용하여 등록했다면 ASP.NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="b61e9-114">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-114">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b61e9-115">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="b61e9-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="b61e9-116">구독 관리자를 사용하여 등록했다면 .NET Core 런타임을 설치하고 사용하도록 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="b61e9-117">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b61e9-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="b61e9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b61e9-118">See also</span></span>

- <span data-ttu-id="b61e9-119">[Using .NET Core 3.0 on Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)(Red Hat Enterprise Linux 7에서 .NET Core 3.0 사용)</span><span class="sxs-lookup"><span data-stu-id="b61e9-119">[Using .NET Core 3.0 on Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)</span></span>
