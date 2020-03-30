---
title: Ubuntu 18.04에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Ubuntu 18.04에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 6265e9b3299af9b4178dbb5d5da057f98d75a63b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134159"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="82fa9-103">Ubuntu 18.04 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="82fa9-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="82fa9-104">이 문서에서는 패키지 관리자를 사용하여 Ubuntu 18.04에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="82fa9-105">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="82fa9-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="82fa9-106">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="82fa9-107">Microsoft 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="82fa9-108">제품 리포지토리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-108">Register the product repository.</span></span>
- <span data-ttu-id="82fa9-109">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-109">Install required dependencies.</span></span>

<span data-ttu-id="82fa9-110">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="82fa9-111">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="82fa9-112">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="82fa9-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="82fa9-113">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="82fa9-114">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-114">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="82fa9-115">**패키지 dotnet-sdk-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82fa9-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="82fa9-116">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="82fa9-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="82fa9-117">설치를 위한 제품을 업데이트하고, ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="82fa9-118">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-118">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="82fa9-119">**패키지 aspnetcore-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82fa9-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="82fa9-120">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="82fa9-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="82fa9-121">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="82fa9-122">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-122">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="82fa9-123">**패키지 dotnet-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82fa9-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="82fa9-124">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="82fa9-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="82fa9-125">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="82fa9-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="82fa9-126">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="82fa9-127">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="82fa9-127">Unable to locate</span></span>

<span data-ttu-id="82fa9-128">**패키지 {.NET Core 패키지}를 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="82fa9-129">이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82fa9-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="82fa9-130">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="82fa9-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
