---
title: Azure Event Grid-서버 리스 앱
description: Azure Event Grid는 안정적인 이벤트 배달 및 이벤트별 지불 모델을 대규모로 라우팅에 대 한 서버 리스 솔루션입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959386"
---
# <a name="event-grid"></a><span data-ttu-id="a8062-103">Event Grid</span><span class="sxs-lookup"><span data-stu-id="a8062-103">Event Grid</span></span>

<span data-ttu-id="a8062-104">[Azure Event Grid](/azure/event-grid/overview) 이벤트 기반 응용 프로그램에 대 한 서버 리스 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="a8062-105">모든 원본에서 Event Grid에 게시 하 고 모든 플랫폼에서 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="a8062-106">또한 event Grid는 응용 프로그램 통합을 간소화 하는 Azure 리소스에서 이벤트에 대 한 기본 제공 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="a8062-107">예를 들어 파일이 업로드 되는 경우 앱에 알리기 위해 blob 저장소 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="a8062-108">응용 프로그램 수 되는 다른 클라우드 또는 온-프레미스 응용 프로그램을 사용자 지정 이벤트 그리드 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="a8062-109">Event Grid는 안정적으로 대규모를 처리 하도록 구축 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="a8062-110">게시 및 구독 하는 데 필요한 인프라를 설정 하는 오버 헤드 없이 메시지는 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![Event Grid 로고](./media/event-grid-logo.png)

<span data-ttu-id="a8062-112">Event grid의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-112">The major features of event grid include:</span></span>

* <span data-ttu-id="a8062-113">완전히 관리 되는 이벤트 라우팅입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-113">Fully managed event routing.</span></span>
* <span data-ttu-id="a8062-114">거의 대규모로 실시간 이벤트 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-114">Near real-time event delivery at scale.</span></span>
* <span data-ttu-id="a8062-115">내부와 Azure 외부의 광범위 한 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="a8062-116">시나리오</span><span class="sxs-lookup"><span data-stu-id="a8062-116">Scenarios</span></span>

<span data-ttu-id="a8062-117">Event Grid는 여러 가지 시나리오를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="a8062-118">이 섹션에서는 가장 일반적인 세 가지 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="a8062-119">작업 자동화</span><span class="sxs-lookup"><span data-stu-id="a8062-119">Ops automation</span></span>

![작업 자동화](./media/ops-automation.png)

<span data-ttu-id="a8062-121">Event Grid 속도 자동화 하는 데 도움이 및 알림으로써 정책 적용을 간소화할 수 있습니다 [Azure Automation](https://docs.microsoft.com/azure/automation) 인프라 프로 비전 된 경우.</span><span class="sxs-lookup"><span data-stu-id="a8062-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](https://docs.microsoft.com/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="a8062-122">응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="a8062-122">Application integration</span></span>

![응용 프로그램 통합](./media/app-integration.png)

<span data-ttu-id="a8062-124">다른 서비스에 앱을 연결할 Event Grid를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="a8062-125">표준 HTTP 프로토콜 사용도 레거시 앱 쉽게 수정할 수 있습니다 Event Grid 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="a8062-126">웹 후크 다른 서비스 및 Event Grid 메시지를 사용 하는 플랫폼에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="a8062-127">서버 리스 앱</span><span class="sxs-lookup"><span data-stu-id="a8062-127">Serverless apps</span></span>

![서버 리스 앱](./media/serverless-apps.png)

<span data-ttu-id="a8062-129">Event Grid는 Azure Functions, Logic Apps 또는 고유한 사용자 지정 코드 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="a8062-130">Event Grid를 사용 하는 데 필요한 주요 이점은 사용 한다는 것입니다를 *푸시* 이벤트가 발생할 때 메시지를 전송 하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="a8062-131">푸시 아키텍처 더 적은 리소스를 소비 하는 것 보다 좋아집니다 *폴링* 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="a8062-132">폴링 일정 한 간격으로 업데이트 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="a8062-133">다른 Azure 메시징 서비스 및 이벤트 표</span><span class="sxs-lookup"><span data-stu-id="a8062-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="a8062-134">Azure를 비롯 한 여러 메시징 서비스를 제공 [Event Hubs](https://docs.microsoft.com/azure/event-hubs) 하 고 [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-134">Azure provides several messaging services, including [Event Hubs](https://docs.microsoft.com/azure/event-hubs) and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging).</span></span> <span data-ttu-id="a8062-135">각 사용 사례는 특정 집합을 해결 하기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="a8062-136">다음 다이어그램은 서비스 간의 차이점에 대 한 개략적인 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure 메시징 비교](./media/azure-messaging-services.png)

<span data-ttu-id="a8062-138">자세한 비교를 참조 하세요 [메시징 서비스 비교](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-138">For a more in-depth comparison, see [Compare messaging services](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="a8062-139">성능 목표</span><span class="sxs-lookup"><span data-stu-id="a8062-139">Performance targets</span></span>

<span data-ttu-id="a8062-140">다음 성능을 이용할 수 있습니다 하는 Event Grid를 사용 하 여 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

* <span data-ttu-id="a8062-141">백분위 99의 종단 간 대기 시간을 1 초 미만의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
* <span data-ttu-id="a8062-142">99.99% 가용성입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-142">99.99% availability.</span></span>
* <span data-ttu-id="a8062-143">지역 마다 초당 10 백만 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-143">10 million events per second per region.</span></span>
* <span data-ttu-id="a8062-144">지역당 100 백만 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-144">100 million subscriptions per region.</span></span>
* <span data-ttu-id="a8062-145">대기 시간이 50ms 일 게시자입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-145">50-ms publisher latency.</span></span>
* <span data-ttu-id="a8062-146">지 수 백오프 1 일 창의 보장 된 배달을 위해을 사용 하 여 24 시간에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8062-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
* <span data-ttu-id="a8062-147">투명 한 지역 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="a8062-148">Event Grid 스키마</span><span class="sxs-lookup"><span data-stu-id="a8062-148">Event Grid schema</span></span>

<span data-ttu-id="a8062-149">Event Grid 사용자 지정 이벤트를 래핑하는 표준 스키마를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="a8062-150">스키마는 봉투 (envelope)에 사용자 지정 데이터 요소를 래핑하는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="a8062-151">Event Grid 메시지의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-151">Here is an example Event Grid message:</span></span>

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

<span data-ttu-id="a8062-152">메시지에 대 한 모든 항목은 제외 하 고 표준는 `data` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="a8062-153">메시지를 검사 하 고 사용할 수 있습니다 합니다 `eventType` 및 `dataVersion` 취소 페이로드 사용자 지정 부분을 직렬화 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="a8062-154">: Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="a8062-154">Azure resources</span></span>

<span data-ttu-id="a8062-155">Event Grid를 사용 하는 데 필요한 주요 이점은 Azure에서 생성 된 자동 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="a8062-156">Azure에서 리소스 자동으로 게시 하는 *항목* 다양 한 이벤트를 구독할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="a8062-157">다음 표에서 리소스 유형, 메시지 유형 및 자동으로 사용할 수 있는 이벤트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="a8062-158">Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="a8062-158">Azure resource</span></span> | <span data-ttu-id="a8062-159">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a8062-159">Event type</span></span> | <span data-ttu-id="a8062-160">설명</span><span class="sxs-lookup"><span data-stu-id="a8062-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="a8062-161">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="a8062-161">Azure subscription</span></span> | <span data-ttu-id="a8062-162">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="a8062-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="a8062-163">발생 경우 리소스 만들기 또는 업데이트 작업이 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="a8062-164">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="a8062-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="a8062-165">리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="a8062-166">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="a8062-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="a8062-167">발생 리소스 만들기 또는 업데이트 작업이 면 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="a8062-168">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="a8062-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="a8062-169">리소스 삭제 작업이 성공할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="a8062-170">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="a8062-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="a8062-171">리소스 삭제 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="a8062-172">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="a8062-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="a8062-173">리소스 삭제 작업이 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="a8062-174">이 이벤트에는 템플릿 배포가 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="a8062-175">Blob Storage</span><span class="sxs-lookup"><span data-stu-id="a8062-175">Blob storage</span></span> | <span data-ttu-id="a8062-176">Microsoft.Storage.BlobCreated</span><span class="sxs-lookup"><span data-stu-id="a8062-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="a8062-177">Blob을 만들 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="a8062-178">Microsoft.Storage.BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="a8062-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="a8062-179">Blob을 삭제할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="a8062-180">Event hubs</span><span class="sxs-lookup"><span data-stu-id="a8062-180">Event hubs</span></span> | <span data-ttu-id="a8062-181">Microsoft.EventHub.CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="a8062-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="a8062-182">캡처 파일을 만들 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="a8062-183">IoT Hub</span><span class="sxs-lookup"><span data-stu-id="a8062-183">IoT Hub</span></span> | <span data-ttu-id="a8062-184">Microsoft.Devices.DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="a8062-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="a8062-185">IoT hub에 장치를 등록할 때 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="a8062-186">Microsoft.Devices.DeviceDeleted</span><span class="sxs-lookup"><span data-stu-id="a8062-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="a8062-187">IoT hub에서 장치를 삭제 하는 경우 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="a8062-188">리소스 그룹</span><span class="sxs-lookup"><span data-stu-id="a8062-188">Resource groups</span></span> | <span data-ttu-id="a8062-189">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="a8062-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="a8062-190">발생 경우 리소스 만들기 또는 업데이트 작업이 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="a8062-191">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="a8062-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="a8062-192">리소스 만들기 또는 업데이트 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="a8062-193">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="a8062-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="a8062-194">발생 리소스 만들기 또는 업데이트 작업이 면 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="a8062-195">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="a8062-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="a8062-196">리소스 삭제 작업이 성공할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="a8062-197">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="a8062-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="a8062-198">리소스 삭제 작업이 실패할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="a8062-199">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="a8062-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="a8062-200">리소스 삭제 작업이 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="a8062-201">이 이벤트에는 템플릿 배포가 취소 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="a8062-202">자세한 내용은 [Azure Event Grid 이벤트 스키마](https://docs.microsoft.com/azure/event-grid/event-schema)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-202">For more information, see [Azure Event Grid event schema](https://docs.microsoft.com/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="a8062-203">Event Grid의 하나라도 온-프레미스를 실행 하는 응용 프로그램에서에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="a8062-204">결론</span><span class="sxs-lookup"><span data-stu-id="a8062-204">Conclusion</span></span>

<span data-ttu-id="a8062-205">이 장에서 Azure Functions, Logic Apps 및 Event Grid의 구성 된 Azure 서버 리스 플랫폼에 대해 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="a8062-206">이러한 리소스를 사용 하 여 완전히 서버 리스 앱 아키텍처를 빌드할 수도 있고 온-프레미스 서버 및 다른 클라우드 리소스와 상호 작용 하는 하이브리드 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="a8062-207">같은 서버 리스 데이터 플랫폼을 통해 결합 [Azure SQL](https://docs.microsoft.com/azure/sql-database) 또는 [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), 완전히 관리 되는 클라우드 네이티브 응용 프로그램을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8062-207">Combined with a serverless data platform such as [Azure SQL](https://docs.microsoft.com/azure/sql-database) or [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="a8062-208">권장 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="a8062-208">Recommended resources</span></span>

* [<span data-ttu-id="a8062-209">App service 계획</span><span class="sxs-lookup"><span data-stu-id="a8062-209">App service plans</span></span>](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [<span data-ttu-id="a8062-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="a8062-210">Application Insights</span></span>](https://docs.microsoft.com/azure/application-insights)
* [<span data-ttu-id="a8062-211">Application Insights 분석</span><span class="sxs-lookup"><span data-stu-id="a8062-211">Application Insights Analytics</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [<span data-ttu-id="a8062-212">Azure: 서버 리스 Azure Functions를 사용 하 여 클라우드로 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="a8062-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
* [<span data-ttu-id="a8062-213">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="a8062-213">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
* [<span data-ttu-id="a8062-214">Azure Event Grid 이벤트 스키마</span><span class="sxs-lookup"><span data-stu-id="a8062-214">Azure Event Grid event schema</span></span>](https://docs.microsoft.com/azure/event-grid/event-schema)
* [<span data-ttu-id="a8062-215">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="a8062-215">Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs)
* [<span data-ttu-id="a8062-216">Azure Functions 설명서</span><span class="sxs-lookup"><span data-stu-id="a8062-216">Azure Functions documentation</span></span>](https://docs.microsoft.com/azure/azure-functions)
* [<span data-ttu-id="a8062-217">Azure Functions 트리거 및 바인딩 개념</span><span class="sxs-lookup"><span data-stu-id="a8062-217">Azure Functions triggers and bindings concepts</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [<span data-ttu-id="a8062-218">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="a8062-218">Azure Logic Apps</span></span>](https://docs.microsoft.com/azure/logic-apps)
* [<span data-ttu-id="a8062-219">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="a8062-219">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging)
* [<span data-ttu-id="a8062-220">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="a8062-220">Azure Table Storage</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [<span data-ttu-id="a8062-221">1.x와 2.x 비교 함수</span><span class="sxs-lookup"><span data-stu-id="a8062-221">Compare functions 1.x and 2.x</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [<span data-ttu-id="a8062-222">Azure 온-프레미스 데이터 게이트웨이 사용 하 여 온-프레미스 데이터 원본에 연결</span><span class="sxs-lookup"><span data-stu-id="a8062-222">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [<span data-ttu-id="a8062-223">Azure portal에서 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="a8062-223">Create your first function in the Azure portal</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [<span data-ttu-id="a8062-224">Azure CLI를 사용 하 여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="a8062-224">Create your first function using the Azure CLI</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [<span data-ttu-id="a8062-225">Visual Studio를 사용 하 여 첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="a8062-225">Create your first function using Visual Studio</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [<span data-ttu-id="a8062-226">지원 되는 언어 기능</span><span class="sxs-lookup"><span data-stu-id="a8062-226">Functions supported languages</span></span>](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [<span data-ttu-id="a8062-227">Azure Functions 모니터링</span><span class="sxs-lookup"><span data-stu-id="a8062-227">Monitor Azure Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [<span data-ttu-id="a8062-228">Azure Functions 프록시 사용</span><span class="sxs-lookup"><span data-stu-id="a8062-228">Work with Azure Functions Proxies</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
><span data-ttu-id="a8062-229">[이전](logic-apps.md)
>[다음](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="a8062-229">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
