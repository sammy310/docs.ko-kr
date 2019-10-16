---
title: 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화 | 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용 하 여 앱의 수명 주기 현대화
ms.date: 04/30/2018
ms.openlocfilehash: d1aa2e156e87cafe99fb994233786f67bf7a81a1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396256"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="06b4b-103">클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화</span><span class="sxs-lookup"><span data-stu-id="06b4b-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="06b4b-104">오늘날의 기업은 marketplace에서 경쟁력을 위해 신속 하 게 혁신을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="06b4b-105">고품질의 최신 응용 프로그램을 제공 하려면이 일정 한 혁신 주기를 구현 하는 데 중요 한 DevOps 도구 및 프로세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="06b4b-106">개발자는 올바른 DevOps 도구를 사용 하 여 지속적인 배포를 간소화 하 고 혁신적인 응용 프로그램을 사용자에 게 더 신속 하 게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="06b4b-107">지속적인 통합 및 배포 방법이 잘 설정 되어 있지만 컨테이너를 도입 하면 특히 다중 컨테이너 응용 프로그램을 사용 하는 경우 새로운 고려 사항이 도입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="06b4b-108">Azure DevOps Services는 공식 Azure DevOps Services 배포 작업을 통해 다양 한 환경에 대 한 다중 컨테이너 응용 프로그램의 지속적인 통합 및 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="06b4b-109">Azure Web App for Containers에 배포</span><span class="sxs-lookup"><span data-stu-id="06b4b-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="06b4b-110">Azure Kubernetes Service에 배포</span><span class="sxs-lookup"><span data-stu-id="06b4b-110">Deploy to Azure Kubernetes Service</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="06b4b-111">그러나 Azure DevOps Services 스크립트 기반 작업을 사용 하 여 [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) 또는 DC/OS에 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="06b4b-112">배포 민첩성을 계속 유지 하기 위해 이러한 도구는 개발 및 CI/CD 솔루션을 선택 하 여 컨테이너 워크 로드에 대 한 뛰어난 개발 및 테스트 프로덕션 환경 배포 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="06b4b-113">그림 4-12은 Azure Container Service에서 Kubernetes 클러스터에 배포 하는 연속 배포 파이프라인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06b4b-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Kubernetes 클러스터에 배포 하는 Azure DevOps Services의 스크린샷](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="06b4b-115">**그림 4-12.**</span><span class="sxs-lookup"><span data-stu-id="06b4b-115">**Figure 4-12.**</span></span> <span data-ttu-id="06b4b-116">Azure DevOps Services 연속 배포 파이프라인, Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="06b4b-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06b4b-117">[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
>[다음](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="06b4b-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
