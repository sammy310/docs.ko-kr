---
title: Azure Container Service에 Windows 컨테이너를 배포해야 하는 경우(즉 ACS-Kubernetes)
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Azure Container Service에 Windows 컨테이너를 배포해야 하는 경우(즉 ACS-Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 3ff51a70d4e158b831155ab4992ec32f5d98cedb
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987766"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="518db-103">Azure Container Service에 Windows 컨테이너를 배포해야 하는 경우(즉 ACS-Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="518db-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="518db-104">Azure Container Service는 Azure용으로 특히 인기 있는 오픈 소스 도구 및 기술의 구성을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="518db-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="518db-105">컨테이너와 애플리케이션 구성 모두에 이식성을 제공하는 개방형 솔루션을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518db-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="518db-106">사용자는 크기, 호스트 수, 오케스트레이터 도구를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518db-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="518db-107">Azure Container Service는 인프라를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="518db-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="518db-108">Kubernetes, Docker Swarm 또는 DC/OS와 같은 오픈 소스 오케스트레이터로 이미 작업 중인 경우에는 컨테이너 워크로드를 클라우드로 옮기도록 기존 관리 사례를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="518db-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="518db-109">이미 익숙한 애플리케이션 관리 도구를 사용하고 원하는 오케스트레이터를 위한 표준 API 엔드포인트를 통해 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="518db-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="518db-110">이러한 모든 오케스트레이터는 사용자가 Linux Docker 컨테이너를 사용하지만 Windows 컨테이너의 미리 보기 상태에 있는 경우 완성된 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="518db-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="518db-111">예를 들어 Kubernetes에서 컨테이너에 대한 지원은 네이티브(주요 구성 요소)이므로 Kubernetes의 Windows 컨테이너를 사용하는 것도 효과적입니다(2018 초기 버전 기준 ACS의 미리 보기).</span><span class="sxs-lookup"><span data-stu-id="518db-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="518db-112">중요 정보: 한층 발전된 “추가 PaaS” 버전의 Kubernetes용 ACS(Azure Container Service)는 AKS(Azure Kubernetes Service)이지만 Windows 컨테이너는 2018년 2분기 기준으로 아직 지원되지 않습니다. 물론 지원은 조만간 진행될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="518db-112">Important note: The evolved and "more PaaS" version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="518db-113">[이전](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[다음](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="518db-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
