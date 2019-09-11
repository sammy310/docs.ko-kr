---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 8dabf8845126705d082d080b643688ed62883f39
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854921"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="1f176-101">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="1f176-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="1f176-102">이 구성 요소는 서비스에서 UDP 바인딩을 통해 알림 메시지를 보내기 위해 사용하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="1f176-103">고정된 계약이 있으며 두 가지 버전의 검색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="1f176-104">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery 버전 1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="1f176-105">알림 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="1f176-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1f176-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1f176-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1f176-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1f176-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1f176-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="1f176-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<udpAnnouncementEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="1f176-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f176-110">구문</span><span class="sxs-lookup"><span data-stu-id="1f176-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f176-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1f176-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1f176-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f176-113">특성</span><span class="sxs-lookup"><span data-stu-id="1f176-113">Attributes</span></span>  
  
|<span data-ttu-id="1f176-114">특성</span><span class="sxs-lookup"><span data-stu-id="1f176-114">Attribute</span></span>|<span data-ttu-id="1f176-115">Description</span><span class="sxs-lookup"><span data-stu-id="1f176-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f176-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="1f176-116">discoveryVersion</span></span>|<span data-ttu-id="1f176-117">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="1f176-118">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="1f176-119">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="1f176-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="1f176-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="1f176-121">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="1f176-122">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="1f176-123">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="1f176-124">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="1f176-124">multicastAddress</span></span>|<span data-ttu-id="1f176-125">검색 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-125">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="1f176-126">기본값은 프로토콜 사양을 따르는 멀티캐스트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-126">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="1f176-127">name</span><span class="sxs-lookup"><span data-stu-id="1f176-127">name</span></span>|<span data-ttu-id="1f176-128">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-128">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1f176-129">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-129">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f176-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1f176-130">Child Elements</span></span>  
  
|<span data-ttu-id="1f176-131">요소</span><span class="sxs-lookup"><span data-stu-id="1f176-131">Element</span></span>|<span data-ttu-id="1f176-132">Description</span><span class="sxs-lookup"><span data-stu-id="1f176-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f176-133">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="1f176-133">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="1f176-134">UDP 엔드포인트에 대한 UDP 전송을 구성할 수 있도록 하는 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-134">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f176-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1f176-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1f176-136">요소</span><span class="sxs-lookup"><span data-stu-id="1f176-136">Element</span></span>|<span data-ttu-id="1f176-137">Description</span><span class="sxs-lookup"><span data-stu-id="1f176-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f176-138">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1f176-138">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1f176-139">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-139">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1f176-140">예제</span><span class="sxs-lookup"><span data-stu-id="1f176-140">Example</span></span>  
 <span data-ttu-id="1f176-141">다음 예제에서는 기본 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송 및 지정된 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송을 통해 알림을 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f176-141">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f176-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f176-142">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
