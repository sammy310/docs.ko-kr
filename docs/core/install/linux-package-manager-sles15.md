---
title: SLES 15에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 SLES 15에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595619"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="38ed8-103">SLES 15 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="38ed8-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="38ed8-104">이 문서에서는 패키지 관리자를 사용하여 SLES 15에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="38ed8-105">Microsoft 리포지토리 키 및 피드 추가</span><span class="sxs-lookup"><span data-stu-id="38ed8-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="38ed8-106">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="38ed8-107">Microsoft 패키지 서명 키를 신뢰할 수 있는 키 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="38ed8-108">패키지 관리자에 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="38ed8-109">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-109">Install required dependencies.</span></span>

<span data-ttu-id="38ed8-110">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="38ed8-111">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="38ed8-112">현재 SLES 15 Microsoft 리포지토리 설치 패키지는 *microsoft-prod.repo* 파일을 잘못된 디렉터리에 설치하므로 zypper가 .NET Core 패키지를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="38ed8-113">이 문제를 해결하려면 올바른 디렉터리에 symlink를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="38ed8-114">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="38ed8-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="38ed8-115">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="38ed8-116">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="38ed8-117">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="38ed8-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="38ed8-118">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="38ed8-119">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="38ed8-120">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="38ed8-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="38ed8-121">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="38ed8-122">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="38ed8-123">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="38ed8-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="38ed8-124">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="38ed8-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="38ed8-125">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38ed8-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="38ed8-126">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="38ed8-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
