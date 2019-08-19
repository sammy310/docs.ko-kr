---
title: Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577946"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="b1848-103">Azure Container Service(즉, Kubernetes)에 Windows 컨테이너를 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="b1848-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="b1848-104">Azure Container Service는 특히 Azure용으로 인기 있는 오픈 소스 도구 및 기술의 구성을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="b1848-105">컨테이너와 응용 프로그램 구성에 대한 이식성이 제공되는 개방형 솔루션을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="b1848-106">크기와 호스트 수 및 오케스트레이터 도구를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="b1848-107">Azure Container Service에서 인프라를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="b1848-108">이미 Kubernetes나 Docker Swarm, DC/OS와 같은 오픈 소스 오케스트레이터를 사용하여 작업하고 있는 경우, 컨테이너 워크로드를 클라우드로 변경하기 위해 기존 관리 방법을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="b1848-109">이미 익숙한 기존의 응용 프로그램 관리 도구를 사용하고, 사용자가 선택한 오케스트레이터 표준 API 끝점을 통해 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="b1848-110">Linux Docker 컨테이너를 사용하는 경우에는 이러한 오케스트레이터가 모두 완성도가 높은 상태지만, Windows 컨테이너를 사용하는 경우에는 미리 보기 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="b1848-111">예를 들어, kubernetes에서 컨테이너 지원은 기본 클래스(일급 객체)이므로 kubernetes에서 Windows 컨테이너를 사용하는 것도 효과적입니다(2018년 초 ACS 미리 보기의 경우).</span><span class="sxs-lookup"><span data-stu-id="b1848-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="b1848-112">중요 참고 사항: Kubernetes의 진화되고 '자세한 PaaS' ACS(Azure Container Service)의 버전은 AKS(Azure Kubernetes Service)입니다. Windows 컨테이너는 2018년 2분기에도 여전히 지원되지 않고 있지만 곧 지원될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b1848-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1848-113">[이전](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[다음](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="b1848-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
