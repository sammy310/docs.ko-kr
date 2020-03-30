---
title: CentOS 7에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 CentOS 7에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: d6cec51422dc59b7f667e36001b7db4742b53a6f
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134347"
---
# <a name="centos-7-package-manager---install-net-core"></a><span data-ttu-id="76adb-103">CentOS 7 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="76adb-103">CentOS 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="76adb-104">이 문서에서는 패키지 관리자를 사용하여 CentOS 7에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-104">This article describes how to use a package manager to install .NET Core on CentOS 7.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="76adb-105">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="76adb-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="76adb-106">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="76adb-107">Microsoft 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="76adb-108">제품 리포지토리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-108">Register the product repository.</span></span>
- <span data-ttu-id="76adb-109">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-109">Install required dependencies.</span></span>

<span data-ttu-id="76adb-110">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="76adb-111">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="76adb-112">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="76adb-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="76adb-113">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="76adb-114">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-114">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="76adb-115">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="76adb-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="76adb-116">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="76adb-117">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-117">In your terminal, run the following command.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="76adb-118">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="76adb-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="76adb-119">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="76adb-120">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-120">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="76adb-121">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="76adb-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="76adb-122">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="76adb-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="76adb-123">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76adb-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="76adb-124">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="76adb-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
