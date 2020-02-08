---
title: SLES 15에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 SLES 15에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: f48c131b4250bd04fffc0d815a3500732caacb7c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921040"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="f7571-103">SLES 15 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f7571-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f7571-104">이 문서에서는 패키지 관리자를 사용하여 SLES 15에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span> <span data-ttu-id="f7571-105">런타임을 설치하려면 .NET Core 런타임과 ASP.NET Core 런타임이 모두 포함된 [ASP.NET Core 런타임](#install-the-aspnet-core-runtime)을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="f7571-106">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="f7571-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="f7571-107">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f7571-108">Microsoft 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="f7571-109">제품 리포지토리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-109">Register the product repository.</span></span>
- <span data-ttu-id="f7571-110">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-110">Install required dependencies.</span></span>

<span data-ttu-id="f7571-111">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f7571-112">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f7571-113">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="f7571-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="f7571-114">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f7571-115">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f7571-116">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="f7571-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f7571-117">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f7571-118">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f7571-119">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="f7571-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="f7571-120">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f7571-121">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f7571-122">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="f7571-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f7571-123">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f7571-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="f7571-124">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7571-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f7571-125">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="f7571-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
