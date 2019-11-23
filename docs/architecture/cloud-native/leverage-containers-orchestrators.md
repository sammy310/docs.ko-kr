---
title: 컨테이너 및 오케스트레이터 활용
description: Azure에서 Docker 컨테이너 및 Kubernetes Orchestrator 활용
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841764"
---
# <a name="leveraging-containers-and-orchestrators"></a>컨테이너 및 오케스트레이터 활용

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

컨테이너 및 orchestrator는 모놀리식 배포 방법에 일반적으로 발생 하는 문제를 해결 하도록 설계 되었습니다.

## <a name="challenges-with-monolithic-deployments"></a>모놀리식 배포 문제

일반적으로 대부분의 응용 프로그램은 단일 단위로 배포 됩니다. 이러한 응용 프로그램을 monolith 라고 합니다. 그림 3-1에 표시 된 것 처럼 여러 모듈 또는 어셈블리로 구성 된 경우에도 응용 프로그램을 단일 단위로 배포 하는 일반적인 방법은 모놀리식 architecture 이라고 합니다.

![모놀리식 아키텍처.](./media/monolithic-architecture.png)

**그림 3-1**. 모놀리식 아키텍처.

모놀리식 아키텍처는 간단 하지만 다음과 같은 다양 한 문제를 겪고 있습니다.

### <a name="deployments"></a>배포

모놀리식 응용 프로그램에 배포 하는 경우 일반적으로 하나의 작은 모듈만 교체 하더라도 전체 응용 프로그램을 다시 시작 해야 합니다. 응용 프로그램을 호스팅하는 컴퓨터의 수에 따라 배포 중에 가동 중지 시간이 발생할 수 있습니다.

### <a name="hosting"></a>호스팅

모놀리식 응용 프로그램은 단일 컴퓨터 인스턴스에서 완전히 호스팅됩니다. 이렇게 하려면 분산 응용 프로그램의 모든 모듈에 필요한 것 보다 높은 기능을 필요로 하는 하드웨어가 필요할 수 있습니다. 또한 앱의 어느 부분도 병목 상태가 되 면 전체 응용 프로그램을 확장 하기 위해 추가 컴퓨터 노드에 배포 해야 합니다.

### <a name="environment"></a>환경

모놀리식 응용 프로그램은 일반적으로 기존 호스팅 환경 (운영 체제, 설치 된 프레임 워크 등)에 배포 됩니다. 이 환경은 응용 프로그램을 개발 하거나 테스트 한 환경과 일치 하지 않을 수 있습니다. 응용 프로그램 환경의 불일치는 모놀리식 배포에 대 한 문제의 일반적인 원인입니다.

### <a name="coupling"></a>커플링

모놀리식 응용 프로그램은 응용 프로그램의 서로 다른 부분과 응용 프로그램 및 해당 환경 간에 상당한 결합을 가질 수 있습니다. 이를 통해 다른 구현에서 확장성 또는 교환을 향상 시키기 위해 특정 서비스나 문제를 나중에 파악 하기 어려울 수 있습니다. 이러한 결합으로 인해 시스템 변경에 대 한 잠재적 영향이 크게 증가 하 여 대규모 응용 프로그램에서 광범위 하 게 테스트 해야 합니다.

### <a name="technology-choice"></a>기술 선택

모놀리식 응용 프로그램은 하나의 단위로 빌드되고 배포 됩니다. 이를 통해 간단 하 고 일관성을 제공 하지만 혁신의 장벽 일 수 있습니다. 시스템의 새 기능이 나 모듈이 보다 최신 플랫폼 또는 프레임 워크에 더 적합할 수 있지만 일관성을 위해 응용 프로그램의 현재 접근 방법 및 개발 및 배포의 용이성을 사용 하 여 빌드될 수 있습니다.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>컨테이너와 orchestrator의 이점은 무엇 인가요?

Docker는 가장 인기 있는 컨테이너 관리 및 이미징 플랫폼으로, Linux 및 Windows에서 컨테이너를 신속 하 게 사용할 수 있습니다. 컨테이너는 모든 시스템에서 동일한 방식으로 실행 되는 별도의 재현 가능한 응용 프로그램 환경을 제공 합니다. 이렇게 하면 클라우드 네이티브 응용 프로그램에서 응용 프로그램 및 앱 구성 요소를 개발 하 고 호스팅하는 데 적합 합니다. 컨테이너는 서로 격리 되므로 충돌을 유발 하는 종속성 없이 동일한 호스트 하드웨어의 두 컨테이너는 서로 다른 버전의 소프트웨어와 운영 체제도 설치 될 수 있습니다.

그리고 컨테이너는 소스 제어에 체크 인할 수 있는 간단한 파일에 의해 정의 됩니다. 업데이트를 적용 하거나 추가 서비스를 설치 하기 위해 수동 작업을 수행 해야 하는 가상 컴퓨터를 비롯 하 여 전체 서버와 달리 컨테이너 인프라를 사용 하면 버전을 쉽게 제어할 수 있습니다. 따라서 컨테이너에서 실행 되도록 빌드된 앱은 자동화 된 도구를 사용 하 여 빌드 파이프라인의 일부로 개발, 테스트 및 배포할 수 있습니다.

컨테이너는 변경할 수 없습니다. 컨테이너의 정의가 있으면 해당 컨테이너를 다시 만들 수 있으며 동일한 방식으로 실행 됩니다. 이 불변성은 구성 요소 기반 디자인에 적합 합니다. 응용 프로그램의 일부는 자주 변경 되지 않는 부분을 자주 변경 하는 경우에만 전체 앱을 다시 배포 하는 이유는 무엇 인가요? 앱의 다양 한 기능 및 교차를 분리 하는 작업은 별도의 단위로 나눌 수 있습니다. 그림 3-2에서는 특정 기능이 나 기능을 위임 하 여 모놀리식 앱이 컨테이너 및 마이크로 서비스를 활용 하는 방법을 보여 줍니다. 앱 자체의 나머지 기능도 컨테이너 화 된 되었습니다.

모놀리식 앱을 분리 하 여 백 엔드에서 마이크로 서비스를 사용할 ![. **그림 3-2**을](./media/breaking-up-monolith-with-backend-microservices.png)
합니다. 백 엔드에서 마이크로 서비스를 사용 하도록 모놀리식 앱을 분리 합니다.

별도 컨테이너를 사용 하 여 빌드된 클라우드 네이티브 앱은 필요한 만큼 응용 프로그램을 배포 하는 기능을 활용 합니다. 각 서비스에 해당 하는 리소스가 있는 노드에서 개별 서비스를 호스트할 수 있습니다. 각 서비스를 실행 하는 환경은 변경할 수 없으며, 개발, 테스트 및 프로덕션 간에 공유할 수 있으며, 쉽게 버전을 관리할 수 있습니다. 응용 프로그램의 서로 다른 영역 간 결합은 서비스 간 호출 또는 메시지로 명시적으로 발생 하며,이는 monolith 내에서 컴파일 타임 종속성이 아닙니다. 그리고 전체 앱의 지정 된 부분은 나머지 앱을 변경할 필요 없이 해당 기능이 나 기능에 가장 적합 한 기술을 선택할 수 있습니다.

## <a name="what-are-the-scaling-benefits"></a>크기 조정 혜택은 무엇 인가요?

컨테이너를 기반으로 하는 서비스는 Kubernetes 같은 오케스트레이션 도구에서 제공 하는 크기 조정 혜택을 활용할 수 있습니다. 기본적으로 컨테이너는 자신에 대 한 정보를 알 수 있습니다. 함께 작업 해야 하는 여러 컨테이너를 시작 하는 경우에는 더 높은 수준으로 구성 하는 것이 유용할 수 있습니다. 많은 수의 컨테이너와 네트워크 구성과 같은 공유 종속성을 구성 하는 것은 오케스트레이션 도구가 날짜를 절약 하는 데 제공 되는 위치입니다. Kubernetes는 컨테이너 화 된 응용 프로그램의 배포, 크기 조정 및 관리를 자동화 하도록 설계 된 컨테이너 오케스트레이션 플랫폼입니다. 컨테이너 그룹의 위에 추상화 계층을 만들고이를 *pod*로 구성 합니다. Pod는 *노드라고*하는 작업자 컴퓨터에서 실행 됩니다. 전체적으로 구성 된 그룹을 *클러스터*라고 합니다. 그림 3-3에서는 Kubernetes 클러스터의 여러 구성 요소를 보여 줍니다.

Kubernetes 클러스터 구성 요소를 ![합니다. **그림 3-3**을](./media/kubernetes-cluster-components.png)
합니다. Kubernetes 클러스터 구성 요소

Kubernetes에는 수요에 맞게 클러스터 크기를 조정 하는 기능이 기본적으로 제공 됩니다. 컨테이너 화 된 마이크로 서비스와 결합 되어 클라우드 네이티브 응용 프로그램에 필요한 경우 추가 리소스를 사용 하 여 수요 급증에 신속 하 고 효율적으로 대응할 수 있는 기능을 제공 합니다.

### <a name="declarative-versus-imperative"></a>선언적 및 명령적

Kubernetes는 선언적 및 명령적 개체 구성을 모두 지원 합니다. 명령적 방식에는 각 단계를 수행할 작업을 Kubernetes 알려주는 다양 한 명령이 실행 됩니다. 이 이미지를 *실행* 합니다. 이 pod를 *삭제* 합니다. 이 포트를 *노출* 합니다. 선언적 방법을 사용 하는 경우 *수행할* 작업 대신 *원하는* 작업을 설명 하는 구성 파일을 사용 하 고 Kubernetes 원하는 최종 상태를 얻기 위해 수행할 작업을 파악 합니다. 명령적 명령을 사용 하 여 클러스터를 이미 구성한 경우 `kubectl get svc SERVICENAME -o yaml > service.yaml`를 사용 하 여 선언적 매니페스트를 내보낼 수 있습니다. 이렇게 하면 다음과 같은 매니페스트 파일이 생성 됩니다.

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

선언적 구성을 사용 하는 경우 구성 파일이 있는 폴더에 대 한 `kubectl diff -f FOLDERNAME`를 사용 하 여 커밋하기 전에 적용 되는 변경 내용을 미리 볼 수 있습니다. 변경 내용을 적용 하려면 `kubectl apply -f FOLDERNAME`를 실행 합니다. 폴더 계층 구조를 재귀적으로 처리 하 `-R`를 추가 합니다.

서비스 외에도 *배포*와 같은 다른 Kubernetes 기능에 대해 선언적 구성을 사용할 수 있습니다. 선언적 배포는 배포 컨트롤러에서 클러스터 리소스를 업데이트 하는 데 사용 됩니다. 배포는 새 변경 내용을 롤아웃 하거나, 추가 로드를 지원 하도록 확장 하거나, 이전 수정 버전으로 롤백하는 데 사용 됩니다. 클러스터가 불안정 한 경우 선언적 배포는 클러스터를 자동으로 원하는 상태로 전환 하는 메커니즘을 제공 합니다.

선언적 구성을 사용 하면 응용 프로그램 코드와 함께 체크 인하고 버전을 지정할 수 있는 코드로 인프라를 나타낼 수 있습니다. 이를 통해 소스 제어 변경에 연결 된 빌드 및 배포 파이프라인을 사용 하 여 향상 된 변경 제어 및 연속 배포에 대 한 지원이 향상 됩니다.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>컨테이너 및 orchestrator에 적합 한 시나리오는 무엇 인가요?

다음 시나리오는 컨테이너 및 orchestrator를 사용 하는 데 적합 합니다.

### <a name="applications-requiring-high-uptime-and-scalability"></a>높은 작동 시간 및 확장성을 필요로 하는 응용 프로그램

가동 시간 및 확장성 요구 사항이 높은 개별 응용 프로그램은 마이크로 서비스, 컨테이너 및 orchestrator를 사용 하는 클라우드 기본 아키텍처에 적합 한 후보입니다. 이러한 응용 프로그램은 버전이 지정 된 환경을 사용 하 여 컨테이너에서 개발할 수 있으며, 프로덕션으로 이동 하기 전에 광범위 하 게 테스트할 수 있으며 가동 중지 시간이 0 인 프로덕션에 배포할 수 있습니다. Kubernetes 클러스터를 사용 하면 이러한 앱이 주문형으로 확장 되 고 노드 오류에서 자동으로 복구 될 수도 있습니다.

### <a name="large-numbers-of-applications"></a>많은 수의 응용 프로그램

이후에 배포 하 고 많은 수의 응용 프로그램을 유지 관리 해야 하는 조직은 컨테이너 및 orchestrator의 이점을 누릴 수 있습니다. 컨테이너 화 된 환경 및 Kubernetes 클러스터를 설정 하는 앞의 노력은 고정 비용입니다. 개별 응용 프로그램을 배포, 유지 관리 및 업데이트 하면 유지 관리 해야 하는 응용 프로그램의 수에 따라 비용이 많이 듭니다. 매우 적은 수의 응용 프로그램을 사용 하면 사용자 지정 응용 프로그램을 수동으로 유지 관리 하는 복잡성이 컨테이너 및 orchestrator를 사용 하 여 솔루션을 구현 하는 비용을 초과할 수 있습니다.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>컨테이너와 orchestrator를 사용 하지 않는 경우는 언제 인가요?

12 단계 앱 원칙에 따라 응용 프로그램을 빌드할 수 없는 경우 또는 컨테이너와 orchestrator을 방지 하는 것이 더 좋을 것입니다. 이러한 경우 VM 기반 호스팅 플랫폼과 함께 이동 하는 것이 가장 좋을 수 있습니다. 또는 특정 기능을 별도의 컨테이너 또는 서버를 사용 하지 않는 함수로 회전할 수 있는 하이브리드 시스템이 있을 수 있습니다.

## <a name="development-resources"></a>개발 리소스

이 섹션에서는 다음 응용 프로그램에 컨테이너 및 orchestrator 사용을 시작 하는 데 도움이 될 수 있는 간단한 개발 리소스 목록을 보여 줍니다. 클라우드 네이티브 마이크로 서비스 아키텍처 앱을 설계 하는 방법에 대 한 지침은이 설명서의 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램용 아키텍처](https://aka.ms/microservicesebook)를 참조 하세요.

### <a name="local-kubernetes-development"></a>로컬 Kubernetes 개발

Kubernetes 배포는 프로덕션 환경에서 뛰어난 가치를 제공 하지만 로컬에서 실행할 수도 있습니다. 개별 앱 또는 마이크로 서비스에서 독립적으로 작업 하는 데는 많은 시간이 걸릴 수 있지만 프로덕션 환경에 배포할 때 실행 되는 것 처럼 전체 시스템을 로컬로 실행할 수 있는 것이 좋습니다. 이를 위해 여러 가지 방법을 사용할 수 있으며,이 중 두 가지는 Minikube 및 Docker Desktop입니다. 또한 Visual Studio는 Docker 개발용 도구를 제공 합니다.

### <a name="minikube"></a>Minikube

Minikube 란? Minikube 프로젝트에서는 "Minikube가 macOS, Linux 및 Windows에서 로컬 Kubernetes 클러스터를 구현 합니다." 라고 표시 됩니다. 주요 목표는 "로컬 Kubernetes 응용 프로그램 개발에 가장 적합 한 도구 이며이에 적합 한 모든 Kubernetes 기능을 지 원하는 것입니다." Minikube 설치는 Docker와는 별개 이지만 Minikube는 Docker 데스크톱과 지원 되는 것과 다른 하이퍼바이저를 지원 합니다. Minikube에서 현재 지원 되는 Kubernetes 기능은 다음과 같습니다.

- DNS
- NodePorts
- ConfigMaps 및 비밀
- 대시보드
- 컨테이너 런타임: Docker, rkt, CRI 및 containerd
- CNI (컨테이너 네트워크 인터페이스)를 사용 하도록 설정
- 수신

Minikube를 설치한 후 이미지를 다운로드 하 고 로컬 Kubernetes 클러스터를 시작 하는 `minikube start` 명령을 실행 하 여 신속 하 게 사용할 수 있습니다. 클러스터가 시작 되 면 표준 Kubernetes `kubectl` 명령을 사용 하 여 상호 작용 합니다.

### <a name="docker-desktop"></a>Docker 데스크톱

Windows의 Docker Desktop에서 직접 Kubernetes 작업을 수행할 수도 있습니다. 이 옵션은 Windows 컨테이너를 사용 하는 경우에만 사용할 수 있으며 비 Windows 컨테이너에도 적합 합니다. 표준 Docker 데스크톱 구성 앱은 Docker 데스크톱에서 실행 되는 Kubernetes를 구성 하는 데 사용 됩니다.

![Docker Desktop에서 Kubernetes 구성](./media/docker-desktop-kubernetes.png)

**그림 3-4**. Docker Desktop에서 Kubernetes를 구성 합니다.

Docker Desktop은 이미 컨테이너 화 된 apps를 로컬로 구성 하 고 실행 하기 위한 가장 인기 있는 도구입니다. Docker Desktop을 사용 하는 경우 프로덕션 환경에 배포할 정확한 Docker 컨테이너 이미지 집합에 대해 로컬로 개발할 수 있습니다. Docker Desktop은 컨테이너 화 된 apps를 로컬로 빌드, 테스트 및 제공 하도록 설계 되었습니다. 이미지가 Azure Container Registry 또는 Docker Hub와 같은 이미지 레지스트리로 배송 된 후 AKS (Azure Kubernetes Service)와 같은 서비스는 프로덕션에서 응용 프로그램을 관리 합니다.

### <a name="visual-studio-docker-tooling"></a>Visual Studio Docker 도구

Visual Studio는 웹 응용 프로그램에 대 한 Docker 개발을 지원 합니다. 새 ASP.NET Core 응용 프로그램을 만드는 경우 그림 3-5에 표시 된 것 처럼 프로젝트 만들기 프로세스의 일부로 Docker 지원을 사용 하 여이 응용 프로그램을 구성 하는 옵션이 제공 됩니다.

![Visual Studio에서 Docker 지원 사용](./media/visual-studio-enable-docker-support.png)

**그림 3-5**. Visual Studio에서 Docker 지원 사용

이 옵션을 선택 하면 프로젝트는 Docker 컨테이너에서 앱을 빌드하고 호스트 하는 데 사용할 수 있는 루트에 `Dockerfile`를 사용 하 여 만들어집니다. 예제 Dockerfile은 그림 3-6에 나와 있습니다.

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

ASP.NET Core 응용 프로그램을 만들 때 Docker 지원을 추가 하지 않으면 나중에 언제 든 지 추가할 수 있습니다. 그림 3-8에 표시 된 것 처럼 Visual Studio 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **Docker 지원**을 선택 합니다.

![Visual Studio Docker 지원 추가](./media/visual-studio-add-docker-support.png)

**그림 3-8**. Visual Studio Docker 지원 추가

Docker 지원 외에도 그림 3-8에 표시 된 컨테이너 오케스트레이션 지원을 추가할 수 있습니다. 기본적으로 orchestrator는 Kubernetes 및 투구를 사용 합니다. Orchestrator를 선택 하면 `azds.yaml` 파일이 프로젝트 루트에 추가 되 고 Kubernetes에 응용 프로그램을 구성 하 고 배포 하는 데 사용 되는 투구 차트가 포함 된 `charts` 폴더가 추가 됩니다. 그림 3-9에서는 새 프로젝트의 결과 파일을 보여 줍니다.

![Visual Studio Orchestrator 지원 추가](./media/visual-studio-add-orchestrator-support.png)

**그림 3-9**. Visual Studio Orchestrator 지원 추가

## <a name="references"></a>참조

- [Kubernetes 란?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Minikube를 사용 하 여 Kubernetes 설치](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Docker용 Visual Studio Tools](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[이전](scale-applications.md)
>[다음](leverage-serverless-functions.md)
