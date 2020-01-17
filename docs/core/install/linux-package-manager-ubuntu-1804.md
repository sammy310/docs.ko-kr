---
title: Ubuntu 18.04에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Ubuntu 18.04에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a8e92cab30302c5636d23f098eb60637141545ca
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740616"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="ac623-103">Ubuntu 18.04 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="ac623-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ac623-104">이 문서에서는 패키지 관리자를 사용하여 Ubuntu 18.04에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span> <span data-ttu-id="ac623-105">런타임을 설치하려면 .NET Core 런타임과 ASP.NET Core 런타임이 모두 포함된 [ASP.NET Core 런타임](#install-the-aspnet-core-runtime)을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="ac623-106">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="ac623-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="ac623-107">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ac623-108">Microsoft 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="ac623-109">제품 리포지토리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-109">Register the product repository.</span></span>
- <span data-ttu-id="ac623-110">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-110">Install required dependencies.</span></span>

<span data-ttu-id="ac623-111">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ac623-112">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ac623-113">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="ac623-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="ac623-114">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ac623-115">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-115">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ac623-116">**패키지 dotnet-sdk-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac623-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ac623-117">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="ac623-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ac623-118">설치를 위한 제품을 업데이트하고, ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="ac623-119">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-119">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ac623-120">**패키지 aspnetcore-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac623-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ac623-121">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="ac623-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="ac623-122">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ac623-123">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-123">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="ac623-124">**패키지 dotnet-runtime-3.1을 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 [패키지 관리자 문제 해결](#troubleshoot-the-package-manager) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac623-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ac623-125">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="ac623-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ac623-126">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ac623-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="ac623-127">**패키지 {.NET Core 패키지}를 찾을 수 없습니다**와 같은 오류 메시지가 표시되는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="ac623-128">이 방법으로 문제가 해결되지 않으면 다음 명령을 사용하여 수동 설치를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac623-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
