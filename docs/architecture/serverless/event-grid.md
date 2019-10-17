---
title: Azure Event Grid 서버 리스 앱
description: Azure Event Grid는 이벤트 당 종 량 제 모델을 통해 안정적으로 이벤트를 전달 하 고 라우팅할 수 있는 서버 리스 솔루션입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3c577139c12567e762aabd58c9dc29457fa37aa1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522721"
---
# <a name="event-grid"></a><span data-ttu-id="fecb5-103">Event Grid</span><span class="sxs-lookup"><span data-stu-id="fecb5-103">Event Grid</span></span>

<span data-ttu-id="fecb5-104">[Azure Event Grid](/azure/event-grid/overview) 는 이벤트 기반 응용 프로그램에 대 한 서버 리스 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="fecb5-105">모든 원본에서 Event Grid에 게시 하 고 모든 플랫폼에서 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="fecb5-106">또한 Event Grid는 응용 프로그램과의 통합을 간소화 하기 위해 Azure 리소스의 이벤트를 기본적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="fecb5-107">예를 들어 blob storage 이벤트를 구독 하 여 파일이 업로드 될 때 앱에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="fecb5-108">그러면 응용 프로그램은 다른 클라우드 또는 온-프레미스 응용 프로그램에서 사용 하는 사용자 지정 event grid 메시지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="fecb5-109">Event Grid은 대규모 확장을 안정적으로 처리할 수 있도록 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="fecb5-110">필요한 인프라를 설정 하는 오버 헤드 없이 메시지를 게시 하 고 구독할 수 있는 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![Event Grid 로고](./media/event-grid-logo.png)

<span data-ttu-id="fecb5-112">Event grid의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-112">The major features of event grid include:</span></span>

- <span data-ttu-id="fecb5-113">완전히 관리 되는 이벤트 라우팅입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-113">Fully managed event routing.</span></span>
- <span data-ttu-id="fecb5-114">대규모로 거의 실시간으로 이벤트를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-114">Near real-time event delivery at scale.</span></span>
- <span data-ttu-id="fecb5-115">Azure 내부 및 외부 모두에서 광범위 한 범위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="fecb5-116">시나리오</span><span class="sxs-lookup"><span data-stu-id="fecb5-116">Scenarios</span></span>

<span data-ttu-id="fecb5-117">Event Grid는 여러 가지 시나리오를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="fecb5-118">이 섹션에서는 가장 일반적인 세 가지 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="fecb5-119">Ops 자동화</span><span class="sxs-lookup"><span data-stu-id="fecb5-119">Ops automation</span></span>

![Ops 자동화](./media/ops-automation.png)

<span data-ttu-id="fecb5-121">Event Grid는 인프라가 프로 비전 될 때 [Azure Automation](https://docs.microsoft.com/azure/automation) 에 게 알려 자동화를 가속화 하 고 정책 적용을 간소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](https://docs.microsoft.com/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="fecb5-122">응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="fecb5-122">Application integration</span></span>

![응용 프로그램 통합](./media/app-integration.png)

<span data-ttu-id="fecb5-124">Event Grid를 사용 하 여 앱을 다른 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="fecb5-125">표준 HTTP 프로토콜을 사용 하는 경우에도 레거시 앱을 쉽게 수정 하 여 Event Grid 메시지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="fecb5-126">웹 후크는 다른 서비스 및 플랫폼에서 Event Grid 메시지를 사용 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="fecb5-127">서버 리스 앱</span><span class="sxs-lookup"><span data-stu-id="fecb5-127">Serverless apps</span></span>

![서버 리스 앱](./media/serverless-apps.png)

<span data-ttu-id="fecb5-129">Event Grid Azure Functions, Logic Apps 또는 사용자 지정 코드를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="fecb5-130">Event Grid를 사용할 경우의 주요 혜택은 이벤트 발생 시 *푸시* 메커니즘을 사용 하 여 메시지를 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="fecb5-131">밀어넣기 아키텍처는 더 적게 사용 되는 리소스를 사용 하며 *폴링* 메커니즘 보다 효율적으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="fecb5-132">폴링은 정기적으로 업데이트를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="fecb5-133">Event Grid 및 기타 Azure 메시징 서비스</span><span class="sxs-lookup"><span data-stu-id="fecb5-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="fecb5-134">Azure는 [Event Hubs](https://docs.microsoft.com/azure/event-hubs) 및 [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)를 비롯 한 여러 메시징 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-134">Azure provides several messaging services, including [Event Hubs](https://docs.microsoft.com/azure/event-hubs) and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging).</span></span> <span data-ttu-id="fecb5-135">각는 특정 사용 사례 집합을 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="fecb5-136">다음 다이어그램에서는 서비스 간의 차이점에 대 한 개략적인 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure 메시징 비교](./media/azure-messaging-services.png)

<span data-ttu-id="fecb5-138">자세히 비교 하려면 [메시징 서비스 비교](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fecb5-138">For a more in-depth comparison, see [Compare messaging services](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="fecb5-139">성능 목표</span><span class="sxs-lookup"><span data-stu-id="fecb5-139">Performance targets</span></span>

<span data-ttu-id="fecb5-140">Event Grid 사용 하 여 다음과 같은 성능 보장을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

- <span data-ttu-id="fecb5-141">99 번째 백분위 수에서 종단 간 대기 시간을 초이 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
- <span data-ttu-id="fecb5-142">99.99% 가용성.</span><span class="sxs-lookup"><span data-stu-id="fecb5-142">99.99% availability.</span></span>
- <span data-ttu-id="fecb5-143">지역별 초당 1000만 이벤트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-143">10 million events per second per region.</span></span>
- <span data-ttu-id="fecb5-144">1억 지역 당 구독.</span><span class="sxs-lookup"><span data-stu-id="fecb5-144">100 million subscriptions per region.</span></span>
- <span data-ttu-id="fecb5-145">50-ms 게시자 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-145">50-ms publisher latency.</span></span>
- <span data-ttu-id="fecb5-146">1 일의 보장 된 배달에 대해 지 수 백오프를 사용 하 여 24 시간을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
- <span data-ttu-id="fecb5-147">투명 한 지역 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="fecb5-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="fecb5-148">Event Grid 스키마</span><span class="sxs-lookup"><span data-stu-id="fecb5-148">Event Grid schema</span></span>

<span data-ttu-id="fecb5-149">Event Grid 표준 스키마를 사용 하 여 사용자 지정 이벤트를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="fecb5-150">스키마는 사용자 지정 데이터 요소를 래핑하는 봉투 (envelope)와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="fecb5-151">메시지 Event Grid 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-151">Here is an example Event Grid message:</span></span>

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

<span data-ttu-id="fecb5-152">메시지에 대 한 모든 내용은 `data` 속성을 제외 하 고 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="fecb5-153">메시지를 검사 하 고 `eventType` 및 `dataVersion`을 사용 하 여 페이로드의 사용자 지정 부분을 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="fecb5-154">: Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="fecb5-154">Azure resources</span></span>

<span data-ttu-id="fecb5-155">Event Grid를 사용할 경우의 주요 혜택은 Azure에서 자동으로 생성 되는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="fecb5-156">Azure에서 리소스는 다양 한 이벤트를 구독할 수 있는 *토픽* 에 자동으로 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="fecb5-157">다음 표에서는 자동으로 사용할 수 있는 리소스 유형, 메시지 유형 및 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="fecb5-158">Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="fecb5-158">Azure resource</span></span> | <span data-ttu-id="fecb5-159">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="fecb5-159">Event type</span></span> | <span data-ttu-id="fecb5-160">설명</span><span class="sxs-lookup"><span data-stu-id="fecb5-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="fecb5-161">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="fecb5-161">Azure subscription</span></span> | <span data-ttu-id="fecb5-162">ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="fecb5-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="fecb5-163">리소스 만들기 또는 업데이트 작업이 성공 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="fecb5-164">Microsoft .Resources. ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="fecb5-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="fecb5-165">리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="fecb5-166">Microsoft.resources.resourcewritecancel</span><span class="sxs-lookup"><span data-stu-id="fecb5-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="fecb5-167">리소스 만들기 또는 업데이트 작업이 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="fecb5-168">Microsoft.resources.resourcedeletesuccess</span><span class="sxs-lookup"><span data-stu-id="fecb5-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="fecb5-169">리소스 삭제 작업이 성공 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="fecb5-170">Microsoft .Resources. Resourcefailure</span><span class="sxs-lookup"><span data-stu-id="fecb5-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="fecb5-171">리소스 삭제 작업이 실패 하는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="fecb5-172">Microsoft.resources.resourcedeletecancel</span><span class="sxs-lookup"><span data-stu-id="fecb5-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="fecb5-173">리소스 삭제 작업이 취소 되 면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="fecb5-174">이 이벤트는 템플릿 배포가 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="fecb5-175">Blob Storage</span><span class="sxs-lookup"><span data-stu-id="fecb5-175">Blob storage</span></span> | <span data-ttu-id="fecb5-176">Microsoft. 저장소를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="fecb5-177">Blob을 만들 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="fecb5-178">Microsoft. 저장소. BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="fecb5-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="fecb5-179">Blob이 삭제 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="fecb5-180">Event hubs</span><span class="sxs-lookup"><span data-stu-id="fecb5-180">Event hubs</span></span> | <span data-ttu-id="fecb5-181">CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="fecb5-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="fecb5-182">캡처 파일을 만들 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="fecb5-183">IoT Hub</span><span class="sxs-lookup"><span data-stu-id="fecb5-183">IoT Hub</span></span> | <span data-ttu-id="fecb5-184">DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="fecb5-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="fecb5-185">장치가 IoT hub에 등록 될 때 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="fecb5-186">Microsoft. 장치를 삭제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="fecb5-187">IoT hub에서 장치를 삭제할 때 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="fecb5-188">리소스 그룹</span><span class="sxs-lookup"><span data-stu-id="fecb5-188">Resource groups</span></span> | <span data-ttu-id="fecb5-189">ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="fecb5-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="fecb5-190">리소스 만들기 또는 업데이트 작업이 성공 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="fecb5-191">Microsoft .Resources. ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="fecb5-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="fecb5-192">리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="fecb5-193">Microsoft.resources.resourcewritecancel</span><span class="sxs-lookup"><span data-stu-id="fecb5-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="fecb5-194">리소스 만들기 또는 업데이트 작업이 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="fecb5-195">Microsoft.resources.resourcedeletesuccess</span><span class="sxs-lookup"><span data-stu-id="fecb5-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="fecb5-196">리소스 삭제 작업이 성공 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="fecb5-197">Microsoft .Resources. Resourcefailure</span><span class="sxs-lookup"><span data-stu-id="fecb5-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="fecb5-198">리소스 삭제 작업이 실패 하는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="fecb5-199">Microsoft.resources.resourcedeletecancel</span><span class="sxs-lookup"><span data-stu-id="fecb5-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="fecb5-200">리소스 삭제 작업이 취소 되 면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="fecb5-201">이 이벤트는 템플릿 배포가 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="fecb5-202">자세한 내용은 [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fecb5-202">For more information, see [Azure Event Grid event schema](https://docs.microsoft.com/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="fecb5-203">온-프레미스에서 실행 되는 응용 프로그램을 비롯 한 모든 종류의 응용 프로그램에서 Event Grid에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="fecb5-204">결론</span><span class="sxs-lookup"><span data-stu-id="fecb5-204">Conclusion</span></span>

<span data-ttu-id="fecb5-205">이 장에서는 Azure Functions, Logic Apps 및 Event Grid으로 구성 된 Azure 서버를 사용 하지 않는 플랫폼에 대해 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="fecb5-206">이러한 리소스를 사용 하 여 완전히 서버를 사용 하지 않는 앱 아키텍처를 빌드하거나 다른 클라우드 리소스 및 온-프레미스 서버와 상호 작용 하는 하이브리드 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="fecb5-207">서버를 사용 하지 않는 데이터 플랫폼 (예: [AZURE SQL](https://docs.microsoft.com/azure/sql-database) 또는 [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction))과 결합 하 여 완전히 관리 되는 클라우드 네이티브 응용 프로그램을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-207">Combined with a serverless data platform such as [Azure SQL](https://docs.microsoft.com/azure/sql-database) or [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="fecb5-208">권장 리소스</span><span class="sxs-lookup"><span data-stu-id="fecb5-208">Recommended resources</span></span>

- [<span data-ttu-id="fecb5-209">App service 계획</span><span class="sxs-lookup"><span data-stu-id="fecb5-209">App service plans</span></span>](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [<span data-ttu-id="fecb5-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="fecb5-210">Application Insights</span></span>](https://docs.microsoft.com/azure/application-insights)
- [<span data-ttu-id="fecb5-211">Application Insights 분석</span><span class="sxs-lookup"><span data-stu-id="fecb5-211">Application Insights Analytics</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [<span data-ttu-id="fecb5-212">Azure: 서버 리스를 사용 하 여 앱을 클라우드로 가져오기 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="fecb5-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
- [<span data-ttu-id="fecb5-213">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="fecb5-213">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
- [<span data-ttu-id="fecb5-214">Azure Event Grid 이벤트 스키마</span><span class="sxs-lookup"><span data-stu-id="fecb5-214">Azure Event Grid event schema</span></span>](https://docs.microsoft.com/azure/event-grid/event-schema)
- [<span data-ttu-id="fecb5-215">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fecb5-215">Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs)
- [<span data-ttu-id="fecb5-216">Azure Functions 설명서</span><span class="sxs-lookup"><span data-stu-id="fecb5-216">Azure Functions documentation</span></span>](https://docs.microsoft.com/azure/azure-functions)
- [<span data-ttu-id="fecb5-217">Azure Functions 트리거 및 바인딩 개념</span><span class="sxs-lookup"><span data-stu-id="fecb5-217">Azure Functions triggers and bindings concepts</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [<span data-ttu-id="fecb5-218">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="fecb5-218">Azure Logic Apps</span></span>](https://docs.microsoft.com/azure/logic-apps)
- [<span data-ttu-id="fecb5-219">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="fecb5-219">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging)
- [<span data-ttu-id="fecb5-220">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="fecb5-220">Azure Table Storage</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [<span data-ttu-id="fecb5-221">1. x 및 2.x 함수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-221">Compare functions 1.x and 2.x</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-versions)
- [<span data-ttu-id="fecb5-222">Azure 온-프레미스 데이터 게이트웨이를 사용 하 여 온-프레미스 데이터 원본에 연결</span><span class="sxs-lookup"><span data-stu-id="fecb5-222">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [<span data-ttu-id="fecb5-223">Azure Portal에서 첫 번째 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fecb5-223">Create your first function in the Azure portal</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [<span data-ttu-id="fecb5-224">Azure CLI를 사용 하 여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="fecb5-224">Create your first function using the Azure CLI</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [<span data-ttu-id="fecb5-225">Visual Studio를 사용 하 여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="fecb5-225">Create your first function using Visual Studio</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [<span data-ttu-id="fecb5-226">함수 지원 언어</span><span class="sxs-lookup"><span data-stu-id="fecb5-226">Functions supported languages</span></span>](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [<span data-ttu-id="fecb5-227">모니터 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="fecb5-227">Monitor Azure Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
- [<span data-ttu-id="fecb5-228">Azure Functions 프록시 작업</span><span class="sxs-lookup"><span data-stu-id="fecb5-228">Work with Azure Functions Proxies</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
><span data-ttu-id="fecb5-229">[이전](logic-apps.md)
>[다음](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="fecb5-229">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
