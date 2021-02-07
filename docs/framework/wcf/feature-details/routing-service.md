---
description: '자세한 정보: 라우팅 서비스'
title: 라우팅 서비스
ms.date: 03/30/2017
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
ms.openlocfilehash: 29fec780e6bc9266a8fe17d779ff0998e13e5c68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733257"
---
# <a name="routing-service"></a><span data-ttu-id="8a3f1-103">라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="8a3f1-103">Routing Service</span></span>

<span data-ttu-id="8a3f1-104">라우팅 서비스는 메시지 라우터 역할을 하는 제네릭 SOAP 매개자입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-104">The Routing Service is a generic SOAP intermediary that acts as a message router.</span></span> <span data-ttu-id="8a3f1-105">라우팅 서비스의 핵심 기능은 메시지 내용을 기반으로 메시지를 라우트할 수 있는, 즉 메시지 헤더나 메시지 본문 같은 메시지 자체에 포함된 값을 기반으로 메시지를 클라이언트 엔드포인트에 전달할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-105">The core functionality of the Routing Service is the ability to route messages based on message content, which allows a message to be forwarded to a client endpoint based on a value within the message itself, in either the header or the message body.</span></span>

<span data-ttu-id="8a3f1-106">는 <xref:System.ServiceModel.Routing.RoutingService> 네임 스페이스에서 WCF (Windows Communication Foundation) 서비스로 구현 됩니다 <xref:System.ServiceModel.Routing> .</span><span class="sxs-lookup"><span data-stu-id="8a3f1-106">The <xref:System.ServiceModel.Routing.RoutingService> is implemented as a Windows Communication Foundation (WCF) service in the <xref:System.ServiceModel.Routing> namespace.</span></span> <span data-ttu-id="8a3f1-107">라우팅 서비스는 메시지를 받은 다음 메시지 내용을 기반으로 각 메시지를 하나 이상의 클라이언트 엔드포인트에 라우트하는 하나 이상의 서비스 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-107">The Routing Service exposes one or more service endpoints that receive messages and then routes each message to one or more client endpoints based on the message content.</span></span> <span data-ttu-id="8a3f1-108">라우팅 서비스는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-108">The service provides the following features:</span></span>

- <span data-ttu-id="8a3f1-109">내용 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a3f1-109">Content-based routing</span></span>

  - <span data-ttu-id="8a3f1-110">서비스 집계</span><span class="sxs-lookup"><span data-stu-id="8a3f1-110">Service aggregation</span></span>

  - <span data-ttu-id="8a3f1-111">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-111">Service versioning</span></span>

  - <span data-ttu-id="8a3f1-112">우선 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a3f1-112">Priority routing</span></span>

  - <span data-ttu-id="8a3f1-113">동적 구성</span><span class="sxs-lookup"><span data-stu-id="8a3f1-113">Dynamic configuration</span></span>

- <span data-ttu-id="8a3f1-114">프로토콜 브리징</span><span class="sxs-lookup"><span data-stu-id="8a3f1-114">Protocol bridging</span></span>

- <span data-ttu-id="8a3f1-115">SOAP 처리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-115">SOAP processing</span></span>

- <span data-ttu-id="8a3f1-116">고급 오류 처리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-116">Advanced error handling</span></span>

- <span data-ttu-id="8a3f1-117">백업 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="8a3f1-117">Backup endpoints</span></span>

<span data-ttu-id="8a3f1-118">위에 나열된 이점을 제공하는 매개자 서비스를 만들 수는 있지만 종종 이러한 구현이 특정 시나리오나 솔루션으로 제한되어 새 애플리케이션에 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-118">While it is possible to create an intermediary service that accomplishes one or more of these goals, often such an implementation is tied to a specific scenario or solution and cannot be readily applied to new applications.</span></span>

<span data-ttu-id="8a3f1-119">라우팅 서비스는 WCF 서비스 및 채널 모델과 호환 되 고 SOAP 기반 메시지의 내용 기반 라우팅을 수행 하는 데 사용할 수 있는, 동적으로 구성 가능한 제네릭 SOAP 매개 자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-119">The Routing Service provides a generic, dynamically configurable, pluggable SOAP intermediary that is compatible with the WCF Service and Channel models and allows you to perform content-based routing of SOAP-based messages.</span></span>

> [!NOTE]
> <span data-ttu-id="8a3f1-120">라우팅 서비스는 현재 WCF REST 서비스의 라우팅을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-120">The Routing Service does not currently support routing of WCF REST services.</span></span>  <span data-ttu-id="8a3f1-121">REST 호출을 라우팅하려면 <xref:System.Web.Routing> 또는 [응용 프로그램 요청 라우팅을](https://go.microsoft.com/fwlink/?LinkId=164589)사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-121">To route REST calls, consider using <xref:System.Web.Routing> or [Application Request Routing](https://go.microsoft.com/fwlink/?LinkId=164589).</span></span>

## <a name="content-based-routing"></a><span data-ttu-id="8a3f1-122">내용 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a3f1-122">Content-Based Routing</span></span>

<span data-ttu-id="8a3f1-123">내용 기반 라우팅은 메시지에 들어 있는 하나 이상의 값을 기반으로 메시지를 라우트할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-123">Content-based routing is the ability to route a message based on one or more values contained within the message.</span></span> <span data-ttu-id="8a3f1-124">라우팅 서비스는 각 메시지를 검사하고 메시지 내용과 사용자 제공 라우팅 논리를 기반으로 메시지를 대상 엔드포인트에 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-124">The Routing Service inspects each message and routes it to the destination endpoint based on the message contents and the routing logic you create.</span></span> <span data-ttu-id="8a3f1-125">내용 기반 라우팅은 서비스 집계, 서비스 버전 관리 및 우선 순위 라우팅에 대한 기초를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-125">Content-based routing provides the basis for service aggregation, service versioning, and priority routing.</span></span>

<span data-ttu-id="8a3f1-126">내용 기반 라우팅을 구현하기 위해 라우팅 서비스는 라우트할 메시지 내의 특정 값과 일치시키는 데 사용되는 <xref:System.ServiceModel.Dispatcher.MessageFilter> 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-126">To implement content-based routing, the Routing Service relies on <xref:System.ServiceModel.Dispatcher.MessageFilter> implementations that are used to match specific values within the messages to be routed.</span></span> <span data-ttu-id="8a3f1-127">**Messagefilter** 가 메시지와 일치 하는 경우 메시지는 **messagefilter** 와 연결 된 대상 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-127">If a **MessageFilter** matches a message, the message is routed to the destination endpoint associated with the **MessageFilter**.</span></span>  <span data-ttu-id="8a3f1-128">메시지 필터는 필터 테이블(<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>)로 그룹화되어 복잡한 라우팅 논리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-128">Message filters are grouped together into filter tables (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) to construct complex routing logic.</span></span> <span data-ttu-id="8a3f1-129">예를 들어 필터 테이블에 다섯 개의 대상 엔드포인트 중 하나로만 메시지를 라우트할 수 있도록 하는 상호 배타적인 다섯 개의 메시지 필터가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-129">For example, a filter table might contain five mutually exclusive message filters that cause messages to be routed to only one of the five destination endpoints.</span></span>

<span data-ttu-id="8a3f1-130">라우팅 서비스를 사용하면 내용 기반 라우팅을 수행하는 데 사용되는 논리를 구성할 수 있을 뿐 아니라 런타임에 라우팅 논리를 동적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-130">The Routing Service allows you to configure the logic that is used to perform content-based routing, as well as dynamically update the routing logic at run time.</span></span>

<span data-ttu-id="8a3f1-131">메시지 필터를 필터 테이블로 그룹화하면 다음과 같은 여러 라우팅 시나리오를 처리할 수 있는 라우팅 논리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-131">Through the grouping of message filters into filter tables, routing logic can be constructed that allows you to handle multiple routing scenarios such as:</span></span>

- <span data-ttu-id="8a3f1-132">서비스 집계</span><span class="sxs-lookup"><span data-stu-id="8a3f1-132">Service aggregation</span></span>

- <span data-ttu-id="8a3f1-133">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-133">Service versioning</span></span>

- <span data-ttu-id="8a3f1-134">우선 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a3f1-134">Priority routing</span></span>

- <span data-ttu-id="8a3f1-135">동적 구성</span><span class="sxs-lookup"><span data-stu-id="8a3f1-135">Dynamic configuration</span></span>

<span data-ttu-id="8a3f1-136">메시지 필터 및 필터 테이블에 대 한 자세한 내용은 [라우팅 소개](routing-introduction.md) 및 [메시지 필터](message-filters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-136">For more information about message filters and filter tables, see [Routing Introduction](routing-introduction.md) and [Message Filters](message-filters.md).</span></span>

### <a name="service-aggregation"></a><span data-ttu-id="8a3f1-137">서비스 집계</span><span class="sxs-lookup"><span data-stu-id="8a3f1-137">Service Aggregation</span></span>

<span data-ttu-id="8a3f1-138">내용 기반 라우팅을 사용하면 외부 클라이언트 애플리케이션의 메시지를 받는 하나의 엔드포인트를 노출한 다음 메시지에 들어 있는 값을 기반으로 각 메시지를 적절한 내부 엔드포인트로 라우트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-138">By using content-based routing, you can expose one endpoint that receives messages from external client applications and then routes each message to the appropriate internal endpoint based on a value within the message.</span></span> <span data-ttu-id="8a3f1-139">이는 다양한 백엔드 애플리케이션에 대해 하나의 특정 엔드포인트를 제공하거나 다양한 서비스로 애플리케이션을 팩터링하는 동안 고객에게 하나의 애플리케이션 엔드포인트를 제공할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-139">This is useful to offer one specific endpoint for a variety of back-end applications, and also to present one application endpoint to customers while factoring your application into a variety of services.</span></span>

### <a name="service-versioning"></a><span data-ttu-id="8a3f1-140">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-140">Service Versioning</span></span>

<span data-ttu-id="8a3f1-141">새 버전의 솔루션으로 마이그레이션하는 경우 기존 고객을 지원하기 위해 이전 버전도 함께 유지 관리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-141">When migrating to a new version of your solution, you may have to maintain the old version in parallel to serve existing customers.</span></span> <span data-ttu-id="8a3f1-142">이를 위해 새 버전에 연결하는 클라이언트가 솔루션과 통신할 때 다른 주소를 사용해야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-142">Often this requires that clients connecting to the newer version must use a different address when communicating with the solution.</span></span> <span data-ttu-id="8a3f1-143">라우팅 서비스를 사용하면 메시지에 들어 있는 버전 관련 정보를 기반으로 메시지를 적절한 솔루션으로 라우트하여 두 버전의 솔루션을 모두 지원하는 하나의 서비스 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-143">The Routing Service allows you to expose one service endpoint that serves both versions of your solution by routing messages to the appropriate solution based on version-specific information contained in the message.</span></span> <span data-ttu-id="8a3f1-144">이러한 구현에 대 한 예제 [는 방법: 서비스 버전 관리](how-to-service-versioning.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-144">For an example of such an implementation see [How To: Service Versioning](how-to-service-versioning.md).</span></span>

### <a name="priority-routing"></a><span data-ttu-id="8a3f1-145">우선 순위 라우팅</span><span class="sxs-lookup"><span data-stu-id="8a3f1-145">Priority Routing</span></span>

<span data-ttu-id="8a3f1-146">여러 클라이언트에 서비스를 제공하는 경우 일부 파트너와의 SLA(서비스 수준 계약)가 있을 수 있습니다. SLA는 해당 파트너의 모든 데이터를 다른 클라이언트의 데이터와 별도로 처리하도록 요구하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-146">When providing a service for multiple clients, you may have a service level agreement (SLA) with some partners that requires all data from these partners to be processed separately from that of other clients.</span></span> <span data-ttu-id="8a3f1-147">메시지에 들어 있는 고객 관련 정보를 검색하는 필터를 사용하면 특정 파트너의 메시지를 해당 파트너의 SLA 요구 사항을 충족시키기 위해 만들어진 엔드포인트로 손쉽게 라우트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-147">By using a filter that looks for customer-specific information contained in the message, you can easily route messages from specific partners to an endpoint that has been created to meet their SLA requirements.</span></span>

## <a name="dynamic-configuration"></a><span data-ttu-id="8a3f1-148">동적 구성</span><span class="sxs-lookup"><span data-stu-id="8a3f1-148">Dynamic Configuration</span></span>

<span data-ttu-id="8a3f1-149">서비스 중단 없이 메시지를 처리해야 하는 업무용 시스템을 지원하려면 런타임에 시스템 구성 요소의 구성을 수정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-149">To support mission-critical systems, where messages must be processed without any service interruptions, it is vital that you be able to modify the configuration of components within the system at run time.</span></span> <span data-ttu-id="8a3f1-150">이러한 요구를 지원하기 위해 라우팅 서비스는 런타임에 라우팅 서비스 구성을 동적으로 업데이트할 수 있는 <xref:System.ServiceModel.IExtension%601> 구현인 <xref:System.ServiceModel.Routing.RoutingExtension>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-150">To support this need, the Routing Service provides an <xref:System.ServiceModel.IExtension%601> implementation, the <xref:System.ServiceModel.Routing.RoutingExtension>, which allows dynamic updating of the Routing Service configuration at run time.</span></span>

<span data-ttu-id="8a3f1-151">라우팅 서비스의 동적 구성에 대 한 자세한 내용은 [라우팅 소개](routing-introduction.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-151">For more information about dynamic configuration of the Routing Service, see [Routing Introduction](routing-introduction.md).</span></span>

## <a name="protocol-bridging"></a><span data-ttu-id="8a3f1-152">프로토콜 브리징</span><span class="sxs-lookup"><span data-stu-id="8a3f1-152">Protocol Bridging</span></span>

<span data-ttu-id="8a3f1-153">매개자 시나리오의 과제 중 하나는 메시지가 수신되는 엔드포인트와 다른 전송 또는 SOAP 버전 요구 사항이 내부 엔드포인트에 있을 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-153">One of the challenges in intermediary scenarios is that the internal endpoints may have different transport or SOAP version requirements than the endpoint that messages are received on.</span></span> <span data-ttu-id="8a3f1-154">이 시나리오를 지원하기 위해 라우팅 서비스는 SOAP 메시지를 대상 엔드포인트에 필요한 <xref:System.ServiceModel.Channels.MessageVersion>으로 처리할 뿐 아니라 프로토콜을 브리징할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-154">To support this scenario, the Routing Service can bridge protocols, including processing the SOAP message to the <xref:System.ServiceModel.Channels.MessageVersion> required by the destination endpoint(s).</span></span> <span data-ttu-id="8a3f1-155">그러면 한 프로토콜은 내부 통신용으로 사용하고 다른 한 프로토콜은 외부 통신용으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-155">In this way, one protocol can be used for internal communication, while another can be used for external communication.</span></span>

<span data-ttu-id="8a3f1-156">서로 다른 전송을 사용하는 엔드포인트 간의 메시지 라우팅을 지원하기 위해 라우팅 서비스는 서로 다른 프로토콜을 브리징할 수 있는 시스템 제공 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-156">To support the routing of messages between endpoints with different transports, the Routing Service uses system-provided bindings that enable the service to bridge dissimilar protocols.</span></span> <span data-ttu-id="8a3f1-157">이 동작은 라우팅 서비스에 표시된 서비스 엔드포인트가 메시지가 라우트되는 클라이언트 엔드포인트와 다른 프로토콜을 사용하는 경우 자동으로 발생합니다</span><span class="sxs-lookup"><span data-stu-id="8a3f1-157">This occurs automatically when the service endpoint exposed by the Routing Service uses a different protocol than the client endpoints that messages are routed to.</span></span>

## <a name="soap-processing"></a><span data-ttu-id="8a3f1-158">SOAP 처리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-158">SOAP Processing</span></span>

<span data-ttu-id="8a3f1-159">라우팅에 공통적으로 요구되는 기능은 SOAP 요구 사항이 서로 다른 엔드포인트 간에 메시지를 라우트할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-159">A common routing requirement is the ability to route messages between endpoints with differing SOAP requirements.</span></span> <span data-ttu-id="8a3f1-160">이러한 요구 사항을 지원 하기 위해 라우팅 서비스는 <xref:System.ServiceModel.Routing.SoapProcessingBehavior> 메시지를 라우팅하도록 대상 끝점의 요구 사항을 충족 하는 새 **MessageVersion** 을 자동으로 만드는를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-160">To support this requirement, the Routing Service provides a <xref:System.ServiceModel.Routing.SoapProcessingBehavior> that automatically creates a new **MessageVersion** that meets the requirements of the destination endpoint before the message is routed to it.</span></span> <span data-ttu-id="8a3f1-161">이 동작은 응답 메시지를 요청 하는 클라이언트 응용 프로그램으로 반환 하기 전에 응답 메시지에 대 한 새 **MessageVersion** 를 만들어 응답의 MessageVersion 원래 요청의  일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-161">This behavior also creates a new **MessageVersion** for any response message before returning it to the requesting client application, to ensure that the **MessageVersion** of the response matches that of the original request.</span></span>

<span data-ttu-id="8a3f1-162">SOAP 처리에 대 한 자세한 내용은 [라우팅 소개](routing-introduction.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-162">For more information about SOAP processing, see [Routing Introduction](routing-introduction.md).</span></span>

## <a name="error-handling"></a><span data-ttu-id="8a3f1-163">오류 처리</span><span class="sxs-lookup"><span data-stu-id="8a3f1-163">Error Handling</span></span>

<span data-ttu-id="8a3f1-164">네트워크 통신을 사용하는 분산 서비스로 구성된 시스템에서는 시스템 내의 통신이 일시적인 네트워크 오류를 처리할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-164">In a system composed of distributed services that rely on network communications, it is important to ensure that communications within your system are resistant to transient network failures.</span></span>  <span data-ttu-id="8a3f1-165">라우팅 서비스는 서비스 중지를 초래하는 다양한 통신 오류 시나리오를 처리할 수 있는 오류 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-165">The Routing Service implements error handling that allows you to handle many communication failure scenarios that might otherwise result in a service outage.</span></span>

<span data-ttu-id="8a3f1-166">라우팅 서비스에서 메시지를 보내려고 시도하는 중에 <xref:System.ServiceModel.CommunicationException>이 발생하면 오류 처리가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-166">If the Routing Service encounters a <xref:System.ServiceModel.CommunicationException> while attempting to send a message, error handling will take place.</span></span>  <span data-ttu-id="8a3f1-167">일반적으로 이러한 예외는 정의된 클라이언트 엔드포인트와 통신을 시도하는 중에 문제가 발생했음을 나타냅니다(예: <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> 또는 <xref:System.ServiceModel.CommunicationObjectFaultedException>).</span><span class="sxs-lookup"><span data-stu-id="8a3f1-167">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span>  <span data-ttu-id="8a3f1-168">또한 오류 처리 코드는 **CommunicationException** 에서 파생 되지 않는 또 다른 일반적인 예외인 **timeoutexception** 이 발생 하는 경우에도이를 catch 하 고 보내기를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-168">The error-handling code will also catch and attempt to retry sending when a **TimeoutException** occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>

<span data-ttu-id="8a3f1-169">오류 처리에 대 한 자세한 내용은 [라우팅 소개](routing-introduction.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-169">For more information about error handling, see [Routing Introduction](routing-introduction.md).</span></span>

## <a name="backup-endpoints"></a><span data-ttu-id="8a3f1-170">백업 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="8a3f1-170">Backup Endpoints</span></span>

<span data-ttu-id="8a3f1-171">필터 테이블의 각 필터 정의와 연결된 대상 클라이언트 엔드포인트 외에도 전송 실패 시 메시지를 라우트할 백업 엔드포인트의 목록을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-171">In addition to the destination client endpoints associated with each filter definition in the filter table, you can also create a list of backup endpoints that the message will be routed to in the event of a transmission failure.</span></span> <span data-ttu-id="8a3f1-172">오류가 발생할 경우 필터 항목에 대해 정의된 백업 목록이 있으면 라우팅 서비스는 이 목록에 정의되어 있는 첫 번째 엔드포인트에 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-172">If an error occurs and a backup list is defined for the filter entry, the Routing Service will attempt to send the message to the first endpoint defined in the list.</span></span> <span data-ttu-id="8a3f1-173">이 전송 시도가 실패하면 라우팅 서비스는 다음 엔드포인트에 메시지를 보내려고 시도하고 전송 시도가 성공하거나 전송과 관련 없는 오류가 반환되거나 백업 목록에 있는 모든 엔드포인트에서 전송 오류가 반환될 때까지 이 작업을 계속 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-173">If this transmission attempt fails, the service will try the next endpoint, and continue this process until the transmission attempt succeeds, returns a non-transmission related error, or all endpoints in the backup list have returned a transmission error.</span></span>

<span data-ttu-id="8a3f1-174">백업 끝점에 대 한 자세한 내용은 [라우팅 소개](routing-introduction.md) 및 [메시지 필터](message-filters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-174">For more information about backup endpoints, see [Routing Introduction](routing-introduction.md) and [Message Filters](message-filters.md).</span></span>

## <a name="streaming"></a><span data-ttu-id="8a3f1-175">스트리밍</span><span class="sxs-lookup"><span data-stu-id="8a3f1-175">Streaming</span></span>

<span data-ttu-id="8a3f1-176">스트리밍을 지원하도록 바인딩을 설정하는 경우 라우팅 서비스는 성공적으로 메시지를 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-176">The routing service can successfully stream messages if you set the binding to support streaming.</span></span>  <span data-ttu-id="8a3f1-177">그러나 메시지를 버퍼링해야 할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3f1-177">However, there are some conditions under which messages may need to buffered:</span></span>

- <span data-ttu-id="8a3f1-178">멀티캐스트(추가 메시지 복사본을 만들기 위한 버퍼)</span><span class="sxs-lookup"><span data-stu-id="8a3f1-178">Multicast (buffer to create additional message copies)</span></span>

- <span data-ttu-id="8a3f1-179">장애 조치(메시지를 백업에 전송해야 하는 경우의 버퍼)</span><span class="sxs-lookup"><span data-stu-id="8a3f1-179">Failover (buffer in case the message needs to be sent to a backup)</span></span>

- <span data-ttu-id="8a3f1-180">System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly가 false임(필터가 본문을 검사할 수 있도록 MessageBuffer와 함께 MessageFilterTable을 표시하기 위한 버퍼)</span><span class="sxs-lookup"><span data-stu-id="8a3f1-180">System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly is false (buffer to present the MessageFilterTable with a MessageBuffer so that filters can inspect the body)</span></span>

- <span data-ttu-id="8a3f1-181">동적 구성</span><span class="sxs-lookup"><span data-stu-id="8a3f1-181">Dynamic configuration</span></span>

## <a name="see-also"></a><span data-ttu-id="8a3f1-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a3f1-182">See also</span></span>

- [<span data-ttu-id="8a3f1-183">라우팅 소개</span><span class="sxs-lookup"><span data-stu-id="8a3f1-183">Routing Introduction</span></span>](routing-introduction.md)
- [<span data-ttu-id="8a3f1-184">라우팅 계약</span><span class="sxs-lookup"><span data-stu-id="8a3f1-184">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="8a3f1-185">메시지 필터</span><span class="sxs-lookup"><span data-stu-id="8a3f1-185">Message Filters</span></span>](message-filters.md)
