---
title: Dapr이 배포되어 있습니다.
description: D 4의 용도, 수행 하는 방법 및 작동 방식에 대 한 개략적인 개요입니다.
author: robvet
ms.date: 02/17/2021
ms.openlocfilehash: 9f23e9822fd0d4b5eda648d2fc1359cce14cf59d
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624047"
---
# <a name="dapr-at-20000-feet"></a>Dapr이 배포되어 있습니다.

1 장에서는 분산 마이크로 서비스 응용 프로그램에 대해 설명 했습니다. 그러나 아키텍처와 운영 복잡성이 크게 증가 한다는 것을 지적 했습니다. 이를 염두에 두면이 질문은 어떻게 "케이크를 사용 하 고 있나요?"를 어떻게 할 수 있나요? 즉, 분산 아키텍처의 민첩성을 활용 하 고 복잡성을 최소화 하려면 어떻게 해야 하나요?

Eapr 또는 *Distributed Application Runtime* 은 최신 분산 응용 프로그램을 빌드하는 새로운 방법입니다.

프로토타입에서 시작 되는 항목은 매우 성공적인 오픈 소스 프로젝트로 발전 했습니다. Microsoft의 스폰서는 고객 및 오픈 소스 커뮤니티와 긴밀 하 게 협력 하 여 Eapr를 설계 하 고 구축 했습니다. 이 프로젝트는 모든 배경에서 개발자를 함께 제공 하 여 분산 응용 프로그램 개발의 가장 어려운 문제 중 일부를 해결 합니다.

이 책에서는 .NET 개발자의 관점에서부터부터 4 번째를 살펴봅니다. 이 장에서는 Eapr 및 작동 방식에 대 한 개념적인 이해를 구축 합니다. 나중에 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.

Jet에서 2만 피트로 비행을 생각해 보세요. 창을 확인 하 고 광범위 한 관점에서 아래 가로를 확인 합니다. D Apr에 대해 동일한 작업을 수행해 보겠습니다. 2만 피트에서 A4에서 직접 비행을 시각화 합니다. 표시 되는 내용

## <a name="dapr-and-the-problem-it-solves"></a>6apr 및 해결 된 문제

D 4는 최신 분산 응용 프로그램: **복잡성** 에 내재 된 큰 과제를 해결 합니다.

플러그형 구성 요소의 아키텍처를 통해, d 4는 분산 응용 프로그램의 기반이 되는 것을 크게 간소화 합니다. 이 클래스는 응용 프로그램을 Capr 런타임의 인프라 기능과 바인딩하는 **동적 붙이기를** 제공 합니다.

서비스의 상태를 변경 하는 데 필요한 요구 사항을 고려 하세요. 디자인은 무엇 인가요? Redis Cache와 같은 상태 저장소를 대상으로 하는 사용자 지정 코드를 작성할 수 있습니다. 그러나 6Apr는 상태 관리 기능을 기본 제공 합니다. 서비스는 Capr 구성 **요소 구성** yaml 파일을 통해 상태 저장소 **구성 요소** 에 동적으로 바인딩하는 eapr 상태 관리 **빌딩 블록** 을 호출 합니다. Redis를 포함 하 여 몇 가지 미리 작성 된 상태 저장소 구성 요소가 포함 된 capr. 이 모델을 사용 하면 서비스에서 상태 관리를 Capr 런타임에 위임 합니다. 서비스에 SDK, 라이브러리 또는 기본 구성 요소에 대 한 직접 참조가 없습니다. 코드를 변경 하지 않고도 Redis에서 MySQL 또는 Cassandra로 상태 저장소를 변경할 수도 있습니다.

그림 2-1에는 2만 피트의 44가 나와 있습니다.

![2만 피트 피트 ](./media/dapr-at-20000-feet/dapr-high-level.png)
 **그림 2-1** 2만 피트

그림의 맨 위 행에서 d 4는 인기 있는 개발 플랫폼에 대 한 언어별 Sdk를 제공 하는 방법을 확인 합니다. 1.0는 Go, Node.js, Python, .NET, Java 및 JavaScript를 지원 합니다. 이 책에서는 ASP.NET Core 통합에 대 한 직접적인 지원도 제공 하는 Dapr .NET SDK에 대해 집중적으로 설명 합니다.

언어별 Sdk는 개발자 환경을 개선 하는 반면, d 4 월은 플랫폼에 독립적입니다. 내부적으로, 4, 4의 프로그래밍 모델은 표준 HTTP/gRPC 통신 프로토콜을 통해 기능을 노출 합니다. 모든 프로그래밍 플랫폼은 네이티브 HTTP 및 gRPC Api를 통해 6Apr를 호출할 수 있습니다.  

그림의 가운데에 있는 파란색 상자는 4 번째 빌딩 블록을 나타냅니다. 각는 응용 프로그램에서 사용할 수 있는 배포 응용 프로그램 기능을 제공 합니다.

아래쪽 행에는 Eapr 및 실행할 수 있는 다양 한 환경에 대 한 이식성이 강조 표시 됩니다.

## <a name="dapr-architecture"></a>4 월 아키텍처

이 시점에서 jet는 계속 해 서 a를 기준으로 하는 Eapr를 전환 하 고 다시 포기 하 여,의 작업 방식에 대해 자세히 살펴봅니다.

### <a name="building-blocks"></a>구성 요소

새로운 관점에서 볼 때에는 보다 자세한 정보를 볼 수 **있습니다.**

빌딩 블록은 분산 인프라 기능을 캡슐화 합니다. HTTP 또는 gRPC Api를 통해 기능에 액세스할 수 있습니다. 그림 2-2에서는 Eapr v 1.0에 사용할 수 있는 블록을 보여 줍니다.

![4apr 빌딩 블록](./media/dapr-at-20000-feet/building-blocks.png)

**그림 2-2**. 4apr 빌딩 블록입니다.

다음 표에서는 각 블록에서 제공 하는 인프라 서비스에 대해 설명 합니다.

| 구성 요소 | Description |
|----------------|-------------|
| [상태 관리](state-management.md) | 장기 실행 상태 저장 서비스에 대 한 컨텍스트 정보를 지원 합니다. |
| [서비스 호출](service-invocation.md) | 플랫폼을 알 수 없는 프로토콜 및 잘 알려진 끝점을 사용 하 여 직접, 보안 서비스 간 호출을 호출 합니다. |
| [게시 및 구독](publish-subscribe.md) | 서비스 간에 안전 하 고 확장 가능한 게시/서브 메시징을 구현 합니다. |
| [바인딩](bindings.md) | 양방향 통신을 사용 하 여 외부 리소스에 의해 발생 한 이벤트에서 코드를 트리거합니다. |
| [가시성](observability.md) | 네트워크 서비스에서 메시지 호출을 모니터링 하 고 측정 합니다. |
| [비밀](secrets.md) | 외부 암호 저장소에 안전 하 게 액세스 합니다. |
| 행위자 | 다시 사용할 수 있는 행위자 개체에 논리와 데이터를 캡슐화 합니다. |

구성 요소는 서비스에서 분산 응용 프로그램 기능의 구현을 추상화 합니다. 그림 2-3에서는 이러한 상호 작용을 보여 줍니다.

![4apr 빌딩 블록 통합](./media/dapr-at-20000-feet/building-blocks-integration.png)

**그림 2-3**. 4apr 빌딩 블록 통합.

빌딩 블록은 각 리소스에 대 한 구체적인 구현을 제공 하는 4 월 구성 요소를 호출 합니다. 서비스에 대 한 코드는 빌딩 블록만 인식 합니다. 외부 Sdk 나 라이브러리에 대 한 종속성을 사용 하지 않습니다. 각 빌딩 블록은 독립적입니다. 응용 프로그램에서 하나, 일부 또는 모두를 사용할 수 있습니다. 값 추가로, 종합적인 관찰성을 비롯 한 업계 모범 사례에서 굽기 구성 요소를 만듭니다.

이후 장에서 각 4Apr 빌딩 블록에 대 한 자세한 설명 및 코드 샘플을 제공 합니다. 이 시점에서 jet는 훨씬 더 계층이 이어집니다. 이제 새로운 관점에서 볼 때에는 이제는 Eapr 구성 요소 계층에 대해 자세히 살펴보겠습니다.

### <a name="components"></a>구성 요소

빌드 블록은 배포 응용 프로그램 기능을 호출 하는 API를 노출 하지만, Capr 구성 요소는 구체적 구현을 제공 하 여이를 수행 합니다.

예를 들어, Wapr **상태 저장소** 구성 요소를 고려 합니다. CRUD 작업에 대 한 상태를 관리 하는 일관 된 방법을 제공 합니다. 서비스 코드를 변경 하지 않으면 다음의 모든 작업 구성 요소 중 하나를 전환할 수 있습니다.

- AWS DynamoDB
- Aerospike
- Azure Blob Storage
- Azure CosmosDB
- Azure Table Storage
- Cassandra
- 클라우드 Firestore (데이터 저장소 모드)
- CloudState
- Couchbase
- Etcd
- HashiCorp Consul
- Hazelcast
- Memcached
- MongoDB
- PostgreSQL
- Redis
- RethinkDB
- SQL Server
- Zookeeper

각 구성 요소는 일반적인 상태 관리 인터페이스를 통해 필요한 구현을 제공 합니다.

```go
 type Store interface {
   Init(metadata Metadata) error
   Delete(req *DeleteRequest) error
   BulkDelete(req []DeleteRequest) error
   Get(req *GetRequest) (*GetResponse, error)
   Set(req *SetRequest) error
   BulkSet(req []SetRequest) error
}
```

> [!TIP]
> Golang 또는 Go 언어로 작성 된 모든의 4 가지 구성 요소 뿐만 아니라, Go는 오픈 소스 커뮤니티에서 널리 사용 되는 언어로, 입증의 플랫폼 간 약정을 위한 것입니다.

Azure Redis Cache에서 상태 저장소로 시작 하는 것일 수 있습니다. 다음 구성을 사용 하 여 지정 합니다.

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Component
 metadata:
   name: statestore
   namespace: default
 spec:
   type: state.redis
   version: v1
   metadata:
   - name: redisHost
     value: <HOST>
   - name: redisPassword
     value: <PASSWORD>
   - name: enableTLS
     value: <bool> # Optional. Allowed: true, false.
   - name: failover
     value: <bool> # Optional. Allowed: true, false.
 ```

**사양** 섹션에서 상태 관리에 대 한 Redis Cache를 사용 하도록 6apr를 구성 합니다. 또한이 섹션에서는 구성 요소별 메타 데이터를 포함 합니다. 이 경우 추가 Redis 설정을 구성 하는 데 사용할 수 있습니다.

나중에 응용 프로그램을 프로덕션 환경으로 이동할 준비가 되었습니다. 프로덕션 환경의 경우 상태 관리를 Azure Table Storage로 변경 해야 할 수 있습니다. Azure Table Storage는 경제적이 고 내구성이 뛰어난 상태 관리 기능을 제공 합니다.

이 문서를 작성할 당시에는 다음과 같은 구성 요소 유형을 d 4에서 제공 합니다.

| 구성 요소 | Description |
|-----------|-------------|
| [서비스 검색](https://github.com/dapr/components-contrib/tree/master/nameresolution) | 서비스 간 검색을 제공 하기 위해 호스팅 환경과 통합 하는 서비스 호출 구성 요소에서 사용 됩니다. |
| [State](https://github.com/dapr/components-contrib/tree/master/state) | 다양 한 상태 저장소 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다. |
| [Pub/sub](https://github.com/dapr/components-contrib/tree/master/pubsub) | 다양 한 메시지 버스 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다. |
| [바인딩](https://github.com/dapr/components-contrib/tree/master/bindings) | 외부 시스템에서 응용 프로그램 이벤트를 트리거하고 선택적 데이터 페이로드가 있는 외부 시스템을 호출 하는 일관 된 인터페이스를 제공 합니다. |
| [미들웨어](https://github.com/dapr/components-contrib/tree/master/middleware) | 사용자 지정 미들웨어가 요청 처리 파이프라인에 연결 하 고 요청 또는 응답에 대 한 추가 작업을 호출할 수 있도록 허용 합니다. |
| [비밀 저장소](https://github.com/dapr/components-contrib/tree/master/secretstores) | 클라우드,에 지, 상용, 오픈 소스 서비스를 비롯 하 여 외부 암호 저장소와 상호 작용 하는 일관 된 인터페이스를 제공 합니다. |

Jet가 d 4의 즉석에서 날아오기를 완료 하는 경우에는 나중에 다시 연결 하 여 함께 연결 하는 방법을 확인할 수 있습니다.

### <a name="sidecar-architecture"></a>사이드카 아키텍처

[사이드카 아키텍처](/azure/architecture/patterns/sidecar)를 통해 구성 요소 및 구성 요소를 노출 합니다. 사이드카를 사용 하면 다른 메모리 프로세스에서 또는 서비스와 함께 별도의 컨테이너에서 실행할 수 있습니다. 사이드카는 서비스에 포함 되지 않고 연결 된 격리 및 캡슐화를 제공 합니다. 이러한 분리를 통해 각각 고유한 런타임 환경을 보유 하 고 다양 한 프로그래밍 플랫폼을 기반으로 빌드할 수 있습니다. 그림 2-4에서는 사이드카 패턴을 보여 줍니다.

![사이드카 아키텍처](./media/dapr-at-20000-feet/sidecar-generic.png)

**그림 2-4**. 사이드카 아키텍처.

이 패턴은 오토바이에 연결된 사이드카와 유사하므로 사이드카라고 합니다. 위의 그림에서 배포 응용 프로그램 기능을 제공 하기 위해 사이드카이 서비스에 연결 되는 방법을 확인 합니다.

### <a name="hosting-environments"></a>호스팅 환경

D apr는 플랫폼 간 지원을 제공 하며 다양 한 환경에서 실행할 수 있습니다. 이러한 환경에는 Kubernetes, Vm 그룹 또는 Azure IoT Edge와 같은에 지 환경이 포함 됩니다.

로컬 개발의 경우 시작 하는 가장 쉬운 방법은 [자체 호스팅 모드](https://docs.dapr.io/concepts/overview/#self-hosted)를 사용 하는 것입니다. 자체 호스팅 모드에서 마이크로 서비스와 사이드카는 Kubernetes와 같은 컨테이너 orchestrator 없이 별도의 로컬 프로세스에서 실행 됩니다. 자세한 내용은 [Eapr CLI 다운로드 및 설치](https://docs.dapr.io/getting-started/install-dapr/)를 참조 하세요.

그림 2-5에서는 HTTP 또는 gRPC를 통해 통신 하는 두 개의 별도 메모리 프로세스에서 호스팅되는 응용 프로그램 및 응용 프로그램을 보여 줍니다.

![자체 호스팅 사이드카 아키텍처](./media/dapr-at-20000-feet/self-hosted-dapr-sidecar.png)

**그림 2-5**. 자체 호스팅 사이드카.

기본적으로 Redis 및 Zipkin에 대 한 Docker 컨테이너를 설치 하 여 기본 상태 관리 및 관찰성를 제공 합니다. 로컬 컴퓨터에 Docker를 설치 하지 않으려면 [docker 컨테이너 없이도 자체 호스팅 모드에서](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/)docker를 실행할 수 있습니다. 그러나 상태 관리 및 pub/sub에 대해 Redis 같은 기본 구성 요소를 수동으로 설치 해야 합니다.

또한 컨테이너 화 된는 Kubernetes와 같은 [환경](https://docs.dapr.io/concepts/overview/#kubernetes-hosted)에서 실행 됩니다. 그림 2-6에는 동일한 Kubernetes pod의 응용 프로그램 컨테이너와 함께 별도의 측면과 자동차 컨테이너에서 실행 되는 4 개의가 나와 있습니다.

![Kubernetes-호스팅된 사이드카 아키텍처](./media/dapr-at-20000-feet/kubernetes-hosted-dapr-sidecar.png)

**그림 2-6**. Kubernetes-호스 티 드 사이드카.

## <a name="dapr-performance-considerations"></a>4 월 성능 고려 사항

앞서 살펴본 것 처럼 사이드카 아키텍처를 노출 하 여 응용 프로그램을 분산 응용 프로그램 기능에서 분리 합니다. Eapr 작업을 호출 하려면 적어도 하나 이상의 out-of-process 네트워크 호출이 필요 합니다. 그림 2-7에는 4Apr 트래픽 패턴의 예가 나와 있습니다.

![4apr 트래픽 패턴](./media/dapr-at-20000-feet/dapr-traffic-patterns.png)

**그림 2-7**. 4apr 트래픽 패턴.

위의 그림을 보면 각 호출에 대해 발생 하는 대기 시간 및 오버 헤드를 확인할 수 있습니다.  

4Apr 팀은 성능에 많은 투자를 받았습니다. 엄청난 규모의 엔지니어링 노력으로 인해 4 월 효율적으로 작성 되었습니다. Eapr 사이드카 간의 호출은 항상 높은 성능과 작은 이진 페이로드를 제공 하는 gRPC를 사용 하 여 수행 됩니다. 대부분의 경우 추가 오버 헤드는 하위 밀리초 여야 합니다.

개발자는 성능을 향상 시키기 위해 gRPC를 사용 하 여 4Apr 빌딩 블록을 호출할 수 있습니다.

gRPC는 오래 된 [원격 프로시저 호출 (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) 프로토콜을 진화 하는 현대적인 고성능 프레임 워크입니다. gRPC는 전송 프로토콜에 대해 HTTP/2를 사용 하며, 다음을 포함 하 여 HTTP RESTFul 서비스 보다 상당한 성능 향상을 제공 합니다.

- 동일한 연결을 통해 여러 병렬 요청을 보내기 위한 멀티플렉싱 지원-HTTP 1.1는 한 번에 하나의 요청/응답 메시지로 처리를 제한 합니다.
- 클라이언트 요청과 서버 응답을 동시에 전송 하기 위한 양방향 전이중 통신입니다.
- 대량 데이터 집합을 비동기적으로 스트림 하는 요청 및 응답을 설정 하는 기본 제공 스트리밍입니다.

자세한 내용은 [Azure 전자책에 대 한 .Net 앱 설계 Cloud-Native](https://docs.microsoft.com/dotnet/architecture/cloud-native/) 에서 [grpc 개요](https://docs.microsoft.com/dotnet/architecture/cloud-native/grpc#what-is-grpc) 를 확인 하세요.  

## <a name="dapr-and-service-meshes"></a>4apr 및 서비스 메시

서비스 메시는 분산 응용 프로그램에 대 한 또 다른 빠르게 진화 하는 기술입니다.

서비스 메시는 서비스 간 통신, 복원 력, 부하 분산 및 원격 분석 캡처를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다. 서비스 및 서비스 메시 계층으로 이러한 문제에 대 한 책임을 이동 합니다. Eapr와 마찬가지로 서비스 메시도 사이드카 아키텍처를 따릅니다.

그림 2-8에서는 서비스 메시 기술을 구현 하는 응용 프로그램을 보여 줍니다.

![서비스 메시](./media/dapr-at-20000-feet/service-mesh-with-side-car.png)

**그림 2-8**. 측 자동차를 사용 하는 서비스 메시.

위의 그림은 각 서비스와 함께 실행 되는 사이드카 프록시가 메시지를 가로채는 방법을 보여 줍니다. 각 프록시는 서비스와 관련 된 트래픽 규칙으로 구성할 수 있습니다. 메시지를 이해 하 고 서비스와 외부 세계에서 메시지를 라우팅할 수 있습니다.

따라서 "서비스 메시는 ' 서비스 메시 인가요?" 라는 질문이 됩니다.

둘 다 사이드카 아키텍처를 사용 하는 반면 각 기술은 다른 용도로 사용 됩니다. D 4는 배포 응용 프로그램 기능을 제공 합니다. 서비스 메시는 전용 네트워크 인프라 계층을 제공 합니다.

서로 다른 수준에서 작동 하는 경우 모두 동일한 응용 프로그램에서 함께 사용할 수 있습니다. 예를 들어 서비스 메시는 서비스 간에 네트워킹 통신을 제공할 수 있습니다. 6apr는 상태 관리 또는 행위자 서비스와 같은 응용 프로그램 서비스를 제공할 수 있습니다.

그림 2-9에서는 Eapr 및 service 메시 기술을 모두 구현 하는 응용 프로그램을 보여 줍니다.

![D apr 및 서비스 메시 함께](./media/dapr-at-20000-feet/dapr-and-service-mesh.png)

**그림 2-9**. D apr 및 서비스 메시를 함께 연결 합니다.

D [apr 온라인 설명서](https://docs.dapr.io/concepts/faq/#networking-and-service-meshes) 에는 eapr 및 service 메시 통합이 포함 되어 있습니다.

## <a name="summary"></a>요약

이 장에서는 배포 응용 프로그램 런타임 (4 월)을 소개 했습니다.

6apr는 고객과 오픈 소스 커뮤니티의 긴밀 한 공동 작업으로 Microsoft에서 후원 한 오픈 소스 프로젝트입니다.

코어는 코어에서 분산 마이크로 서비스 응용 프로그램의 내재 된 복잡성을 줄이는 데 도움이 됩니다. 블록 Api를 빌드하는 개념을 기반으로 합니다. 다단계 빌딩 블록은 상태 관리, 서비스 간 호출 및 pub/sub 메시징과 같은 일반적인 분산 응용 프로그램 기능을 노출 합니다. 4 월 구성 요소는 빌딩 블록 아래에 있으며 각 기능에 대 한 구체적인 구현을 제공 합니다. 응용 프로그램은 구성 파일을 통해 다양 한 구성 요소에 바인딩됩니다.

다음 장에서는 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.

### <a name="references"></a>참조

- [4apr 설명서](https://dapr.io/)
- [66Apr 학습](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1)
- [.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)
- [Azure 용 Cloud-Native .NET 앱 설계](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> [이전](the-world-is-distributed.md)
> [다음](getting-started.md)
