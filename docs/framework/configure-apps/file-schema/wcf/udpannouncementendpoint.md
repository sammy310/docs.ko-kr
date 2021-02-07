---
description: 다음에 대해 자세히 알아보세요. <udpAnnouncementEndpoint>
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: f59e3e5365666835e910249e2cb37c2ce0e465e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749261"
---
# \<udpAnnouncementEndpoint>

<span data-ttu-id="110a5-102">이 구성 요소는 서비스에서 UDP 바인딩을 통해 알림 메시지를 보내기 위해 사용하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="110a5-103">고정된 계약이 있으며 두 가지 버전의 검색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="110a5-104">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery 버전 1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="110a5-105">알림 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="110a5-106">구문</span><span class="sxs-lookup"><span data-stu-id="110a5-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="110a5-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="110a5-107">Attributes and Elements</span></span>  

 <span data-ttu-id="110a5-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="110a5-109">특성</span><span class="sxs-lookup"><span data-stu-id="110a5-109">Attributes</span></span>  
  
|<span data-ttu-id="110a5-110">attribute</span><span class="sxs-lookup"><span data-stu-id="110a5-110">Attribute</span></span>|<span data-ttu-id="110a5-111">설명</span><span class="sxs-lookup"><span data-stu-id="110a5-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="110a5-112">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="110a5-112">discoveryVersion</span></span>|<span data-ttu-id="110a5-113">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-113">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="110a5-114">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-114">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="110a5-115">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-115">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="110a5-116">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="110a5-116">maxAnnouncementDelay</span></span>|<span data-ttu-id="110a5-117">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-117">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="110a5-118">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-118">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="110a5-119">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-119">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="110a5-120">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="110a5-120">multicastAddress</span></span>|<span data-ttu-id="110a5-121">검색 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-121">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="110a5-122">기본값은 프로토콜 사양을 따르는 멀티캐스트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-122">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="110a5-123">name</span><span class="sxs-lookup"><span data-stu-id="110a5-123">name</span></span>|<span data-ttu-id="110a5-124">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="110a5-125">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="110a5-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="110a5-126">Child Elements</span></span>  
  
|<span data-ttu-id="110a5-127">요소</span><span class="sxs-lookup"><span data-stu-id="110a5-127">Element</span></span>|<span data-ttu-id="110a5-128">설명</span><span class="sxs-lookup"><span data-stu-id="110a5-128">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="110a5-129">UDP 엔드포인트에 대한 UDP 전송을 구성할 수 있도록 하는 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-129">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="110a5-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="110a5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="110a5-131">요소</span><span class="sxs-lookup"><span data-stu-id="110a5-131">Element</span></span>|<span data-ttu-id="110a5-132">설명</span><span class="sxs-lookup"><span data-stu-id="110a5-132">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="110a5-133">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="110a5-134">예제</span><span class="sxs-lookup"><span data-stu-id="110a5-134">Example</span></span>  

 <span data-ttu-id="110a5-135">다음 예제에서는 기본 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송 및 지정된 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송을 통해 알림을 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="110a5-135">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="110a5-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="110a5-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
