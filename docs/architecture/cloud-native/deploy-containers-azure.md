---
title: Azure에서 컨테이너 배포
description: Azure Container Registry, Azure Kubernetes Service 및 Azure Dev Spaces를 사용 하 여 Azure에 컨테이너를 배포 합니다.
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840486"
---
# <a name="deploying-containers-in-azure"></a>Azure에서 컨테이너 배포

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

컨테이너는 다양 한 이점을 제공 합니다. 그 중 하나는 이식성입니다. 로컬로 개발 하 고 테스트 한 동일한 컨테이너를 쉽게 사용 하 고 스테이징 및 프로덕션 환경에서 앱을 실행할 수 있는 Azure에 배포할 수 있습니다. Azure는 컨테이너 기반 응용 프로그램 호스팅에 대 한 다양 한 옵션을 제공 하며, 이와 같은 다양 한 배포 방법을 지원 합니다. 가장 일반적이 고 가장 유연한 방법은 컨테이너를 호스트 하는 데 사용할 서비스에서 액세스할 수 있는 ACR (Azure Container Registry)에 배포 하는 것입니다. Azure Web App for Containers, AKS (azure Kubernetes Services) 및 ACI (Azure Container Instance)는 모두 ACR로 푸시되는 컨테이너 이미지에 액세스할 수 있습니다.

## <a name="azure-container-registry"></a>Azure Container Registry

ACR (Azure Container Registry)를 사용 하 여 모든 컨테이너 배포에 대 한 이미지를 작성, 저장 및 관리할 수 있습니다. 컨테이너를 배포할 수 있는 다른 컨테이너 레지스트리 (공용 및 개인)가 있습니다. 다른 옵션에 대 한 ACR의 장점으로, 이미지를 프로덕션 환경에 가깝게 유지 하 여 빌드 및 배포 시간을 향상 시킬 수 있습니다. 또한 Azure 리소스의 나머지 부분에 사용 하는 것과 동일한 보안 절차를 사용 하 여 보안을 강화 하 고, 보안을 개선 하 고, 자산 관리 작업을 줄일 수 있습니다.

Azure Portal을 사용 하거나 [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) 또는 [PowerShell 도구](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)를 사용 하 여 [컨테이너 레지스트리를 만듭니다](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) . 새 컨테이너 레지스트리를 만들려면 Azure 구독, 리소스 그룹 및 고유한 이름이 필요 합니다. 그림 3-11에서는 *registryname*. azurecr.io에서 호스트 되는 레지스트리를 만들기 위한 기본 옵션을 보여 줍니다.

![컨테이너 레지스트리](./media/create-container-registry.png)
**그림 3-11**을 만듭니다. 컨테이너 레지스트리 만들기

레지스트리를 만든 후에는 해당 레지스트리를 사용 하기 전에 인증 해야 합니다. 일반적으로 Azure CLI 명령을 사용 하 여 레지스트리에 로그인 합니다.

```azurecli
az acr login --name *registryname*
```

Azure Container Registry에서 레지스트리를 만든 후에는 docker 명령을 사용 하 여 컨테이너 이미지를 푸시할 수 있습니다. 그러나이 작업을 수행 하려면 먼저 ACR 로그인 서버의 정규화 된 이름 (URL)을 사용 하 여 이미지에 태그를 표시 해야 합니다. 이는 *registryname*. azurecr.io 형식을 갖습니다.

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

이미지에 태그를 지정한 후에는 `docker push` 명령을 사용 하 여 ACR 인스턴스로 이미지를 푸시합니다.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

이미지를 레지스트리에 푸시한 후에는 다음 명령을 사용 하 여 로컬 Docker 환경에서 이미지를 제거 하는 것이 좋습니다.

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

개발자는 자신의 컴퓨터에서 컨테이너 레지스트리로 직접 푸시하는 경우가 거의 없습니다. 대신 Azure DevOps와 같은 도구에 정의 된 빌드 파이프라인이이 프로세스를 담당 해야 합니다. [클라우드-기본 DevOps 챕터](devops.md)에서 자세히 알아보세요.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

컨테이너 기반 응용 프로그램에 여러 컨테이너가 포함 된 경우 Kubernetes와 같은 *orchestrator* 를 사용 하 여 컨테이너 간의 상호 작용을 정의 하 고 관리 하는 것이 좋습니다. ACR에 컨테이너 이미지를 배포한 후에는 Azure Kubernetes 서비스를 쉽게 구성 하 여 ACR에서 업데이트 된 이미지를 자동으로 배포할 수 있습니다. 전체 CI/CD 파이프라인을 사용 하는 경우 업데이트를 신속 하 게 배포할 때 관련 된 위험을 최소화 하기 위해 [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html) 전략을 구성할 수 있습니다. 새 버전의 앱은 전송 된 트래픽이 없는 프로덕션 환경에서 초기에 구성 되며 소수의 사용자는 새로 배포 된 앱 버전으로 라우팅됩니다. 팀이 새 버전의 소프트웨어에서 확신을 얻게 되 면 새 버전의 인스턴스는 더 이상 사용 되지 않으며 이전 버전의 인스턴스는 더 이상 사용 되지 않습니다. AKS는이 스타일의 배포를 쉽게 지원 합니다.

Azure의 대부분 리소스와 마찬가지로 포털을 사용 하거나 명령줄 도구나 투구 또는 Terraform 같은 인프라 자동화 도구를 사용 하 여 Azure Kubernetes 클러스터를 만들 수 있습니다. 새 클러스터를 시작 하려면 다음 정보를 제공 해야 합니다.

- Azure 구독
- 리소스 그룹
- Kubernetes 클러스터 이름
- Region
- Kubernetes 버전
- DNS 이름 접두사
- 노드 크기
- 노드 수

이 정보는 시작 하기에 충분 합니다. Azure Portal에서 생성 프로세스의 일부로 클러스터의 다음 기능에 대 한 옵션을 구성할 수도 있습니다.

- 소수 자릿수
- 인증
- 네트워킹
- 모니터링
- Tags

이 [빠른 시작은 Azure Portal를 사용 하 여 AKS 클러스터를 배포 하는 과정](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)을 안내 합니다.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

복잡 한 Kubernetes 클러스터는 호스트에 상당한 리소스를 요구할 수 있으므로 개발자가 단일 컴퓨터 (특히 랩톱)에서 전체 응용 프로그램을 실행 하기 어려울 수 있습니다. Azure Dev Spaces 개발자가 Azure에서 호스트 되는 Azure Kubernetes 클러스터의 고유한 버전으로 작업할 수 있도록 하 여이에 대 한 솔루션을 제공 합니다. Azure Dev Spaces는 AKS를 사용 하 여 마이크로 서비스 기반 응용 프로그램을 쉽게 개발할 수 있도록 설계 되었습니다.

Azure Dev Spaces의 가치를 이해 하기 위해 Microsoft Azure에서 컨테이너의 오후 Gabe Monroy, PM에서이 따옴표를 공유 하겠습니다.

"수십 개의 구성 요소로 구성 된 복잡 한 마이크로 서비스 응용 프로그램에서 버그를 수정 하려는 새 직원이 있으며 각각 자체 구성 및 지원 서비스가 있다고 가정 합니다. 시작 하려면 IDE 설정, 도구 체인 빌드, 컨테이너 화 된 서비스 종속성, 로컬 Kubernetes 환경, 지원 서비스에 대 한 mock 등의 작업을 비롯 하 여 프로덕션을 모방 하도록 로컬 개발 환경을 구성 해야 합니다. 개발 환경을 설정 하는 데 소요 되는 모든 시간을 사용 하 여 첫 번째 버그를 수정 하는 데 며칠이 걸릴 수 있습니다.

> 또는 Dev Spaces 및 AKS를 사용할 수 있습니다. "

Azure Dev Spaces 사용 하는 프로세스에는 다음 단계가 포함 됩니다.

1. 개발 공간을 만듭니다.
2. 루트 개발 공간을 구성 합니다.
3. 사용자 고유의 시스템 버전에 대 한 자식 개발 공간을 구성 합니다.
4. Dev 공간에 연결 합니다.

이러한 모든 단계는 Azure CLI 및 새로운 `azds` 명령줄 도구를 사용 하 여 수행할 수 있습니다. 예를 들어, 지정 된 Kubernetes 클러스터에 대 한 새 Azure Dev 공간을 만들려면 다음과 같은 명령을 사용 합니다.

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

그런 다음 `azds prep` 명령을 사용 하 여 응용 프로그램을 실행 하는 데 필요한 Docker 및 투구 차트 자산을 생성할 수 있습니다. 그런 다음 `azds up`를 사용 하 여 AKS에서 코드를 실행 합니다. 이 명령을 처음 실행 하면 투구 차트가 설치 되 고 사용자의 지침에 따라 컨테이너가 빌드되고 배포 됩니다. 이를 처음 실행 하면 몇 분 정도 걸릴 수 있습니다. 그러나 변경을 수행한 후 `azds space select`를 사용 하 여 사용자 고유의 자식 개발 공간에 연결 하 고 격리 된 자식 개발 공간에 업데이트를 배포 하 고 디버그할 수 있습니다. 개발 공간이 준비 되 고 실행 되 면 `azds up` 명령을 다시 실행 하거나 Visual Studio 또는 Visual Studio Code에서 기본 제공 되는 도구를 사용 하 여 업데이트를 보낼 수 있습니다. VS Code를 사용 하 여 명령 팔레트를 사용 하 여 개발 공간에 연결 합니다. 그림 3-12에서는 Visual Studio에서 Azure Dev Spaces를 사용 하 여 웹 응용 프로그램을 시작 하는 방법을 보여 줍니다.

**그림 3-12**](./media/azure-dev-spaces-visual-studio-launchsettings.png)
Visual Studio에서 Azure Dev Spaces에 연결 ![합니다. Visual Studio에서 Azure Dev Spaces에 연결

## <a name="references"></a>참조

- [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html)
- [VS Code Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Visual Studio를 사용 하 여 Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
>[이전](combine-containers-serverless-approaches.md)
>[다음](scale-containers-serverless.md)
