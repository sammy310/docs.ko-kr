---
title: openSUSE 15에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 openSUSE 15에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740674"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="9baef-103">openSUSE 15 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="9baef-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9baef-104">이 문서에서는 패키지 관리자를 사용하여 openSUSE 15에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="9baef-105">런타임을 설치하려면 .NET Core 런타임과 ASP.NET Core 런타임이 모두 포함된 [ASP.NET Core 런타임](#install-the-aspnet-core-runtime)을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="9baef-106">Microsoft 키 및 피드 등록</span><span class="sxs-lookup"><span data-stu-id="9baef-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="9baef-107">.NET을 설치하기 전에 먼저 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9baef-108">Microsoft 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="9baef-109">제품 리포지토리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-109">Register the product repository.</span></span>
- <span data-ttu-id="9baef-110">필수 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-110">Install required dependencies.</span></span>

<span data-ttu-id="9baef-111">이 작업은 머신당 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9baef-112">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="9baef-113">.NET Core 3.1 종속성 오류</span><span class="sxs-lookup"><span data-stu-id="9baef-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="9baef-114">OpenSUSE에 대한 .NET Core 3.1 패키지 피드에 **krb5** 종속성 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="9baef-115">.NET Core 3.1 또는 ASP.NET Core 3.1을 설치하기 전에 다음 명령을 사용하여 올바른 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9baef-116">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="9baef-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="9baef-117">설치를 위한 제품을 업데이트하고, .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9baef-118">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9baef-119">OpenSUSE에 대한 .NET Core 3.1 패키지 피드에 **krb5** 종속성 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="9baef-120">다음 명령을 사용하여 올바른 종속성을 설치한 다음 .NET Core 3.1 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9baef-121">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="9baef-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9baef-122">설치를 위한 제품을 업데이트하고, ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="9baef-123">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9baef-124">OpenSUSE에 대한 .NET Core 3.1 패키지 피드에 **krb5** 종속성 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="9baef-125">다음 명령을 사용하여 올바른 종속성을 설치한 다음 ASP.NET Core 3.1 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9baef-126">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="9baef-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="9baef-127">설치를 위한 제품을 업데이트하고, .NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9baef-128">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9baef-129">OpenSUSE에 대한 .NET Core 3.1 패키지 피드에 **krb5** 종속성 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="9baef-130">다음 명령을 사용하여 올바른 종속성을 설치한 다음 .NET Core 3.1 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9baef-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9baef-131">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="9baef-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
