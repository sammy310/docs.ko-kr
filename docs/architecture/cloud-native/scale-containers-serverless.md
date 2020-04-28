---
title: 컨테이너 및 서버리스 애플리케이션 크기 조정
description: 사용자 수요를 충족 하기 위해 Azure Kubernetes Service를 사용 하 여 클라우드 네이티브 응용 프로그램 크기 조정
ms.date: 04/13/2020
ms.openlocfilehash: b4580e6994611ad394bbaa2d5bb07f64c2798569
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199926"
---
# <a name="scaling-containers-and-serverless-applications"></a>컨테이너 및 서버리스 애플리케이션 크기 조정

응용 프로그램의 크기를 조정 하는 방법에는 두 가지가 있습니다. 이전의은 단일 리소스에 용량을 추가 하는 것을 의미 하는 반면, 후자는 용량을 늘리기 위해 리소스를 더 추가 하는 것을 나타냅니다.

## <a name="the-simple-solution-scaling-up"></a>간단한 해결 방법: 수직 확장

CPU, 메모리, 디스크 i/o 속도 및 네트워크 i/o 속도를 증가 시켜 기존 호스트 서버를 업그레이드 하는 것을 *확장*이라고 합니다. 클라우드 네이티브 응용 프로그램을 확장 하려면 클라우드 공급 업체에서 더 많은 리소스를 선택 해야 합니다. 예를 들어 Kubernetes 클러스터에서 더 큰 Vm을 사용 하는 새 노드 풀을 만들 수 있습니다. 그런 다음 컨테이너 화 된 서비스를 새 풀로 마이그레이션합니다.

서버 리스 앱은 전용 app service 계획에서 [프리미엄 함수 계획](https://docs.microsoft.com/azure/azure-functions/functions-scale) 또는 프리미엄 인스턴스 크기를 선택 하 여 확장 합니다.

## <a name="scaling-out-cloud-native-apps"></a>클라우드-네이티브 앱 확장

클라우드 네이티브 응용 프로그램은 종종 수요 변동에 상당한 변화를 경험 하 고 있으며, 잠시 후에 규모를 조정 해야 합니다. 규모 확장을 선호 합니다. 규모 확장은 기존 클러스터에 추가 컴퓨터 (노드라고 함) 또는 응용 프로그램 인스턴스를 추가 하 여 수평으로 수행 됩니다. Kubernetes에서 앱에 대 한 구성 설정 (예: [노드 풀 크기](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)조정)을 조정 하거나 자동 크기 조정을 통해 수동으로 크기를 조정할 수 있습니다.

AKS 클러스터는 다음 두 가지 방법 중 하나로 자동 크기 조정 될 수 있습니다.

먼저 [수평 Pod Autoscaler](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale#autoscale-pods) 는 리소스 수요를 모니터링 하 고이에 맞게 Pod 복제본을 자동으로 조정 합니다. 트래픽이 늘어나면 서비스를 확장 하기 위해 추가 복제본이 자동으로 프로 비전 됩니다. 마찬가지로, 수요가 감소 하는 경우 서비스를 확장 하기 위해 제거 됩니다. 크기를 조정할 메트릭 (예: CPU 사용량)을 정의 합니다. 실행할 복제본의 최소 및 최대 수를 지정할 수도 있습니다. AKS는 메트릭을 모니터링 하 고 그에 따라 크기를 조정 합니다.

그런 다음 [AKS Cluster Autoscaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler) 기능을 사용 하면 Kubernetes 클러스터에서 계산 노드를 자동으로 확장 하 여 수요를 충족할 수 있습니다. 이를 통해 더 많은 계산 용량이 필요한 경우 기본 Azure 가상 머신 확장 집합에 새 Vm을 자동으로 추가할 수 있습니다. 또한 더 이상 필요 하지 않은 경우 노드를 제거 합니다.

그림 3-13에서는 이러한 두 크기 조정 서비스 간의 관계를 보여 줍니다.

![App Service 계획을 확장 합니다.](./media/aks-cluster-autoscaler.png)

**그림 3-13**. App Service 계획을 확장 합니다.

함께 작동 하 여 변동 수요를 지원 하기 위해 컨테이너 인스턴스와 계산 노드의 최적 수를 확인 합니다. 수평 pod autoscaler는 필요한 pod의 수를 최적화 합니다. 클러스터 autoscaler는 필요한 노드 수를 최적화 합니다.

### <a name="scaling-azure-functions"></a>Azure Functions 크기 조정

Azure Functions는 수요에 따라 자동으로 확장 됩니다. 서버 리소스는 트리거된 이벤트의 수에 따라 동적으로 할당 되 고 제거 됩니다. 함수가 실행 될 때 사용 되는 계산 리소스에 대해서만 요금이 청구 됩니다. 청구는 실행 횟수, 실행 시간 및 사용 된 메모리를 기준으로 합니다.

기본 소비 계획은 대부분의 앱에서 경제적이 고 확장 가능한 솔루션을 제공 하지만 premium 옵션을 사용 하면 개발자는 사용자 지정 Azure Functions 요구 사항에 유연 하 게 사용할 수 있습니다. Premium 요금제로 업그레이드 하면 인스턴스 크기, 사전 준비 인스턴스 (콜드 시작 지연 방지) 및 전용 Vm을 제어할 수 있습니다.

>[!div class="step-by-step"]
>[이전](deploy-containers-azure.md)
>[다음](other-deployment-options.md)
