---
title: 컨테이너 및 서버리스 애플리케이션 크기 조정
description: Azure Kubernetes Service를 사용 하 여 클라우드 네이티브 응용 프로그램을 확장 하 여 사용자 요구에 맞게 개별 컴퓨터 리소스를 늘리거나 응용 프로그램 클러스터의 컴퓨터 수를 늘립니다.
ms.date: 09/23/2019
ms.openlocfilehash: 2d0537fb3ed56beb4eccbf9b8c34a5d87793413b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841014"
---
# <a name="scaling-containers-and-serverless-applications"></a>컨테이너 및 서버리스 애플리케이션 크기 조정

응용 프로그램의 크기를 조정 하는 일반적인 방법에는 수직 확장 및 수평 확장 이라는 두 가지가 있습니다. 이전에는 하나의 호스트에 기능을 추가 하는 것을 참조 하지만, 후자는 전체 호스트 수에 추가 하는 것을 나타냅니다. 이에 대해 생각 하는 데 사용 하는 일반적인 비유는 마을에서 사용자와 일부 친구를 가져오는 방법입니다. 단 하나의 friend 인 경우 두 사용자의 레이스 자동차를 홉 할 수 있습니다. 그러나 3 또는 4 인 경우에는 SUVs 또는 minivan 중 하나를 사용 하 여 용량을 늘리기 위해 확장 해야 할 수 있습니다. 총 수가 수십 개 이상으로 증가 하는 경우에는 여러 차량을 사용 해야 할 수 있습니다 (누군가가 버스를 구동 하지 않는 경우). 더 많은 인스턴스를 추가 하 여 확장 하는 개념을 보여 줍니다 (이 경우 더 많은 차량). 응용 프로그램에 적용 되는 방식을 살펴보겠습니다.

## <a name="the-simple-solution-scaling-up"></a>간단한 해결 방법: 수직 확장

기존 서버를 업그레이드 하 여 더 많은 리소스 (CPU, 메모리, 디스크 i/o 속도, 네트워크 i/o 속도)를 제공 하는 프로세스를 *확장*이라고 합니다. 클라우드 네이티브 응용 프로그램에서 수직 확장은 일반적으로 실제 컴퓨터에서 실제 하드웨어를 구입 하 고 설치 하는 것을 의미 하지 않으며, 사용 가능한 옵션 목록에서 더 많은 지원 계획을 선택 합니다. 일반적으로 클라우드 네이티브 앱은 Kubernetes node 풀에서 개별 노드를 호스트 하는 데 사용 되는 VM (가상 머신) 크기를 수정 하 여 확장 합니다. 노드, 클러스터 및 pod와 같은 Kubernetes 개념은 [다음 섹션](leverage-containers-orchestrators.md)에서 자세히 설명 합니다. Azure는 [Windows](https://docs.microsoft.com/azure/virtual-machines/windows/sizes?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json) 및 [Linux](https://docs.microsoft.com/azure/virtual-machines/linux/sizes)를 실행 하는 다양 한 VM 크기를 지원 합니다. 응용 프로그램을 수직으로 확장 하려면 노드 VM 크기가 큰 새 노드 풀을 만든 다음 워크 로드를 새 풀로 마이그레이션합니다. 여기에는 현재 미리 보기로 제공 되는 기능인 [AKS 클러스터에 대 한 여러 노드 풀이](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)필요 합니다. 서버를 사용 하지 않는 앱은 [프리미엄 계획](https://docs.microsoft.com/azure/azure-functions/functions-scale) 및 프리미엄 인스턴스 크기를 선택 하거나 다른 전용 app service 계획을 선택 하 여 확장 합니다.

## <a name="scaling-out-cloud-native-apps"></a>클라우드-네이티브 앱 확장

클라우드 네이티브 앱은 노드를 추가 하거나 서비스 요청에 pod를 추가 하 여 확장을 지원 합니다. 이는 앱에 대 한 구성 설정 (예: [노드 풀 크기 조정](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually))을 조정 하거나 자동 크기 *조정을*통해 수동으로 수행할 수 있습니다. 자동 크기 조정은 자동 온도 조절기에서 추가 열 또는 냉각을 호출 하 여 온도에 응답 하는 방법과 비슷하게 요청에 응답 하기 위해 앱에서 사용 하는 리소스를 조정 합니다. 자동 크기 조정을 사용 하는 경우 수동 크기 조정을 사용할 수 없습니다.

AKS 클러스터는 다음 두 가지 방법 중 하나로 확장할 수 있습니다.

- [클러스터 autoscaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler) 는 리소스 제약으로 인해 노드에 대해 예약할 수 없는 pod을 감시 합니다. 필요에 따라 추가 노드를 추가 합니다.
- **수평 pod autoscaler** 는 Kubernetes 클러스터에서 메트릭 서버를 사용 하 여 pod의 리소스 요구 사항을 모니터링 합니다. 서비스가 더 많은 리소스를 필요로 하는 경우 autoscaler는 pod의 수를 늘립니다.

그림 3-13에서는 이러한 두 크기 조정 서비스 간의 관계를 보여 줍니다.

![App Service 계획을 확장 합니다.](./media/aks-cluster-autoscaler.png)

**그림 3-13**. App Service 계획을 확장 합니다.

이러한 서비스는 필요에 따라 pod 또는 노드 수를 줄일 수도 있습니다. 이러한 두 서비스는 함께 작동 하 고 종종 클러스터에 함께 배포 됩니다. 결합 된 수평 pod autoscaler는 응용 프로그램 수요를 충족 하는 데 필요한 pod 수를 실행 하는 데 초점을 맞춥니다. 클러스터 autoscaler는 예약 된 pod을 지 원하는 데 필요한 노드 수를 실행 하는 데 초점을 맞추고 있습니다.

### <a name="scaling-azure-functions"></a>크기 조정 Azure Functions

Azure Functions 자동 확장을 지원 합니다. 기본 소비 계획은 들어오는 이벤트의 수에 따라 동적으로 리소스를 추가 (및 제거) 합니다. 실행 횟수, 실행 시간 및 사용 된 메모리에 따라 함수가 실행 중일 때 사용 되는 계산 리소스에 대해서만 요금이 청구 됩니다. 프리미엄 요금제를 사용 하면 이러한 같은 기능을 사용할 수 있지만, 사용 되는 인스턴스 크기를 제어 하 고, 인스턴스를 이미 준비 (콜드 시작 지연 방지) 하 고, 함수를 실행할 전용 Vm을 구성할 수도 있습니다. 기본 구성은 대부분의 앱에서 경제적이 고 확장 가능한 솔루션을 제공 해야 하지만, premium 옵션을 사용 하면 개발자는 사용자 지정 Azure Functions 요구 사항에 유연 하 게 사용할 수 있습니다.

## <a name="references"></a>참조 항목

- [여러 노드 풀 AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS Cluster Autoscaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [자습서: AKS에서 응용 프로그램 크기 조정](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Azure Functions 크기 조정 및 호스팅](https://docs.microsoft.com/azure/azure-functions/functions-scale)

>[!div class="step-by-step"]
>[이전](deploy-containers-azure.md)
>[다음](other-deployment-options.md)
