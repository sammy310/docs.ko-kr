---
title: Azure에서 컨테이너 배포
description: Azure Container Registry, Azure Kubernetes Service 및 Azure Dev Spaces를 사용 하 여 Azure에 컨테이너를 배포 합니다.
ms.date: 04/13/2020
ms.openlocfilehash: ba2854323ee0f1394a3cff0dd3756cb3c7c32d5b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614151"
---
# <a name="deploying-containers-in-azure"></a>Azure에서 컨테이너 배포

이 장과 1 장에서는 컨테이너에 대해 설명 했습니다. 컨테이너는 이식성을 비롯 한 클라우드 네이티브 응용 프로그램에 많은 이점을 제공 합니다. Azure 클라우드에서는 스테이징 및 프로덕션 환경에서 동일한 컨테이너 화 된 서비스를 배포할 수 있습니다. Azure는 이러한 컨테이너 화 된 워크 로드를 호스트 하기 위한 몇 가지 옵션을 제공 합니다.

- AKS(Azure Kubernetes Services)
- ACI(Azure Container Instance)
- 컨테이너에 대 한 Azure Web Apps

## <a name="azure-container-registry"></a>Azure Container Registry

마이크로 서비스을 컨테이너 화 때 먼저 빌드 컨테이너 "이미지"를 만듭니다. 이미지는 서비스 코드, 종속성 및 런타임의 이진 표현입니다. Docker API의 명령을 사용 하 여 이미지를 수동으로 만들 수 있지만 `Docker Build` , 자동화 된 빌드 프로세스의 일부로 생성 하는 것이 더 나은 방법입니다.

컨테이너 이미지를 만든 후에는 컨테이너 레지스트리에 저장 됩니다. 컨테이너 이미지를 작성, 저장 및 관리할 수 있습니다. 공개 및 개인의 여러 레지스트리를 사용할 수 있습니다. ACR (Azure Container Registry)은 Azure 클라우드의 완전히 관리 되는 컨테이너 레지스트리 서비스입니다. Azure 네트워크 내에 이미지를 유지 하므로 Azure 컨테이너 호스트에 배포 하는 시간을 줄일 수 있습니다. 다른 Azure 리소스에 사용 하는 것과 동일한 보안 및 id 절차를 사용 하 여 보안을 유지할 수도 있습니다.

[Azure Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)또는 [PowerShell 도구](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)를 사용 하 여 Azure Container Registry를 만듭니다. Azure에서 레지스트리를 만드는 방법은 간단 합니다. Azure 구독, 리소스 그룹 및 고유한 이름이 필요 합니다. 그림 3-11에서는에서 호스트 되는 레지스트리를 만들기 위한 기본 옵션을 보여 줍니다 `registryname.azurecr.io` .

![컨테이너 레지스트리 만들기](./media/create-container-registry.png)

**그림 3-11**. 컨테이너 레지스트리 만들기

레지스트리를 만든 후에는이를 사용 하기 전에 인증 해야 합니다. 일반적으로 Azure CLI 명령을 사용 하 여 레지스트리에 로그인 합니다.

```azurecli
az acr login --name *registryname*
```

인증 된 후에는 docker 명령을 사용 하 여 컨테이너 이미지를 푸시할 수 있습니다. 그러나 이렇게 하려면 먼저 ACR 로그인 서버의 정규화 된 이름 (URL)을 사용 하 여 이미지에 태그를 지정할 수 있습니다. *Registryname*. azurecr.io 형식을 갖습니다.

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

이미지에 태그를 지정한 후 명령을 사용 하 여 `docker push` ACR 인스턴스로 이미지를 푸시합니다.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

이미지를 레지스트리에 푸시한 후에는 다음 명령을 사용 하 여 로컬 Docker 환경에서 이미지를 제거 하는 것이 좋습니다.

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

개발자는 컨테이너 레지스트리에 이미지를 수동으로 푸시하는 것이 가장 좋습니다. 대신 GitHub 또는 Azure DevOps와 같은 도구에 정의 된 빌드 파이프라인이이 프로세스를 담당 해야 합니다. [클라우드-기본 DevOps 챕터](devops.md)에서 자세히 알아보세요.

## <a name="acr-tasks"></a>ACR 작업

[ACR 작업](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) 은 Azure Container Registry에서 사용할 수 있는 기능 집합입니다. Azure 클라우드에서 컨테이너 이미지를 작성 하 고 관리 하 여 [내부 루프 개발 주기](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) 를 확장 합니다. `docker build`개발 컴퓨터에서 및를 로컬로 호출 하는 대신 `docker push` 클라우드의 ACR 작업에 의해 자동으로 처리 됩니다.

다음 AZ CLI 명령은 컨테이너 이미지를 빌드하고 ACR로 푸시합니다.

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

이전 명령 블록에서 볼 수 있듯이, 개발 컴퓨터에 Docker Desktop을 설치할 필요가 없습니다. 또한 소스 코드와 기본 이미지 업데이트 모두에서 컨테이너 이미지를 다시 작성 하도록 ACR 작업 트리거를 구성할 수 있습니다.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

이 장에서는 Azure Kubernetes Service (AKS)의 길이에 대해 설명 했습니다. 컨테이너 화 된 클라우드 네이티브 응용 프로그램을 관리 하는 사실상 컨테이너 오 케 스트레이 터입니다.

ACR 같은 레지스트리에 이미지를 배포한 후에는 AKS를 자동으로 풀 및 배포 하도록 구성할 수 있습니다. CI/CD 파이프라인이 준비 되 면 업데이트를 신속 하 게 배포할 때 관련 된 위험을 최소화 하기 위해 [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html) 전략을 구성할 수 있습니다. 새 버전의 앱은 전송 된 트래픽이 없는 프로덕션 환경에서 초기에 구성 됩니다. 그러면 시스템에서 사용자의 일부를 새로 배포 된 버전으로 라우팅합니다. 팀이 새 버전에서 자신감을 얻게 되 면 더 많은 인스턴스를 출시 하 고 이전을 사용 중지할 수 있습니다. AKS는이 스타일의 배포를 쉽게 지원 합니다.

Azure의 대부분 리소스와 마찬가지로 포털, 명령줄 또는 투구 또는 Terraform 같은 자동화 도구를 사용 하 여 Azure Kubernetes Service 클러스터를 만들 수 있습니다. 새 클러스터를 시작 하려면 다음 정보를 제공 해야 합니다.

- Azure 구독
- Resource group
- Kubernetes 클러스터 이름
- 지역
- Kubernetes 버전
- DNS 이름 접두사
- 노드 크기
- 노드 수

이 정보는 시작 하기에 충분 합니다. Azure Portal 만들기 프로세스의 일부로 클러스터의 다음 기능에 대 한 옵션을 구성할 수도 있습니다.

- 확장
- 인증
- 네트워킹
- 모니터링
- 태그

이 [빠른 시작은 Azure Portal를 사용 하 여 AKS 클러스터를 배포 하는 과정](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)을 안내 합니다.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

클라우드 네이티브 응용 프로그램을 신속 하 게 확장 하 여 큰 계산 리소스를 실행 해야 할 수 있습니다. 이러한 시나리오에서는 전체 응용 프로그램을 개발 컴퓨터 (특히 랩톱)에서 호스팅할 수 없습니다. Azure Dev Spaces AKS를 사용 하 여이 문제를 해결 하도록 설계 되었습니다. 개발자는이를 통해 AKS development 클러스터에 응용 프로그램의 나머지 부분을 호스트 하는 동안 로컬 버전의 서비스를 사용할 수 있습니다.

개발자는 전체 컨테이너 화 된 응용 프로그램을 포함 하는 AKS 클러스터에서 실행 중인 (개발) 인스턴스를 공유 합니다. 그러나 해당 컴퓨터에 설정 된 개인 공간을 사용 하 여 로컬에서 서비스를 개발 합니다. 준비가 되 면 종속성을 복제 하지 않고 AKS 클러스터에서 종단 간 테스트를 진행 합니다. Azure Dev Spaces AKS의 서비스를 사용 하 여 로컬 컴퓨터의 코드를 병합 합니다. 개발자는 Visual Studio 또는 Visual Studio Code를 사용 하 여 Kubernetes에서 직접 코드를 신속 하 게 반복 하 고 디버그할 수 있습니다.

Azure Dev Spaces의 가치를 이해 하기 위해 Microsoft Azure에서 컨테이너의 오후 Gabe Monroy, PM에서이 따옴표를 공유 하겠습니다.

> "수십 개의 구성 요소로 구성 된 복잡 한 마이크로 서비스 응용 프로그램에서 버그를 수정 하려는 새 직원이 있으며 각각 자체 구성 및 지원 서비스가 있다고 가정 합니다. 시작 하려면 IDE 설정, 도구 체인 빌드, 컨테이너 화 된 서비스 종속성, 로컬 Kubernetes 환경, 지원 서비스에 대 한 mock 등의 작업을 비롯 하 여 프로덕션을 모방 하도록 로컬 개발 환경을 구성 해야 합니다. 개발 환경을 설정 하는 데 소요 되는 모든 시간을 사용 하 여 첫 번째 버그를 수정 하는 데 며칠이 걸릴 수 있습니다.
> 또는 Dev Spaces 및 AKS를 사용할 수 있습니다. "

Azure Dev Spaces 사용 하는 프로세스에는 다음 단계가 포함 됩니다.

1. 개발 공간을 만듭니다.
2. 루트 개발 공간을 구성 합니다.
3. 사용자 고유의 시스템 버전에 대 한 자식 개발 공간을 구성 합니다.
4. Dev 공간에 연결 합니다.

이러한 모든 단계는 Azure CLI 및 새로운 명령줄 도구를 사용 하 여 수행할 수 있습니다 `azds` . 예를 들어, 지정 된 Kubernetes 클러스터에 대 한 새 Azure Dev 공간을 만들려면 다음과 같은 명령을 사용 합니다.

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

그런 다음 명령을 사용 하 여 `azds prep` 응용 프로그램을 실행 하는 데 필요한 Docker 및 투구 차트 자산을 생성할 수 있습니다. 그런 다음를 사용 하 여 AKS에서 코드를 실행 `azds up` 합니다. 이 명령을 처음 실행 하면 투구 차트가 설치 됩니다. 컨테이너는 사용자의 지침에 따라 빌드되고 배포 됩니다. 이 작업은 처음 실행 될 때까지 몇 분 정도 걸릴 수 있습니다. 그러나를 변경한 후에는를 사용 하 여 사용자 고유의 자식 개발 공간에 연결한 `azds space select` 다음 격리 된 자식 개발 공간에서 업데이트를 배포 하 고 디버그할 수 있습니다. 개발 공간이 준비 되 고 실행 되 면 명령을 다시 실행 하 여 업데이트를 보내거나 `azds up` Visual Studio 또는 Visual Studio Code에서 기본 제공 되는 도구를 사용할 수 있습니다. VS Code를 사용 하 여 명령 팔레트를 사용 하 여 개발 공간에 연결 합니다. 그림 3-12에서는 Visual Studio에서 Azure Dev Spaces를 사용 하 여 웹 응용 프로그램을 시작 하는 방법을 보여 줍니다.

![Visual Studio ](./media/azure-dev-spaces-visual-studio-launchsettings.png)
 **그림 3-12**에서 Azure Dev Spaces에 연결 합니다. Visual Studio에서 Azure Dev Spaces에 연결

>[!div class="step-by-step"]
>[이전](combine-containers-serverless-approaches.md)
>[다음](scale-containers-serverless.md)
