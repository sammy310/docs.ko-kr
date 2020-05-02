---
title: Fedora 31에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Fedora 31에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 56e5789132af2aa1171ea51698ae55d1eea5d457
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645297"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="fde31-103">Fedora 31 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="fde31-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="fde31-104">이 문서에서는 패키지 관리자를 사용하여 Fedora 31에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="fde31-105">Microsoft 리포지토리 키 및 피드 추가</span><span class="sxs-lookup"><span data-stu-id="fde31-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="fde31-106">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="fde31-107">Microsoft 패키지 서명 키를 신뢰할 수 있는 키 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="fde31-108">패키지 관리자에 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="fde31-109">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-109">Install required dependencies.</span></span>

<span data-ttu-id="fde31-110">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="fde31-111">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="fde31-112">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="fde31-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="fde31-113">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="fde31-114">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="fde31-115">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="fde31-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="fde31-116">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="fde31-117">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="fde31-118">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="fde31-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="fde31-119">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="fde31-120">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fde31-121">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="fde31-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="fde31-122">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fde31-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="fde31-123">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fde31-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="fde31-124">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="fde31-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
