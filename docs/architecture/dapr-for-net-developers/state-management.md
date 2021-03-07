---
title: D Apr 상태 관리 빌딩 블록
description: 상태 관리 구성 요소, 해당 기능, 이점 및 적용 방법에 대 한 설명입니다.
author: amolenk
ms.date: 02/07/2021
ms.reviewer: robvet
ms.openlocfilehash: 05daf18ece1da377f3d5d6a91c4839f196f14f80
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401837"
---
# <a name="the-dapr-state-management-building-block"></a>D Apr 상태 관리 빌딩 블록

분산 응용 프로그램은 독립 서비스로 구성 됩니다. 각 서비스는 상태 비저장 이어야 하지만, 일부 서비스는 상태를 추적 하 여 비즈니스 작업을 완료 해야 합니다. 전자 상거래 사이트에 대 한 쇼핑 바구니 서비스를 고려 합니다. 서비스에서 상태를 추적할 수 없는 경우 고객은 웹 사이트를 종료 하 여 시장 바구니 콘텐츠를 느슨하게 만들어 판매 및 불만이 있는 사용자 환경을 만들 수 있습니다. 이러한 시나리오의 경우 상태를 분산 된 상태 저장소로 유지 해야 합니다. D [apr 상태 관리 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/state-management/) 은 상태 추적을 간소화 하 고 다양 한 데이터 저장소에서 고급 기능을 제공 합니다.

상태 관리 빌딩 블록을 사용해 보려면 [3 장의 카운터 응용 프로그램 샘플](getting-started.md)을 살펴보세요.

## <a name="what-it-solves"></a>해결 방법

배포 응용 프로그램의 상태를 추적 하는 것은 어려울 수 있습니다. 예를 들면 다음과 같습니다.

- 응용 프로그램에는 다양 한 유형의 데이터 저장소가 필요할 수 있습니다.
- 데이터에 액세스 하 고 업데이트 하는 데 다른 일관성 수준이 필요할 수 있습니다.
- 여러 사용자가 동시에 데이터를 업데이트 하 여 충돌을 해결 해야 할 수 있습니다.
- 서비스는 데이터 저장소와 상호 작용 하는 동안 발생 하는 수명이 짧은 [일시적인 오류](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) 를 모두 다시 시도해 야 합니다.

이 문제를 해결 하기 위한 것입니다. 종속성이 없는 추적 상태 또는 타사 저장소 Sdk의 학습 곡선을 간소화 합니다.

> [!IMPORTANT]
> Eapr 상태 관리는 [키/값](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) API를 제공 합니다. 이 기능은 관계형 또는 그래프 데이터 저장소를 지원 하지 않습니다.

## <a name="how-it-works"></a>작동 방법

응용 프로그램은 사이드카와 상호 작용 하 여 키/값 데이터를 저장 하 고 검색 합니다. 내부적으로 사이드카 API는 구성 가능한 상태 저장소 구성 요소를 사용 하 여 데이터를 유지 합니다. 개발자는 Azure Cosmos DB, SQL Server 및 Cassandra를 포함 하는 증가 하는 [지원 되는 상태 저장소](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) 컬렉션에서 선택할 수 있습니다.

API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다. 다음 URL을 사용 하 여 HTTP API를 호출 합니다.

```http
http://localhost:<dapr-port>/v1.0/state/<store-name>/
```

- `<dapr-port>`: d 4에서 수신 하는 HTTP 포트입니다.
- `<store-name>`: 사용할 상태 저장소 구성 요소의 이름입니다.

그림 5-1에서는 eapr를 사용 하는 시장 바구니 서비스에서 라는 Eapr 상태 저장소 구성 요소를 사용 하 여 키/값 쌍을 저장 하는 방법을 보여 줍니다 `statestore` .

![Eapr 상태 저장소에 키/값 쌍을 저장 하는 다이어그램입니다.](media/state-management/state-management-flow.png)

**그림 5-1**. Eapr 상태 저장소에 키/값 쌍 저장

위의 그림에서 설명 하는 단계를 확인 합니다.

1. 바구니 서비스는 Eapr 사이드카에서 상태 관리 API를 호출 합니다. 요청의 본문은 여러 키/값 쌍을 포함할 수 있는 JSON 배열을 포함 합니다.
1. 사이드카는 구성 요소 구성 파일을 기반으로 상태 저장소를 결정 합니다. 이 경우 Redis cache 상태 저장소입니다.
1. 사이드카는 Redis 캐시에 데이터를 유지 합니다.

저장 된 데이터를 검색 하는 것은 유사한 API 호출입니다. 아래 예제에서 *말아 넘기기* 명령은 사이드카 API를 호출 하 여 데이터를 검색 합니다.

```console
curl http://localhost:3500/v1.0/state/statestore/basket1
```

이 명령은 응답 본문에 저장 된 상태를 반환 합니다.

```json
{
  "items": [
    {
      "itemId": "DaprHoodie",
      "quantity": 1
    }
  ],
  "customerId": 1
}
```

다음 섹션에서는 상태 관리 빌딩 블록의 고급 기능을 사용 하는 방법을 설명 합니다.

### <a name="consistency"></a>일관성

[CAP 정리](https://en.wikipedia.org/wiki/CAP_theorem) 는 상태를 저장 하는 분산 시스템에 적용 되는 원칙 집합입니다. 그림 5-2에서는 CAP 정리의 세 가지 속성을 보여 줍니다.

![캡 정리입니다.](media/state-management/cap-theorem.png)

**그림 5-2**. 캡 정리입니다.

정리 분산 데이터 시스템이 일관성, 가용성 및 파티션 허용 오차를 절충 하는 것을 제공 합니다. 그리고 모든 데이터 저장소에서 다음 *의 세 가지 속성 중 하나만 보장할* 수 있습니다.

- *일관성* (**C**). 모든 복제본이 업데이트 될 때까지 시스템에서 요청을 차단 해야 하는 경우에도 클러스터의 모든 노드는 최신 데이터로 응답 합니다. 현재 업데이트 중인 항목에 대해 "일관 된 시스템"을 쿼리하면 모든 복제본이 성공적으로 업데이트 될 때까지 응답이 수신 되지 않습니다. 그러나 항상 최신 데이터를 받게 됩니다.

- *가용성* (**A**). 모든 노드는 응답이 가장 최근 데이터가 아닌 경우에도 즉각적인 응답을 반환 합니다. 업데이트 중인 항목에 대해 "사용 가능한 시스템"을 쿼리하면 서비스에서 제공할 수 있는 가장 좋은 답을 얻을 수 있습니다.

- *파티션 허용 오차* (**P**)입니다. 복제 된 데이터 노드가 실패 하거나 다른 복제 된 데이터 노드와의 연결이 끊어지는 경우에도 시스템이 계속 작동 하도록 보장 합니다.

배포 응용 프로그램은 **P** 속성을 처리 해야 합니다. 서비스가 네트워크 호출을 통해 서로 통신 하는 경우 네트워크 중단 (**P**)이 발생 합니다. 이러한 점을 염두에 두면 배포 응용 프로그램은 **AP** 또는 **CP** 여야 합니다.

**AP** 응용 프로그램은 일관성 보다 가용성을 선택 합니다. 이 옵션은 **최종 일관성** 전략에 따라 지원 됩니다. 여러 복제본에 중복 데이터를 저장 하는 Azure CosmosDB와 같은 기본 데이터 저장소를 고려 합니다. 최종 일관성을 유지 하면서 상태 저장소는 하나의 복제본에 업데이트를 기록 하 고 클라이언트를 사용 하 여 쓰기 요청을 완료 합니다. 이 시간 후에는 저장소에서 해당 복제본을 비동기식으로 업데이트 합니다. 읽기 요청은 최신 업데이트가 아직 수신 되지 않은 복제본을 포함 하 여 모든 복제본의 데이터를 반환할 수 있습니다.

**CP** 응용 프로그램은 가용성에 대 한 일관성을 선택 합니다. 이 옵션은 **강력한 일관성** 전략으로 지원 됩니다. 이 시나리오에서 상태 저장소는 쓰기 요청을 완료 *하기 전에* *모든* 항목 (또는 일부 경우에는 *쿼럼* )을 동기식으로 업데이트 합니다. 읽기 작업은 복제본에서 가장 최신 데이터를 일관 되 게 반환 합니다.

상태 작업의 일관성 수준은 작업에 *일관성 힌트* 를 연결 하 여 지정 합니다. 다음 *말아* 명령은 `Hello=World` 강력한 일관성 힌트를 사용 하 여 상태 저장소에 키/값 쌍을 씁니다.

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        {
          "key": "Hello",
          "value": "World",
          "options": {
            "consistency": "strong"
          }
        }
      ]'
```

> [!IMPORTANT]
> 작업에 연결 된 일관성 힌트를 충족 하는 데는 최대 4 개의 주 저장소 구성 요소가 있습니다. 모든 데이터 저장소에서 두 가지 일관성 수준을 모두 지원 하지는 않습니다. 일관성 힌트가 설정 되지 않은 경우 기본 동작은 **최종** 입니다.

### <a name="concurrency"></a>동시성

다중 사용자 응용 프로그램에서 동시에 여러 사용자가 동일한 데이터를 동시에 업데이트할 수 있습니다. 6apr는 충돌을 관리 하기 위해 OCC (낙관적 동시성 제어)를 지원 합니다. OCC는 사용자가 데이터의 서로 다른 부분에서 작업 하기 때문에 업데이트 충돌이 드물게 발생 한다는 가정을 기반으로 합니다. 업데이트가 성공 하 고 그렇지 않은 경우 다시 시도 하는 것이 더 효율적입니다. 비관적 잠금을 구현 하는 대안은 장기 실행 잠금으로 인해 성능에 영향을 줄 수 있으므로 데이터 경합이 발생할 수 있습니다.

Etag를 사용 하는 OCC (낙관적 동시성 제어)는 6apr에서 지원 됩니다. ETag는 저장 된 키/값 쌍의 특정 버전과 관련 된 값입니다. 키/값 쌍이 업데이트 될 때마다 ETag 값도 업데이트 됩니다. 클라이언트에서 키/값 쌍을 검색 하면 응답에 현재 ETag 값이 포함 됩니다. 클라이언트는 키/값 쌍을 업데이트 하거나 삭제할 때 해당 ETag 값을 요청 본문으로 다시 보내야 합니다. 다른 클라이언트가 그 동안 데이터를 업데이트 한 경우에는 Etag가 일치 하지 않고 요청이 실패 합니다. 이 시점에서 클라이언트는 업데이트 된 데이터를 검색 하 고 변경 내용을 다시 적용 한 다음 업데이트를 다시 제출 해야 합니다. 이 전략을 **첫 번째-쓰기-wins** 라고 합니다.

또한 6apr는 **마지막 쓰기-wins** 전략을 지원 합니다. 이 접근 방식을 사용 하면 클라이언트는 ETag를 쓰기 요청에 연결 하지 않습니다. 상태 저장소 구성 요소는 세션이 진행 되는 동안 기본 값이 변경 된 경우에도 항상 업데이트를 허용 합니다. 마지막-쓰기-wins는 데이터 경합이 낮은 처리량이 높은 쓰기 시나리오에 유용 합니다. 또한 가끔 사용자 업데이트를 덮어쓸 수 있습니다.

### <a name="transactions"></a>트랜잭션

D 4 월은 트랜잭션으로 구현 된 단일 작업으로 데이터 저장소에 대 한 *다중 항목 변경 내용을* 기록할 수 있습니다. 이 기능은 [ACID](https://en.wikipedia.org/wiki/ACID) 트랜잭션을 지 원하는 데이터 저장소에 대해서만 사용할 수 있습니다. 이 문서를 작성할 당시 이러한 매장에는 Redis, MongoDB, PostgreSQL, SQL Server 및 Azure CosmosDB가 포함 됩니다.

아래 예제에서는 다중 항목 작업을 단일 트랜잭션에서 상태 저장소로 보냅니다. 트랜잭션을 커밋하기 위해서는 모든 작업이 성공 해야 합니다. 하나 이상의 작업이 실패 하면 전체 트랜잭션이 롤백됩니다.

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name>/transaction \
  -H "Content-Type: application/json" \
  -d '{
        "operations": [
          {
            "operation": "upsert",
            "request": { "key": "Key1", "value": "Value1"
            }
          },
          {
            "operation": "delete",
            "request": { "key": "Key2" }
          }
        ]
      }'
```

트랜잭션을 지원 하지 않는 데이터 저장소의 경우에도 여러 키를 단일 요청으로 보낼 수 있습니다. 다음 예에서는 **대량** 쓰기 작업을 보여 줍니다.

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        { "key": "Key1", "value": "Value1" },
        { "key": "Key2", "value": "Value2" }
      ]'
```

대량 작업의 경우에는 각 키/값 쌍 업데이트를 데이터 저장소에 대 한 별도의 요청으로 전송 합니다.

## <a name="use-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

Dapr .NET SDK는 .NET Core 플랫폼에 대 한 언어별 지원을 제공 합니다. 개발자는 `DaprClient` [3 장에](getting-started.md) 도입 된 클래스를 사용 하 여 데이터를 읽고 쓸 수 있습니다. 다음 예제에서는 메서드를 사용 하 여 `DaprClient.GetStateAsync<TValue>` 상태 저장소에서 데이터를 읽는 방법을 보여 줍니다. 메서드에는 저장소 이름, 및 키가 매개 변수로 필요 합니다 `statestore` `AMS` .

```csharp
var weatherForecast = await daprClient.GetStateAsync<WeatherForecast>("statestore", "AMS");
```

상태 저장소에 키에 대 한 데이터가 포함 되어 있지 않으면 `AMS` 결과는가 됩니다 `default(WeatherForecast)` .

데이터 저장소에 데이터를 쓰려면 메서드를 사용 합니다 `DaprClient.SaveStateAsync<TValue>` .

```csharp
daprClient.SaveStateAsync("statestore", "AMS", weatherForecast);
```

이 예제에서는 ETag 값이 상태 저장소 구성 요소에 전달 되지 않으므로 **마지막-쓰기-wins** 전략을 사용 합니다. **첫 번째 쓰기-wins** 전략과 함께 occ (낙관적 동시성 제어)를 사용 하려면 먼저 메서드를 사용 하 여 현재 ETag를 검색 합니다 `DaprClient.GetStateAndETagAsync` . 그런 다음 업데이트 된 값을 작성 하 고 메서드를 사용 하 여 검색 된 ETag를 따라 전달 합니다 `DaprClient.TrySaveStateAsync` .

```csharp
var (weatherForecast, etag) = await daprClient.GetStateAndETagAsync<WeatherForecast>("statestore", city);

// ... make some changes to the retrieved weather forecast

var result = await daprClient.TrySaveStateAsync("statestore", city, weatherForecast, etag);
```

`DaprClient.TrySaveStateAsync`데이터가 검색 된 후 상태 저장소에서 데이터 및 연결 된 ETag가 변경 되 면 메서드가 실패 합니다. 메서드는 호출이 성공 했는지 여부를 나타내는 부울 값을 반환 합니다. 오류를 처리 하는 전략은 상태 저장소에서 업데이트 된 데이터를 다시 로드 하 고 변경 내용을 다시 적용 한 다음 업데이트를 다시 전송 하는 것입니다.

데이터의 다른 변경 내용에 관계 없이 항상 쓰기가 성공 하 게 하려면 **마지막-쓰기-wins** 전략을 사용 합니다.

SDK는 데이터를 대량으로 검색 하 고, 데이터를 삭제 하 고, 트랜잭션을 실행 하는 다른 방법을 제공 합니다. 자세한 내용은 [Dapr .NET SDK 리포지토리](https://github.com/dapr/dotnet-sdk)를 참조 하세요.

### <a name="aspnet-core-integration"></a>ASP.NET Core 통합

또한 ASP.NET Core는 최신 클라우드 기반 웹 응용 프로그램을 빌드하기 위한 플랫폼 간 프레임 워크인 지원 합니다. Dapr SDK는 상태 관리 기능을 [ASP.NET Core 모델 바인딩](/aspnet/core/mvc/models/model-binding) 기능에 직접 통합 합니다. 구성이 간단 합니다. `IMVCBuilder.AddDapr` `.AddDapr` 다음 예제와 같이 클래스에 확장 메서드를 추가 하 여를 추가 합니다 `Startup.cs` .

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers().AddDapr();
}
```

구성 된 후에는 ASP.NET Core 특성을 사용 하 여 키/값 쌍을 컨트롤러 작업에 직접 삽입할 수 있습니다 `FromState` . 개체를 참조 하 `DaprClient` 는 것은 더 이상 필요 하지 않습니다. 다음 예제에서는 지정 된 도시의 날씨 예보를 반환 하는 Web API를 보여 줍니다.

```csharp
[HttpGet("{city}")]
public ActionResult<WeatherForecast> Get([FromState("statestore", "city")] StateEntry<WeatherForecast> forecast)
{
    if (forecast.Value == null)
    {
      return NotFound();
    }

    return forecast.Value;
}
```

이 예에서 컨트롤러는 특성을 사용 하 여 날씨 예측을 로드 합니다 `FromState` . 첫 번째 특성 매개 변수는 상태 저장소 `statestore` 입니다. 두 번째 특성 매개 변수는 `city` 상태 키를 가져올 [경로 템플릿](/aspnet/core/mvc/controllers/routing#route-templates) 변수의 이름입니다. 두 번째 매개 변수를 생략 하면 바인딩된 메서드 매개 변수 ()의 이름이 `forecast` 경로 템플릿 변수를 조회 하는 데 사용 됩니다.

클래스에는 `StateEntry` `StoreName` ,, `Key` `Value` 및의 단일 키/값 쌍에 대해 검색 된 모든 정보에 대 한 속성이 포함 `ETag` 되어 있습니다. ETag는 OCC (낙관적 동시성 제어) 전략을 구현 하는 데 유용 합니다. 또한 클래스는 인스턴스를 요구 하지 않고 검색 된 키/값 데이터를 삭제 하거나 업데이트 하는 메서드를 제공 합니다 `DaprClient` . 다음 예제에서 `TrySaveAsync` 메서드는 OCC를 사용 하 여 검색 된 일기 예보를 업데이트 하는 데 사용 됩니다.

```csharp
[HttpPut("{city}")]
public async Task Put(WeatherForecast updatedForecast, [FromState("statestore", "city")] StateEntry<WeatherForecast> currentForecast)
{
    // update cached current forecast with updated forecast passed into service endpoint
    currentForecast.Value = updatedForecast;

    // update state store
    var success = await currentForecast.TrySaveAsync();

    // ... check result
}
```

## <a name="state-store-components"></a>상태 저장소 구성 요소

이 문서를 작성할 당시에는 다음 트랜잭션 상태 저장소에 대 한 지원을 제공 합니다.

- Azure CosmosDB
- Azure SQL Server
- MongoDB
- PostgreSQL
- Redis

또한 다음은 트랜잭션 기능이 아니라 CRUD 작업을 지 원하는 상태 저장소에 대 한 지원을 포함 합니다.

- Aerospike
- Azure Blob Storage
- Azure Table Storage
- Cassandra
- Cloudstate
- Couchbase
- etcd
- Google Cloud Firestore
- Hashicorp Consul
- Hazelcast
- Memcached
- Zookeeper

### <a name="configuration"></a>구성

자체 호스팅 로컬 개발을 위해 초기화 된 경우 Redis는 기본 상태 저장소로 서를 등록 합니다. 기본 상태 저장소 구성의 예는 다음과 같습니다. 기본 이름인를 적어둡니다 `statestore` .

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

 > [!NOTE]
 > 여러 상태 저장소를 각각 다른 이름으로 단일 응용 프로그램에 등록할 수 있습니다.

Redis 상태 저장소에는 `redisHost` `redisPassword` Redis 인스턴스에 연결 하는 데 필요한 메타 데이터가 필요 합니다. 위의 예제에서 Redis 암호 (기본적으로 빈 문자열)는 일반 문자열로 저장 됩니다. 가장 좋은 방법은 일반 텍스트 문자열을 피하고 항상 비밀 참조를 사용 하는 것입니다. 비밀 관리에 대해 자세히 알아보려면 [10 장](secrets.md)을 참조 하세요.

다른 메타 데이터 필드인는 `actorStateStore` 상태 저장소를 행위자 빌딩 블록에서 사용할 수 있는지 여부를 나타냅니다.

### <a name="key-prefix-strategies"></a>키 접두사 전략

상태 저장소 구성 요소를 사용 하면 다른 전략을 사용 하 여 기본 저장소에 키/값 쌍을 저장할 수 있습니다. 고객이 구매 하고자 하는 품목을 저장 하는 시장 바구니 서비스의 이전 예를 회수할 수 있습니다.

```console
curl -X POST http://localhost:3500/v1.0/state/statestore \
  -H "Content-Type: application/json" \
  -d '[{
        "key": "basket1",
        "value": {
          "customerId": 1,
          "items": [
            { "itemId": "DaprHoodie", "quantity": 1 }
          ]
        }
     }]'
```

Redis 콘솔 도구를 사용 하 여 Redis 캐시 내에서 Redis state store 구성 요소가 데이터를 유지 하는 방법을 확인 합니다.

```
127.0.0.1:6379> KEYS *
1) "basketservice||basket1"

127.0.0.1:6379> HGETALL basketservice||basket1
1) "data"
2) "{\"items\":[{\"itemId\":\"DaprHoodie\",\"quantity\":1}],\"customerId\":1}"
3) "version"
4) "1"
```

출력은 데이터의 전체 Redis **키** 를로 표시 합니다 `basketservice||basket1` . 기본적으로, 644는 `application id` `basketservice` 키에 대 한 접두사로 ()의를 사용 합니다. 이 명명 규칙을 사용 하면 여러 개의 Capr 인스턴스가 키 이름 충돌 없이 동일한 데이터 저장소를 공유할 수 있습니다. 개발자의 경우, 응용 프로그램을 실행 하는 경우에는 항상 동일한 것을 지정 해야 합니다 `application id` . 생략 하는 경우에는 고유 응용 프로그램 ID를 생성 합니다. 이 `application id` 변경 되 면 응용 프로그램은 이전 키 접두사를 사용 하 여 저장 된 상태에 더 이상 액세스할 수 없습니다.

즉, 상태 저장소 구성 요소 파일의 메타 데이터 필드에서 키 접두사에 대 한 *상수 값* 을 구성할 수 `keyPrefix` 있습니다. 다음 예제를 참조하세요.

```yaml
spec:
  metadata:
  - name: keyPrefix
  - value: MyPrefix
```

상수 키 접두사를 사용 하면 여러 개의 4Apr 응용 프로그램에서 상태 저장소에 액세스할 수 있습니다. 자세히,를로 설정 하면 `keyPrefix` `none` 접두사가 완전히 생략 됩니다.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

이 책에는 이라는 참조 응용 프로그램이 포함 되어 있습니다 `eShopOnDapr` . 이전 Microsoft 마이크로 서비스 참조 응용 프로그램에서 모델링 `eShopOnContainers` 됩니다.

원래 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 아키텍처는 인터페이스를 사용 `IBasketRepository` 하 여 바구니 서비스의 데이터를 읽고 씁니다. `RedisBasketRepository`클래스는 Redis를 기본 데이터 저장소로 사용 하 여 구현을 제공 했습니다.

```csharp
public class RedisBasketRepository : IBasketRepository
{
    private readonly ConnectionMultiplexer _redis;
    private readonly IDatabase _database;

    public RedisBasketRepository(ConnectionMultiplexer redis)
    {
        _redis = redis;
        _database = redis.GetDatabase();
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        var data = await _database.StringGetAsync(customerId);

        if (data.IsNullOrEmpty)
        {
            return null;
        }

        return JsonConvert.DeserializeObject<CustomerBasket>(data);
    }

    // ...
}
```

이 코드는 타사 NuGet 패키지를 사용 합니다 `StackExchange.Redis` . 다음 단계는 지정 된 고객에 대 한 장바구니를 로드 하는 데 필요 합니다.

1. `ConnectionMultiplexer`생성자에를 삽입 합니다. 는 `ConnectionMultiplexer` 파일의 종속성 주입 프레임 워크에 등록 됩니다 `Startup.cs` .

   ```csharp
   services.AddSingleton<ConnectionMultiplexer>(sp =>
   {
       var settings = sp.GetRequiredService<IOptions<BasketSettings>>().Value;
       var configuration = ConfigurationOptions.Parse(settings.ConnectionString, true);
       configuration.ResolveDns = true;
       return ConnectionMultiplexer.Connect(configuration);
   });
   ```

1. 를 사용 `ConnectionMultiplexer` 하 여 `IDatabase` 각 소비 클래스에서 인스턴스를 만듭니다.

1. `IDatabase`지정 된를 키로 사용 하 여 Redis StringGet 호출을 실행 하려면 인스턴스를 사용 합니다 `customerId` .

1. 데이터가 Redis에서 로드 되는지 확인 합니다. 그렇지 않으면를 반환 `null` 합니다.

1. Redis에서 개체로 데이터를 Deserialize 하 `CustomerBasket` 고 결과를 반환 합니다.

업데이트 된 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) 참조 응용 프로그램에서 새 `DaprBasketRepository` 클래스는 클래스를 대체 합니다 `RedisBasketRepository` .

```csharp
public class DaprBasketRepository : IBasketRepository
{
    private const string StoreName = "eshop-basket-statestore";

    private readonly DaprClient _daprClient;

    public DaprBasketRepository(DaprClient daprClient)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));;
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        return await _daprClient.GetStateAsync<CustomerBasket>(StoreName, customerId);
    }

    // ...
}
```

업데이트 된 코드는 Dapr .NET SDK를 사용 하 여 상태 관리 구성 블록을 통해 데이터를 읽고 씁니다. 고객에 대 한 바구니를 로드 하는 새로운 단계가 크게 간소화 되었습니다.

1. `DaprClient`생성자에를 삽입 합니다. 는 `DaprClient` 파일의 종속성 주입 프레임 워크에 등록 됩니다 `Startup.cs` .
1. 메서드를 사용 `DaprClient.GetStateAsync` 하 여 구성 된 상태 저장소에서 고객의 쇼핑 바구니 항목을 로드 하 고 결과를 반환 합니다.

업데이트 된 구현은 여전히 Redis를 기본 데이터 저장소로 사용 합니다. 그러나 `StackExchange.Redis` 응용 프로그램에서 참조 및 복잡성을 추상화 하는 경우 모든 필수 구성 파일은 다음과 같습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

또한 기본 데이터 저장소를 변경 하는 것이 더 간단해 집니다. 예를 들어 Azure Table Storage로 전환 하려면 구성 파일의 내용만 변경 하면 됩니다. 코드를 변경할 필요가 없습니다.

## <a name="summary"></a>요약

6Apr 상태 관리 빌딩 블록은 다양 한 데이터 저장소에 키/값 데이터를 저장 하기 위한 API를 제공 합니다. API는 다음에 대 한 지원을 제공 합니다.

- 대량 작업
- 강력 하 고 결과적 일관성
- 낙관적 동시성 제어
- 다중 항목 트랜잭션

.NET SDK는 .NET Core 및 ASP.NET Core에 대 한 언어별 지원을 제공 합니다. 모델 바인딩 통합은 ASP.NET Core 컨트롤러 동작 메서드에서의 액세스 및 업데이트 상태를 간소화 합니다.

EShopOnDapr reference 응용 프로그램에서 다음과 같은 이점이 있습니다.

1. 새 구현에서는 코드 줄 수가 줄어듭니다.
1. 타사 API의 복잡성을 추상화 합니다 `StackExchange.Redis` .
1. 기본 Redis cache를 다른 유형의 데이터 저장소로 바꾸려면 상태 저장소 구성 파일을 변경 해야 합니다.

### <a name="references"></a>참조

- [4 월 지원 상태 저장소](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/)

> [!div class="step-by-step"]
> [이전](reference-application.md)
> [다음](service-invocation.md)
