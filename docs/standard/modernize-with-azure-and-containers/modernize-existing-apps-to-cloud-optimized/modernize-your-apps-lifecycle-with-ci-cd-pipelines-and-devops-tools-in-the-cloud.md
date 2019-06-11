---
title: 클라우드에서 DevOps 도구와 CI/CD 파이프라인을 사용하여 앱의 수명 주기 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 클라우드에서 DevOps 도구와 CI/CD 파이프라인를 사용하여 앱의 수명 주기 최신화
ms.date: 04/30/2018
ms.openlocfilehash: cc991bba5df3a9cd972d9a172c1a8f1035ce8c58
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758644"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>클라우드에서 DevOps 도구와 CI/CD 파이프라인을 사용하여 앱의 수명 주기 최신화

오늘날의 비즈니스는 시장에서 경쟁력을 갖기 위해 빠른 속도로 혁신해야 합니다. 높은 수준의 최신 응용 프로그램을 제공하려면 이러한 혁신을 주기적으로 구현하기 위해 중요한 DevOps 도구와 프로세스가 필요합니다. 적절한 DevOps 도구를 사용하여 개발자는 지속적인 배포를 간소화하고 사용자에게 혁신적인 응용 프로그램을 보다 신속하게 전달할 수 있습니다.

지속적인 통합과 배포 방법이 잘 정립되더라도 컨테이너를 도입하는 경우, 특히 다중 컨테이너 응용 프로그램을 사용하여 작업하는 경우에는 새로운 고려 사항이 발생하게 됩니다.

Azure DevOps 서비스는 다양 한 공식 Azure DevOps 서비스 배포 작업을 통해 환경에 다중 컨테이너 응용 프로그램의 지속적인 통합 및 배포를 지원합니다.

- [독립 실행형 Docker 호스트 VM에 배포](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux 또는 Windows Server 2016 이상)

- [Azure Container Service-Kubernetes에 배포](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

또한에 배포할 수 있지만 [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) 또는 DC/OS Azure DevOps 서비스 스크립트 기반 작업을 사용 하 여 합니다.

배포 민첩성을 촉진 합니다. 계속 하려면 이러한 도구는 다양 한 개발 및 CI/CD 솔루션을 사용 하 여 컨테이너 워크 로드에 대 한 개발-테스트-에-프로덕션에 배포 환경을 제공 합니다.

그림 4-12에 Azure Container Service에서 Kubernetes 클러스터에 배포 하는 지속적인 배포 파이프라인을 보여 줍니다.

![Azure DevOps 서비스 연속 배포 파이프라인을 Kubernetes 클러스터에 배포](./media/image12.png)

> **그림 4-12입니다.** Azure DevOps 서비스 연속 배포 파이프라인을 Kubernetes 클러스터에 배포

>[!div class="step-by-step"]
>[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
>[다음](migrate-to-hybrid-cloud-scenarios.md)
