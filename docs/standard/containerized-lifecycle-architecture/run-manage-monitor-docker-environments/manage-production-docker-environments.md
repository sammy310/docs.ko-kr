---
title: 프로덕션 Docker 환경 관리
description: 컨테이너 기반 프로덕션 환경을 관리 하는 것에 대 한 주요 내용을 알아야 가져옵니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3f8c51b95f52a655de470ac237c51dd4ee9c13eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672102"
---
# <a name="manage-production-docker-environments"></a>프로덕션 Docker 환경 관리

클러스터 관리 및 오케스트레이션은 호스트 그룹을 제어 하는 과정입니다. 이 추가 하 고 호스트 및 컨테이너의 현재 상태에 대 한 정보를 가져오기 시작 하 고 프로세스를 중지 하는 클러스터에서 호스트 제거 될 수 있습니다. 클러스터 관리 및 오케스트레이션은 밀접 한 관련이 스케줄러 있어야 하므로 각 호스트에 대 한 액세스 클러스터의 서비스를 예약 하려면 예약 합니다. 따라서 동일한 도구 모두를 위해 자주 사용 됩니다.

## <a name="container-service-and-management-tools"></a>컨테이너 서비스 및 관리 도구

Container Service는 인기 있는 오픈 소스 컨테이너 클러스터링 및 오케스트레이션 솔루션의 신속한 배포를 제공합니다. Docker 이미지를 사용 하 여 응용 프로그램 컨테이너가 완전히 이식 가능한 지 확인 합니다. 컨테이너 서비스를 사용 하 여 DC/OS (powered by Mesosphere 및 Apache Mesos) 배포할 수 있으며 이러한 응용 프로그램을 수천 초 단위로 확장할 수 있도록 Azure portal 또는 Azure Resource Manager 템플릿을 사용 하는 Docker Swarm 클러스터-수많은 등의 컨테이너입니다.

Azure Virtual Machine Scale Sets를 사용 하 여 이러한 클러스터를 배포 하 고 클러스터 네트워킹 및 저장소에 대 한 Azure 제품 활용 합니다. 컨테이너 서비스에 액세스 하려면 Azure 구독이 필요 합니다. Container Service를 사용 하 여 오케스트레이션 계층에 포함 되는 응용 프로그램 이식성을 유지 하면서 Azure의 엔터프라이즈급 기능을 활용을 걸릴 수 있습니다.

표 6-1의 오 케 스트레이 터, 스케줄러 및 클러스터링 플랫폼 관련 된 일반적인 관리 도구를 나열 합니다.

**표 6-1**합니다. Docker 관리 도구

| 관리 도구 | 설명 | 관련된 오 케 스트레이 터 |
|------------------|-------------|-----------------------|
| [컨테이너에 대 한 azure Monitor](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Azure는 Kubernetes 관리 도구 전용 | Azure Kubernetes 서비스 (AKS) |
| [Kubernetes 웹 UI (대시보드)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Kubernetes 관리 도구를 모니터링 하 고 로컬 Kubernetes 클러스터를 관리할 수 있습니다. | AKS(Azure Kubernetes Service)<br/>로컬 Kubernetes |
| [Service Fabric에 대 한 azure portal](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Azure에서 온 프레미스, 로컬 개발 및 기타 클라우드에서 Service Fabric 클러스터를 관리 하는 것에 대 한 온라인 및 데스크톱 버전 | Azure Service Fabric |
| [컨테이너 모니터링 (Azure 모니터)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | 일반 컨테이너 관리 y 모니터링 솔루션입니다. 통해 Kubernetes 클러스터를 관리할 수 있습니다 [컨테이너에 대 한 Azure Monitor](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview)합니다. | Azure Service Fabric<br/>AKS(Azure Kubernetes Service)<br/>Mesosphere DC/OS를 사용 합니다. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

클러스터 배포 및 관리에 대 한 다른 선택에는 Azure Service Fabric은입니다. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) 는 개발자 뿐만 아니라 컨테이너 오케스트레이션을 포함 하는 Microsoft 마이크로 서비스 플랫폼 프로그래밍 모델 확장성이 뛰어난 마이크로 서비스 응용 프로그램을 빌드할 수 있습니다. Service Fabric Linux 및 Windows 컨테이너에서 Docker를 지원 하 고 Windows 및 Linux 서버에서 실행할 수 있습니다.

다음은 서비스 패브릭 관리 도구:

- [Service Fabric에 대 한 azure portal](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) 클러스터 관련 작업 (만들기/업데이트/삭제)는 클러스터 또는 인프라 (Vm, 부하 분산 장치, 네트워킹 등)를 구성 합니다.

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) 특수화 된 웹 UI 및 insights 및 Service Fabric 클러스터, 노드/v m의 관점에서 응용 프로그램 및 서비스의 관점에서 특정 작업을 제공 하는 데스크톱 다중 플랫폼 도구입니다.

>[!div class="step-by-step"]
>[이전](run-microservices-based-applications-in-production.md)
>[다음](monitor-containerized-application-services.md)
