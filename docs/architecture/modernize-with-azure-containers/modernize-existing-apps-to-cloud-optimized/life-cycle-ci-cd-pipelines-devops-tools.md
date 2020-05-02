---
title: 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화
ms.date: 04/30/2018
ms.openlocfilehash: afb7bae7780a766329ca604d192b2d7353e32bf5
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739171"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>클라우드에서 CI/CD 파이프라인 및 DevOps 도구를 사용하여 앱의 수명 주기 현대화

오늘날의 기업들은 시장에서의 경쟁력 확보를 위해 신속히 혁신해야 합니다. 고품질의 최신 애플리케이션을 제공하기 위해서는 이처럼 지속적인 혁신 주기를 실현하는 데 필수적인 DevOps 도구와 프로세스가 필요합니다. 개발자는 적절한 DevOps 도구를 사용하여 연속 배포를 간소화하고 혁신적인 애플리케이션을 사용자에게 신속히 제공할 수 있습니다.

지속적인 통합 및 배포 방법이 잘 확립되어 있기는 하지만 컨테이너를 도입하면 새롭게 고려해야 할 상황이 생기는데, 특히 다중 컨테이너 애플리케이션을 사용할 때 그러합니다.

Azure DevOps Services는 공식 Azure DevOps Services 배포 작업을 통해 다양한 환경에 대한 다중 컨테이너 애플리케이션의 지속적인 통합과 배포를 지원합니다.

- [Azure Web App for Containers로 배포](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [Azure Kubernetes Service로 배포](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

하지만 사용자는 Azure DevOps Services 스크립트 기반 작업을 사용하여 [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) 또는 DC/OS로 배포할 수도 있습니다.

민첩한 배포를 지원하기 위해 이들 도구는 다양한 개발 및 CI/CD 솔루션으로 컨테이너 워크로드에 대해 탁월한 개발-테스트-프로덕션 배포 경험을 제공합니다.

그림 4-12는 Azure Container Service에서 Kubernetes 클러스터에 배포하는 연속 배포 파이프라인을 보여줍니다.

![Kubernetes 클러스터에 배포하는 Azure DevOps Services의 스크린샷](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

**그림 4-12.** Kubernetes 클러스터에 배포하는 Azure DevOps Services의 연속 배포 파이프라인

>[!div class="step-by-step"]
>[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
>[다음](migrate-to-hybrid-cloud-scenarios.md)
