---
title: .NET 컨테이너에서 대상으로 지정할 OS
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | .NET 컨테이너에서 대상으로 지정할 OS
ms.date: 01/13/2021
ms.openlocfilehash: b128a7b98d7f46034a56314bd8cc6b4f5731f121
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957912"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="d31e9-103">.NET 컨테이너에서 대상으로 지정할 OS</span><span class="sxs-lookup"><span data-stu-id="d31e9-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="d31e9-104">Docker에서 지원하는 운영 체제의 다양함과 .NET Framework 및 .NET 5 간 차이를 고려해 보면 사용하는 프레임워크에 따라 특정 OS와 특정 버전을 목표로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET 5, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="d31e9-105">Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="d31e9-106">해당 Windows 버전은 각각 .NET Framework나 .NET 5에서 필요할 수 있는 다양한 특성(Windows Server Core의 IIS와 Nano Server의 Kestrel 같은 자체 호스팅 웹 서버)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET 5, respectively.</span></span>

<span data-ttu-id="d31e9-107">Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="d31e9-108">그림 3-1에서는 사용하는 .NET 프레임워크에 따라 가능한 OS 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-108">In Figure 3-1, you can see the possible OS version depending on the .NET framework used.</span></span>

![.NET 컨테이너에 사용할 OS를 보여 주는 다이어그램](./media/net-container-os-targets/targeting-operating-systems.png)

<span data-ttu-id="d31e9-110">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="d31e9-110">**Figure 3-1.**</span></span> <span data-ttu-id="d31e9-111">.NET framework의 버전에 따라 대상으로 하는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="d31e9-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="d31e9-112">레거시 .NET Framework 애플리케이션을 배포할 때는 레거시 앱 및 IIS와 호환되지만 더 큰 이미지를 가지는 Windows Server Core를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-112">When deploying legacy .NET Framework applications you have to target Windows Server Core, compatible with legacy apps and IIS, but it has a larger image.</span></span> <span data-ttu-id="d31e9-113">.NET 5 애플리케이션을 배포할 때는 클라우드에 최적화되고 Kestrel을 사용하며 더 규모가 작으면서 더 빠르게 시작하는 Windows Nano Server를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-113">When deploying .NET 5 applications, you can target Windows Nano Server, which is cloud optimized, uses Kestrel and is smaller and starts faster.</span></span> <span data-ttu-id="d31e9-114">또한 Debian, Alpine 등을 지원하는 Linux를 대상으로 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-114">You can also target Linux, supporting Debian, Alpine, and others.</span></span> <span data-ttu-id="d31e9-115">Kestrel을 사용하고 더 규모가 작으며 더 빠르게 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-115">Also uses Kestrel, is smaller, and starts faster.</span></span>

<span data-ttu-id="d31e9-116">다른 Linux 배포판을 사용하려 하거나 Microsoft에서 제공하지 않는 버전 이미지가 필요한 경우 자체 Docker 이미지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-116">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="d31e9-117">예를 들어 .NET Framework 및Windows Server Core에서 실행되는 기존 ASP.NET Core를 통해 이미지를 만들 수 있으나 Docker에는 그렇게 일반적인 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-117">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="d31e9-118">Dockerfile 파일에 이미지 이름을 추가할 때는 다음 예제에서처럼 사용하는 태그에 따라 운영 체제와 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-118">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="d31e9-119">이미지</span><span class="sxs-lookup"><span data-stu-id="d31e9-119">Image</span></span> | <span data-ttu-id="d31e9-120">주석</span><span class="sxs-lookup"><span data-stu-id="d31e9-120">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="d31e9-121">mcr.microsoft.com/dotnet/runtime:5.0</span><span class="sxs-lookup"><span data-stu-id="d31e9-121">mcr.microsoft.com/dotnet/runtime:5.0</span></span> | <span data-ttu-id="d31e9-122">.NET 5 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-122">.NET 5 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="d31e9-123">mcr.microsoft.com/dotnet/aspnet:5.0</span><span class="sxs-lookup"><span data-stu-id="d31e9-123">mcr.microsoft.com/dotnet/aspnet:5.0</span></span> | <span data-ttu-id="d31e9-124">ASP.NET Core 5.0 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-124">ASP.NET Core 5.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="d31e9-125">aspnetcore 이미지에는 ASP.NET Core에 대한 몇 가지 최적화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31e9-125">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="d31e9-126">mcr.microsoft.com/dotnet/aspnet:5.0-buster-slim</span><span class="sxs-lookup"><span data-stu-id="d31e9-126">mcr.microsoft.com/dotnet/aspnet:5.0-buster-slim</span></span> | <span data-ttu-id="d31e9-127">Linux Debian 배포판의 .NET 5 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="d31e9-127">.NET 5 runtime-only on Linux Debian distro</span></span> |
| <span data-ttu-id="d31e9-128">mcr.microsoft.com/dotnet/aspnet:5.0-nanoserver-1809</span><span class="sxs-lookup"><span data-stu-id="d31e9-128">mcr.microsoft.com/dotnet/aspnet:5.0-nanoserver-1809</span></span> | <span data-ttu-id="d31e9-129">Windows Nano Server(Windows Server 버전 1809)의 .NET 5 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="d31e9-129">.NET 5 runtime-only on Windows Nano Server (Windows Server version 1809)</span></span> |

> [!div class="step-by-step"]
> <span data-ttu-id="d31e9-130">[이전](container-framework-choice-factors.md)
> [다음](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="d31e9-130">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
