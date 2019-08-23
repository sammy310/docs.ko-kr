---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: ed87db92bcbfa0aa9016e36f391d707c5b17bf2b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934489"
---
# <a name="udptransportsettings"></a><span data-ttu-id="34ed4-101">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="34ed4-101">\<udpTransportSettings></span></span>
<span data-ttu-id="34ed4-102">이 구성 요소는 [ \<udpDiscoveryEndpoint >](udpdiscoveryendpoint.md)에 대 한 UDP 전송 설정을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-102">This configuration element exposes UDP transport settings for [\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md).</span></span>  
  
<span data-ttu-id="34ed4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34ed4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="34ed4-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="34ed4-104">\<standardEndpoints></span></span>  
<span data-ttu-id="34ed4-105">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="34ed4-105">\<udpDiscoveryEndpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ed4-106">구문</span><span class="sxs-lookup"><span data-stu-id="34ed4-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34ed4-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34ed4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="34ed4-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34ed4-109">특성</span><span class="sxs-lookup"><span data-stu-id="34ed4-109">Attributes</span></span>  
  
|<span data-ttu-id="34ed4-110">특성</span><span class="sxs-lookup"><span data-stu-id="34ed4-110">Attribute</span></span>|<span data-ttu-id="34ed4-111">Description</span><span class="sxs-lookup"><span data-stu-id="34ed4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34ed4-112">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="34ed4-112">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="34ed4-113">중복 메시지를 식별하기 위해 전송에 사용되는 최대 메시지 해시 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-113">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="34ed4-114">TransportManager 수준에서 중복 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-114">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="34ed4-115">이 속성을 0으로 설정하면 중복 검색이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-115">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="34ed4-116">시스템 관리자나 개발자는 이 특성을 사용하여 중복 메시지 검색 알고리즘을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-116">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="34ed4-117">직접 작성한 중복 검색 알고리즘을 구현하려는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-117">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="34ed4-118">기본값은 4112입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-118">The default is 4112.</span></span>|  
|<span data-ttu-id="34ed4-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="34ed4-119">maxBufferPoolSize</span></span>|<span data-ttu-id="34ed4-120">전송에 사용할 수 있는 버퍼 풀의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-120">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="34ed4-121">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="34ed4-121">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="34ed4-122">메시지를 처음 보낸 후 재전송해야 하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-122">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="34ed4-123">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-123">The default is 2.</span></span>|  
|<span data-ttu-id="34ed4-124">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="34ed4-124">maxPendingMessageCount</span></span>|<span data-ttu-id="34ed4-125">수신되었으나 개별 채널 인스턴스의 InputQueue에서 아직 제거되지 않은 최대 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-125">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="34ed4-126">InputQueue가 보류 중인 메시지 수 제한에 도달하는 경우 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-126">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="34ed4-127">기본값은 32입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-127">The default is 32.</span></span>|  
|<span data-ttu-id="34ed4-128">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="34ed4-128">maxReceivedMessageSize</span></span>|<span data-ttu-id="34ed4-129">바인딩에서 처리할 수 있는 메시지의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-129">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="34ed4-130">기본값은 65507입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-130">The default value is 65507.</span></span>|  
|<span data-ttu-id="34ed4-131">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="34ed4-131">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="34ed4-132">메시지를 처음 보낸 후 재전송해야 하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-132">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="34ed4-133">메시지를 유니캐스트 주소로 보내고 응답 메시지가 해당 RelatesTo 헤더에서 수신되면 구성된 횟수만큼 재전송하기 하기 전에 재전송이 일찍 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-133">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="34ed4-134">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-134">The default value is 1.</span></span>|  
|<span data-ttu-id="34ed4-135">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="34ed4-135">multicastInterfaceId</span></span>|<span data-ttu-id="34ed4-136">멀티홈 컴퓨터에서 멀티캐스트 트래픽을 보내고 받을 때 사용해야 하는 네트워크 어댑터를 고유하게 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-136">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="34ed4-137">런타임에 전송에서 이 특성 값을 사용하여 인터페이스 인덱스를 조회합니다. 이 인덱스는 `IP_MULTICAST_IF` 및 `IPV6_MULTICAST_IF` 소켓 옵션을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-137">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="34ed4-138">해당되는 경우 동일한 인터페이스 인덱스가 멀티캐스트 그룹을 조인할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-138">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="34ed4-139">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-139">The default value is `null`.</span></span>|  
|<span data-ttu-id="34ed4-140">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="34ed4-140">socketReceiveBufferSize</span></span>|<span data-ttu-id="34ed4-141">기본 WinSock 소켓의 수신 버퍼 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-141">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="34ed4-142">수신 채널의 사용자는 바인딩의 이 특성을 사용하여 데이터를 받을 때 시스템이 동작하는 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-142">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="34ed4-143">예를 들어 최대 임계값으로 인바운드 WCF 메시지를 사용하는 특정 애플리케이션에서 이 특성에 더 큰 값을 사용하면 애플리케이션에서 메시지를 처리할 수 있을 때까지 대기하는 동안 메시지가 WinSock 버퍼에 쌓이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-143">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="34ed4-144">같은 상황에서 더 작은 값을 사용하면 결과적으로 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-144">Using a lower value in the same situation would result in messages getting dropped.</span></span> <span data-ttu-id="34ed4-145">이 특성은 기본 WinSock `SO_RCVBUF` 소켓 옵션을 노출 합니다. 이 특성 값의 `maxReceivedMessageSize`크기는 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-145">This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="34ed4-146">이 값을 보다 `maxReceivedMessageSize` 작은 값으로 설정 하면 런타임 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-146">Setting it to a value smaller than the `maxReceivedMessageSize` will result in a runtime exception.</span></span><br /><br /> <span data-ttu-id="34ed4-147">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-147">The default value is 65536.</span></span>|  
|<span data-ttu-id="34ed4-148">timeToLive</span><span class="sxs-lookup"><span data-stu-id="34ed4-148">timeToLive</span></span>|<span data-ttu-id="34ed4-149">멀티캐스트 패킷이 이동할 수 있는 네트워크 세그먼트 홉의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-149">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="34ed4-150">이 특성은 `IP_MULTICAST_TTL` 및 `IP_TTL` 소켓 옵션과 관련된 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-150">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="34ed4-151">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-151">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34ed4-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34ed4-152">Child Elements</span></span>  
 <span data-ttu-id="34ed4-153">없음</span><span class="sxs-lookup"><span data-stu-id="34ed4-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34ed4-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34ed4-154">Parent Elements</span></span>  
  
|<span data-ttu-id="34ed4-155">요소</span><span class="sxs-lookup"><span data-stu-id="34ed4-155">Element</span></span>|<span data-ttu-id="34ed4-156">Description</span><span class="sxs-lookup"><span data-stu-id="34ed4-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34ed4-157">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="34ed4-157">\<udpDiscoveryEndpoint></span></span>](udpdiscoveryendpoint.md)|<span data-ttu-id="34ed4-158">고정 검색 계약 및 UDP 전송 바인딩이 있는 표준 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="34ed4-158">A standard endpoint that has fixed discovery contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34ed4-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="34ed4-159">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
