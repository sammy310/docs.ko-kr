---
title: Linux CentOS 8에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 CentOS 8에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728506"
---
# <a name="centos-8-package-manager---install-net-core"></a><span data-ttu-id="3d62a-103">CentOS 8 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="3d62a-103">CentOS 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="3d62a-104">이 문서에서는 패키지 관리자를 사용하여 CentOS 8에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d62a-104">This article describes how to use a package manager to install .NET Core on CentOS 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="3d62a-105">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="3d62a-105">Install the .NET Core SDK</span></span>

<span data-ttu-id="3d62a-106">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d62a-106">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="3d62a-107">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="3d62a-107">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="3d62a-108">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d62a-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="3d62a-109">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="3d62a-109">Install the .NET Core Runtime</span></span>

<span data-ttu-id="3d62a-110">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d62a-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3d62a-111">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="3d62a-111">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
