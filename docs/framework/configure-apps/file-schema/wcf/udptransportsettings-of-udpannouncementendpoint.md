---
description: '다음에 대 한 자세한 정보:: <udpTransportSettings><udpAnnouncementEndpoint>'
title: <udpAnnouncementEndpoint>의 <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: 2997004e162728b20daa4f137e1edf132cd33d52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749209"
---
# <a name="udptransportsettings-of-udpannouncementendpoint"></a><span data-ttu-id="7786b-103">\<udpAnnouncementEndpoint>의 \<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="7786b-103">\<udpTransportSettings> of \<udpAnnouncementEndpoint></span></span>

<span data-ttu-id="7786b-104">이 구성 요소는에 대 한 UDP 전송 설정을 노출 [\<udpAnnouncementEndpoint>](udpannouncementendpoint.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-104">This configuration element exposes UDP transport settings for [\<udpAnnouncementEndpoint>](udpannouncementendpoint.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<udpAnnouncementEndpoint>**](udpannouncementendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<updTransportSettings>**  

## <a name="syntax"></a><span data-ttu-id="7786b-105">구문</span><span class="sxs-lookup"><span data-stu-id="7786b-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpAnnouncementEndpoint>
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
    </udpAnnouncementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7786b-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7786b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7786b-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7786b-108">특성</span><span class="sxs-lookup"><span data-stu-id="7786b-108">Attributes</span></span>  
  
|<span data-ttu-id="7786b-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7786b-109">Attribute</span></span>|<span data-ttu-id="7786b-110">설명</span><span class="sxs-lookup"><span data-stu-id="7786b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7786b-111">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="7786b-111">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="7786b-112">중복 메시지를 식별하기 위해 전송에 사용되는 최대 메시지 해시 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-112">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="7786b-113">TransportManager 수준에서 중복 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-113">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="7786b-114">이 속성을 0으로 설정하면 중복 검색이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-114">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="7786b-115">시스템 관리자나 개발자는 이 특성을 사용하여 중복 메시지 검색 알고리즘을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-115">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="7786b-116">직접 작성한 중복 검색 알고리즘을 구현하려는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-116">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="7786b-117">기본값은 4112입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-117">The default is 4112.</span></span>|  
|<span data-ttu-id="7786b-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="7786b-118">maxBufferPoolSize</span></span>|<span data-ttu-id="7786b-119">전송에 사용할 수 있는 버퍼 풀의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-119">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="7786b-120">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="7786b-120">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="7786b-121">메시지를 처음 보낸 후 재전송해야 하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-121">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="7786b-122">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-122">The default is 2.</span></span>|  
|<span data-ttu-id="7786b-123">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="7786b-123">maxPendingMessageCount</span></span>|<span data-ttu-id="7786b-124">수신되었으나 개별 채널 인스턴스의 InputQueue에서 아직 제거되지 않은 최대 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-124">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="7786b-125">InputQueue가 보류 중인 메시지 수 제한에 도달하는 경우 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-125">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="7786b-126">기본값은 32입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-126">The default is 32.</span></span>|  
|<span data-ttu-id="7786b-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="7786b-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="7786b-128">바인딩에서 처리할 수 있는 메시지의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-128">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="7786b-129">기본값은 65507입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-129">The default value is 65507.</span></span>|  
|<span data-ttu-id="7786b-130">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="7786b-130">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="7786b-131">메시지를 처음 보낸 후 재전송해야 하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-131">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="7786b-132">메시지를 유니캐스트 주소로 보내고 응답 메시지가 해당 RelatesTo 헤더에서 수신되면 구성된 횟수만큼 재전송하기 하기 전에 재전송이 일찍 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-132">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="7786b-133">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-133">The default value is 1.</span></span>|  
|<span data-ttu-id="7786b-134">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="7786b-134">multicastInterfaceId</span></span>|<span data-ttu-id="7786b-135">멀티홈 컴퓨터에서 멀티캐스트 트래픽을 보내고 받을 때 사용해야 하는 네트워크 어댑터를 고유하게 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-135">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="7786b-136">런타임에 전송에서 이 특성 값을 사용하여 인터페이스 인덱스를 조회합니다. 이 인덱스는 `IP_MULTICAST_IF` 및 `IPV6_MULTICAST_IF` 소켓 옵션을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-136">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="7786b-137">해당되는 경우 동일한 인터페이스 인덱스가 멀티캐스트 그룹을 조인할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-137">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="7786b-138">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-138">The default value is `null`.</span></span>|  
|<span data-ttu-id="7786b-139">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="7786b-139">socketReceiveBufferSize</span></span>|<span data-ttu-id="7786b-140">기본 WinSock 소켓의 수신 버퍼 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-140">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="7786b-141">수신 채널의 사용자는 바인딩의 이 특성을 사용하여 데이터를 받을 때 시스템이 동작하는 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-141">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="7786b-142">예를 들어 최대 임계값으로 인바운드 WCF 메시지를 사용하는 특정 애플리케이션에서 이 특성에 더 큰 값을 사용하면 애플리케이션에서 메시지를 처리할 수 있을 때까지 대기하는 동안 메시지가 WinSock 버퍼에 쌓이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-142">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="7786b-143">같은 상황에서 더 작은 값을 사용하면 메시지가 삭제됩니다. 이 특성은 기본 WinSock `SO_RCVBUF` 소켓 옵션을 노출합니다. 이 특성의 값은 적어도 `maxReceivedMessageSize` 크기 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-143">Using a lower value in the same situation would result in messages getting dropped.This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="7786b-144">이 값을 `maxReceivedMessageSize`보다 작은 값으로 설정하며 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-144">Setting it to a value smaller than the `maxReceivedMessageSize` will result in runtime exception.</span></span><br /><br /> <span data-ttu-id="7786b-145">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-145">The default value is 65536.</span></span>|  
|<span data-ttu-id="7786b-146">timeToLive</span><span class="sxs-lookup"><span data-stu-id="7786b-146">timeToLive</span></span>|<span data-ttu-id="7786b-147">멀티캐스트 패킷이 이동할 수 있는 네트워크 세그먼트 홉의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-147">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="7786b-148">이 특성은 `IP_MULTICAST_TTL` 및 `IP_TTL` 소켓 옵션과 관련된 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-148">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="7786b-149">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-149">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7786b-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7786b-150">Child Elements</span></span>  

 <span data-ttu-id="7786b-151">없음</span><span class="sxs-lookup"><span data-stu-id="7786b-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7786b-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7786b-152">Parent Elements</span></span>  
  
|<span data-ttu-id="7786b-153">요소</span><span class="sxs-lookup"><span data-stu-id="7786b-153">Element</span></span>|<span data-ttu-id="7786b-154">설명</span><span class="sxs-lookup"><span data-stu-id="7786b-154">Description</span></span>|  
|-------------|-----------------|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|<span data-ttu-id="7786b-155">고정 알림 계약 및 UDP 전송 바인딩이 있는 표준 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="7786b-155">A standard endpoint that has fixed announcement contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7786b-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7786b-156">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
