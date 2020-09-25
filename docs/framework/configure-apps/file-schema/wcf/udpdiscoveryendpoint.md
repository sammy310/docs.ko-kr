---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: f02cbddcdd4390d754f93e6f6d9aae6646cb137b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183626"
---
# \<udpDiscoveryEndpoint>

<span data-ttu-id="63ec6-101">이 구성 요소는 UDP 멀티캐스트 바인딩을 통한 검색 작업에 대해 미리 구성된 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-101">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="63ec6-102">이 엔드포인트에는 고정된 계약이 있으며 두 가지 버전의 WS-Discovery 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-102">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="63ec6-103">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery V1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-103">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpDiscoveryEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="63ec6-104">구문</span><span class="sxs-lookup"><span data-stu-id="63ec6-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63ec6-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="63ec6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="63ec6-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63ec6-107">특성</span><span class="sxs-lookup"><span data-stu-id="63ec6-107">Attributes</span></span>  
  
|<span data-ttu-id="63ec6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="63ec6-108">Attribute</span></span>|<span data-ttu-id="63ec6-109">설명</span><span class="sxs-lookup"><span data-stu-id="63ec6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63ec6-110">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="63ec6-110">discoveryMode</span></span>|<span data-ttu-id="63ec6-111">검색 프로토콜의 모드를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-111">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="63ec6-112">유효한 값은 "임시" 및 "관리"입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-112">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="63ec6-113">관리 모드에서는 프로토콜이 검색 가능한 서비스의 리포지토리로 작동하는 검색 프록시를 사용하고,</span><span class="sxs-lookup"><span data-stu-id="63ec6-113">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="63ec6-114">애드혹 모드에서는 프로토콜이 UDP 멀티캐스트 메커니즘을 사용하여 사용 가능한 서비스를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-114">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="63ec6-115">이 값은 <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-115">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="63ec6-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="63ec6-116">discoveryVersion</span></span>|<span data-ttu-id="63ec6-117">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="63ec6-118">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="63ec6-119">이 값은 <xref:System.ServiceModel.Discovery.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-119">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="63ec6-120">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="63ec6-120">maxResponseDelay</span></span>|<span data-ttu-id="63ec6-121">검색 프로토콜이 Probe Match 또는 Resolve Match 같은 특정 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="63ec6-122">모든 Probe Match가 동시에 전송되는 경우 네트워크 폭주가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-122">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="63ec6-123">이러한 현상이 발생하는 것을 방지하기 위해 각 Probe Match 사이에 임의의 지연 간격을 두고 Probe Match가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-123">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="63ec6-124">0에서 이 특성에 의해 설정되는 값까지의 범위 내에서 임의의 지연 간격이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-124">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="63ec6-125">이 특성이 0으로 설정되면 Probe Match 메시지가 지연 간격 없이 연속하여 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-125">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="63ec6-126">그렇지 않으면 모든 Probe Match 메시지를 보내는 데 걸리는 총 시간이 maxResponseDelay를 초과하지 않는 범위 내에서 Probe Match 메시지가 약간의 임의의 지연 간격을 두고 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-126">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="63ec6-127">이 값은 서비스에만 관련된 것으로 클라이언트에서 사용되는 값은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-127">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="63ec6-128">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="63ec6-128">multicastAddress</span></span>|<span data-ttu-id="63ec6-129">검색 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-129">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="63ec6-130">기본값은 프로토콜 사양을 따르는 멀티캐스트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-130">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="63ec6-131">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-131">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="63ec6-132">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-132">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63ec6-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="63ec6-133">Child Elements</span></span>  
  
|<span data-ttu-id="63ec6-134">요소</span><span class="sxs-lookup"><span data-stu-id="63ec6-134">Element</span></span>|<span data-ttu-id="63ec6-135">설명</span><span class="sxs-lookup"><span data-stu-id="63ec6-135">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="63ec6-136">UDP 엔드포인트에 대한 UDP 전송을 구성할 수 있도록 하는 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-136">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63ec6-137">부모 요소</span><span class="sxs-lookup"><span data-stu-id="63ec6-137">Parent Elements</span></span>  
  
|<span data-ttu-id="63ec6-138">요소</span><span class="sxs-lookup"><span data-stu-id="63ec6-138">Element</span></span>|<span data-ttu-id="63ec6-139">설명</span><span class="sxs-lookup"><span data-stu-id="63ec6-139">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="63ec6-140">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-140">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="63ec6-141">예제</span><span class="sxs-lookup"><span data-stu-id="63ec6-141">Example</span></span>  

 <span data-ttu-id="63ec6-142">다음 예제에서는 UDP 멀티캐스트 전송을 통해 검색 메시지를 수신하는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63ec6-142">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="63ec6-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63ec6-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
