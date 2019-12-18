---
title: Fedora 29에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Fedora 29에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 1cd761e323467ef34fdad58de7385c1ca7b2c14a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998932"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="63c15-103">Fedora 29 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="63c15-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="63c15-104">이 문서에서는 패키지 관리자를 사용하여 Fedora 29에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span> <span data-ttu-id="63c15-105">런타임을 설치하려면 .NET Core 런타임과 ASP.NET Core 런타임이 모두 포함된 [ASP.NET Core 런타임](#install-the-aspnet-core-runtime)을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="63c15-106">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="63c15-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="63c15-107">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="63c15-108">Microsoft 키 등록</span><span class="sxs-lookup"><span data-stu-id="63c15-108">Register the Microsoft key</span></span>
- <span data-ttu-id="63c15-109">제품 리포지토리 등록</span><span class="sxs-lookup"><span data-stu-id="63c15-109">register the product repository</span></span>
- <span data-ttu-id="63c15-110">필수 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="63c15-110">Install required dependencies</span></span>

<span data-ttu-id="63c15-111">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="63c15-112">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="63c15-113">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="63c15-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="63c15-114">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="63c15-115">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="63c15-116">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="63c15-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="63c15-117">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="63c15-118">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="63c15-119">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="63c15-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="63c15-120">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="63c15-121">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="63c15-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="63c15-122">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="63c15-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
