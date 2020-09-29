---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용하여 앱을 배포하는 방법을 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163598"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>AKS(Azure Kubernetes Service)에 배포

Azure CLI(Azure 명령줄 인터페이스)가 설치된 기본 클라이언트 운영 체제(Windows, macOS 또는 Linux)를 사용하여 AKS와 상호 작용할 수 있습니다. 자세한 내용은 [Azure CLI 설명서](/cli/azure/?view=azure-cli-latest) 및 사용 가능한 환경에 대한 [설치 가이드](/cli/azure/install-azure-cli?view=azure-cli-latest)를 참조하세요.

## <a name="create-the-aks-environment-in-azure"></a>Azure에서 AKS 환경 만들기

AKS 환경을 만드는 여러 가지 방법이 있습니다. Azure CLI 명령을 사용하는 방법도 있고 Azure Portal을 사용하는 방법도 있습니다.

여기서는 Azure CLI를 사용하여 클러스터를 만들고 Azure Portal에서 결과를 검토하는 예제를 살펴볼 수 있습니다. 개발 머신에 Kubectl 및 Docker도 있어야 합니다.

## <a name="create-the-aks-cluster"></a>AKS 클러스터 만들기

이 명령을 사용하여 AKS 클러스터를 만듭니다(리소스 그룹이 있어야 함).

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> `--node-vm-size` 및 `--node-count` 매개 변수 값은 샘플/개발 애플리케이션에 적합합니다.

만들기 작업이 완료되면 다음을 확인할 수 있습니다.

- 초기 리소스 그룹에서 만든 AKS 클러스터
- 다음 이미지에 표시된 것처럼 AKS 클러스터와 관련된 리소스를 포함하는 새로운 관련 리소스 그룹

AKS 클러스터를 포함하는 초기 리소스 그룹:

![AKS 리소스 그룹의 브라우저 보기.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

**그림 4-17**. Azure의 AKS 리소스 그룹 보기.

AKS 클러스터 리소스 그룹:

![Azure AKS 리소스 그룹의 브라우저 보기.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

**그림 4-18**. Azure의 AKS 보기.

> [!IMPORTANT]
> 일반적으로 AKS 클러스터 리소스 그룹에서는 리소스를 수정할 필요가 없습니다. 예를 들어 AKS 클러스터를 삭제하면 리소스 그룹이 삭제됩니다.

`Azure CLI` 및 `Kubectl`을 사용하여 만든 노드를 볼 수도 있습니다.

먼저, 자격 증명을 가져옵니다.

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![위 명령의 콘솔 출력: /home/miguel/.kube/config에서 “explore-docker-aks”가 현재 컨텍스트로 병합됩니다.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

**그림 4-19**. `aks get-credentials` 명령 결과입니다.

다음과 같이 Kubectl에서 노드를 가져옵니다.

```console
kubectl get nodes
```

![위 명령의 콘솔 출력: 상태, 기간(실행된 시간) 및 버전이 있는 노드 목록](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

**그림 4-20**. `kubectl get nodes` 명령 결과입니다.

> [!div class="step-by-step"]
> [이전](orchestrate-high-scalability-availability.md)
> [다음](docker-apps-development-environment.md)
