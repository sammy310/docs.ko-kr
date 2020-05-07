---
title: Fedora 32에 .NET Core 설치 - 패키지 관리자 - .NET Core
description: 패키지 관리자를 사용하여 Fedora 32에 .NET Core SDK 및 런타임을 설치합니다.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624953"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="fd085-103">Fedora 32 패키지 관리자 - .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="fd085-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="fd085-104">이 문서에서는 패키지 관리자를 사용하여 Fedora 32에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="fd085-105">Fedora 32부터는 Fedora의 기본 패키지 리포지토리에서 .NET Core 3.1을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="fd085-106">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="fd085-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="fd085-107">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="fd085-108">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="fd085-109">ASP.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="fd085-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="fd085-110">ASP.NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="fd085-111">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="fd085-112">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="fd085-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="fd085-113">.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="fd085-114">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fd085-115">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="fd085-115">How to install other versions</span></span>

<span data-ttu-id="fd085-116">다른 버전의 .NET Core를 설치하려면 [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) 또는 [.NET Core 런타임](runtime.md?pivots=os-linux#download-and-manually-install)을 수동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd085-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
