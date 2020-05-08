---
title: 컨테이너 및 오케스트레이터 활용
description: Azure에서 Docker 컨테이너 및 Kubernetes Orchestrator 활용
ms.date: 04/13/2020
ms.openlocfilehash: 64c6c0666398d9ccbc87efad18017bf278568fc4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895547"
---
# <a name="leveraging-containers-and-orchestrators"></a>컨테이너 및 오케스트레이터 활용

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

컨테이너 및 orchestrator는 모놀리식 배포 방법에 일반적으로 발생 하는 문제를 해결 하도록 설계 되었습니다.

## <a name="challenges-with-monolithic-deployments"></a>모놀리식 배포 문제

일반적으로 대부분의 응용 프로그램은 단일 단위로 배포 됩니다. 이러한 응용 프로그램을 monolith 라고 합니다. 그림 3-1에 표시 된 것 처럼 여러 모듈 또는 어셈블리로 구성 된 경우에도 응용 프로그램을 단일 단위로 배포 하는 일반적인 방법은 모놀리식 architecture 이라고 합니다.

![모놀리식 아키텍처.](./media/monolithic-architecture.png)

**그림 3-1**. 모놀리식 아키텍처.

모놀리식 아키텍처는 간단 하지만 다음과 같은 다양 한 문제를 겪고 있습니다.

### <a name="deployment"></a>배포

모놀리식 응용 프로그램은 약간만 변경 된 경우에도 전체 응용 프로그램을 완전히 배포 해야 합니다. 전체 배포는 비용이 많이 들고 오류가 발생할 수 있습니다. 또한 일시적으로 사용할 수 없는 영향을 주는 응용 프로그램을 다시 시작 해야 합니다.

### <a name="scaling"></a>확장

모놀리식 응용 프로그램은 전적으로 많은 기능을 필요로 하는 단일 컴퓨터 인스턴스에서 호스팅됩니다. 모놀리식의 어느 부분에서 확장이 필요한 경우에는 다른 컴퓨터에 전체 응용 프로그램의 다른 복사본을 배포 해야 합니다. Monolith를 사용 하면 응용 프로그램 구성 요소를 개별적으로 규모를 조정할 수 없습니다. 크기를 조정 하지 않아도 되는 구성 요소는 비효율적 이며 비용이 많이 드는 리소스 사용량을 초래 합니다.

### <a name="environment"></a>환경

모놀리식 응용 프로그램은 일반적으로 미리 설치 된 운영 체제, 런타임 및 라이브러리 종속성이 있는 호스팅 환경에 배포 됩니다. 이 환경은 응용 프로그램을 개발 하거나 테스트할 때와 일치 하지 않을 수 있습니다. 응용 프로그램 환경에서의 불일치는 모놀리식 배포에 대 한 문제의 일반적인 원인입니다.

### <a name="coupling"></a>커플링

모놀리식 응용 프로그램은 기능 구성 요소에 대해 높은 결합을 경험할 가능성이 높습니다. 하드 경계가 없으면 시스템 변경으로 인해 의도 하지 않은 부작용이 발생 하는 경우가 많습니다. 새로운 기능/픽스는 복잡 하 고 시간이 많이 걸리고 구현 비용이 많이 듭니다. 업데이트에는 광범위 한 테스트가 필요 합니다. 또한 결합을 사용 하면 구성 요소를 리팩터링 하거나 대체 구현에서 교환 하기가 어려워집니다. 문제를 엄격 하 게 분리 하 여 생성 된 경우에도 아키텍처 erosion은의를 모놀리식 코드 베이스 deteriorates로 설정 하 고 "특수 한 경우"를 종료 하지 않습니다.

### <a name="platform-lock-in"></a>플랫폼 잠금

모놀리식 응용 프로그램은 단일 기술 스택을 사용 하 여 생성 됩니다. 일관성을 제공 하는 동안 이러한 약정은 혁신에 장벽이 될 수 있습니다. 최신 기술이 더 적합 한 경우에도 응용 프로그램의 현재 스택을 사용 하 여 새로운 기능 및 구성 요소를 빌드할 수 있습니다. 더 장기적인 위험은 기술 스택이 오래 되 고 사용 되지 않는 것입니다. 전체 응용 프로그램을 새로운 최신 플랫폼으로 다시 설계 하는 것이 가장 저렴 하 고 위험 합니다.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>컨테이너와 orchestrator의 이점은 무엇 인가요?

1 장에서는 컨테이너를 소개 했습니다. 클라우드 기본 [구조](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) 를 시작 하는 엔터프라이즈에 대 한 지침-클라우드 네이티브 컨테이너 화에 대 한 첫 번째 단계인 cncf (Cloud Native 컴퓨팅 Foundation) 순위를 강조 했습니다. 이 섹션에서는 컨테이너의 이점에 대해 설명 합니다.

Docker는 가장 인기 있는 컨테이너 관리 플랫폼입니다. Linux 또는 Windows의 컨테이너와 함께 작동 합니다. 컨테이너는 모든 시스템에서 동일한 방식으로 실행 되는 별도의 재현 가능한 응용 프로그램 환경을 제공 합니다. 이를 통해 클라우드 네이티브 서비스를 개발 및 호스트할 수 있습니다. 컨테이너는 서로 격리 됩니다. 동일한 호스트 하드웨어의 두 컨테이너는 충돌을 발생 시 키 지 않으면 서 다른 버전의 소프트웨어를 사용할 수 있습니다.

컨테이너는 프로젝트 아티팩트가 되며 소스 제어에 체크 인 되는 간단한 텍스트 기반 파일로 정의 됩니다. 전체 서버 및 가상 컴퓨터를 업데이트 하는 데 수동 작업이 필요 하지만 컨테이너는 쉽게 버전 제어 됩니다. 컨테이너에서 실행 되도록 빌드된 앱은 자동화 된 도구를 사용 하 여 빌드 파이프라인의 일부로 개발, 테스트 및 배포할 수 있습니다.

컨테이너는 변경할 수 없습니다. 컨테이너를 정의한 후에는 정확히 동일한 방식으로 다시 만들고 실행할 수 있습니다. 이 불변성은 구성 요소 기반 디자인에 적합 합니다. 응용 프로그램의 일부가 다른 부분과 다르게 발전 하는 경우 가장 자주 변경 되는 파트를 배포할 수 있는 경우 전체 앱을 다시 배포 해야 하는 이유는 무엇 인가요? 앱의 다양 한 기능 및 교차를 분리 하는 작업은 별도의 단위로 나눌 수 있습니다. 그림 3-2에서는 특정 기능이 나 기능을 위임 하 여 모놀리식 앱이 컨테이너 및 마이크로 서비스를 활용 하는 방법을 보여 줍니다. 앱 자체의 나머지 기능도 컨테이너 화 된 되었습니다.

컨테이너는 변경할 수 없습니다. 컨테이너를 정의한 후에는 정확히 동일한 방식으로 다시 만들고 실행할 수 있습니다. 이 불변성은 구성 요소 기반 디자인에 적합 합니다. 응용 프로그램의 일부가 다른 부분과 다르게 발전 하는 경우 가장 자주 변경 되는 파트를 배포할 수 있는 경우 전체 앱을 다시 배포 해야 하는 이유는 무엇 인가요? 앱의 다양 한 기능 및 교차를 분리 하는 작업은 별도의 단위로 나눌 수 있습니다. 그림 3-2에서는 특정 기능이 나 기능을 위임 하 여 모놀리식 앱이 컨테이너 및 마이크로 서비스를 활용 하는 방법을 보여 줍니다. 앱 자체의 나머지 기능도 컨테이너 화 된 되었습니다.

![백 엔드에서 마이크로 서비스를 사용 하도록 모놀리식 앱을 분리 합니다. ](./media/breaking-up-monolith-with-backend-microservices.png)
 **그림 3-2**. 백 엔드에서 마이크로 서비스를 사용 하도록 모놀리식 앱을 분리 합니다.

각 클라우드 네이티브 서비스는 별도의 컨테이너에 빌드 및 배포 됩니다. 각는 필요에 따라 업데이트할 수 있습니다. 각 서비스에 해당 하는 리소스가 있는 노드에서 개별 서비스를 호스트할 수 있습니다. 각 서비스를 실행 하는 환경은 개발, 테스트 및 프로덕션 환경에서 공유 되 고 쉽게 버전이 관리 되는 변경 불가능 합니다. 응용 프로그램의 서로 다른 영역 간 결합은 서비스 간 호출 또는 메시지로 명시적으로 발생 하며,이는 monolith 내에서 컴파일 타임 종속성이 아닙니다. 응용 프로그램의 나머지 부분을 변경할 필요 없이 지정 된 기능에 가장 적합 한 기술을 선택할 수도 있습니다.

컨테이너 화 된 services에는 자동화 된 관리가 필요 합니다. 독립적으로 배포 된 컨테이너의 많은 집합을 수동으로 관리 하는 것은 불가능 합니다. 예를 들어 다음 작업을 고려 하십시오.

- 여러 컴퓨터의 클러스터에서 컨테이너 인스턴스를 프로 비전 하는 방법
- 배포 된 후 컨테이너는 어떻게 서로를 검색 하 고 통신할 수 있나요?
- 컨테이너는 주문형으로 규모를 확장 하거나 축소할 수 있나요?
- 각 컨테이너의 상태를 모니터링 하려면 어떻게 해야 하나요?
- 하드웨어 및 소프트웨어 오류에 대해 컨테이너를 어떻게 보호 하나요?
- 가동 중지 시간이 없는 라이브 응용 프로그램에 대해 컨테이너를 업그레이드 하려면 어떻게 해야 하나요?

Container orchestrator는 이러한 문제를 해결 하 고 이러한 문제를 자동화 합니다.

클라우드 네이티브 에코 시스템에서 Kubernetes는 사실상 컨테이너 orchestrator가 되었습니다. 이 플랫폼은 CNCF (Cloud Native 컴퓨팅 Foundation)에서 관리 하는 오픈 소스 플랫폼입니다. Kubernetes는 컴퓨터 클러스터에서 컨테이너 화 된 워크 로드의 배포, 크기 조정 및 운영 문제를 자동화 합니다. 그러나 Kubernetes을 설치 하 고 관리 하는 것은 어렵습니다 복잡 합니다.

Kubernetes를 클라우드 공급 업체에서 관리 되는 서비스로 활용 하는 것이 훨씬 더 나은 방법입니다. Azure 클라우드는 완전히 관리 되는 Kubernetes platform [Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/)를 제공 합니다. AKS는 Kubernetes 관리의 복잡성 및 운영 오버 헤드를 요약 합니다. Kubernetes를 클라우드 서비스로 사용 합니다. Microsoft는이를 관리 하 고 지 원하는 작업을 담당 합니다. 또한 AKS는 다른 Azure 서비스 및 개발 도구와 긴밀 하 게 통합 됩니다.

AKS는 클러스터 기반 기술입니다. 페더레이션된 가상 머신 또는 노드의 풀이 Azure 클라우드에 배포 됩니다. 이들은 모두 항상 사용 가능한 환경 또는 클러스터를 형성 합니다. 클러스터는 클라우드 네이티브 응용 프로그램에 원활한 단일 엔터티로 표시 됩니다. 내부적으로 AKS는 부하를 균등 하 게 분산 하는 미리 정의 된 전략에 따라 이러한 노드에서 컨테이너 화 된 서비스를 배포 합니다.

컨테이너 화 된 services에는 자동화 된 관리가 필요 합니다. 독립적으로 배포 된 컨테이너의 많은 집합을 수동으로 관리 하는 것은 불가능 합니다. 예를 들어 다음 작업을 고려 하십시오.

- 여러 컴퓨터의 클러스터에서 컨테이너 인스턴스를 프로 비전 하는 방법
- 배포 된 후 컨테이너는 어떻게 서로를 검색 하 고 통신할 수 있나요?
- 컨테이너는 주문형으로 규모를 확장 하거나 축소할 수 있나요?
- 각 컨테이너의 상태를 모니터링 하려면 어떻게 해야 하나요?
- 하드웨어 및 소프트웨어 오류에 대해 컨테이너를 어떻게 보호 하나요?
- 가동 중지 시간이 없는 라이브 응용 프로그램에 대해 컨테이너를 업그레이드 하려면 어떻게 해야 하나요?

Container orchestrator는 이러한 문제를 해결 하 고 이러한 문제를 자동화 합니다.

클라우드 네이티브 에코 시스템에서 Kubernetes는 사실상 컨테이너 orchestrator가 되었습니다. 이 플랫폼은 CNCF (Cloud Native 컴퓨팅 Foundation)에서 관리 하는 오픈 소스 플랫폼입니다. Kubernetes는 컴퓨터 클러스터에서 컨테이너 화 된 워크 로드의 배포, 크기 조정 및 운영 문제를 자동화 합니다. 그러나 Kubernetes을 설치 하 고 관리 하는 것은 어렵습니다 복잡 합니다.

Kubernetes를 클라우드 공급 업체에서 관리 되는 서비스로 활용 하는 것이 훨씬 더 나은 방법입니다. Azure 클라우드는 완전히 관리 되는 Kubernetes platform [Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/)를 제공 합니다. AKS는 Kubernetes 관리의 복잡성 및 운영 오버 헤드를 요약 합니다. Kubernetes를 클라우드 서비스로 사용 합니다. Microsoft는이를 관리 하 고 지 원하는 작업을 담당 합니다. 또한 AKS는 다른 Azure 서비스 및 개발 도구와 긴밀 하 게 통합 됩니다.

AKS는 클러스터 기반 기술입니다. 페더레이션된 가상 머신 또는 노드의 풀이 Azure 클라우드에 배포 됩니다. 이들은 모두 항상 사용 가능한 환경 또는 클러스터를 형성 합니다. 클러스터는 클라우드 네이티브 응용 프로그램에 원활한 단일 엔터티로 표시 됩니다. 내부적으로 AKS는 부하를 균등 하 게 분산 하는 미리 정의 된 전략에 따라 이러한 노드에서 컨테이너 화 된 서비스를 배포 합니다.

## <a name="what-are-the-scaling-benefits"></a>크기 조정 혜택은 무엇 인가요?

컨테이너를 기반으로 하는 서비스는 Kubernetes 같은 오케스트레이션 도구에서 제공 하는 크기 조정 혜택을 활용할 수 있습니다. 기본적으로 컨테이너는 자신에 대 한 정보를 알 수 있습니다. 여러 컨테이너를 함께 사용 해야 하는 경우에는 더 높은 수준으로 구성 해야 합니다. 많은 수의 컨테이너와 네트워크 구성과 같은 공유 종속성을 구성 하는 것은 오케스트레이션 도구가 날짜를 절약 하는 데 제공 되는 위치입니다. Kubernetes는 컨테이너 그룹에 대 한 추상화 계층을 만들고 *pod*으로 구성 합니다. Pod는 *노드라고*하는 작업자 컴퓨터에서 실행 됩니다. 이 구성 된 구조를 *클러스터*라고 합니다. 그림 3-3에서는 Kubernetes 클러스터의 여러 구성 요소를 보여 줍니다.

![Kubernetes 클러스터 구성 요소 ](./media/kubernetes-cluster-components.png)
 **그림 3-3**. Kubernetes 클러스터 구성 요소

컨테이너 화 된 워크 로드 크기 조정은 컨테이너 orchestrator의 핵심 기능입니다. AKS는 두 차원 (컨테이너 인스턴스 및 계산 노드)에서 자동 크기 조정을 지원 합니다. AKS는 수요 급증에 신속 하 고 효율적으로 대응 하 고 리소스를 더 추가할 수 있는 기능을 제공 합니다. AKS의 크기 조정에 대해서는이 장의 뒷부분에서 설명 합니다.

### <a name="declarative-versus-imperative"></a>선언적 및 명령적

Kubernetes는 선언적 및 명령적 구성을 모두 지원 합니다. 명령적 방식에는 각 단계를 수행할 작업을 Kubernetes 알려주는 다양 한 명령이 실행 됩니다. 이 이미지를 실행 합니다. 이 pod를 삭제 합니다. 이 포트를 노출 합니다. 선언적 접근법을 사용 하 여 수행할 작업 대신 원하는 작업을 설명 하는 매니페스트 라는 구성 파일을 만듭니다. Kubernetes는 매니페스트를 읽고 원하는 최종 상태를 실제 끝 상태로 변환 합니다.

명령적 명령은 학습 및 대화형 실험에 유용 합니다. 그러나 Kubernetes 매니페스트 파일을 선언적으로 만들어 인프라를 코드 방법으로 사용 하 여 안정적이 고 반복 가능한 배포를 제공 하려고 합니다. 매니페스트 파일은 프로젝트 아티팩트가 되며 CI/CD 파이프라인에서 Kubernetes 배포를 자동화 하는 데 사용 됩니다.

명령적 명령을 사용 하 여 클러스터를 이미 구성한 경우를 사용 `kubectl get svc SERVICENAME -o yaml > service.yaml`하 여 선언적 매니페스트를 내보낼 수 있습니다. 이 명령은 아래와 비슷한 매니페스트를 생성 합니다.

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

선언적 구성을 사용 하는 경우 구성 파일이 있는 폴더에 대해를 사용 `kubectl diff -f FOLDERNAME` 하 여 커밋하기 전에 적용 되는 변경 내용을 미리 볼 수 있습니다. 변경 내용을 적용 하려면를 실행 `kubectl apply -f FOLDERNAME`합니다. 를 `-R` 추가 하 여 폴더 계층 구조를 재귀적으로 처리 합니다.

또한 배포 중인 다른 Kubernetes 기능과 함께 선언적 구성을 사용할 수 있습니다. 선언적 배포는 릴리스, 업데이트 및 크기 조정을 관리 하는 데 도움이 됩니다. Kubernetes 배포 컨트롤러에 새 변경 내용을 배포 하거나, 부하를 확장 하거나, 이전 수정 버전으로 롤백하는 방법을 지시 합니다. 클러스터가 불안정 한 경우 선언적 배포에서 클러스터를 자동으로 원하는 상태로 되돌립니다. 예를 들어 노드가 충돌 하는 경우 배포 메커니즘은 대체를 다시 배포 하 여 원하는 상태를 유지 합니다.

선언적 구성을 사용 하면 응용 프로그램 코드와 함께 체크 인하고 버전을 지정할 수 있는 코드로 인프라를 나타낼 수 있습니다. 빌드 및 배포 파이프라인을 사용 하 여 지속적인 배포에 대 한 향상 된 변경 제어 및 향상 된 지원을 제공 합니다.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>컨테이너 및 orchestrator에 적합 한 시나리오는 무엇 인가요?

다음 시나리오는 컨테이너 및 orchestrator를 사용 하는 데 적합 합니다.

### <a name="applications-requiring-high-uptime-and-scalability"></a>높은 작동 시간 및 확장성을 필요로 하는 응용 프로그램

가동 시간 및 확장성 요구 사항이 높은 개별 응용 프로그램은 마이크로 서비스, 컨테이너 및 orchestrator를 사용 하는 클라우드 기본 아키텍처에 적합 한 후보입니다. 컨테이너에서 개발 하 고, 버전이 있는 환경에서 테스트 하 고, 가동 중지 시간 없이 프로덕션에 배포할 수 있습니다. Kubernetes 클러스터를 사용 하면 이러한 앱이 주문형으로 확장 되 고 노드 오류에서 자동으로 복구 될 수도 있습니다.

### <a name="large-numbers-of-applications"></a>많은 수의 응용 프로그램

많은 수의 응용 프로그램을 배포 하 고 유지 관리 하는 조직은 컨테이너와 orchestrator의 이점을 누릴 수 있습니다. 컨테이너 화 된 환경 및 Kubernetes 클러스터를 설정 하는 앞의 노력은 고정 비용입니다. 개별 응용 프로그램을 배포, 유지 관리 및 업데이트 하면 응용 프로그램의 수에 따라 비용이 많이 듭니다. 적은 수의 응용 프로그램을 통해 사용자 지정 응용 프로그램을 수동으로 유지 관리 하는 복잡성이 컨테이너 및 orchestrator를 사용 하 여 솔루션을 구현 하는 비용을 초과할 수 있습니다.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>컨테이너와 orchestrator를 사용 하지 않는 경우는 언제 인가요?

12 단계 앱 원칙에 따라 응용 프로그램을 빌드할 수 없는 경우 컨테이너와 orchestrator을 방지 하는 것이 좋습니다. 이러한 경우 VM 기반 호스팅 플랫폼 또는 일부 하이브리드 시스템을 고려해 야 합니다. 이를 통해 항상 특정 기능을 별도의 컨테이너 또는 서버를 사용 하지 않는 함수로 회전할 수 있습니다.

## <a name="development-resources"></a>개발 리소스

이 섹션에서는 다음 응용 프로그램에 컨테이너 및 orchestrator 사용을 시작 하는 데 도움이 될 수 있는 간단한 개발 리소스 목록을 보여 줍니다. 클라우드 네이티브 마이크로 서비스 아키텍처 앱을 설계 하는 방법에 대 한 지침은이 설명서의 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램용 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)를 참조 하세요.

### <a name="local-kubernetes-development"></a>로컬 Kubernetes 개발

Kubernetes 배포는 프로덕션 환경에서 뛰어난 가치를 제공 하지만 개발 컴퓨터에서 로컬로 실행할 수도 있습니다. 개별 마이크로 서비스를 독립적으로 사용할 수 있지만 프로덕션 환경에 배포할 때 실행 되는 것 처럼 전체 시스템을 로컬로 실행 해야 하는 경우가 있을 수 있습니다. Minikube 및 Docker Desktop을 통해 도움이 되는 몇 가지 도구가 있습니다. 또한 Visual Studio는 Docker 개발용 도구를 제공 합니다.

### <a name="minikube"></a>Minikube

Minikube 란? Minikube 프로젝트에서는 "Minikube가 macOS, Linux 및 Windows에서 로컬 Kubernetes 클러스터를 구현 합니다." 라고 표시 됩니다. 주요 목표는 "로컬 Kubernetes 응용 프로그램 개발에 가장 적합 한 도구 이며이에 적합 한 모든 Kubernetes 기능을 지 원하는 것입니다." Minikube 설치는 Docker와는 별개 이지만 Minikube는 Docker 데스크톱과 지원 되는 것과 다른 하이퍼바이저를 지원 합니다. Minikube에서 현재 지원 되는 Kubernetes 기능은 다음과 같습니다.

- DNS
- NodePorts
- ConfigMaps 및 비밀
- 대시보드
- 컨테이너 런타임: Docker, rkt, CRI 및 containerd
- CNI (컨테이너 네트워크 인터페이스)를 사용 하도록 설정
- 수신

Minikube를 설치한 후 이미지를 다운로드 하 고 로컬 Kubernetes 클러스터를 `minikube start` 시작 하는 명령을 실행 하 여 사용을 빠르게 시작할 수 있습니다. 클러스터가 시작 되 면 표준 Kubernetes `kubectl` 명령을 사용 하 여 상호 작용 합니다.

### <a name="docker-desktop"></a>Docker Desktop

Windows의 Docker Desktop에서 직접 Kubernetes 작업을 수행할 수도 있습니다. Windows 컨테이너를 사용 하는 경우에만 사용할 수 있는 옵션이 며 비 Windows 컨테이너에도 적합 합니다. 그림 3-4에서는 Docker Desktop을 실행할 때 로컬 Kubernetes 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.

![Docker Desktop에서 Kubernetes 구성](./media/docker-desktop-kubernetes.png)

**그림 3-4**. Docker Desktop에서 Kubernetes를 구성 합니다.

Docker Desktop은 컨테이너 화 된 apps를 로컬로 구성 하 고 실행 하는 데 가장 많이 사용 되는 도구입니다. Docker Desktop을 사용 하는 경우 프로덕션 환경에 배포할 정확한 Docker 컨테이너 이미지 집합에 대해 로컬로 개발할 수 있습니다. Docker Desktop은 컨테이너 화 된 apps를 로컬로 빌드, 테스트 및 제공 하도록 설계 되었습니다. Linux 및 Windows 컨테이너를 모두 지원 합니다. 이미지를 Azure Container Registry 또는 Docker Hub와 같은 이미지 레지스트리로 푸시하는 경우 AKS에서 프로덕션으로 끌어오고 배포할 수 있습니다.

### <a name="visual-studio-docker-tooling"></a>Visual Studio Docker 도구

Visual Studio는 웹 기반 응용 프로그램에 대 한 Docker 개발을 지원 합니다. 새 ASP.NET Core 응용 프로그램을 만드는 경우 그림 3-5에 표시 된 것 처럼 Docker 지원으로 구성 하는 옵션을 사용할 수 있습니다.

![Visual Studio에서 Docker 지원 사용](./media/visual-studio-enable-docker-support.png)

**그림 3-5**. Visual Studio에서 Docker 지원 사용

이 옵션을 선택 하면 프로젝트는 해당 루트 `Dockerfile` 에를 사용 하 여 생성 됩니다 .이 프로젝트는 Docker 컨테이너에서 앱을 빌드하고 호스트 하는 데 사용할 수 있습니다. 예제 Dockerfile은 그림 3 -6에 나와 있습니다.

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

**그림 3-6**. Visual Studio에서 Dockerfile을 생성 했습니다.

앱이 실행 되는 기본 동작은 Docker도 사용 하도록 구성 됩니다. 그림 3-7에서는 Docker 지원을 추가 하 여 만든 새 ASP.NET Core 프로젝트에서 사용할 수 있는 다양 한 실행 옵션을 보여 줍니다.

![Visual Studio Docker 실행 옵션](./media/visual-studio-docker-run-options.png)

**그림 3-7**. Visual Studio Docker 실행 옵션

로컬 개발 외에도 [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) 는 여러 개발자가 Azure 내에서 고유한 Kubernetes 구성으로 작업할 수 있는 편리한 방법을 제공 합니다. 그림 3-7에서 볼 수 있듯이, Azure Dev Spaces에서 응용 프로그램을 실행할 수도 있습니다.

또한 언제 든 지 기존 ASP.NET Core 응용 프로그램에 Docker 지원을 추가할 수 있습니다. 그림 3-8에 표시 된 것 처럼 Visual Studio 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고**Docker 지원을** **추가** > 합니다.

**그림 3-8**. Visual Studio에 Docker 지원 추가

그림 3-8에 표시 된 컨테이너 오케스트레이션 지원도 추가할 수 있습니다. 기본적으로 orchestrator는 Kubernetes 및 투구를 사용 합니다. Orchestrator를 선택 하면 `azds.yaml` 파일이 프로젝트 루트에 추가 되 고 Kubernetes에 응용 프로그램을 구성 `charts` 하 고 배포 하는 데 사용 되는 투구 차트가 포함 된 폴더가 추가 됩니다. 그림 3-9에서는 새 프로젝트의 결과 파일을 보여 줍니다.

그림 3-8에 표시 된 컨테이너 오케스트레이션 지원도 추가할 수 있습니다. 기본적으로 orchestrator는 Kubernetes 및 투구를 사용 합니다. Orchestrator를 선택 하면 `azds.yaml` 파일이 프로젝트 루트에 추가 되 고 Kubernetes에 응용 프로그램을 구성 `charts` 하 고 배포 하는 데 사용 되는 투구 차트가 포함 된 폴더가 추가 됩니다. 그림 3-9에서는 새 프로젝트의 결과 파일을 보여 줍니다.

**그림 3-9**. Visual Studio에 오케스트레이션 지원 추가

### <a name="visual-studio-code-docker-tooling"></a>Visual Studio Code Docker 도구

Docker 개발을 지 원하는 Visual Studio Code에 사용할 수 있는 다양 한 확장이 있습니다.

Microsoft는 [Visual Studio Code 확장을 위한 Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)를 제공 합니다. 이 확장은 응용 프로그램에 컨테이너 지원을 추가 하는 프로세스를 간소화 합니다. 필수 파일을 스 캐 폴드 하 고, Docker 이미지를 빌드하고, 컨테이너 내에서 앱을 디버그할 수 있습니다. 확장에는 시작, 중지, 검사, 제거 등의 컨테이너 및 이미지에 대 한 작업을 쉽게 수행할 수 있도록 하는 visual explorer 기능이 있습니다. 또한 확장은 실행 중인 여러 컨테이너를 단일 단위로 관리할 수 있는 Docker Compose 지원 합니다.

>[!div class="step-by-step"]
>[이전](scale-applications.md)
>[다음](leverage-serverless-functions.md)
