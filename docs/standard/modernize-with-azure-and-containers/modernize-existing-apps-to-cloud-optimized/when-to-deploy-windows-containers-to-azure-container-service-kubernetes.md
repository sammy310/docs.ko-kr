---
title: Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144795"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="7caf0-103">Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="7caf0-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="7caf0-104">Azure Container Service에는 특별히 Azure 용으로 인기 있는 오픈 소스 도구 및 기술의 구성을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="7caf0-105">컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공 하는 개방형 솔루션을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="7caf0-106">크기, 호스트 수 및 오 케 스트레이 터 도구를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="7caf0-107">Azure Container Service를 인프라를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="7caf0-108">이미 Kubernetes나 Docker Swarm, DC/OS와 같은 오픈 소스 오케스트레이터를 사용하여 작업하고 있는 경우, 컨테이너 워크로드를 클라우드로 변경하기 위해 기존 관리 방법을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="7caf0-109">이미 익숙한 기존의 응용 프로그램 관리 도구를 사용하고, 사용자가 선택한 오케스트레이터 표준 API 끝점을 통해 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="7caf0-110">Linux Docker 컨테이너를 사용하는 경우에는 이러한 오케스트레이터가 모두 완성도가 높은 상태지만, Windows 컨테이너를 사용하는 경우에는 미리 보기 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="7caf0-111">예를 들어, kubernetes에서 컨테이너 지원은 기본 클래스(일급 객체)이므로 kubernetes에서 Windows 컨테이너를 사용하는 것도 효과적입니다(2018년 초 ACS 미리 보기의 경우).</span><span class="sxs-lookup"><span data-stu-id="7caf0-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="7caf0-112">중요 참고 사항: 진화 하 고 "자세한 PaaS" Kubernetes에 대 한 ACS (Azure Container Service)의 버전은 AKS (Azure Kubernetes Service), 단, Windows 컨테이너는 여전히 Q2 2018 년부터 지원 되지 않지만 곧 지원 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="7caf0-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7caf0-113">[이전](when-to-deploy-windows-containers-to-service-fabric.md)
>[다음](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="7caf0-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>