---
title: Eapr 관찰성 빌딩 블록
description: 관찰성 빌딩 블록에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: edwinvw
ms.date: 02/17/2021
ms.reviewer: robvet
ms.openlocfilehash: 745b9c07c31cc3ee11d5df945f2ccb87d0c9c2ed
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623982"
---
# <a name="the-dapr-observability-building-block"></a>Eapr 관찰성 빌딩 블록

최신 분산 시스템은 복잡 합니다. 느슨하게 결합 되 고 독립적으로 배포 가능한 작은 서비스로 시작 합니다. 이러한 서비스는 프로세스 및 서버 경계를 교차 합니다. 그런 다음 다른 종류의 인프라 지원 서비스 (데이터베이스, 메시지 브로커, 키 자격 증명 모음)를 사용 합니다. 마지막으로 이러한 개별 요소를 함께 구성 하 여 응용 프로그램을 구성 합니다.

서로 다른 여러 부분으로 이동 하는 경우 어떻게 되나요? 불행 하 게도 과거의 레거시 모니터링 접근 방식이 충분 하지 않습니다. 대신 시스템은 종단 간에서 **관찰** 가능 해야 합니다. 최신 [관찰성](../cloud-native/observability-patterns.md) 사례는 응용 프로그램의 상태에 대 한 가시성과 통찰력을 항상 제공 합니다. 이를 통해 출력을 관찰 하 여 내부 상태를 유추할 수 있습니다. 관찰성는 분산 응용 프로그램 모니터링 및 문제 해결에 필수적입니다.

관찰성를 얻는 데 사용 되는 시스템 정보를 **원격 분석** 이라고 합니다. 다음 네 가지 광범위 한 범주로 나눌 수 있습니다.

1. **분산 추적은** 분산 트랜잭션과 관련 된 서비스와 서비스 간의 트래픽에 대 한 통찰력을 제공 합니다.
1. **메트릭은** 서비스 성능 및 해당 리소스 소비에 대 한 통찰력을 제공 합니다.
1. **로깅은** 코드가 실행 되는 방법 및 오류가 발생 한 경우에 대 한 통찰력을 제공 합니다.
1. **상태** 끝점은 서비스의 가용성에 대 한 통찰력을 제공 합니다.

원격 분석의 깊이는 응용 프로그램 플랫폼의 관찰성 기능에 의해 결정 됩니다. Azure cloud를 살펴보겠습니다. 모든 원격 분석 범주를 포함 하는 다양 한 원격 분석 환경을 제공 합니다. 구성 없이 대부분의 Azure IaaS 및 PaaS 서비스는 [Azure 애플리케이션 Insights](/azure/azure-monitor/app/app-insights-overview) 서비스에 원격 분석을 전파 하 고 게시 합니다. Application Insights은 시각적 대시보드가 매우 많은 시스템 로깅, 추적 및 문제 영역을 제공 합니다. 통신을 기반으로 하는 서비스 간의 종속성을 보여 주는 다이어그램도 렌더링할 수 있습니다.

그러나 응용 프로그램에서 Azure PaaS 및 IaaS 리소스를 사용할 수 없는 경우는 어떻게 되나요? Application Insights의 다양 한 원격 분석 환경을 활용할 수 있나요? 대답은 예입니다. 비 Azure 응용 프로그램은 라이브러리를 가져오고, 구성을 추가 하 고, 코드를 계측 하 여 원격 분석을 Azure 애플리케이션 Insights로 내보낼 수 있습니다. 그러나이 방법은 응용 프로그램을 Application Insights에 긴밀 하 게 **결합** . 앱을 다른 모니터링 플랫폼으로 이동 하는 것은 비용이 많이 드는 리팩터링을 포함할 수 있습니다. 코드 외부에서 관찰성를 사용 하 고 결합 하는 것을 방지 하는 것이 좋습니다.

Eapr를 사용 하면 가능 합니다. 관찰성가 배포 응용 프로그램에를 추가할 수 있는 방법을 살펴보겠습니다.

## <a name="what-it-solves"></a>해결 방법

응용 프로그램에서의 관찰성 분리 관찰성 구성 요소입니다. 이 도구는 사이드카에서 생성 하는 트래픽을 자동으로 캡처합니다. 블록은 여러 서비스에 걸쳐 있는 단일 작업의 트래픽을 연관 시킵니다. 또한 성능 메트릭, 리소스 사용률 및 시스템 상태를 노출 합니다. 원격 분석은 선택의 모니터링 백 엔드에 정보를 공급할 수 있도록 하는 오픈 표준 형식으로 게시 됩니다. 여기에서 정보를 시각화, 쿼리 및 분석할 수 있습니다.

관찰성를 추상화 하는 경우 응용 프로그램은 구현 방법을 인식 하지 못합니다. 라이브러리를 참조 하거나 사용자 지정 계측 코드를 구현할 필요가 없습니다. 관찰성는 개발자가 비즈니스 논리를 구축 하는 데 집중할 수 있도록 합니다. 관찰성는 다른 팀에서 만들고 다른 기술 스택을 사용 하 여 구축 된 경우에도 수준에서 구성 되 고 서비스 간에 일관 됩니다.

## <a name="how-it-works"></a>작동 방식

[사이드카 아키텍처](dapr-at-20000-feet.md#sidecar-architecture) 는 기본 제공 관찰성 기능을 사용 합니다. 서비스가 통신할 때, 사이드카는 트래픽을 가로채서 추적, 메트릭 및 로깅 정보를 추출 합니다. 원격 분석은 개방형 표준 형식으로 게시 됩니다. 기본적으로 [OpenTelemetry](https://opentelemetry.io/) 및 [Zipkin](https://zipkin.io/)를 지원 합니다.

D 4는 다른 백 엔드 모니터링 도구에 원격 분석을 게시할 수 있는 [수집기](https://docs.dapr.io/operations/monitoring/tracing/open-telemetry-collector/) 를 제공 합니다. 이러한 도구는 분석 및 쿼리를 위한 4Apr 원격 분석을 제공 합니다. 그림 9-1은 Eapr 관찰성 아키텍처를 보여 줍니다.

![Eapr 관찰성 아키텍처](media/observability/observability-architecture.png)

**그림 9-1**. 관찰성 아키텍처.

1. 서비스 A는 서비스 B에 대 한 작업을 호출 합니다. 호출은 서비스 A에 대 한 사이드카에서 서비스 B에 대 한 사이드카로 라우팅됩니다.
1. 서비스 B가 작업을 완료 하면 사이드카를 통해 서비스 A에 응답을 다시 보냅니다. 모든 요청 및 응답에 대해 사용 가능한 모든 원격 분석을 수집 하 고 게시 합니다.
1. 구성 된 수집기는 원격 분석을 수집 모니터링 백 엔드에 보냅니다.  

개발자는 관찰성를 추가 하는 것이 pub/sub 또는 state management와 같은 다른 이상의 구성 요소 구성과 다르다는 점에 유의 하세요. 빌딩 블록을 참조 하는 대신 수집기 및 모니터링 백 엔드를 추가 합니다. 그림 9-1에서는 여러 다른 모니터링 백 엔드와 통합 되는 여러 수집기를 구성할 수 있습니다.

이 챕터의 시작 부분에서 4 개의 원격 분석 범주가 식별 되었습니다. 다음 섹션에서는 각 범주에 대 한 세부 정보를 제공 합니다. 여기에는 인기 있는 모니터링 백 엔드와 통합 되는 수집기를 구성 하는 방법에 대 한 지침이 포함 됩니다.

### <a name="distributed-tracing"></a>분산 추적

분산 추적은 분산 응용 프로그램의 서비스 간에 흐르는 트래픽에 대 한 통찰력을 제공 합니다. 교환 된 요청 및 응답 메시지의 로그는 문제 해결을 위한 중요 한 정보입니다. 하드 파트는 동일한 작업에서 발생 하는 *메시지의 상관* 관계를 말합니다.

D 4에서 [W3C 추적 컨텍스트](https://www.w3.org/TR/trace-context) 를 사용 하 여 관련 메시지를 상호 연결 합니다. 또한 고유한 작업을 구성 하는 요청 및 응답에 동일한 컨텍스트 정보를 삽입 합니다. 그림 9-2에서는 상관 관계의 작동 방식을 보여 줍니다.

![W3C 추적 컨텍스트 예제](media/observability/w3c-trace-context.png)

**그림9-2** W3C 추적 컨텍스트 예제입니다.

1. 서비스 A는 서비스 B에 대 한 작업을 호출 합니다. 서비스 A가 호출을 시작 하면, Capr에서 고유한 추적 컨텍스트를 만들어 요청에 삽입 합니다.
1. 서비스 B에서 요청을 수신 하 고 서비스 C에 대 한 작업을 호출 합니다. d C 4는 들어오는 요청이 추적 컨텍스트를 포함 하 고 있는 것을 검색 하 고이를 서비스 C로 보내는 요청에 삽입 하 여 전파 합니다.  
1. 서비스 C에서 요청을 수신 하 고 처리 합니다. T 4는 들어오는 요청이 추적 컨텍스트를 포함 하는 것을 감지 하 고 서비스 B에 대 한 나가는 응답에 다시 삽입 하 여 전파 합니다.
1. 서비스 B는 응답을 수신 하 고 처리 합니다. 그런 다음 새 응답을 만들고 서비스 A에 대 한 나가는 응답에 다시 삽입 하 여 추적 컨텍스트를 전파 합니다.

함께 포함 되는 요청 및 응답 집합을 *추적* 이라고 합니다. 그림 9-3에서는 추적을 보여 줍니다.

![추적 및 범위](media/observability/traces-spans.png)

**그림 9-3** 추적 및 범위.

그림에서 추적은 여러 서비스에서 발생 하는 고유한 응용 프로그램 트랜잭션을 나타내는 방법을 확인 합니다. 추적은 *범위의* 컬렉션입니다. 각 범위는 단일 작업이 나 추적 내에서 수행 되는 작업 단위를 나타냅니다. 범위는 고유한 트랜잭션을 구현 하는 서비스 간에 전송 되는 요청 및 응답입니다.

다음 섹션에서는 모니터링 백 엔드에 게시 하 여 추적 원격 분석을 검사 하는 방법을 설명 합니다.

#### <a name="use-a-zipkin-monitoring-back-end"></a>Zipkin 모니터링 백 엔드 사용

[Zipkin](https://zipkin.io/) 은 오픈 소스 분산 추적 시스템입니다. 원격 분석 데이터를 수집 하 고 시각화할 수 있습니다. Zipkin에 대 한 기본 지원을 제공 합니다. 다음 예에서는 Zipkin를 구성 하 여 4Apr 원격 분석을 시각화 하는 방법을 보여 줍니다.

##### <a name="enable-and-configure-tracing"></a>추적 사용 및 구성

시작 하려면 4apr 런타임에 구성 파일을 사용 하 여 추적을 사용 하도록 설정 해야 합니다. 다음은 이라는 구성 파일의 예입니다 `tracing-config.yaml` .  

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: tracing-config
  namespace: default
spec:
  tracing:
    samplingRate: "1"
    zipkin:
      endpointAddress: "http://zipkin.default.svc.cluster.local:9411/api/v2/spans"
```

`samplingRate`특성은 추적을 게시 하는 데 사용 되는 간격을 지정 합니다. 값은 `0` (추적 사용 안 함) 사이 여야 하며 `1` (모든 추적이 게시 됨) 예를 들어 값이 이면 `0.5` 다른 모든 추적이 게시 되 고 게시 된 트래픽이 크게 줄어듭니다. 는 `endpointAddress` Kubernetes 클러스터에서 실행 되는 Zipkin 서버의 끝점을 가리킵니다. Zipkin에 대 한 기본 포트는 `9411` 입니다. Kubernetes CLI를 사용 하 여 Kubernetes 클러스터에 구성을 적용 해야 합니다.

```console
kubectl apply -f tracing-config.yaml
```

##### <a name="install-the-zipkin-server"></a>Zipkin 서버 설치

자체 호스팅 모드에서 Zipkin 서버를 설치 하는 경우에는 Windows의 또는에 있는 기본 구성 파일에서 자동으로 설치 되 고 추적 기능이 사용 하도록 설정 됩니다 `$HOME/.dapr/config.yaml` `%USERPROFILE%\.dapr\config.yaml` .

Kubernetes 클러스터에는 Zipkin를 설치 하지만 기본적으로는 추가 되지 않습니다. 이라는 다음 Kubernetes 매니페스트 파일은 `zipkin.yaml` 표준 Zipkin 서버를 클러스터에 배포 합니다.

```yaml
kind: Deployment
apiVersion: apps/v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  replicas: 1
  selector:
    matchLabels:
      service: zipkin
  template:
    metadata:
      labels:
        service: zipkin
    spec:
      containers:
        - name: zipkin
          image: openzipkin/zipkin-slim
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 9411
              protocol: TCP

---

kind: Service
apiVersion: v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  type: NodePort
  ports:
    - port: 9411
      targetPort: 9411
      nodePort: 32411
      protocol: TCP
      name: zipkin
  selector:
    service: zipkin

```

배포에서는 표준 컨테이너 이미지를 사용 합니다 `openzipkin/zipkin-slim` . Zipkin 서비스는 포트에서 원격 분석을 보는 데 사용할 수 있는 Zipkin 웹 프런트 엔드를 노출 합니다 `32411` . Kubernetes CLI를 사용 하 여 Zipkin 매니페스트 파일을 Kubernetes 클러스터에 적용 하 고 Zipkin 서버를 배포 합니다.

```console
kubectl apply -f zipkin.yaml
```

##### <a name="configure-the-services-to-use-the-tracing-configuration"></a>추적 구성을 사용 하도록 서비스 구성

이제 모든 것이 올바르게 설정 되어 원격 분석 게시를 시작 합니다. 응용 프로그램의 일부로 배포 된 모든 6Apr 사이드카를 시작할 때 원격 분석을 내보내도록 지시 해야 합니다. 이렇게 하려면 `dapr.io/config` 구성을 참조 하는 주석을 `tracing-config` 각 서비스의 배포에 추가 합니다. 다음은 주석이 포함 된 eShop 주문 API 서비스의 매니페스트 파일의 예입니다.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ordering-api
  namespace: eshop
  labels:
    app: eshop
spec:
  replicas: 1
  selector:
    matchLabels:
      app: eshop
  template:
    metadata:
      labels:
        app: simulation
      annotations:
        dapr.io/enabled: "true"
        dapr.io/app-id: "ordering-api"
        dapr.io/config: "tracing-config"
    spec:
      containers:
      - name: simulation
        image: eshop/ordering.api:linux-latest
```

##### <a name="inspect-the-telemetry-in-zipkin"></a>Zipkin에서 원격 분석 검사

응용 프로그램이 시작 되 면 사이드카는 Zipkin 서버에 원격 분석을 내보냅니다. 이 원격 분석을 검사 하려면 웹 브라우저를로 가리킵니다 <http://localhost:32411> . Zipkin 웹 프런트 엔드가 표시 됩니다.

![Zipkin 시작 페이지](media/observability/zipkin.png)

*추적 찾기* 탭에서 추적을 쿼리할 수 있습니다. 제한을 지정 하지 않고 *쿼리 실행* 단추를 누르면 수집 *추적이* 모두 표시 됩니다.

![추적 목록](media/observability/zipkin-traces-overview.png)

특정 추적 옆의 *표시* 단추를 클릭 하면 해당 추적에 대 한 세부 정보가 표시 됩니다.

![추적 세부 정보](media/observability/zipkin-trace-details.png)

세부 정보 페이지의 각 항목은 선택한 추적의 일부인 요청을 나타내는 범위입니다.

##### <a name="inspect-the-dependencies-between-services"></a>서비스 간 종속성 검사

사이드카는 서비스 간의 트래픽을 처리 하므로 Zipkin는 추적 정보를 사용 하 여 서비스 간의 종속성을 확인할 수 있습니다. 작동 하는지 확인 하려면 Zipkin 웹 페이지의 *종속성* 탭으로 이동 하 고 돋보기 모양의 단추를 선택 합니다. Zipkin는 서비스 및 해당 종속성에 대 한 개요를 표시 합니다.

![Zipkin의 종속성 그래프](media/observability/zipkin-dependencies.png)

서비스 간의 줄에서 적용 되는 점은 요청을 나타내고 원본에서 대상으로 이동 합니다. 빨간색 점은 실패 한 요청을 의미 합니다.

#### <a name="use-a-jaeger-or-new-relic-monitoring-back-end"></a>Jaeger 또는 새 유물 모니터링 백 엔드 사용

Zipkin 외에도 다른 모니터링 백 엔드 소프트웨어는 Zipkin 형식을 사용 하 여 수집 원격 분석을 지원 합니다. [Jaeger](https://www.jaegertracing.io/) 는 Uber 기술로 만든 오픈 소스 추적 시스템입니다. 분산 서비스 간의 트랜잭션을 추적 하 고 복잡 한 마이크로 서비스 환경의 문제를 해결 하는 데 사용 됩니다. [새 유물](https://newrelic.com/) 은 *전체 스택* 관찰성 플랫폼입니다. 분산 응용 프로그램의 관련 데이터를 연결 하 여 시스템에 대 한 전체 그림을 제공 합니다. 이를 수행 하려면 `endpointAddress` Jaeger 또는 새 유물 서버를 가리키는를 지정 합니다. Jaeger 서버에 원격 분석을 보내도록 Aapr를 구성 하는 구성 파일의 예는 다음과 같습니다. Jaeger의 URL은 Zipkin에 대 한 URL과 동일 합니다. 유일한 차이점은 서버를 실행 하는 포트입니다.

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "http://localhost:9415/api/v2/spans"
 ```

새 유물을 사용해 보려면 새 유물 API의 끝점을 지정 합니다. 새 유물에 대 한 구성 파일의 예는 다음과 같습니다.

 ```yaml
apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "https://trace-api.newrelic.com/trace/v1?Api-Key=<NR-API-KEY>&Data-Format=zipkin&Data-Format-Version=2"
 ```

사용 방법에 대 한 자세한 내용은 Jaeger 및 새 유물 웹 사이트를 확인 하세요.

### <a name="metrics"></a>메트릭

메트릭은 성능 및 리소스 소비에 대 한 통찰력을 제공 합니다. 내부적으로, A4는 광범위 한 시스템 및 런타임 메트릭의 컬렉션을 내보냅니다. 6apr는 [프로메테우스](https://prometheus.io/) 를 메트릭 표준으로 사용 합니다. 사이드카 및 시스템 서비스는 포트에서 메트릭 끝점을 노출 `9090` 합니다. *프로메테우스 scraper* 는 미리 정의 된 간격으로이 끝점을 호출 하 여 메트릭을 수집 합니다. Scraper는 모니터링 백 엔드에 메트릭 값을 보냅니다. 그림 9-4에서는 스크랩 프로세스를 보여 줍니다.

![스크랩 프로메테우스 메트릭](media/observability/prometheus-scraper.png)

**그림 9-4**. 스크랩 프로메테우스 메트릭입니다.

위의 그림에서 각 사이드카 및 시스템 서비스는 포트 9090에서 수신 대기 하는 메트릭 끝점을 노출 합니다. Scrapper는 각 끝점에서 메트릭을 캡처하고 모니터링 백 엔드에 정보를 게시 합니다.  

#### <a name="service-discovery"></a>서비스 검색

메트릭 scraper에서 메트릭을 수집할 위치를 어떻게 알 수 있는지 궁금할 수 있습니다. 프로메테우스는 대상 배포 환경에 기본 제공 되는 검색 메커니즘과 통합할 수 있습니다. 예를 들어 Kubernetes에서 실행 하는 경우 Kubernetes API와 통합 하 여 환경에서 실행 중인 사용 가능한 모든 Kubernetes 리소스를 찾을 수 있습니다.

#### <a name="metrics-list"></a>메트릭 목록

6apr는 cccsystem 서비스 및 해당 런타임에 대 한 많은 메트릭을 생성 합니다. 일부 사례:

| 메트릭                                         | 원본 | Description                                                  |
| ---------------------------------------------- | :----: | ------------------------------------------------------------ |
| dapr_operator_service_created_total            | 시스템 | Eapr 운영자 서비스에서 만든 총 Capr 서비스 수입니다. |
| dapr_injector_sidecar_injection/requests_total | 시스템 | Sidecar-Injector service에서 받은 총 사이드카 주입 요청 수입니다. |
| dapr_placement_runtimes_total                  | 시스템 | 6Apr 배치 서비스에 보고 된 총 호스트 수입니다. |
| dapr_sentry_cert_sign_request_received_total   | 시스템 | Eapr Sentry 서비스에서 받은 CRSs (인증서 서명 요청) 수입니다. |
| dapr_runtime_component_loaded      | 런타임 | 성공적으로 로드 된 Capr 구성 요소 수입니다.           |
| dapr_grpc_io_server_completed_rpcs | 런타임 | 메서드 및 상태별 gRPC 호출 수입니다.                    |
| dapr_http_server_request_count     | 런타임 | HTTP 서버에서 시작 된 HTTP 요청 수입니다.           |
| dapr_http/client/sent_bytes        | 런타임 | HTTP 클라이언트에서 요청 본문 (헤더 포함 안 함)으로 보낸 총 바이트 수입니다. |

사용 가능한 메트릭에 대 한 자세한 내용은 참조는 [64 메트릭 설명서](https://docs.dapr.io/operations/monitoring/metrics/)입니다.

#### <a name="configure-dapr-metrics"></a>= 4 월 메트릭 구성

런타임에는 `--enable-metrics=false` Eapr 명령에 인수를 포함 하 여 메트릭 컬렉션 끝점을 사용 하지 않도록 설정할 수 있습니다. 또는 인수를 사용 하 여 끝점에 대 한 기본 포트를 변경할 수도 있습니다 `--metrics-port 9090` .

또한, Cc4 구성 파일을 사용 하 여 런타임 메트릭 수집을 정적으로 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  metric:
    enabled: false
```

#### <a name="visualize-dapr-metrics"></a>Aapr 메트릭 시각화

프로메테우스 scraper 모니터링 백 엔드에 메트릭을 수집 하 고 게시 하는 경우 원시 데이터를 어떻게 이해할 수 있나요? 메트릭을 분석 하기 위한 인기 있는 시각화 도구는 [Grafana](https://grafana.com/grafana/)입니다. Grafana를 사용 하 여 사용 가능한 메트릭에 대 한 대시보드를 만들 수 있습니다. 다음은 4 가지 시스템 서비스 메트릭을 표시 하는 대시보드의 예입니다.

![Grafana 시스템 서비스 메트릭을 표시 하는 대시보드](media/observability/grafana-sample.png)

이 문서에는 [프로메테우스 및 Grafana을 설치 하는 방법에 대 한 자습서](https://docs.dapr.io/operations/monitoring/metrics/grafana/)가 포함 되어 있습니다.

### <a name="logging"></a>로깅

로깅은 런타임에 서비스에서 발생 하는 상황에 대 한 통찰력을 제공 합니다. 응용 프로그램을 실행 하는 경우, 사이드카는 d 4에서 자동으로 로그 항목을 내보냅니다. 그러나 응용 프로그램 코드에 계측 된 로깅 항목이 자동으로 포함 **되지 않습니다** . 응용 프로그램 코드에서 로깅을 내보내려면 [.net 용 OPENTELEMETRY sdk](https://opentelemetry.io/docs/net/)와 같은 특정 SDK를 가져올 수 있습니다. 응용 프로그램 코드를 로깅하는 방법에 대 한 내용은이 장의 뒷부분에 있는 *Dapr .NET SDK 사용* 섹션에서 다룹니다.  

#### <a name="log-entry-structure"></a>로그 항목 구조

D 4에서 구조적 로깅을 내보냅니다. 각 로그 항목의 형식은 다음과 같습니다.

| 필드    | Description                                          | 예제                             |
| -------- | ---------------------------------------------------- | ----------------------------------- |
| time     | ISO8601 형식이 지정 된 타임 스탬프                          | `2021-01-10T14:19:31.000Z`          |
| 수준    | 항목의 수준 ( `debug` \| `info` \| `warn` \| `error` )   | `info`                              |
| 형식     | 로그 형식                                             | `log`                               |
| msg      | 로그 메시지                                          | `metrics server started on :62408/` |
| scope    | 로깅 범위                                        | `dapr.runtime`                      |
| 인스턴스 | D 4가 실행 되는 호스트 이름                             | TSTSRV01                            |
| app_id   | 4apr 앱 ID                                          | ordering-api                        |
| ver      | 4apr 런타임 버전                                 | `1.0.0`-rc. 2                        |

문제 해결 시나리오에서 로깅 항목을 검색 하는 경우 `time` 및 `level` 필드가 특히 유용 합니다. 시간 필드는 특정 기간을 정확 하 게 확인할 수 있도록 로그 항목을 정렬 합니다. 문제를 해결할 때 *디버그 수준의* 로그 항목은 코드의 동작에 대 한 자세한 정보를 제공 합니다.

#### <a name="plain-text-versus-json-format"></a>일반 텍스트와 JSON 형식 비교

기본적으로, d 4는 구조적 로깅을 일반 텍스트 형식으로 내보냅니다. 모든 로그 항목의 형식은 키/값 쌍이 포함 된 문자열입니다. 일반 텍스트로 기록 하는 예는 다음과 같습니다.

```text
== DAPR == time="2021-01-12T16:11:39.4669323+01:00" level=info msg="starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="log level set to: info" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="metrics server started on :62408/" app_id=ordering-api instance=TSTSRV03 scope=dapr.metrics type=log ver=1.0.0-rc.2
```

단순 하지만이 형식은 구문 분석 하기가 어렵습니다. 모니터링 도구를 사용 하 여 로그 항목을 보는 경우 JSON 형식의 로깅을 사용 하도록 설정할 수 있습니다. JSON 항목을 사용 하 여 모니터링 도구는 개별 필드를 인덱싱하고 쿼리할 수 있습니다. JSON 형식의 동일한 로그 항목은 다음과 같습니다.

```json
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d", "scope": "dapr.runtime", "time": "2021-01-12T16:11:39.4669323+01:00", "type": "log", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "log level set to: info", "scope": "dapr.runtime", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "metrics server started on :62408/", "scope": "dapr.metrics", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
```

JSON 서식 지정을 사용 하도록 설정 하려면 각 사이드카를 구성 해야 합니다. 자체 호스팅 모드에서는 명령줄에 플래그를 지정할 수 있습니다 `--log-as-json` .

```console
dapr run --app-id ordering-api --log-level info --log-as-json dotnet run
```

Kubernetes에서는 `dapr.io/log-as-json` 응용 프로그램에 대 한 각 배포에 주석을 추가할 수 있습니다.

```yaml
annotations:
   dapr.io/enabled: "true"
   dapr.io/app-id: "ordering-api"
   dapr.io/app-port: "80"
   dapr.io/config: "dapr-config"
   dapr.io/log-as-json: "true"
```

투구를 사용 하 여 Kubernetes 클러스터에 d 4를 설치 하는 경우 모든 Eapr 시스템 서비스에 대해 JSON 형식의 로깅을 사용 하도록 설정할 수 있습니다.

```console
helm repo add dapr https://dapr.github.io/helm-charts/
helm repo update
kubectl create namespace dapr-system
helm install dapr dapr/dapr --namespace dapr-system --set global.logAsJson=true
```

#### <a name="collect-logs"></a>로그 수집

Analysis에 대 한 모니터링 백 엔드에는 4Apr에서 내보낸 로그를 공급할 수 있습니다. 로그 수집기는 시스템에서 로그를 수집 하 여 모니터링 백 엔드에 전송 하는 구성 요소입니다. 인기 있는 로그 수집기는 [Fluentd](https://www.fluentd.org/)입니다. 자세한 내용은 [Fluentd에서 How to: Set Up, 탄력적 검색 및 Kibana in The Kubernetes in](https://docs.dapr.io/operations/monitoring/logging/fluentd/) The eapr 설명서를 참조 하세요. 이 문서에는 Fluentd as 로그 수집기 및 [Elk Stack](https://www.elastic.co/elastic-stack) (탄력적 검색 및 Kibana)을 모니터링 백 엔드로 설정 하기 위한 지침이 포함 되어 있습니다.

### <a name="health-status"></a>상태

서비스의 상태는 가용성에 대 한 통찰력을 제공 합니다. 각 6Apr 사이드카는 호스팅 환경에서 사이드카 상태를 확인 하는 데 사용할 수 있는 상태 API를 노출 합니다. API에는 하나의 작업이 있습니다.

```console
GET http://localhost:3500/v1.0/healthz
```

작업은 두 개의 HTTP 상태 코드를 반환 합니다.

- 204: 사이드카 정상적인 경우
- 500: 사이드카 비정상 인 경우

자체 호스팅 모드로 실행 하는 경우 상태 API가 자동으로 호출 되지 않습니다. 응용 프로그램 코드 또는 상태 모니터링 도구를 통해 API를 호출할 수 있습니다.

Kubernetes에서 실행 하는 경우 사이드카 인젝터는 자동으로 Kubernetes를 구성 하 여 *선거의 프로브* 및 *준비 프로브* 를 실행 하는 상태 API를 사용 합니다.

Kubernetes는 선거의 프로브를 사용 하 여 컨테이너가 실행 중인지 여부를 확인 합니다. 선거의 프로브에서 오류 코드를 반환 하는 경우 Kubernetes은 컨테이너가 비활성 이라고 가정 하 고 자동으로 다시 시작 합니다. 이 기능은 응용 프로그램의 전반적인 가용성을 높입니다.

Kubernetes는 준비 프로브를 사용 하 여 컨테이너가 트래픽 수락을 시작할 준비가 되었는지 여부를 확인 합니다. 모든 컨테이너가 준비 되 면 pod가 준비 된 것으로 간주 됩니다. 준비는 부하 분산 시나리오에서 Kubernetes 서비스가 pod로 트래픽을 보낼 수 있는지 여부를 결정 합니다. 준비 되지 않은 pod는 부하 분산 장치에서 자동으로 제거 됩니다.

선거의 및 준비 프로브에는 몇 가지 구성 가능한 매개 변수가 있습니다. 둘 다 pod 매니페스트 파일의 컨테이너 사양 섹션에서 구성 됩니다. 기본적으로, 사이드카는 각 컨테이너에 대해 다음과 같은 구성을 사용 합니다.

```yaml
livenessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold : 3
readinessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold: 3
```

 프로브에 사용할 수 있는 매개 변수는 다음과 같습니다.

- 는 `path` Eapr 상태 API 끝점을 지정 합니다.
- 는 `port` Eapr 상태 API 포트를 지정 합니다.
- 는 `initialDelaySeconds` 컨테이너를 처음 검색 하기 시작 하기 전에 Kubernetes가 대기 하는 시간 (초)을 지정 합니다.
- `periodSeconds`Kubernetes 각 프로브 사이에 대기 하는 시간 (초)을 지정 합니다.
- 는 `timeoutSeconds` 제한 시간이 초과 되기 전에 Kubernetes가 API의 응답을 대기 하는 시간 (초)을 지정 합니다. 제한 시간은 실패로 해석 됩니다.
- 는 `failureThreshold` 컨테이너를 연결 하지 않거나 준비 되지 않은 것으로 간주 하기 전에 Kubernetes에서 허용 하는 실패 상태 코드의 수를 지정 합니다.

### <a name="dapr-dashboard"></a>4 월 대시보드

6apr는 응용 프로그램, 구성 요소 및 구성에 대 한 상태 정보를 제공 하는 대시보드를 제공 합니다. App-v CLI를 사용 하 여 포트 8080에서 로컬 컴퓨터의 웹 응용 프로그램으로 대시보드를 시작 합니다.

```console
dapr dashboard
```

Kubernetes에서 실행 되는 Eapr 응용 프로그램의 경우 다음 명령을 사용 합니다.

```console
dapr dashboard -k
```

응용 프로그램에서 사이드카가 있는 모든 서비스에 대 한 개요를 포함 하는 대시보드가 열립니다. 다음 스크린샷은 Kubernetes에서 실행 되는 eShopOnDapr 응용 프로그램에 대 한 4 월 대시보드를 보여 줍니다.

![6apr 대시보드 개요 페이지](media/observability/dapr-dashboard-overview.png)

4Apr 대시보드는 응용 프로그램의 문제를 해결할 때 매우 유용 합니다. 이는 사이드카 및 시스템 서비스에 대 한 정보를 제공 합니다. 로깅 항목을 포함 하 여 각 서비스의 구성으로 드릴 다운할 수 있습니다.

또한 대시보드는 응용 프로그램에 대해 구성 된 구성 요소 및 구성 요소를 보여 줍니다.

![4apr 대시보드 구성 요소 페이지](media/observability/dapr-dashboard-components.png)

대시보드를 통해 사용할 수 있는 많은 양의 정보가 있습니다. 응용 프로그램을 검색 하 고, 응용 프로그램을 검색 하 고, 대시보드를 찾아볼 수 있습니다. 함께 제공 되는 eShopOnDapr 응용 프로그램을 사용 하 여를 시작할 수 있습니다.

Eapr 대시보드 명령에 대 한 자세한 내용은이 문서에서 eapr [대시보드 CLI 명령 참조](https://docs.dapr.io/reference/cli/dapr-dashboard/) 를 확인 하세요.

## <a name="use-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

Dapr .NET SDK는 특정 관찰성 기능을 포함 하지 않습니다. 모든 관찰성 기능은 Aapr 수준에서 제공 됩니다.

.NET 응용 프로그램 코드에서 원격 분석을 내보내려는 경우 [.net 용 OPENTELEMETRY SDK](https://opentelemetry.io/docs/net/)를 고려해 야 합니다. 개방형 원격 분석 프로젝트는 플랫폼 간, 오픈 소스 및 공급 업체에 관계 없이 제공 됩니다. 원격 분석 데이터를 생성, 내보내기, 수집, 처리 및 내보내는 종단 간 구현을 제공 합니다. 자동 및 수동 계측을 지 원하는 언어 마다 단일 계측 라이브러리가 있습니다. 원격 분석은 오픈 원격 분석 표준을 사용 하 여 게시 됩니다. 이 프로젝트에는 클라우드 공급자, 공급 업체 및 최종 사용자의 광범위 한 업계 지원 및 채택이 있습니다.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

함께 제공 되는 eShopOnDapr reference 응용 프로그램의 관찰성는 여러 부분으로 구성 됩니다. 모든 사이드카의 원격 분석이 캡처됩니다. 또한 이전 eShopOnContainers 샘플에서 상속 된 다른 관찰성 기능이 있습니다.

### <a name="custom-health-dashboard"></a>사용자 지정 상태 대시보드

EShopOnDapr의 **Webstatus** 프로젝트는 eShop 서비스의 상태에 대 한 통찰력을 제공 하는 사용자 지정 상태 대시보드입니다. 이 대시보드는 Eapr 상태 API를 사용 하지 않지만 ASP.NET Core의 기본 제공 [상태 검사 메커니즘](/aspnet/core/host-and-deploy/health-checks) 을 사용 합니다. 대시보드는 서비스의 상태 뿐만 아니라 서비스의 종속성 상태를 제공할 뿐입니다. 예를 들어 데이터베이스를 사용 하는 서비스는 다음 스크린샷에 표시 된 것 처럼이 데이터베이스의 상태를 제공 합니다.

![eShopOnDapr 사용자 지정 상태 대시보드](media/observability/eshop-health-dashboard.png)

### <a name="seq-log-aggregator"></a>Seq 로그 집계

[Seq](https://datalust.co/seq) 는 eShopOnDapr에서 로그를 집계 하는 데 사용 되는 인기 있는 로그 집계 서버입니다. Seq 수집는 응용 프로그램 서비스에서 로깅하는 반면, Eapr 시스템 서비스 또는 사이드카에서는 로깅 되지 않습니다. Seq 인덱스 응용 프로그램은 로그를 분석 하 고 쿼리 하는 웹 프런트 엔드를 제공 합니다. 또한 모니터링 대시보드를 빌드하기 위한 기능도 제공 합니다.

EShopOnDapr 응용 프로그램 서비스는 [SeriLog](https://serilog.net/) 로깅 라이브러리를 사용 하 여 구조적 로깅을 내보냅니다. Serilog는 **싱크** 라는 구문에 로그 이벤트를 게시 합니다. 싱크는 Serilog에서 로깅 이벤트를 작성 하는 대상 플랫폼입니다. Seq 용 하나를 포함 하 여 [많은 Serilog 싱크를 사용할 수](https://github.com/serilog/serilog/wiki/Provided-Sinks)있습니다. Seq는 eShopOnDapr에서 사용 되는 Serilog 싱크입니다.

### <a name="application-insights"></a>Application Insights

eShopOnDapr services는 .NET Core 용 Microsoft Application Insights SDK를 사용 하 여 Azure 애플리케이션 Insights에 직접 원격 분석을 보냅니다. 자세한 내용은 Microsoft 문서에서 [ASP.NET Core 응용 프로그램에 대 한 Azure 애플리케이션 정보](/azure/azure-monitor/app/asp-net-core) 를 참조 하세요.

## <a name="summary"></a>요약

프로덕션 환경에서 분산 시스템을 실행할 때는 좋은 관찰성 중요 합니다.

D 4는 분산 추적, 로깅, 메트릭 및 상태를 포함 하 여 다양 한 유형의 원격 분석을 제공 합니다.

D 4는 사이드카 시스템 서비스 및에 대 한 원격 분석만 생성 합니다. 응용 프로그램 코드에서 원격 분석은 자동으로 포함 되지 않습니다. 그러나 .NET 용 OpenTelemetry SDK와 같은 특정 SDK를 사용 하 여 응용 프로그램 코드에서 원격 분석을 내보낼 수 있습니다.

4apr 원격 분석은 오픈 표준 기반 형식으로 생성 되므로 사용 가능한 다양 한 모니터링 도구 집합으로 수집 수 있습니다. 몇 가지 예로는 Zipkin, Azure 애플리케이션 Insights, ELK Stack, New 유물, Grafana 등이 있습니다. 특정 모니터링 백 엔드를 사용 하 여 응용 프로그램을 모니터링 하는 방법에 대 한 자습서는 6Apr 설명서에서 [응용 프로그램 모니터링](https://docs.dapr.io/operations/monitoring/) 을 참조 하세요.

원격 분석을 수집 하 고 모니터링 백 엔드에 게시 하는 원격 분석 scraper 필요 합니다.

구조적 로깅을 내보내도록 capr를 구성할 수 있습니다. 구조적 로깅은 백 엔드 모니터링 도구를 통해 인덱싱될 수 있으므로 선호 됩니다. 인덱싱된 로깅은 사용자가 로깅을 검색할 때 풍부한 쿼리를 실행할 수 있도록 합니다.

6apr는 단일 서비스 및 구성에 대 한 정보를 제공 하는 대시보드를 제공 합니다.

## <a name="references"></a>참조

- [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview/)
- [원격 분석 열기](https://opentelemetry.io/)
- [Zipkin](https://zipkin.io/)
- [W3C 추적 컨텍스트](https://www.w3.org/TR/trace-context/)
- [Jaeger](https://www.jaegertracing.io/)
- [New Relic](https://newrelic.com/)
- [Prometheus](https://prometheus.io/)
- [Grafana](https://grafana.com/grafana/)
- [.NET 용 원격 분석 SDK 열기](https://opentelemetry.io/docs/net/)
- [Fluentd](https://www.fluentd.org/)
- [ELK 스택](https://www.elastic.co/elastic-stack)
- [차이가](https://datalust.co/seq)
- [Serilog](https://serilog.net/)

> [!div class="step-by-step"]
> [이전](bindings.md)
> [다음](secrets.md)
