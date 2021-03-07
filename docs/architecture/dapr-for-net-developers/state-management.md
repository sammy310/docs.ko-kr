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
# <a name="the-dapr-state-management-building-block"></a><span data-ttu-id="4ddbf-103">D Apr 상태 관리 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="4ddbf-103">The Dapr state management building block</span></span>

<span data-ttu-id="4ddbf-104">분산 응용 프로그램은 독립 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-104">Distributed applications are composed of independent services.</span></span> <span data-ttu-id="4ddbf-105">각 서비스는 상태 비저장 이어야 하지만, 일부 서비스는 상태를 추적 하 여 비즈니스 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-105">While each service should be stateless, some services must track state to complete business operations.</span></span> <span data-ttu-id="4ddbf-106">전자 상거래 사이트에 대 한 쇼핑 바구니 서비스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-106">Consider a shopping basket service for an e-Commerce site.</span></span> <span data-ttu-id="4ddbf-107">서비스에서 상태를 추적할 수 없는 경우 고객은 웹 사이트를 종료 하 여 시장 바구니 콘텐츠를 느슨하게 만들어 판매 및 불만이 있는 사용자 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-107">If the service can't track state, the customer could loose the shopping basket content by leaving the website, resulting in a lost sale and an unhappy customer experience.</span></span> <span data-ttu-id="4ddbf-108">이러한 시나리오의 경우 상태를 분산 된 상태 저장소로 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-108">For these scenarios, state needs to be persisted to a distributed state store.</span></span> <span data-ttu-id="4ddbf-109">D [apr 상태 관리 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/state-management/) 은 상태 추적을 간소화 하 고 다양 한 데이터 저장소에서 고급 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-109">The [Dapr state management building block](https://docs.dapr.io/developing-applications/building-blocks/state-management/) simplifies state tracking and offers advanced features across various data stores.</span></span>

<span data-ttu-id="4ddbf-110">상태 관리 빌딩 블록을 사용해 보려면 [3 장의 카운터 응용 프로그램 샘플](getting-started.md)을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-110">To try out the state management building block, have a look at the [counter application sample in chapter 3](getting-started.md).</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="4ddbf-111">해결 방법</span><span class="sxs-lookup"><span data-stu-id="4ddbf-111">What it solves</span></span>

<span data-ttu-id="4ddbf-112">배포 응용 프로그램의 상태를 추적 하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-112">Tracking state in a distributed application can be challenging.</span></span> <span data-ttu-id="4ddbf-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-113">For example:</span></span>

- <span data-ttu-id="4ddbf-114">응용 프로그램에는 다양 한 유형의 데이터 저장소가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-114">The application may require different types of data stores.</span></span>
- <span data-ttu-id="4ddbf-115">데이터에 액세스 하 고 업데이트 하는 데 다른 일관성 수준이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-115">Different consistency levels may be required for accessing and updating data.</span></span>
- <span data-ttu-id="4ddbf-116">여러 사용자가 동시에 데이터를 업데이트 하 여 충돌을 해결 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-116">Multiple users may update data at the same time, requiring  conflict resolution.</span></span>
- <span data-ttu-id="4ddbf-117">서비스는 데이터 저장소와 상호 작용 하는 동안 발생 하는 수명이 짧은 [일시적인 오류](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) 를 모두 다시 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-117">Services must retry any short-lived [transient errors](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) that  occur while interacting with the data store.</span></span>

<span data-ttu-id="4ddbf-118">이 문제를 해결 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-118">The Dapr state management building block addresses these challenges.</span></span> <span data-ttu-id="4ddbf-119">종속성이 없는 추적 상태 또는 타사 저장소 Sdk의 학습 곡선을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-119">It streamlines tracking state without dependencies or a learning curve on third-party storage SDKs.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ddbf-120">Eapr 상태 관리는 [키/값](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-120">Dapr state management offers a [key/value](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) API.</span></span> <span data-ttu-id="4ddbf-121">이 기능은 관계형 또는 그래프 데이터 저장소를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-121">The feature doesn't support relational or graph data storage.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4ddbf-122">작동 방법</span><span class="sxs-lookup"><span data-stu-id="4ddbf-122">How it works</span></span>

<span data-ttu-id="4ddbf-123">응용 프로그램은 사이드카와 상호 작용 하 여 키/값 데이터를 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-123">The application interacts with a Dapr sidecar to store and retrieve key/value data.</span></span> <span data-ttu-id="4ddbf-124">내부적으로 사이드카 API는 구성 가능한 상태 저장소 구성 요소를 사용 하 여 데이터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-124">Under the hood, the sidecar API consumes a configurable state store component to persist data.</span></span> <span data-ttu-id="4ddbf-125">개발자는 Azure Cosmos DB, SQL Server 및 Cassandra를 포함 하는 증가 하는 [지원 되는 상태 저장소](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) 컬렉션에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-125">Developers can choose from a growing collection of [supported state stores](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) that include Azure Cosmos DB, SQL Server, and Cassandra.</span></span>

<span data-ttu-id="4ddbf-126">API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-126">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="4ddbf-127">다음 URL을 사용 하 여 HTTP API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-127">Use the following URL to call the HTTP API:</span></span>

```http
http://localhost:<dapr-port>/v1.0/state/<store-name>/
```

- <span data-ttu-id="4ddbf-128">`<dapr-port>`: d 4에서 수신 하는 HTTP 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-128">`<dapr-port>`: the HTTP port that Dapr listens on.</span></span>
- <span data-ttu-id="4ddbf-129">`<store-name>`: 사용할 상태 저장소 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-129">`<store-name>`: the name of the state store component to use.</span></span>

<span data-ttu-id="4ddbf-130">그림 5-1에서는 eapr를 사용 하는 시장 바구니 서비스에서 라는 Eapr 상태 저장소 구성 요소를 사용 하 여 키/값 쌍을 저장 하는 방법을 보여 줍니다 `statestore` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-130">Figure 5-1 shows how a Dapr-enabled shopping basket service stores a key/value pair using the Dapr state store component named `statestore`.</span></span>

![Eapr 상태 저장소에 키/값 쌍을 저장 하는 다이어그램입니다.](media/state-management/state-management-flow.png)

<span data-ttu-id="4ddbf-132">**그림 5-1**.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-132">**Figure 5-1**.</span></span> <span data-ttu-id="4ddbf-133">Eapr 상태 저장소에 키/값 쌍 저장</span><span class="sxs-lookup"><span data-stu-id="4ddbf-133">Storing a key/value pair in a Dapr state store.</span></span>

<span data-ttu-id="4ddbf-134">위의 그림에서 설명 하는 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-134">Note the steps in the previous figure:</span></span>

1. <span data-ttu-id="4ddbf-135">바구니 서비스는 Eapr 사이드카에서 상태 관리 API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-135">The basket service calls the state management API on the Dapr sidecar.</span></span> <span data-ttu-id="4ddbf-136">요청의 본문은 여러 키/값 쌍을 포함할 수 있는 JSON 배열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-136">The body of the request encloses a JSON array that can contain multiple key/value pairs.</span></span>
1. <span data-ttu-id="4ddbf-137">사이드카는 구성 요소 구성 파일을 기반으로 상태 저장소를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-137">The Dapr sidecar determines the state store based on the component configuration file.</span></span> <span data-ttu-id="4ddbf-138">이 경우 Redis cache 상태 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-138">In this case, it's a Redis cache state store.</span></span>
1. <span data-ttu-id="4ddbf-139">사이드카는 Redis 캐시에 데이터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-139">The sidecar persists the data to the Redis cache.</span></span>

<span data-ttu-id="4ddbf-140">저장 된 데이터를 검색 하는 것은 유사한 API 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-140">Retrieving the stored data is a similar API call.</span></span> <span data-ttu-id="4ddbf-141">아래 예제에서 *말아 넘기기* 명령은 사이드카 API를 호출 하 여 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-141">In the example below, a *curl* command retrieves the data by calling the Dapr sidecar API:</span></span>

```console
curl http://localhost:3500/v1.0/state/statestore/basket1
```

<span data-ttu-id="4ddbf-142">이 명령은 응답 본문에 저장 된 상태를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-142">The command returns the stored state in the response body:</span></span>

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

<span data-ttu-id="4ddbf-143">다음 섹션에서는 상태 관리 빌딩 블록의 고급 기능을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-143">The following sections explain how to use the more advanced features of the state management building block.</span></span>

### <a name="consistency"></a><span data-ttu-id="4ddbf-144">일관성</span><span class="sxs-lookup"><span data-stu-id="4ddbf-144">Consistency</span></span>

<span data-ttu-id="4ddbf-145">[CAP 정리](https://en.wikipedia.org/wiki/CAP_theorem) 는 상태를 저장 하는 분산 시스템에 적용 되는 원칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-145">The [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem) is a set of principles that apply to distributed systems that store state.</span></span> <span data-ttu-id="4ddbf-146">그림 5-2에서는 CAP 정리의 세 가지 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-146">Figure 5-2 shows the three properties of the CAP theorem.</span></span>

![캡 정리입니다.](media/state-management/cap-theorem.png)

<span data-ttu-id="4ddbf-148">**그림 5-2**.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-148">**Figure 5-2**.</span></span> <span data-ttu-id="4ddbf-149">캡 정리입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-149">The CAP theorem.</span></span>

<span data-ttu-id="4ddbf-150">정리 분산 데이터 시스템이 일관성, 가용성 및 파티션 허용 오차를 절충 하는 것을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-150">The theorem states that distributed data systems offer a trade-off between consistency, availability, and partition tolerance.</span></span> <span data-ttu-id="4ddbf-151">그리고 모든 데이터 저장소에서 다음 *의 세 가지 속성 중 하나만 보장할* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-151">And, that any datastore can only *guarantee two of the three properties*:</span></span>

- <span data-ttu-id="4ddbf-152">*일관성* (**C**).</span><span class="sxs-lookup"><span data-stu-id="4ddbf-152">*Consistency* (**C**).</span></span> <span data-ttu-id="4ddbf-153">모든 복제본이 업데이트 될 때까지 시스템에서 요청을 차단 해야 하는 경우에도 클러스터의 모든 노드는 최신 데이터로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-153">Every node in the cluster responds with the most recent data, even if the system must block the request until all replicas update.</span></span> <span data-ttu-id="4ddbf-154">현재 업데이트 중인 항목에 대해 "일관 된 시스템"을 쿼리하면 모든 복제본이 성공적으로 업데이트 될 때까지 응답이 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-154">If you query a "consistent system" for an item that is currently updating, you won't get a response until all replicas successfully update.</span></span> <span data-ttu-id="4ddbf-155">그러나 항상 최신 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-155">However, you'll always receive the most current data.</span></span>

- <span data-ttu-id="4ddbf-156">*가용성* (**A**).</span><span class="sxs-lookup"><span data-stu-id="4ddbf-156">*Availability* (**A**).</span></span> <span data-ttu-id="4ddbf-157">모든 노드는 응답이 가장 최근 데이터가 아닌 경우에도 즉각적인 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-157">Every node returns an immediate response, even if that response isn't the most recent data.</span></span> <span data-ttu-id="4ddbf-158">업데이트 중인 항목에 대해 "사용 가능한 시스템"을 쿼리하면 서비스에서 제공할 수 있는 가장 좋은 답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-158">If you query an "available system" for an item that is updating, you'll get the best possible answer the service can provide at that moment.</span></span>

- <span data-ttu-id="4ddbf-159">*파티션 허용 오차* (**P**)입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-159">*Partition Tolerance* (**P**).</span></span> <span data-ttu-id="4ddbf-160">복제 된 데이터 노드가 실패 하거나 다른 복제 된 데이터 노드와의 연결이 끊어지는 경우에도 시스템이 계속 작동 하도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-160">Guarantees the system continues to operate even if a replicated data node fails or loses connectivity with other replicated data nodes.</span></span>

<span data-ttu-id="4ddbf-161">배포 응용 프로그램은 **P** 속성을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-161">Distributed applications must handle the **P** property.</span></span> <span data-ttu-id="4ddbf-162">서비스가 네트워크 호출을 통해 서로 통신 하는 경우 네트워크 중단 (**P**)이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-162">As services communicate among each other with network calls, network disruptions (**P**) will occur.</span></span> <span data-ttu-id="4ddbf-163">이러한 점을 염두에 두면 배포 응용 프로그램은 **AP** 또는 **CP** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-163">With that in mind, distributed applications must either be **AP** or **CP**.</span></span>

<span data-ttu-id="4ddbf-164">**AP** 응용 프로그램은 일관성 보다 가용성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-164">**AP** applications choose availability over consistency.</span></span> <span data-ttu-id="4ddbf-165">이 옵션은 **최종 일관성** 전략에 따라 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-165">Dapr supports this choice with its **eventual consistency** strategy.</span></span> <span data-ttu-id="4ddbf-166">여러 복제본에 중복 데이터를 저장 하는 Azure CosmosDB와 같은 기본 데이터 저장소를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-166">Consider an underlying data store, such as Azure CosmosDB, which stores redundant data on multiple replicas.</span></span> <span data-ttu-id="4ddbf-167">최종 일관성을 유지 하면서 상태 저장소는 하나의 복제본에 업데이트를 기록 하 고 클라이언트를 사용 하 여 쓰기 요청을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-167">With eventual consistency, the state store writes the update to one replica and completes the write request with the client.</span></span> <span data-ttu-id="4ddbf-168">이 시간 후에는 저장소에서 해당 복제본을 비동기식으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-168">After this time, the store will asynchronously update its replicas.</span></span> <span data-ttu-id="4ddbf-169">읽기 요청은 최신 업데이트가 아직 수신 되지 않은 복제본을 포함 하 여 모든 복제본의 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-169">Read requests can return data from any of the replicas, including those replicas that haven't yet received the latest update.</span></span>

<span data-ttu-id="4ddbf-170">**CP** 응용 프로그램은 가용성에 대 한 일관성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-170">**CP** applications choose consistency over availability.</span></span> <span data-ttu-id="4ddbf-171">이 옵션은 **강력한 일관성** 전략으로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-171">Dapr supports this choice with its **strong consistency** strategy.</span></span> <span data-ttu-id="4ddbf-172">이 시나리오에서 상태 저장소는 쓰기 요청을 완료 *하기 전에* *모든* 항목 (또는 일부 경우에는 *쿼럼* )을 동기식으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-172">In this scenario, the state store will synchronously update *all* (or, in some cases, a *quorum* of) required replicas *before* completing the write request.</span></span> <span data-ttu-id="4ddbf-173">읽기 작업은 복제본에서 가장 최신 데이터를 일관 되 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-173">Read operations will return the most up-to-date data consistently across replicas.</span></span>

<span data-ttu-id="4ddbf-174">상태 작업의 일관성 수준은 작업에 *일관성 힌트* 를 연결 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-174">The consistency level for a state operation is specified by attaching a *consistency hint* to the operation.</span></span> <span data-ttu-id="4ddbf-175">다음 *말아* 명령은 `Hello=World` 강력한 일관성 힌트를 사용 하 여 상태 저장소에 키/값 쌍을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-175">The following *curl* command writes a `Hello=World` key/value pair to a state store using a strong consistency hint:</span></span>

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
> <span data-ttu-id="4ddbf-176">작업에 연결 된 일관성 힌트를 충족 하는 데는 최대 4 개의 주 저장소 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-176">It is up to the Dapr state store component to fulfill the consistency hint attached to the operation.</span></span> <span data-ttu-id="4ddbf-177">모든 데이터 저장소에서 두 가지 일관성 수준을 모두 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-177">Not all data stores support both consistency levels.</span></span> <span data-ttu-id="4ddbf-178">일관성 힌트가 설정 되지 않은 경우 기본 동작은 **최종** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-178">If no consistency hint is set, the default behavior is **eventual**.</span></span>

### <a name="concurrency"></a><span data-ttu-id="4ddbf-179">동시성</span><span class="sxs-lookup"><span data-stu-id="4ddbf-179">Concurrency</span></span>

<span data-ttu-id="4ddbf-180">다중 사용자 응용 프로그램에서 동시에 여러 사용자가 동일한 데이터를 동시에 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-180">In a multi-user application, there's a chance that multiple users will update the same data concurrently (at the same time).</span></span> <span data-ttu-id="4ddbf-181">6apr는 충돌을 관리 하기 위해 OCC (낙관적 동시성 제어)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-181">Dapr supports optimistic concurrency control (OCC) to manage conflicts.</span></span> <span data-ttu-id="4ddbf-182">OCC는 사용자가 데이터의 서로 다른 부분에서 작업 하기 때문에 업데이트 충돌이 드물게 발생 한다는 가정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-182">OCC is based on an assumption that update conflicts are uncommon because users work on different parts of the data.</span></span> <span data-ttu-id="4ddbf-183">업데이트가 성공 하 고 그렇지 않은 경우 다시 시도 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-183">It's more efficient to assume an update will succeed and retry if it doesn't.</span></span> <span data-ttu-id="4ddbf-184">비관적 잠금을 구현 하는 대안은 장기 실행 잠금으로 인해 성능에 영향을 줄 수 있으므로 데이터 경합이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-184">The alternative, implementing pessimistic locking, can affect performance with long-running locking causing data contention.</span></span>

<span data-ttu-id="4ddbf-185">Etag를 사용 하는 OCC (낙관적 동시성 제어)는 6apr에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-185">Dapr supports optimistic concurrency control (OCC) using ETags.</span></span> <span data-ttu-id="4ddbf-186">ETag는 저장 된 키/값 쌍의 특정 버전과 관련 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-186">An ETag is a value associated with a specific version of a stored key/value pair.</span></span> <span data-ttu-id="4ddbf-187">키/값 쌍이 업데이트 될 때마다 ETag 값도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-187">Each time a key/value pair updates, the ETag value updates as well.</span></span> <span data-ttu-id="4ddbf-188">클라이언트에서 키/값 쌍을 검색 하면 응답에 현재 ETag 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-188">When a client retrieves a key/value pair, the response includes the current ETag value.</span></span> <span data-ttu-id="4ddbf-189">클라이언트는 키/값 쌍을 업데이트 하거나 삭제할 때 해당 ETag 값을 요청 본문으로 다시 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-189">When a client updates or deletes a key/value pair, it must send that ETag value back in the request body.</span></span> <span data-ttu-id="4ddbf-190">다른 클라이언트가 그 동안 데이터를 업데이트 한 경우에는 Etag가 일치 하지 않고 요청이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-190">If another client has updated the data in the meantime, the ETags won't match and the request will fail.</span></span> <span data-ttu-id="4ddbf-191">이 시점에서 클라이언트는 업데이트 된 데이터를 검색 하 고 변경 내용을 다시 적용 한 다음 업데이트를 다시 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-191">At this point, the client must retrieve the updated data, make the change again, and resubmit the update.</span></span> <span data-ttu-id="4ddbf-192">이 전략을 **첫 번째-쓰기-wins** 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-192">This strategy is called **first-write-wins**.</span></span>

<span data-ttu-id="4ddbf-193">또한 6apr는 **마지막 쓰기-wins** 전략을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-193">Dapr also supports a **last-write-wins** strategy.</span></span> <span data-ttu-id="4ddbf-194">이 접근 방식을 사용 하면 클라이언트는 ETag를 쓰기 요청에 연결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-194">With this approach, the client doesn't attach an ETag to the write request.</span></span> <span data-ttu-id="4ddbf-195">상태 저장소 구성 요소는 세션이 진행 되는 동안 기본 값이 변경 된 경우에도 항상 업데이트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-195">The state store component will always allow the update, even if the underlying value has changed during the session.</span></span> <span data-ttu-id="4ddbf-196">마지막-쓰기-wins는 데이터 경합이 낮은 처리량이 높은 쓰기 시나리오에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-196">Last-write-wins is useful for high-throughput write scenarios with low data contention.</span></span> <span data-ttu-id="4ddbf-197">또한 가끔 사용자 업데이트를 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-197">As well, overwriting an occasional user update can be tolerated.</span></span>

### <a name="transactions"></a><span data-ttu-id="4ddbf-198">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4ddbf-198">Transactions</span></span>

<span data-ttu-id="4ddbf-199">D 4 월은 트랜잭션으로 구현 된 단일 작업으로 데이터 저장소에 대 한 *다중 항목 변경 내용을* 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-199">Dapr can write *multi-item changes* to a data store as a single operation implemented as a transaction.</span></span> <span data-ttu-id="4ddbf-200">이 기능은 [ACID](https://en.wikipedia.org/wiki/ACID) 트랜잭션을 지 원하는 데이터 저장소에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-200">This functionality is only available for data stores that support [ACID](https://en.wikipedia.org/wiki/ACID) transactions.</span></span> <span data-ttu-id="4ddbf-201">이 문서를 작성할 당시 이러한 매장에는 Redis, MongoDB, PostgreSQL, SQL Server 및 Azure CosmosDB가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-201">At the time of this writing, these stores include Redis, MongoDB, PostgreSQL, SQL Server, and Azure CosmosDB.</span></span>

<span data-ttu-id="4ddbf-202">아래 예제에서는 다중 항목 작업을 단일 트랜잭션에서 상태 저장소로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-202">In the example below, a multi-item operation is sent to the state store in a single transaction.</span></span> <span data-ttu-id="4ddbf-203">트랜잭션을 커밋하기 위해서는 모든 작업이 성공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-203">All operations must succeed for the transaction to commit.</span></span> <span data-ttu-id="4ddbf-204">하나 이상의 작업이 실패 하면 전체 트랜잭션이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-204">If one or more of the operations fail, the entire transaction rolls back.</span></span>

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

<span data-ttu-id="4ddbf-205">트랜잭션을 지원 하지 않는 데이터 저장소의 경우에도 여러 키를 단일 요청으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-205">For data stores that don't support transactions, multiple keys can still be sent as a single request.</span></span> <span data-ttu-id="4ddbf-206">다음 예에서는 **대량** 쓰기 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-206">The following example shows a **bulk** write operation:</span></span>

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        { "key": "Key1", "value": "Value1" },
        { "key": "Key2", "value": "Value2" }
      ]'
```

<span data-ttu-id="4ddbf-207">대량 작업의 경우에는 각 키/값 쌍 업데이트를 데이터 저장소에 대 한 별도의 요청으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-207">For bulk operations, Dapr will submit each key/value pair update as a separate request to the data store.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="4ddbf-208">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="4ddbf-208">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="4ddbf-209">Dapr .NET SDK는 .NET Core 플랫폼에 대 한 언어별 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-209">The Dapr .NET SDK provides language-specific support for .NET Core platform.</span></span> <span data-ttu-id="4ddbf-210">개발자는 `DaprClient` [3 장에](getting-started.md) 도입 된 클래스를 사용 하 여 데이터를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-210">Developers can use the `DaprClient` class introduced in [chapter 3](getting-started.md) to read and write data.</span></span> <span data-ttu-id="4ddbf-211">다음 예제에서는 메서드를 사용 하 여 `DaprClient.GetStateAsync<TValue>` 상태 저장소에서 데이터를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-211">The following example shows how to use the `DaprClient.GetStateAsync<TValue>` method to read data from a state store.</span></span> <span data-ttu-id="4ddbf-212">메서드에는 저장소 이름, 및 키가 매개 변수로 필요 합니다 `statestore` `AMS` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-212">The method expects the store name, `statestore`, and key, `AMS`, as parameters:</span></span>

```csharp
var weatherForecast = await daprClient.GetStateAsync<WeatherForecast>("statestore", "AMS");
```

<span data-ttu-id="4ddbf-213">상태 저장소에 키에 대 한 데이터가 포함 되어 있지 않으면 `AMS` 결과는가 됩니다 `default(WeatherForecast)` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-213">If the state store contains no data for key `AMS`, the result will be `default(WeatherForecast)`.</span></span>

<span data-ttu-id="4ddbf-214">데이터 저장소에 데이터를 쓰려면 메서드를 사용 합니다 `DaprClient.SaveStateAsync<TValue>` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-214">To write data to the data store, use the `DaprClient.SaveStateAsync<TValue>` method:</span></span>

```csharp
daprClient.SaveStateAsync("statestore", "AMS", weatherForecast);
```

<span data-ttu-id="4ddbf-215">이 예제에서는 ETag 값이 상태 저장소 구성 요소에 전달 되지 않으므로 **마지막-쓰기-wins** 전략을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-215">The example uses the **last-write-wins** strategy as an ETag value isn't passed to the state store component.</span></span> <span data-ttu-id="4ddbf-216">**첫 번째 쓰기-wins** 전략과 함께 occ (낙관적 동시성 제어)를 사용 하려면 먼저 메서드를 사용 하 여 현재 ETag를 검색 합니다 `DaprClient.GetStateAndETagAsync` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-216">To use optimistic concurrency control (OCC) with a **first-write-wins** strategy, first retrieve the current ETag using the `DaprClient.GetStateAndETagAsync` method.</span></span> <span data-ttu-id="4ddbf-217">그런 다음 업데이트 된 값을 작성 하 고 메서드를 사용 하 여 검색 된 ETag를 따라 전달 합니다 `DaprClient.TrySaveStateAsync` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-217">Then write the updated value and pass along the retrieved ETag using the `DaprClient.TrySaveStateAsync` method.</span></span>

```csharp
var (weatherForecast, etag) = await daprClient.GetStateAndETagAsync<WeatherForecast>("statestore", city);

// ... make some changes to the retrieved weather forecast

var result = await daprClient.TrySaveStateAsync("statestore", city, weatherForecast, etag);
```

<span data-ttu-id="4ddbf-218">`DaprClient.TrySaveStateAsync`데이터가 검색 된 후 상태 저장소에서 데이터 및 연결 된 ETag가 변경 되 면 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-218">The `DaprClient.TrySaveStateAsync` method fails when the data (and associated ETag) has been changed in the state store after the data was retrieved.</span></span> <span data-ttu-id="4ddbf-219">메서드는 호출이 성공 했는지 여부를 나타내는 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-219">The method returns a boolean value to indicate whether the call succeeded.</span></span> <span data-ttu-id="4ddbf-220">오류를 처리 하는 전략은 상태 저장소에서 업데이트 된 데이터를 다시 로드 하 고 변경 내용을 다시 적용 한 다음 업데이트를 다시 전송 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-220">A strategy to handle the failure is to simply reload the updated data from the state store, make the change again, and resubmit the update.</span></span>

<span data-ttu-id="4ddbf-221">데이터의 다른 변경 내용에 관계 없이 항상 쓰기가 성공 하 게 하려면 **마지막-쓰기-wins** 전략을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-221">If you always want a write to succeed regardless of other changes to the data, use the **last-write-wins** strategy.</span></span>

<span data-ttu-id="4ddbf-222">SDK는 데이터를 대량으로 검색 하 고, 데이터를 삭제 하 고, 트랜잭션을 실행 하는 다른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-222">The SDK provides other methods to retrieve data in bulk, delete data, and execute transactions.</span></span> <span data-ttu-id="4ddbf-223">자세한 내용은 [Dapr .NET SDK 리포지토리](https://github.com/dapr/dotnet-sdk)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-223">For more information, see the [Dapr .NET SDK repository](https://github.com/dapr/dotnet-sdk).</span></span>

### <a name="aspnet-core-integration"></a><span data-ttu-id="4ddbf-224">ASP.NET Core 통합</span><span class="sxs-lookup"><span data-stu-id="4ddbf-224">ASP.NET Core integration</span></span>

<span data-ttu-id="4ddbf-225">또한 ASP.NET Core는 최신 클라우드 기반 웹 응용 프로그램을 빌드하기 위한 플랫폼 간 프레임 워크인 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-225">Dapr also supports ASP.NET Core, a cross-platform framework for building modern cloud-based web applications.</span></span> <span data-ttu-id="4ddbf-226">Dapr SDK는 상태 관리 기능을 [ASP.NET Core 모델 바인딩](/aspnet/core/mvc/models/model-binding) 기능에 직접 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-226">The Dapr SDK integrates state management capabilities directly into the [ASP.NET Core model binding](/aspnet/core/mvc/models/model-binding) capabilities.</span></span> <span data-ttu-id="4ddbf-227">구성이 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-227">Configuration is simple.</span></span> <span data-ttu-id="4ddbf-228">`IMVCBuilder.AddDapr` `.AddDapr` 다음 예제와 같이 클래스에 확장 메서드를 추가 하 여를 추가 합니다 `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-228">Add the `IMVCBuilder.AddDapr` by appending the `.AddDapr` extension method in your `Startup.cs` class as shown in the next example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers().AddDapr();
}
```

<span data-ttu-id="4ddbf-229">구성 된 후에는 ASP.NET Core 특성을 사용 하 여 키/값 쌍을 컨트롤러 작업에 직접 삽입할 수 있습니다 `FromState` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-229">Once configured, Dapr can inject a key/value pair directly into a controller action using the ASP.NET Core `FromState` attribute.</span></span> <span data-ttu-id="4ddbf-230">개체를 참조 하 `DaprClient` 는 것은 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-230">Referencing the `DaprClient` object is no longer necessary.</span></span> <span data-ttu-id="4ddbf-231">다음 예제에서는 지정 된 도시의 날씨 예보를 반환 하는 Web API를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-231">The next example shows a Web API that returns the weather forecast for a given city:</span></span>

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

<span data-ttu-id="4ddbf-232">이 예에서 컨트롤러는 특성을 사용 하 여 날씨 예측을 로드 합니다 `FromState` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-232">In the example, the controller loads the weather forecast using the `FromState` attribute.</span></span> <span data-ttu-id="4ddbf-233">첫 번째 특성 매개 변수는 상태 저장소 `statestore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-233">The first attribute parameter is the state store, `statestore`.</span></span> <span data-ttu-id="4ddbf-234">두 번째 특성 매개 변수는 `city` 상태 키를 가져올 [경로 템플릿](/aspnet/core/mvc/controllers/routing#route-templates) 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-234">The second attribute parameter, `city`, is the name of the [route template](/aspnet/core/mvc/controllers/routing#route-templates) variable to get the state key.</span></span> <span data-ttu-id="4ddbf-235">두 번째 매개 변수를 생략 하면 바인딩된 메서드 매개 변수 ()의 이름이 `forecast` 경로 템플릿 변수를 조회 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-235">If you omit the second parameter, the name of the bound method parameter (`forecast`) is used to look up the route template variable.</span></span>

<span data-ttu-id="4ddbf-236">클래스에는 `StateEntry` `StoreName` ,, `Key` `Value` 및의 단일 키/값 쌍에 대해 검색 된 모든 정보에 대 한 속성이 포함 `ETag` 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-236">The `StateEntry` class contains properties for all the information that is retrieved for a single key/value pair: `StoreName`, `Key`, `Value`, and `ETag`.</span></span> <span data-ttu-id="4ddbf-237">ETag는 OCC (낙관적 동시성 제어) 전략을 구현 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-237">The ETag is useful for implementing optimistic concurrency control (OCC) strategy.</span></span> <span data-ttu-id="4ddbf-238">또한 클래스는 인스턴스를 요구 하지 않고 검색 된 키/값 데이터를 삭제 하거나 업데이트 하는 메서드를 제공 합니다 `DaprClient` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-238">The class also provides methods to delete or update retrieved key/value data without requiring a `DaprClient` instance.</span></span> <span data-ttu-id="4ddbf-239">다음 예제에서 `TrySaveAsync` 메서드는 OCC를 사용 하 여 검색 된 일기 예보를 업데이트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-239">In the next example, the `TrySaveAsync` method is used to update the retrieved weather forecast using OCC.</span></span>

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

## <a name="state-store-components"></a><span data-ttu-id="4ddbf-240">상태 저장소 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4ddbf-240">State store components</span></span>

<span data-ttu-id="4ddbf-241">이 문서를 작성할 당시에는 다음 트랜잭션 상태 저장소에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-241">At the time of this writing, Dapr provides support for the following transactional state stores:</span></span>

- <span data-ttu-id="4ddbf-242">Azure CosmosDB</span><span class="sxs-lookup"><span data-stu-id="4ddbf-242">Azure CosmosDB</span></span>
- <span data-ttu-id="4ddbf-243">Azure SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ddbf-243">Azure SQL Server</span></span>
- <span data-ttu-id="4ddbf-244">MongoDB</span><span class="sxs-lookup"><span data-stu-id="4ddbf-244">MongoDB</span></span>
- <span data-ttu-id="4ddbf-245">PostgreSQL</span><span class="sxs-lookup"><span data-stu-id="4ddbf-245">PostgreSQL</span></span>
- <span data-ttu-id="4ddbf-246">Redis</span><span class="sxs-lookup"><span data-stu-id="4ddbf-246">Redis</span></span>

<span data-ttu-id="4ddbf-247">또한 다음은 트랜잭션 기능이 아니라 CRUD 작업을 지 원하는 상태 저장소에 대 한 지원을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-247">Dapr also includes support for state stores that support CRUD operations, but not transactional capabilities:</span></span>

- <span data-ttu-id="4ddbf-248">Aerospike</span><span class="sxs-lookup"><span data-stu-id="4ddbf-248">Aerospike</span></span>
- <span data-ttu-id="4ddbf-249">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="4ddbf-249">Azure Blob Storage</span></span>
- <span data-ttu-id="4ddbf-250">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="4ddbf-250">Azure Table Storage</span></span>
- <span data-ttu-id="4ddbf-251">Cassandra</span><span class="sxs-lookup"><span data-stu-id="4ddbf-251">Cassandra</span></span>
- <span data-ttu-id="4ddbf-252">Cloudstate</span><span class="sxs-lookup"><span data-stu-id="4ddbf-252">Cloudstate</span></span>
- <span data-ttu-id="4ddbf-253">Couchbase</span><span class="sxs-lookup"><span data-stu-id="4ddbf-253">Couchbase</span></span>
- <span data-ttu-id="4ddbf-254">etcd</span><span class="sxs-lookup"><span data-stu-id="4ddbf-254">etcd</span></span>
- <span data-ttu-id="4ddbf-255">Google Cloud Firestore</span><span class="sxs-lookup"><span data-stu-id="4ddbf-255">Google Cloud Firestore</span></span>
- <span data-ttu-id="4ddbf-256">Hashicorp Consul</span><span class="sxs-lookup"><span data-stu-id="4ddbf-256">Hashicorp Consul</span></span>
- <span data-ttu-id="4ddbf-257">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="4ddbf-257">Hazelcast</span></span>
- <span data-ttu-id="4ddbf-258">Memcached</span><span class="sxs-lookup"><span data-stu-id="4ddbf-258">Memcached</span></span>
- <span data-ttu-id="4ddbf-259">Zookeeper</span><span class="sxs-lookup"><span data-stu-id="4ddbf-259">Zookeeper</span></span>

### <a name="configuration"></a><span data-ttu-id="4ddbf-260">구성</span><span class="sxs-lookup"><span data-stu-id="4ddbf-260">Configuration</span></span>

<span data-ttu-id="4ddbf-261">자체 호스팅 로컬 개발을 위해 초기화 된 경우 Redis는 기본 상태 저장소로 서를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-261">When initialized for local, self-hosted development, Dapr registers Redis as the default state store.</span></span> <span data-ttu-id="4ddbf-262">기본 상태 저장소 구성의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-262">Here's an example of the default state store configuration.</span></span> <span data-ttu-id="4ddbf-263">기본 이름인를 적어둡니다 `statestore` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-263">Note the default name, `statestore`:</span></span>

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
 > <span data-ttu-id="4ddbf-264">여러 상태 저장소를 각각 다른 이름으로 단일 응용 프로그램에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-264">Many state stores can be registered to a single application each with a different name.</span></span>

<span data-ttu-id="4ddbf-265">Redis 상태 저장소에는 `redisHost` `redisPassword` Redis 인스턴스에 연결 하는 데 필요한 메타 데이터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-265">The Redis state store requires `redisHost` and `redisPassword` metadata to connect to the Redis instance.</span></span> <span data-ttu-id="4ddbf-266">위의 예제에서 Redis 암호 (기본적으로 빈 문자열)는 일반 문자열로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-266">In the example above, the Redis password (which is an empty string by default) is stored as a plain string.</span></span> <span data-ttu-id="4ddbf-267">가장 좋은 방법은 일반 텍스트 문자열을 피하고 항상 비밀 참조를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-267">The best practice is to avoid clear-text strings and always use secret references.</span></span> <span data-ttu-id="4ddbf-268">비밀 관리에 대해 자세히 알아보려면 [10 장](secrets.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-268">To learn more about secret management, see [chapter 10](secrets.md).</span></span>

<span data-ttu-id="4ddbf-269">다른 메타 데이터 필드인는 `actorStateStore` 상태 저장소를 행위자 빌딩 블록에서 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-269">The other metadata field, `actorStateStore`, indicates whether the state store can be consumed by the actors building block.</span></span>

### <a name="key-prefix-strategies"></a><span data-ttu-id="4ddbf-270">키 접두사 전략</span><span class="sxs-lookup"><span data-stu-id="4ddbf-270">Key prefix strategies</span></span>

<span data-ttu-id="4ddbf-271">상태 저장소 구성 요소를 사용 하면 다른 전략을 사용 하 여 기본 저장소에 키/값 쌍을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-271">State store components enable different strategies to store key/value pairs in the underlying store.</span></span> <span data-ttu-id="4ddbf-272">고객이 구매 하고자 하는 품목을 저장 하는 시장 바구니 서비스의 이전 예를 회수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-272">Recall the earlier example of a shopping basket service storing items a customer wishes to purchase:</span></span>

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

<span data-ttu-id="4ddbf-273">Redis 콘솔 도구를 사용 하 여 Redis 캐시 내에서 Redis state store 구성 요소가 데이터를 유지 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-273">Using the Redis Console tool, look inside the Redis cache to see how the Redis state store component persisted the data:</span></span>

```
127.0.0.1:6379> KEYS *
1) "basketservice||basket1"

127.0.0.1:6379> HGETALL basketservice||basket1
1) "data"
2) "{\"items\":[{\"itemId\":\"DaprHoodie\",\"quantity\":1}],\"customerId\":1}"
3) "version"
4) "1"
```

<span data-ttu-id="4ddbf-274">출력은 데이터의 전체 Redis **키** 를로 표시 합니다 `basketservice||basket1` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-274">The output shows the full Redis **key** for the data as `basketservice||basket1`.</span></span> <span data-ttu-id="4ddbf-275">기본적으로, 644는 `application id` `basketservice` 키에 대 한 접두사로 ()의를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-275">By default, Dapr uses the `application id` of the Dapr instance (`basketservice`) as a prefix for the key.</span></span> <span data-ttu-id="4ddbf-276">이 명명 규칙을 사용 하면 여러 개의 Capr 인스턴스가 키 이름 충돌 없이 동일한 데이터 저장소를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-276">This naming convention enables multiple Dapr instances to share the same data store without key name collisions.</span></span> <span data-ttu-id="4ddbf-277">개발자의 경우, 응용 프로그램을 실행 하는 경우에는 항상 동일한 것을 지정 해야 합니다 `application id` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-277">For the developer, it's critical always to specify the same `application id` when running the application with Dapr.</span></span> <span data-ttu-id="4ddbf-278">생략 하는 경우에는 고유 응용 프로그램 ID를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-278">If omitted, Dapr will generate a unique application ID.</span></span> <span data-ttu-id="4ddbf-279">이 `application id` 변경 되 면 응용 프로그램은 이전 키 접두사를 사용 하 여 저장 된 상태에 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-279">If the `application id` changes, the application can no longer access the state stored with the previous key prefix.</span></span>

<span data-ttu-id="4ddbf-280">즉, 상태 저장소 구성 요소 파일의 메타 데이터 필드에서 키 접두사에 대 한 *상수 값* 을 구성할 수 `keyPrefix` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-280">That said, it's possible to configure a *constant value* for the key prefix in the `keyPrefix` metadata field in the state store component file.</span></span> <span data-ttu-id="4ddbf-281">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-281">Consider the following example:</span></span>

```yaml
spec:
  metadata:
  - name: keyPrefix
  - value: MyPrefix
```

<span data-ttu-id="4ddbf-282">상수 키 접두사를 사용 하면 여러 개의 4Apr 응용 프로그램에서 상태 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-282">A constant key prefix enables the state store to be accessed across multiple Dapr applications.</span></span> <span data-ttu-id="4ddbf-283">자세히,를로 설정 하면 `keyPrefix` `none` 접두사가 완전히 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-283">What's more, setting the `keyPrefix` to `none` omits the prefix completely.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="4ddbf-284">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="4ddbf-284">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="4ddbf-285">이 책에는 이라는 참조 응용 프로그램이 포함 되어 있습니다 `eShopOnDapr` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-285">This book includes a reference application entitled `eShopOnDapr`.</span></span> <span data-ttu-id="4ddbf-286">이전 Microsoft 마이크로 서비스 참조 응용 프로그램에서 모델링 `eShopOnContainers` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-286">It's modeled from an earlier Microsoft microservices reference application, `eShopOnContainers`.</span></span>

<span data-ttu-id="4ddbf-287">원래 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 아키텍처는 인터페이스를 사용 `IBasketRepository` 하 여 바구니 서비스의 데이터를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-287">The original [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) architecture used an `IBasketRepository` interface to read and write data for the basket service.</span></span> <span data-ttu-id="4ddbf-288">`RedisBasketRepository`클래스는 Redis를 기본 데이터 저장소로 사용 하 여 구현을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-288">The `RedisBasketRepository` class provided the implementation using Redis as the underlying data store:</span></span>

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

<span data-ttu-id="4ddbf-289">이 코드는 타사 NuGet 패키지를 사용 합니다 `StackExchange.Redis` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-289">This code uses the third-party `StackExchange.Redis` NuGet package.</span></span> <span data-ttu-id="4ddbf-290">다음 단계는 지정 된 고객에 대 한 장바구니를 로드 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-290">The following steps are required to load the shopping basket for a given customer:</span></span>

1. <span data-ttu-id="4ddbf-291">`ConnectionMultiplexer`생성자에를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-291">Inject a `ConnectionMultiplexer` into the constructor.</span></span> <span data-ttu-id="4ddbf-292">는 `ConnectionMultiplexer` 파일의 종속성 주입 프레임 워크에 등록 됩니다 `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-292">The `ConnectionMultiplexer` is registered with the dependency injection framework in the `Startup.cs` file:</span></span>

   ```csharp
   services.AddSingleton<ConnectionMultiplexer>(sp =>
   {
       var settings = sp.GetRequiredService<IOptions<BasketSettings>>().Value;
       var configuration = ConfigurationOptions.Parse(settings.ConnectionString, true);
       configuration.ResolveDns = true;
       return ConnectionMultiplexer.Connect(configuration);
   });
   ```

1. <span data-ttu-id="4ddbf-293">를 사용 `ConnectionMultiplexer` 하 여 `IDatabase` 각 소비 클래스에서 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-293">Use the `ConnectionMultiplexer` to create an `IDatabase` instance in each consuming class.</span></span>

1. <span data-ttu-id="4ddbf-294">`IDatabase`지정 된를 키로 사용 하 여 Redis StringGet 호출을 실행 하려면 인스턴스를 사용 합니다 `customerId` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-294">Use the `IDatabase` instance to execute a Redis StringGet call using the given `customerId` as the key.</span></span>

1. <span data-ttu-id="4ddbf-295">데이터가 Redis에서 로드 되는지 확인 합니다. 그렇지 않으면를 반환 `null` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-295">Check if data is loaded from Redis; if not, return `null`.</span></span>

1. <span data-ttu-id="4ddbf-296">Redis에서 개체로 데이터를 Deserialize 하 `CustomerBasket` 고 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-296">Deserialize the data from Redis to a `CustomerBasket` object and return the result.</span></span>

<span data-ttu-id="4ddbf-297">업데이트 된 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) 참조 응용 프로그램에서 새 `DaprBasketRepository` 클래스는 클래스를 대체 합니다 `RedisBasketRepository` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-297">In the updated [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) reference application, a new `DaprBasketRepository` class replaces the `RedisBasketRepository` class:</span></span>

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

<span data-ttu-id="4ddbf-298">업데이트 된 코드는 Dapr .NET SDK를 사용 하 여 상태 관리 구성 블록을 통해 데이터를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-298">The updated code uses the Dapr .NET SDK to read and write data using the state management building block.</span></span> <span data-ttu-id="4ddbf-299">고객에 대 한 바구니를 로드 하는 새로운 단계가 크게 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-299">The new steps to load the basket for a customer are dramatically simplified:</span></span>

1. <span data-ttu-id="4ddbf-300">`DaprClient`생성자에를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-300">Inject a `DaprClient` into the constructor.</span></span> <span data-ttu-id="4ddbf-301">는 `DaprClient` 파일의 종속성 주입 프레임 워크에 등록 됩니다 `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-301">The `DaprClient` is registered with the dependency injection framework in the `Startup.cs` file.</span></span>
1. <span data-ttu-id="4ddbf-302">메서드를 사용 `DaprClient.GetStateAsync` 하 여 구성 된 상태 저장소에서 고객의 쇼핑 바구니 항목을 로드 하 고 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-302">Use the `DaprClient.GetStateAsync` method to load the customer's shopping basket items from the configured state store and return the result.</span></span>

<span data-ttu-id="4ddbf-303">업데이트 된 구현은 여전히 Redis를 기본 데이터 저장소로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-303">The updated implementation still uses Redis as the underlying data store.</span></span> <span data-ttu-id="4ddbf-304">그러나 `StackExchange.Redis` 응용 프로그램에서 참조 및 복잡성을 추상화 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4ddbf-304">But, Dapr abstracts the `StackExchange.Redis` references and complexity from the application.</span></span> <span data-ttu-id="4ddbf-305">모든 필수 구성 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-305">A Dapr configuration file is all that's needed:</span></span>

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

<span data-ttu-id="4ddbf-306">또한 기본 데이터 저장소를 변경 하는 것이 더 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-306">The Dapr implementation also simplifies changing the underlying data store.</span></span> <span data-ttu-id="4ddbf-307">예를 들어 Azure Table Storage로 전환 하려면 구성 파일의 내용만 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-307">For example, switching to Azure Table Storage requires only changing the contents of the configuration file.</span></span> <span data-ttu-id="4ddbf-308">코드를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-308">No code changes are necessary.</span></span>

## <a name="summary"></a><span data-ttu-id="4ddbf-309">요약</span><span class="sxs-lookup"><span data-stu-id="4ddbf-309">Summary</span></span>

<span data-ttu-id="4ddbf-310">6Apr 상태 관리 빌딩 블록은 다양 한 데이터 저장소에 키/값 데이터를 저장 하기 위한 API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-310">The Dapr state management building block offers an API for storing key/value data across various data stores.</span></span> <span data-ttu-id="4ddbf-311">API는 다음에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-311">The API provides support for:</span></span>

- <span data-ttu-id="4ddbf-312">대량 작업</span><span class="sxs-lookup"><span data-stu-id="4ddbf-312">Bulk operations</span></span>
- <span data-ttu-id="4ddbf-313">강력 하 고 결과적 일관성</span><span class="sxs-lookup"><span data-stu-id="4ddbf-313">Strong and eventual consistency</span></span>
- <span data-ttu-id="4ddbf-314">낙관적 동시성 제어</span><span class="sxs-lookup"><span data-stu-id="4ddbf-314">Optimistic concurrency control</span></span>
- <span data-ttu-id="4ddbf-315">다중 항목 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4ddbf-315">Multi-item transactions</span></span>

<span data-ttu-id="4ddbf-316">.NET SDK는 .NET Core 및 ASP.NET Core에 대 한 언어별 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-316">The .NET SDK provides language-specific support for .NET Core and ASP.NET Core.</span></span> <span data-ttu-id="4ddbf-317">모델 바인딩 통합은 ASP.NET Core 컨트롤러 동작 메서드에서의 액세스 및 업데이트 상태를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-317">Model binding integration simplifies accessing and updating state from ASP.NET Core controller action methods.</span></span>

<span data-ttu-id="4ddbf-318">EShopOnDapr reference 응용 프로그램에서 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-318">In the eShopOnDapr reference application, the benefits to moving to Dapr state management are clear:</span></span>

1. <span data-ttu-id="4ddbf-319">새 구현에서는 코드 줄 수가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-319">The new implementation uses fewer lines of code.</span></span>
1. <span data-ttu-id="4ddbf-320">타사 API의 복잡성을 추상화 합니다 `StackExchange.Redis` .</span><span class="sxs-lookup"><span data-stu-id="4ddbf-320">It abstracts away the complexity of the third-party `StackExchange.Redis` API.</span></span>
1. <span data-ttu-id="4ddbf-321">기본 Redis cache를 다른 유형의 데이터 저장소로 바꾸려면 상태 저장소 구성 파일을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddbf-321">Replacing the underlying Redis cache with a different type of data store now only requires changes to the state store configuration file.</span></span>

### <a name="references"></a><span data-ttu-id="4ddbf-322">참조</span><span class="sxs-lookup"><span data-stu-id="4ddbf-322">References</span></span>

- [<span data-ttu-id="4ddbf-323">4 월 지원 상태 저장소</span><span class="sxs-lookup"><span data-stu-id="4ddbf-323">Dapr supported state stores</span></span>](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/)

> [!div class="step-by-step"]
> <span data-ttu-id="4ddbf-324">[이전](reference-application.md)
> [다음](service-invocation.md)</span><span class="sxs-lookup"><span data-stu-id="4ddbf-324">[Previous](reference-application.md)
[Next](service-invocation.md)</span></span>
