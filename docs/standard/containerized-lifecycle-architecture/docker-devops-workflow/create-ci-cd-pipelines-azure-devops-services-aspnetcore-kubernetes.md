---
title: Docker 애플리케이션에 대한 외부 루프 DevOps 워크플로의 단계
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e11c9ec61ea7d5131595f01ce76b5bb810bb70c0
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063308"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Azure DevOps 서비스에서 컨테이너의 .NET Core 2.0 애플리케이션에 대한 CI/CD 파이프라인 만들기 및 Kubernetes 클러스터에 배포

그림 5-12에서 다루는 코드 관리, 코드 컴파일 엔드-투-엔드 DevOps 시나리오를 볼 수 있습니다, Docker 이미지 빌드, Docker 이미지 푸시 Docker 레지스트리를 마지막으로 Azure에서 Kubernetes 클러스터에 배포 합니다.

![워크플로: 개발 컴퓨터에서 시작합니다. 리포지토리에 푸시할 Docker 레지스트리로 푸시되 다음을 사용 하 여 CD/배포 작업을 마지막으로, AKS에 푸시하는 사용자 지정 이미지를 사용 하 여 빌드/CI 작업을 시작 합니다.](media/docker-workflow-ci-cd-aks.png)

**그림 5-12**. Docker 이미지를 만들고 Azure에서 Kubernetes 클러스터에 배포 하는 CI/CD 시나리오

두 개의 파이프라인, / CI, 빌드 및 릴리스/CD (예: Docker 허브 또는 Azure Container Registry) Docker 레지스트리를 통해 연결 되어 있는지를 강조 표시 하는 것이 반드시 합니다. Docker 레지스트리에 Docker 없이 기존 CI/CD 프로세스에 비해 주요 차이점 중 하나입니다.

그림 5-13에서와 같이 첫 번째 단계는 빌드/CI 파이프라인. Azure DevOps 서비스에서 코드를 컴파일하려면 코드, Docker 이미지를 만들고 Docker 허브 또는 Azure Container Registry와 같은 Docker 레지스트리로 푸시하는 CI 빌드/파이프라인을 만들 수 있습니다.

![Azure DevOps, 빌드 프로세스 작업 정의의 브라우저 보기입니다.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**그림 5-13**. Azure DevOps Docker 이미지를 빌드하고 Docker 레지스트리에 이미지 푸시하기 빌드/CI 파이프라인

두 번째 단계는 배포/릴리스 파이프라인을 만드는 것입니다. Azure DevOps 서비스에서는 그림 5-14에 나와 있는 것 처럼 Azure DevOps 서비스에 대 한 Kubernetes 작업을 사용 하 여 Kubernetes 클러스터를 대상으로 하는 배포 파이프라인을 쉽게 만들 수 있습니다.

![Azure DevOps의 브라우저 보기 Kubernetes 작업 정의를 배포 합니다.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**그림 5-14**. Azure DevOps 서비스 Kubernetes 클러스터에 배포할 릴리스/CD 파이프라인

> [! 연습] eShopModernized Kubernetes에 배포 합니다.
>
> Azure DevOps CI/CD 파이프라인의 자세한 연습에 대 한이 게시물을 참조 Kubernetes에 배포 합니다. \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[이전](docker-application-outer-loop-devops-workflow.md)
>[다음](../run-manage-monitor-docker-environments/index.md)
