---
title: Docker 컨테이너에 대해 .NET 5와 .NET Framework 중에 선택
description: 컨테이너화된 .NET 애플리케이션에 대한 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET 5와 .NET Framework 중에 선택
ms.date: 02/02/2021
ms.openlocfilehash: 5c3d4eff00399c8a6a041daaa71cf9fe5c9d854f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665161"
---
# <a name="choosing-between-net-5-and-net-framework-for-docker-containers"></a><span data-ttu-id="5942e-103">Docker 컨테이너에 대해 .NET 5와 .NET Framework 중에 선택</span><span class="sxs-lookup"><span data-stu-id="5942e-103">Choosing Between .NET 5 and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="5942e-104">.NET에서 서버 쪽 컨테이너화된 Docker 애플리케이션을 빌드하는 데 지원되는 두 가지 프레임워크는 [.NET Framework와 .NET 5](https://dotnet.microsoft.com/download)입니다.</span><span class="sxs-lookup"><span data-stu-id="5942e-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET 5](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="5942e-105">두 프레임워크는 여러 .NET 플랫폼 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5942e-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="5942e-106">그러나 두 프레임워크 간에는 기본적인 차이가 있으며, 사용하는 프레임워크는 수행하려는 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="5942e-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="5942e-107">이 섹션에서는 각 프레임워크를 선택해야 하는 경우에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5942e-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5942e-108">[이전](../container-docker-introduction/docker-containers-images-registries.md)
>[다음](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="5942e-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
