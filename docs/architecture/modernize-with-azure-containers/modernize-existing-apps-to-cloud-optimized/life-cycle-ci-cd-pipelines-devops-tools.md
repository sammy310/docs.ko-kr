---
title: 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화
ms.date: 04/30/2018
ms.openlocfilehash: 17a78c108bfc61471128a34191ec7a5d7cc28289
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503856"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="f8af1-103">클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화</span><span class="sxs-lookup"><span data-stu-id="f8af1-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="f8af1-104">오늘날의 기업들은 시장에서의 경쟁력 확보를 위해 신속히 혁신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="f8af1-105">고품질의 최신 애플리케이션을 제공하기 위해서는 이처럼 지속적인 혁신 주기를 실현하는 데 필수적인 DevOps 도구와 프로세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="f8af1-106">개발자는 적절한 DevOps 도구를 사용하여 연속 배포를 간소화하고 혁신적인 애플리케이션을 사용자에게 신속히 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="f8af1-107">지속적인 통합 및 배포 방법이 잘 확립되어 있기는 하지만 컨테이너를 도입하면 새롭게 고려해야 할 상황이 생기는데, 특히 다중 컨테이너 애플리케이션을 사용할 때 그러합니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="f8af1-108">Azure DevOps Services는 공식 Azure DevOps Services 배포 작업을 통해 다양한 환경에 대한 다중 컨테이너 애플리케이션의 지속적인 통합과 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="f8af1-109">Azure Web App for Containers로 배포</span><span class="sxs-lookup"><span data-stu-id="f8af1-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="f8af1-110">Azure Kubernetes Service로 배포</span><span class="sxs-lookup"><span data-stu-id="f8af1-110">Deploy to Azure Kubernetes Service</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="f8af1-111">하지만 사용자는 Azure DevOps Services 스크립트 기반 작업을 사용하여 [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html)이나 DC/OS로 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-111">But you also can deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="f8af1-112">민첩한 배포를 지원하기 위해 이들 도구는 다양한 개발 및 CI/CD 솔루션으로 컨테이너 워크로드에 대해 탁월한 개발-테스트-프로덕션 배포 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="f8af1-113">그림 4-12는 Azure Container Service에서 Kubernetes 클러스터에 배포하는 연속 배포 파이프라인을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8af1-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Kubernetes 클러스터에 배포하는 Azure DevOps Services의 스크린샷](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="f8af1-115">**그림 4-12.**</span><span class="sxs-lookup"><span data-stu-id="f8af1-115">**Figure 4-12.**</span></span> <span data-ttu-id="f8af1-116">Kubernetes 클러스터에 배포하는 Azure DevOps Services의 연속 배포 파이프라인</span><span class="sxs-lookup"><span data-stu-id="f8af1-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f8af1-117">[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
>[다음](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="f8af1-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
