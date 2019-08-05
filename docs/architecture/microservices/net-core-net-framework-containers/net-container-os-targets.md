---
title: .NET 컨테이너에서 대상으로 지정할 OS
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | .NET 컨테이너에서 대상으로 지정할 OS
ms.date: 01/07/2019
ms.openlocfilehash: 6f160aeba5257722490788271e6f89359342cc0d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675760"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="ed285-103">.NET 컨테이너에서 대상으로 지정할 OS</span><span class="sxs-lookup"><span data-stu-id="ed285-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="ed285-104">Docker에서 지원하는 운영 체제의 다양함과 .NET Framework 및 .NET Core 간 차이를 고려해 보면 사용하는 프레임워크에 따라 특정 OS와 특정 버전을 목표로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="ed285-105">Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="ed285-106">이러한 Windows 버전은 각각 .NET Framework나 .NET Core에서 필요할 수 있는 다양한 특성(Windows Server Core의 IIS와 Nano Server의 Kestrel 같은 자체 호스팅 웹 서버)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="ed285-107">Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="ed285-108">그림 3-1에서는 사용하는 .NET 프레임워크에 따라 가능한 OS 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![레거시 .NET Framework 애플리케이션을 배포할 때는 레거시 앱 및 IIS와 호환되고 더 큰 이미지를 가지는 Windows Server Core를 대상으로 해야 합니다.](./media/image1.png)

<span data-ttu-id="ed285-113">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="ed285-113">**Figure 3-1.**</span></span> <span data-ttu-id="ed285-114">.NET framework의 버전에 따라 대상으로 하는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="ed285-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="ed285-115">다른 Linux 배포판을 사용하려 하거나 Microsoft에서 제공하지 않는 버전 이미지가 필요한 경우 자체 Docker 이미지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="ed285-116">예를 들어 .NET Framework 및Windows Server Core에서 실행되는 기존 ASP.NET Core를 통해 이미지를 만들 수 있으나 Docker에는 그렇게 일반적인 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="ed285-117">Dockerfile 파일에 이미지 이름을 추가할 때는 다음 예제에서처럼 사용하는 태그에 따라 운영 체제와 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ed285-118">이미지</span><span class="sxs-lookup"><span data-stu-id="ed285-118">Image</span></span></th>
<th><span data-ttu-id="ed285-119">설명</span><span class="sxs-lookup"><span data-stu-id="ed285-119">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed285-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="ed285-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span></td>
<td><span data-ttu-id="ed285-121">.NET Core 2.2 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ed285-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="ed285-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span></td>
<td><p><span data-ttu-id="ed285-123">ASP.NET Core 2.2 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></p>
<p><span data-ttu-id="ed285-124">aspnetcore 이미지에는 ASP.NET Core에 대한 몇 가지 최적화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed285-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ed285-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="ed285-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span></td>
<td><span data-ttu-id="ed285-126">Linux Alpine distro의 .NET Core 2.2 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="ed285-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ed285-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="ed285-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span></td>
<td><span data-ttu-id="ed285-128">Windows Nano Server(Windows Server 버전 1803)의 .NET Core 2.2 런타임 전용</span><span class="sxs-lookup"><span data-stu-id="ed285-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span></td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> <span data-ttu-id="ed285-129">[이전](container-framework-choice-factors.md)
> [다음](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="ed285-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
