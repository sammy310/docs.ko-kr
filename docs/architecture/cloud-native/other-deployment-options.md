---
title: 기타 컨테이너 배포 옵션
description: Azure를 사용 하는 다른 컨테이너 배포 옵션
ms.date: 05/13/2020
ms.openlocfilehash: acb022e3d4fd4862c592fa571894e1b8ce17f465
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613761"
---
# <a name="other-container-deployment-options"></a>기타 컨테이너 배포 옵션

Azure Kubernetes 서비스 (AKS) 외에도 컨테이너 및 Azure Container Instances에 대 한 Azure App Service 컨테이너를 배포할 수 있습니다.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>컨테이너의 App Service에 배포 하는 것이 적합 한가요?

오케스트레이션을 필요로 하지 않는 간단한 프로덕션 응용 프로그램은 컨테이너의 Azure App Service에 매우 적합 합니다.

## <a name="how-to-deploy-to-app-service-for-containers"></a>컨테이너의 App Service에 배포 하는 방법

[컨테이너의 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)에 배포 하려면 해당 인스턴스에 액세스 하는 데 필요한 AZURE CONTAINER REGISTRY (ACR) 인스턴스 및 자격 증명이 필요 합니다. 컨테이너 이미지를 ACR 리포지토리로 푸시하여 Azure App Service로 끌어올 수 있습니다. 완료 되 면 연속 배포에 대해 앱을 구성할 수 있습니다. 그렇게 하면 이미지가 ACR에서 변경 될 때마다 자동으로 업데이트를 배포 합니다.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Azure Container Instances에 배포 하는 것이 적합 한가요?

[ACI (Azure Container Instances)](https://azure.microsoft.com/services/container-instances/) 를 사용 하면 가상 머신 또는 클러스터를 설정 하지 않고도 관리 되는 서버 리스 클라우드 환경에서 Docker 컨테이너를 실행할 수 있습니다. 격리 된 컨테이너에서 실행할 수 있는 단기 실행 작업에 적합 한 솔루션입니다. 간단한 서비스, 테스트 시나리오, 작업 자동화, 빌드 작업 등에 대해 ACI를 고려 합니다. ACI는 컨테이너 인스턴스를 회전 하 고 작업을 수행한 다음 아래로 회전 합니다.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Azure Container Instances에 앱을 배포 하는 방법

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)에 배포 하려면 AZURE CONTAINER REGISTRY (ACR) 및 액세스를 위한 자격 증명이 필요 합니다. 컨테이너 이미지를 리포지토리에 푸시 하면 ACI로 끌어올 수 있습니다. Azure Portal 또는 명령줄 인터페이스를 사용 하 여 ACI로 작업할 수 있습니다. ACR은 ACI와 긴밀 하 게 통합 됩니다. 그림 3-14에서는 ACR에 개별 컨테이너 이미지를 푸시하는 방법을 보여 줍니다.

![Azure Container Registry 실행 인스턴스](./media/acr-runinstance-contextmenu.png)

**그림 3-14**. Azure Container Registry 실행 인스턴스

ACI에서 인스턴스를 만드는 작업은 신속 하 게 수행할 수 있습니다. 이미지 레지스트리, Azure 리소스 그룹 정보, 할당할 메모리 양 및 수신 대기할 포트를 지정 합니다. 이 [빠른 시작에서는 Azure Portal를 사용 하 여 ACI에 컨테이너 인스턴스를 배포 하는 방법을 보여 줍니다](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

배포가 완료 되 면 새로 배포 된 컨테이너의 IP 주소를 찾아 지정 된 포트를 통해 통신 합니다.

Azure Container Instances는 Azure에서 간단한 컨테이너 워크 로드를 실행 하는 가장 빠른 방법을 제공 합니다. App service, orchestrator 또는 virtual machine을 구성할 필요가 없습니다. 전체 컨테이너 오케스트레이션, 서비스 검색, 자동 크기 조정 또는 조정 된 업그레이드가 필요한 시나리오의 경우 Azure Kubernetes 서비스 (AKS)를 권장 합니다.

## <a name="references"></a>참조

- [Kubernetes란?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Minikube를 사용 하 여 Kubernetes 설치](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Docker용 Visual Studio Tools](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [서버 리스 콜드 시작 이해](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [사전 준비 Azure Functions 인스턴스](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [사용자 지정 이미지를 사용하여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Docker 컨테이너에서 Azure Functions 실행](https://markheath.net/post/azure-functions-docker)
- [사용자 지정 이미지를 사용하여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Kubernetes 이벤트 기반 자동 크기 조정을 사용 하는 Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)
- [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html)
- [VS Code Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Visual Studio를 사용 하 여 Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)
- [여러 노드 풀 AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS Cluster Autoscaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [자습서: AKS에서 응용 프로그램 크기 조정](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Azure Functions 크기 조정 및 호스팅](https://docs.microsoft.com/azure/azure-functions/functions-scale)
- [문서 Azure Container Instances](https://docs.microsoft.com/azure/container-instances/)
- [ACR에서 컨테이너 인스턴스 배포](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[이전](scale-containers-serverless.md)
>[다음](communication-patterns.md)
