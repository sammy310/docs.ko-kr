---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션
description: Azure Kubernetes Service를 사용 하 여 앱을 배포 하는 방법에 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006545"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>AKS(Azure Kubernetes Service)에 배포

원하는 클라이언트 운영 체제를 사용 하 여 AKS 상호 작용할 수 있습니다, 여기 살펴보겠습니다 Microsoft Windows 및 Windows, Ubuntu Linux의 포함 된 버전을 사용 하 여 수행 하는 방법을 Bash 명령을 사용 하 여 합니다.

AKS를 사용 하기 전에 가지 필수 구성 요소가 다음과 같습니다.

- Linux 또는 Mac 개발 컴퓨터
- Windows 개발 컴퓨터
  - Windows에서 사용 하도록 설정 하는 개발자 모드
  - Linux 용 Windows 하위 시스템
- Azure CLI 설치 [Windows, Mac 또는 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> 에 대 한 전체 정보를 찾으려면:
>
> Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Linux 용 Windows 하위 시스템: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Azure에서 AKS 환경 만들기

AKS 환경을 만드는 방법은 여러 가지가 있습니다. Azure CLI 명령을 사용 하 여 또는 Azure portal을 사용 하 여 수행할 수 있습니다.

여기 몇 가지 예제 클러스터를 만들고 결과 검토 하려면 Azure portal에서 Azure CLI를 사용 하 여 탐색할 수 있습니다. Kubectl 및 Docker 개발 컴퓨터에 해야 합니다.  

## <a name="create-the-aks-cluster"></a>AKS 클러스터 만들기

이 명령을 사용 하 여 AKS 클러스터를 만듭니다.

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

만들기 작업이 완료 되 면 Azure portal에서 만든 AKS를 확인할 수 있습니다.

리소스 그룹:

![브라우저 보기 Azure AKS 리소스 그룹입니다.](media/aks-resource-group-view.png)

**그림 4-17**. Azure에서 AKS 리소스 그룹 보기입니다.

AKS 클러스터의 경우:

![AKS 리소스 그룹의 브라우저 보기입니다.](media/aks-cluster-view.png)

**그림 4-18**. Azure에서 AKS 보기입니다.

사용 하 여 만든 노드를 볼 수도 있습니다 `Azure-CLI` 고 `Kubectl`입니다.

먼저 자격 증명 가져오기:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![위 명령의 출력을 콘솔: 병합 된 "/root/.kube/config에서 현재 컨텍스트로 MsSampleK8Cluster 합니다.](media/get-credentials-command-result.png)

**그림 4-19**. `aks get-credentials` 명령 결과입니다.

그리고 Kubectl에서 노드를 시작 합니다.

```console
kubectl get nodes
```

![위 명령 출력을 콘솔: 노드 상태, 기간 (시간 실행) 및 버전을 사용 하 여 목록](media/kubectl-get-nodes-command-result.png)

**그림 4-20**. `kubectl get nodes` 명령 결과입니다.

>[!div class="step-by-step"]
>[이전](orchestrate-high-scalability-availability.md)
>[다음](docker-apps-development-environment.md)
