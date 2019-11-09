---
title: Azure Kubernetes Service의 모니터링
description: Azure Kubernetes Service의 모니터링
ms.date: 09/23/2019
ms.openlocfilehash: 71192601eac2169db188b25da3dc91b71b860903
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841128"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Azure Kubernetes Service의 모니터링

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Kubernetes의 기본 제공 로깅은 기본 형식입니다. 그러나 로그를 Kubernetes 하 고 적절 하 게 분석할 수 있는 위치에 저장할 수 있는 몇 가지 유용한 옵션이 있습니다. AKS 클러스터를 모니터링 해야 하는 경우 Kubernetes에 대 한 탄력적 스택 구성은 훌륭한 솔루션입니다.

## <a name="elastic-stack"></a>탄력적 스택

탄력적 스택은 Kubernetes 클러스터에서 정보를 수집 하는 강력한 옵션입니다. Kubernetes는 Elasticsearch 끝점에 로그를 보내는 작업을 지원 하며, [대부분](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)의 경우 그림 7-5에 표시 된 것 처럼 환경 변수를 설정 하기만 하면 됩니다.

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**그림 7-5** -Kubernetes에 대 한 구성 변수

그러면 클러스터에 Elasticsearch가 설치 되 고 모든 클러스터 로그를 대상으로 전송 됩니다.

Kubernetes의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예](./media/kibana-dashboard.png)
**그림 7-6**을 ![합니다. Kubernetes의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예

## <a name="azure-container-monitoring"></a>Azure 컨테이너 모니터링

Azure 컨테이너 모니터링은 Kubernetes 뿐만 아니라 DC/OS, Docker Swarm 및 Red Hat OpenShift와 같은 다른 오케스트레이션 엔진에서 로그를 사용 하도록 지원 합니다.

다양 한 컨테이너의 로그를 사용 하 ![](./media/containers-diagram.png)
**그림 7-7**.  다양 한 컨테이너의 로그 사용

로그 및 메트릭 정보는 클러스터에서 실행 되는 컨테이너 뿐만 아니라 클러스터 호스트 자체 에서도 수집 됩니다. 두 로그 정보의 상관 관계를 설정 하 여 오류를 보다 쉽게 추적할 수 있습니다.

로그 수집기 설치는 [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) 및 [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) 클러스터에 따라 다릅니다. 그러나 두 경우 모두 로그 수집은 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)로 구현 됩니다. 즉, 로그 수집기는 각 노드에서 컨테이너로 실행 됩니다.

Orchestrator 또는 운영 체제에서 Azure Monitor 디먼을 실행 하는 것과 관계 없이 로그 정보는 사용자가 익숙한 동일한 Azure Monitor 도구에 전달 됩니다. 이를 통해 하이브리드 Kubernetes/Azure Functions 환경과 같은 여러 로그 원본을 혼합 하는 환경에서 병렬 환경이 보장 됩니다.

실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드를 ![합니다. **그림 7-8**을](./media/containers-dashboard.png)
합니다. 실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드

## <a name="logfinalize"></a>.Log. Finalize ()

로깅은 가장 간과 되는 응용 프로그램을 대규모로 배포 하는 가장 중요 한 부분 중 하나입니다. 응용 프로그램의 크기와 복잡성이 증가 함에 따라 응용 프로그램을 디버깅 하는 데 어려움이 있습니다. 최고 품질의 로그를 사용 가능 하 게 설정 하면 디버깅이 훨씬 간편해 지 며 "거의 불가능 하지 않음" 영역에서 "편리한 환경"으로 이동 합니다.

>[!div class="step-by-step"]
>[이전](logging-with-elastic-stack.md)
>[다음](azure-monitor.md)
