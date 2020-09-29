---
title: Azure Event Grid - 서버리스 앱
description: Azure Event Grid는 안정적으로 이벤트를 전달하고 이벤트별 요금 모델을 통해 대규모로 라우팅할 수 있는 서버리스 솔루션입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 30937bafd8069eb4508dce18351964103421373a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171886"
---
# <a name="event-grid"></a><span data-ttu-id="7cbcc-103">Event Grid</span><span class="sxs-lookup"><span data-stu-id="7cbcc-103">Event Grid</span></span>

<span data-ttu-id="7cbcc-104">[Azure Event Grid](/azure/event-grid/overview)는 이벤트 기반 애플리케이션을 위한 서버리스 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="7cbcc-105">모든 원본에서 Event Grid에 게시하고 모든 플랫폼에서 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="7cbcc-106">또한 Event Grid는 애플리케이션과의 통합을 간소화하기 위해 Azure 리소스의 이벤트를 기본적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="7cbcc-107">예를 들어 Blob 스토리지 이벤트를 구독하여 파일이 업로드될 때 앱에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="7cbcc-108">그러면 애플리케이션은 다른 클라우드 또는 온-프레미스 애플리케이션에서 사용하는 사용자 지정 이벤트 그리드 메시지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="7cbcc-109">Event Grid는 안정적으로 대규모 이벤트를 처리할 수 있도록 빌드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="7cbcc-110">필요한 인프라를 설정하는 오버헤드 없이 메시지를 게시하고 구독할 수 있는 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![Event Grid 로고](./media/event-grid-logo.png)

<span data-ttu-id="7cbcc-112">Event Grid의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-112">The major features of event grid include:</span></span>

- <span data-ttu-id="7cbcc-113">완전 관리형 이벤트 라우팅</span><span class="sxs-lookup"><span data-stu-id="7cbcc-113">Fully managed event routing.</span></span>
- <span data-ttu-id="7cbcc-114">거의 실시간으로 대규모 이벤트 전달</span><span class="sxs-lookup"><span data-stu-id="7cbcc-114">Near real-time event delivery at scale.</span></span>
- <span data-ttu-id="7cbcc-115">Azure 내부 및 외부 모두에서 광범위한 적용 범위</span><span class="sxs-lookup"><span data-stu-id="7cbcc-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="7cbcc-116">시나리오</span><span class="sxs-lookup"><span data-stu-id="7cbcc-116">Scenarios</span></span>

<span data-ttu-id="7cbcc-117">Event Grid는 다양한 시나리오에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="7cbcc-118">이 섹션에서는 가장 일반적인 세 가지 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="7cbcc-119">작업 자동화</span><span class="sxs-lookup"><span data-stu-id="7cbcc-119">Ops automation</span></span>

![작업 자동화](./media/ops-automation.png)

<span data-ttu-id="7cbcc-121">Event Grid는 인프라를 프로비전할 때 [Azure Automation](/azure/automation)에 알려 자동화를 가속화하고 정책 적용을 간소화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="7cbcc-122">애플리케이션 통합</span><span class="sxs-lookup"><span data-stu-id="7cbcc-122">Application integration</span></span>

![애플리케이션 통합](./media/app-integration.png)

<span data-ttu-id="7cbcc-124">Event Grid를 사용하여 앱을 다른 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="7cbcc-125">표준 HTTP 프로토콜을 사용하면 레거시 앱도 쉽게 수정하여 Event Grid 메시지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="7cbcc-126">웹후크를 사용하면 다른 서비스 및 플랫폼에서 Event Grid 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="7cbcc-127">서버리스 앱</span><span class="sxs-lookup"><span data-stu-id="7cbcc-127">Serverless apps</span></span>

![서버리스 앱](./media/serverless-apps.png)

<span data-ttu-id="7cbcc-129">Event Grid는 Azure Functions, Logic Apps 또는 사용자 지정 코드를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="7cbcc-130">Event Grid를 사용하는 주요 이점은 이벤트가 발생할 때 메시지를 보내기 위해 *푸시* 메커니즘을 사용한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="7cbcc-131">푸시 아키텍처는 *폴링* 메커니즘보다 적은 리소스를 사용하고 더 효율적으로 크기 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="7cbcc-132">폴링은 정기적으로 업데이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="7cbcc-133">Event Grid 및 기타 Azure 메시징 서비스</span><span class="sxs-lookup"><span data-stu-id="7cbcc-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="7cbcc-134">Azure는 [Event Hubs](/azure/event-hubs) 및 [Service Bus](/azure/service-bus-messaging)를 비롯한 여러 메시징 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-134">Azure provides several messaging services, including [Event Hubs](/azure/event-hubs) and [Service Bus](/azure/service-bus-messaging).</span></span> <span data-ttu-id="7cbcc-135">각 서비스는 특정 사용 사례 집합을 해결하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="7cbcc-136">다음 다이어그램에서는 서비스 간 차이점에 대한 개략적인 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure 메시징 비교](./media/azure-messaging-services.png)

<span data-ttu-id="7cbcc-138">보다 자세한 비교는 [메시징 서비스 비교](/azure/event-grid/compare-messaging-services)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-138">For a more in-depth comparison, see [Compare messaging services](/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="7cbcc-139">성능 목표</span><span class="sxs-lookup"><span data-stu-id="7cbcc-139">Performance targets</span></span>

<span data-ttu-id="7cbcc-140">Event Grid 사용하여 다음과 같은 성능 보장을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

- <span data-ttu-id="7cbcc-141">99번째 백분위 수에서 종단 간 대기 시간 1초 미만</span><span class="sxs-lookup"><span data-stu-id="7cbcc-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
- <span data-ttu-id="7cbcc-142">99.99% 가용성입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-142">99.99% availability.</span></span>
- <span data-ttu-id="7cbcc-143">지역별 초당 이벤트 수 1,000만 개</span><span class="sxs-lookup"><span data-stu-id="7cbcc-143">10 million events per second per region.</span></span>
- <span data-ttu-id="7cbcc-144">지역별 구독 수 1억 개</span><span class="sxs-lookup"><span data-stu-id="7cbcc-144">100 million subscriptions per region.</span></span>
- <span data-ttu-id="7cbcc-145">게시자 대기 시간 50ms</span><span class="sxs-lookup"><span data-stu-id="7cbcc-145">50-ms publisher latency.</span></span>
- <span data-ttu-id="7cbcc-146">1일 이내 전송 보장을 위해 지수 백오프를 사용하여 24시간 다시 시도</span><span class="sxs-lookup"><span data-stu-id="7cbcc-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
- <span data-ttu-id="7cbcc-147">투명한 지역 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="7cbcc-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="7cbcc-148">Event Grid 스키마</span><span class="sxs-lookup"><span data-stu-id="7cbcc-148">Event Grid schema</span></span>

<span data-ttu-id="7cbcc-149">Event Grid는 표준 스키마를 사용하여 사용자 지정 이벤트를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="7cbcc-150">스키마는 사용자 지정 데이터 요소를 래핑하는 봉투(envelope)와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="7cbcc-151">다음은 Event Grid 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-151">Here is an example Event Grid message:</span></span>

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

<span data-ttu-id="7cbcc-152">메시지에 대한 모든 것은 `data` 속성을 제외하고 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="7cbcc-153">메시지를 검사하고 `eventType` 및 `dataVersion`을 사용하여 페이로드의 사용자 지정 부분을 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="7cbcc-154">: Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="7cbcc-154">Azure resources</span></span>

<span data-ttu-id="7cbcc-155">Event Grid를 사용하는 주요 이점은 Azure에서 생성되는 자동 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="7cbcc-156">Azure에서 리소스는 다양한 이벤트를 구독할 수 있게 해주는 *토픽*에 자동으로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="7cbcc-157">다음 표에서는 자동으로 사용할 수 있는 리소스 유형, 메시지 유형 및 이벤트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="7cbcc-158">Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="7cbcc-158">Azure resource</span></span> | <span data-ttu-id="7cbcc-159">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="7cbcc-159">Event type</span></span> | <span data-ttu-id="7cbcc-160">설명</span><span class="sxs-lookup"><span data-stu-id="7cbcc-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="7cbcc-161">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="7cbcc-161">Azure subscription</span></span> | <span data-ttu-id="7cbcc-162">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="7cbcc-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="7cbcc-163">리소스 생성 또는 업데이트 작업이 성공하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="7cbcc-164">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="7cbcc-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="7cbcc-165">리소스 생성 또는 업데이트 작업이 실패하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="7cbcc-166">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="7cbcc-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="7cbcc-167">리소스 생성 또는 업데이트 작업이 취소되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="7cbcc-168">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="7cbcc-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="7cbcc-169">리소스 삭제 작업이 성공하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="7cbcc-170">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="7cbcc-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="7cbcc-171">리소스 삭제 작업이 실패하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="7cbcc-172">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="7cbcc-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="7cbcc-173">리소스 삭제 작업이 취소되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="7cbcc-174">이 이벤트는 템플릿 배포가 취소될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="7cbcc-175">Blob Storage</span><span class="sxs-lookup"><span data-stu-id="7cbcc-175">Blob storage</span></span> | <span data-ttu-id="7cbcc-176">Microsoft.Storage.BlobCreated</span><span class="sxs-lookup"><span data-stu-id="7cbcc-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="7cbcc-177">Blob을 만들 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="7cbcc-178">Microsoft.Storage.BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="7cbcc-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="7cbcc-179">Blob을 삭제할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="7cbcc-180">이벤트 허브(영문)</span><span class="sxs-lookup"><span data-stu-id="7cbcc-180">Event hubs</span></span> | <span data-ttu-id="7cbcc-181">Microsoft.EventHub.CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="7cbcc-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="7cbcc-182">캡처 파일을 만들 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="7cbcc-183">IoT Hub</span><span class="sxs-lookup"><span data-stu-id="7cbcc-183">IoT Hub</span></span> | <span data-ttu-id="7cbcc-184">Microsoft.Devices.DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="7cbcc-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="7cbcc-185">IoT 허브에 디바이스를 등록하는 경우 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="7cbcc-186">Microsoft.Devices.DeviceDeleted</span><span class="sxs-lookup"><span data-stu-id="7cbcc-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="7cbcc-187">IoT 허브에서 디바이스를 삭제하는 경우 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="7cbcc-188">리소스 그룹</span><span class="sxs-lookup"><span data-stu-id="7cbcc-188">Resource groups</span></span> | <span data-ttu-id="7cbcc-189">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="7cbcc-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="7cbcc-190">리소스 생성 또는 업데이트 작업이 성공하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="7cbcc-191">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="7cbcc-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="7cbcc-192">리소스 생성 또는 업데이트 작업이 실패하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="7cbcc-193">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="7cbcc-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="7cbcc-194">리소스 생성 또는 업데이트 작업이 취소되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="7cbcc-195">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="7cbcc-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="7cbcc-196">리소스 삭제 작업이 성공하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="7cbcc-197">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="7cbcc-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="7cbcc-198">리소스 삭제 작업이 실패하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="7cbcc-199">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="7cbcc-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="7cbcc-200">리소스 삭제 작업이 취소되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="7cbcc-201">이 이벤트는 템플릿 배포가 취소될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="7cbcc-202">자세한 내용은 [Azure Event Grid 이벤트 스키마](/azure/event-grid/event-schema)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-202">For more information, see [Azure Event Grid event schema](/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="7cbcc-203">온-프레미스에서 실행되는 애플리케이션도 포함해 모든 종류의 애플리케이션에서 Event Grid에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="7cbcc-204">결론</span><span class="sxs-lookup"><span data-stu-id="7cbcc-204">Conclusion</span></span>

<span data-ttu-id="7cbcc-205">이 장에서는 Azure Functions, Logic Apps 및 Event Grid로 구성된 Azure 서버리스 플랫폼에 대해 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="7cbcc-206">이러한 리소스를 사용하여 온전하게 서버리스 앱 아키텍처를 빌드하거나 다른 클라우드 리소스 및 온-프레미스 서버와 상호 작용하는 하이브리드 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="7cbcc-207">[Azure SQL](/azure/sql-database) 또는 [CosmosDB](/azure/cosmos-db/introduction) 같은 서버리스 데이터 플랫폼과 결합하여 완전 관리형 클라우드 네이티브 애플리케이션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-207">Combined with a serverless data platform such as [Azure SQL](/azure/sql-database) or [CosmosDB](/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="7cbcc-208">권장되는 리소스</span><span class="sxs-lookup"><span data-stu-id="7cbcc-208">Recommended resources</span></span>

- [<span data-ttu-id="7cbcc-209">App Service 계획</span><span class="sxs-lookup"><span data-stu-id="7cbcc-209">App service plans</span></span>](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [<span data-ttu-id="7cbcc-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="7cbcc-210">Application Insights</span></span>](/azure/application-insights)
- [<span data-ttu-id="7cbcc-211">Application Insights 분석</span><span class="sxs-lookup"><span data-stu-id="7cbcc-211">Application Insights Analytics</span></span>](/azure/application-insights/app-insights-analytics)
- [<span data-ttu-id="7cbcc-212">Azure: 서버리스 Azure Functions를 사용하여 앱을 클라우드로 전환</span><span class="sxs-lookup"><span data-stu-id="7cbcc-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
- [<span data-ttu-id="7cbcc-213">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="7cbcc-213">Azure Event Grid</span></span>](/azure/event-grid/overview)
- [<span data-ttu-id="7cbcc-214">Azure Event Grid 이벤트 스키마</span><span class="sxs-lookup"><span data-stu-id="7cbcc-214">Azure Event Grid event schema</span></span>](/azure/event-grid/event-schema)
- [<span data-ttu-id="7cbcc-215">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="7cbcc-215">Azure Event Hubs</span></span>](/azure/event-hubs)
- <span data-ttu-id="7cbcc-216">[Azure Functions 설명서](/azure/azure-functions) 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbcc-216">[Azure Functions documentation](/azure/azure-functions)</span></span>
- [<span data-ttu-id="7cbcc-217">Azure Functions 트리거 및 바인딩 개념</span><span class="sxs-lookup"><span data-stu-id="7cbcc-217">Azure Functions triggers and bindings concepts</span></span>](/azure/azure-functions/functions-triggers-bindings)
- [<span data-ttu-id="7cbcc-218">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="7cbcc-218">Azure Logic Apps</span></span>](/azure/logic-apps)
- [<span data-ttu-id="7cbcc-219">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="7cbcc-219">Azure Service Bus</span></span>](/azure/service-bus-messaging)
- [<span data-ttu-id="7cbcc-220">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="7cbcc-220">Azure Table Storage</span></span>](/azure/cosmos-db/table-storage-overview)
- [<span data-ttu-id="7cbcc-221">Azure 온-프레미스 데이터 게이트웨이를 사용하여 온-프레미스 데이터 원본에 연결</span><span class="sxs-lookup"><span data-stu-id="7cbcc-221">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](/azure/analysis-services/analysis-services-gateway)
- [<span data-ttu-id="7cbcc-222">Azure Portal에서 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="7cbcc-222">Create your first function in the Azure portal</span></span>](/azure/azure-functions/functions-create-first-azure-function)
- [<span data-ttu-id="7cbcc-223">Azure CLI를 사용하여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="7cbcc-223">Create your first function using the Azure CLI</span></span>](/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [<span data-ttu-id="7cbcc-224">Visual Studio를 사용하여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="7cbcc-224">Create your first function using Visual Studio</span></span>](/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [<span data-ttu-id="7cbcc-225">Functions 지원 언어</span><span class="sxs-lookup"><span data-stu-id="7cbcc-225">Functions supported languages</span></span>](/azure/azure-functions/supported-languages)
- [<span data-ttu-id="7cbcc-226">Azure Functions 모니터링</span><span class="sxs-lookup"><span data-stu-id="7cbcc-226">Monitor Azure Functions</span></span>](/azure/azure-functions/functions-monitoring)

>[!div class="step-by-step"]
><span data-ttu-id="7cbcc-227">[이전](logic-apps.md)
>[다음](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="7cbcc-227">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
