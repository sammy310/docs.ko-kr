---
title: 클라우드에서 DevOps 도구와 CI/CD 파이프라인을 사용하여 앱의 수명 주기 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 클라우드에서 DevOps 도구와 CI/CD 파이프라인를 사용하여 앱의 수명 주기 최신화
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 7f2637db3ed43f98d5b3b0cac43f7221388770fc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611664"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="373e2-103">클라우드에서 DevOps 도구와 CI/CD 파이프라인을 사용하여 앱의 수명 주기 최신화</span><span class="sxs-lookup"><span data-stu-id="373e2-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="373e2-104">오늘날의 비즈니스는 시장에서 경쟁력을 갖기 위해 빠른 속도로 혁신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="373e2-105">높은 수준의 최신 응용 프로그램을 제공하려면 이러한 혁신을 주기적으로 구현하기 위해 중요한 DevOps 도구와 프로세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="373e2-106">적절한 DevOps 도구를 사용하여 개발자는 지속적인 배포를 간소화하고 사용자에게 혁신적인 응용 프로그램을 보다 신속하게 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="373e2-107">지속적인 통합과 배포 방법이 잘 정립되더라도 컨테이너를 도입하는 경우, 특히 다중 컨테이너 응용 프로그램을 사용하여 작업하는 경우에는 새로운 고려 사항이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="373e2-108">Azure DevOps 서비스는 다양 한 공식 Azure DevOps 서비스 배포 작업을 통해 환경에 다중 컨테이너 응용 프로그램의 지속적인 통합 및 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- <span data-ttu-id="373e2-109">[독립 실행형 Docker 호스트 VM에 배포](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux 또는 Windows Server 2016 이상)</span><span class="sxs-lookup"><span data-stu-id="373e2-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

- [<span data-ttu-id="373e2-110">Service Fabric에 배포</span><span class="sxs-lookup"><span data-stu-id="373e2-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

- [<span data-ttu-id="373e2-111">Azure Container Service-Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="373e2-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="373e2-112">또한에 배포할 수 있지만 [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) 또는 DC/OS Azure DevOps 서비스 스크립트 기반 작업을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="373e2-113">배포 민첩성을 촉진 합니다. 계속 하려면 이러한 도구는 다양 한 개발 및 CI/CD 솔루션을 사용 하 여 컨테이너 워크 로드에 대 한 개발-테스트-에-프로덕션에 배포 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="373e2-114">그림 4-12에 Azure Container Service에서 Kubernetes 클러스터에 배포 하는 지속적인 배포 파이프라인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="373e2-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps 서비스 연속 배포 파이프라인을 Kubernetes 클러스터에 배포](./media/image12.png)

> <span data-ttu-id="373e2-116">**그림 4-12입니다.**</span><span class="sxs-lookup"><span data-stu-id="373e2-116">**Figure 4-12.**</span></span> <span data-ttu-id="373e2-117">Azure DevOps 서비스 연속 배포 파이프라인을 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="373e2-117">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="373e2-118">[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
>[다음](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="373e2-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>