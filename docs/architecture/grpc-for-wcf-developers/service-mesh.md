---
title: 서비스 메시-WCF 개발자를 위한 gRPC
description: 서비스 메시를 사용 하 여 Kubernetes 클러스터의 gRPC 서비스에 대 한 요청을 라우팅하고 분산 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: cc4855b1ed27e29076e4f13f5c5d3dffa63a6554
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711272"
---
# <a name="service-meshes"></a>서비스 메시

서비스 메시는 네트워크 내에서 라우팅 서비스 요청을 제어 하는 인프라 구성 요소입니다. 서비스 메시는 다음과 같은 Kubernetes 클러스터 내에서 모든 종류의 네트워크 수준 문제를 처리할 수 있습니다.

- 서비스 검색
- 부하 분산
- 내결함성
- 암호화
- 모니터링

Kubernetes service 메시는 메시에 포함 된 각 pod에 *사이드카 proxy*라는 추가 컨테이너를 추가 하 여 작동 합니다. 프록시는 모든 인바운드 및 아웃 바운드 네트워크 요청을 처리 하 여 네트워크 문제를 구성 하 고 관리 하는 작업은 응용 프로그램 컨테이너와 별도로 유지 하 고 대부분의 경우 응용 프로그램 코드를 변경 하지 않고도 수행할 수 있습니다.

[이전 챕터의 예제](kubernetes.md#test-the-application)를 사용 합니다. 여기서 웹 응용 프로그램의 grpc 요청은 모두 grpc 서비스의 단일 인스턴스로 라우팅됩니다. 이는 서비스의 호스트 이름이 IP 주소로 확인 되 고 해당 IP 주소가 `HttpClientHandler` 인스턴스의 수명 동안 캐시 되기 때문에 발생 합니다. DNS 조회를 수동으로 처리 하거나 여러 클라이언트를 만들어이 문제를 해결할 수 있지만 비즈니스 또는 고객 가치를 추가 하지 않으면 응용 프로그램 코드가 상당히 복잡 해질 수 있습니다.

서비스 메시를 사용 하 여 응용 프로그램 컨테이너의 요청은 사이드카 프록시로 전송 되며이를 통해 다른 서비스의 모든 인스턴스에 지능적으로 배포할 수 있습니다. 메시도 다음을 수행할 수 있습니다.

- 서비스의 개별 인스턴스 오류에 대해 원활 하 게 대응 합니다.
- 실패 한 호출 또는 시간 제한에 대 한 재시도 의미 체계를 처리 합니다.
- 클라이언트 응용 프로그램에 반환 하지 않고 실패 한 요청을 대체 인스턴스로 경로를 조정 합니다.

다음 스크린샷은 응용 프로그램 코드를 변경 하거나 사용 중인 Docker 이미지를 변경 하지 않고 Linkerd 서비스 메시로 실행 되는 StockWeb 응용 프로그램을 보여 줍니다. 필요한 유일한 변경 내용은 `stockdata` 및 `stockweb` 서비스에 대 한 YAML 파일의 배포에 대 한 주석을 추가 하는 것입니다.

![서비스 메시를 사용 하는 StockWeb](media/service-mesh/stockweb-servicemesh-screenshot.png)

응용 프로그램 코드의 단일 `HttpClient` 인스턴스에서 발생 하더라도 StockWeb 응용 프로그램의 요청이 StockData 서비스의 두 복제본으로 라우트 되었음을 서버 열에서 볼 수 있습니다. 실제로 코드를 검토 하는 경우 StockData 서비스에 대 한 모든 100 요청이 동일한 `HttpClient` 인스턴스를 사용 하 여 동시에 실행 되는 것을 확인할 수 있습니다. 그러나 서비스 메시에서는 이러한 요청이 분산 되지만 많은 서비스 인스턴스를 사용할 수 있습니다.

서비스 메시는 클러스터 내의 트래픽에만 적용 됩니다. 외부 클라이언트의 경우 [다음 챕터 부하 분산을](load-balancing.md)참조 하세요.

## <a name="service-mesh-options"></a>서비스 메시 옵션

현재 Kubernetes: Istio, Linkerd 및 Consul Connect와 함께 사용할 수 있는 세 가지 범용 서비스 메시 구현이 있습니다. 세 가지 모두 요청 라우팅/프록시, 트래픽 암호화, 복원 력, 호스트 간 인증 및 트래픽 제어를 제공 합니다.

서비스 메시를 선택 하는 것은 여러 요소에 따라 다릅니다.

- 비용, 규정 준수, 유료 지원 계획 등의 조직의 특정 요구 사항입니다.
- 클러스터의 특성, 크기, 배포 된 서비스 수 및 클러스터 네트워크 내의 트래픽 양에 대 한 것입니다.
- 메시를 쉽게 배포 및 관리 하 고 서비스에서 사용할 수 있습니다.

각 서비스 메시에 대 한 자세한 내용은 해당 웹 사이트에서 확인할 수 있습니다.

- [**Istio** -istio.io](https://istio.io)
- [**Linkerd** -linkerd.io](https://linkerd.io)
- [**Consul** -consul.io/mesh.html](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a>예: Linkerd를 배포에 추가

이 예제에서는 [이전 섹션](kubernetes.md)의 *StockKube* 응용 프로그램과 함께 linkerd 서비스 메시를 사용 하는 방법에 대해 알아봅니다.
이 예제를 따르려면 [Linkerd CLI를 설치](https://linkerd.io/2/getting-started/#step-1-install-the-cli)해야 합니다. Windows 이진 파일은 GitHub 릴리스 섹션에서 다운로드할 수 있습니다. edge 릴리스 중 하나가 아니라 **안정적인** 최신 릴리스를 사용 해야 합니다.

Linkerd CLI가 설치 된 상태에서 [Linkerd 웹 사이트의*시작* 지침]을 따라 Kubernetes 클러스터에 linkerd 구성 요소를 설치 합니다. 지침은 로컬 Kubernetes 인스턴스에서 몇 분 정도 소요 될 수 있습니다.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Kubernetes 배포에 Linkerd 추가

Linkerd CLI는 Kubernetes 파일에 필요한 섹션과 속성을 추가 하는 `inject` 명령을 제공 합니다. 명령을 실행 하 고 새 파일에 출력을 쓸 수 있습니다.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

새 파일을 검사 하 여 변경한 내용을 확인할 수 있습니다. 배포 개체의 경우 Linkerd가 생성 될 때 Pod에 사이드카 proxy 컨테이너를 삽입 하도록 메타 데이터 주석이 추가 됩니다.

`linkerd inject` 명령의 출력을 직접 `kubectl`로 파이프 하는 것도 가능 합니다. 다음 명령은 PowerShell 또는 모든 Linux 셸에서 작동 합니다.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Linkerd 대시보드의 서비스 검사

`linkerd` CLI를 사용 하 여 Linkerd 대시보드를 시작 합니다.

```console
linkerd dashboard
```

대시보드는 메시에 연결 된 모든 서비스에 대 한 자세한 정보를 제공 합니다.

![StockKube 응용 프로그램을 보여 주는 linkerd 대시보드](media/service-mesh/linkerd-screenshot.png)

다음 예제와 같이 StockData gRPC 서비스의 복제본 수를 늘리고 브라우저에서 StockWeb 페이지를 새로 고치면 서버 열에 Id가 혼합 되어 있어 사용 가능한 모든 인스턴스에서 요청이 처리 되 고 있음을 알 수 있습니다. .

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
>[이전](kubernetes.md)
>[다음](load-balancing.md)
