---
title: Azure Kubernetes Service의 모니터링
description: Azure Kubernetes Service의 모니터링
ms.date: 05/13/2020
ms.openlocfilehash: 3900f169b9be4f807e72392da38a1224d6ce28e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163702"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Azure Kubernetes Service의 모니터링

Kubernetes의 기본 제공 로깅은 기본 형식입니다. 그러나 로그를 Kubernetes 하 고 적절 하 게 분석할 수 있는 위치에 저장할 수 있는 몇 가지 유용한 옵션이 있습니다. AKS 클러스터를 모니터링 해야 하는 경우 Kubernetes에 대 한 탄력적 스택 구성은 훌륭한 솔루션입니다.

## <a name="azure-monitor-for-containers"></a>컨테이너용 Azure Monitor

[컨테이너에 대 한 Azure Monitor는](/azure/azure-monitor/insights/container-insights-overview) 뿐만 아니라 DC/OS, Docker Swarm 및 Red Hat openshift와 같은 다른 오케스트레이션 엔진에서 뿐만 아니라 Kubernetes의 로그 사용을 지원 합니다.

![다양 한 컨테이너의 로그 사용 ](./media/containers-diagram.png)
 **그림 7-10**. 다양 한 컨테이너의 로그 사용

[프로메테우스](https://prometheus.io/) 는 인기 있는 오픈 소스 메트릭 모니터링 솔루션입니다. 클라우드 기본 계산 파운데이션의 일부입니다. 일반적으로, 프로메테우스를 사용 하려면 고유한 저장소로 프로메테우스 서버를 관리 해야 합니다. 그러나 [컨테이너에 대 한 Azure Monitor는 프로메테우스 메트릭 끝점과의 직접 통합을 제공](/azure/azure-monitor/insights/container-insights-prometheus-integration)하므로 별도의 서버가 필요 하지 않습니다.

로그 및 메트릭 정보는 클러스터에서 실행 되는 컨테이너 뿐만 아니라 클러스터 호스트 자체 에서도 수집 됩니다. 두 로그 정보의 상관 관계를 설정 하 여 오류를 보다 쉽게 추적할 수 있습니다.

로그 수집기 설치는 [Windows](/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) 및 [Linux](/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) 클러스터에 따라 다릅니다. 그러나 두 경우 모두 로그 수집은 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)로 구현 됩니다. 즉, 로그 수집기는 각 노드에서 컨테이너로 실행 됩니다.

Orchestrator 또는 운영 체제에서 Azure Monitor 디먼을 실행 하는 것과 관계 없이 로그 정보는 사용자가 익숙한 동일한 Azure Monitor 도구에 전달 됩니다. 이를 통해 하이브리드 Kubernetes/Azure Functions 환경과 같은 여러 로그 원본을 혼합 하는 환경에서 병렬 환경이 보장 됩니다.

![실행 중인 많은 컨테이너 ](./media/containers-dashboard.png)
 의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드 **그림 7-11**. 실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드

## <a name="logfinalize"></a>.Log. Finalize ()

로깅은 가장 간과 되는 응용 프로그램을 대규모로 배포 하는 가장 중요 한 부분 중 하나입니다. 응용 프로그램의 크기와 복잡성이 증가 함에 따라 응용 프로그램을 디버깅 하는 데 어려움이 있습니다. 최고 품질의 로그를 사용 가능 하 게 설정 하면 디버깅이 훨씬 간편해 지 며 "거의 불가능 하지 않음" 영역에서 "편리한 환경"으로 이동 합니다.

>[!div class="step-by-step"]
>[이전](logging-with-elastic-stack.md)
>[다음](azure-monitor.md)
