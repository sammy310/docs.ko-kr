---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 4f3cf2748acc75b0ec83732664c5f97114f3663a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195126"
---
# <a name="announcementendpoint"></a><span data-ttu-id="0925d-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="0925d-101">\<announcementEndpoint></span></span>
<span data-ttu-id="0925d-102">이 구성 요소는 고정 알림 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="0925d-103">서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="0925d-104">Windows Communication Foundation (WCF) 서비스에서 알림 끝점을 지정 합니다 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) AnnouncementClient 발표 하는 데 사용 하 여 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="0925d-105">WCF 서비스를 실제로 다른 서비스에서 알림을 수신 하려는 클라이언트는 역할을 하합니다 따라서 해당 클라이언트에 대 한 알림 끝점을 구성 해야 합니다 [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="0925d-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0925d-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="0925d-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0925d-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0925d-108">구문</span><span class="sxs-lookup"><span data-stu-id="0925d-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0925d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0925d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0925d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0925d-111">특성</span><span class="sxs-lookup"><span data-stu-id="0925d-111">Attributes</span></span>  
  
|<span data-ttu-id="0925d-112">특성</span><span class="sxs-lookup"><span data-stu-id="0925d-112">Attribute</span></span>|<span data-ttu-id="0925d-113">설명</span><span class="sxs-lookup"><span data-stu-id="0925d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0925d-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="0925d-114">discoveryVersion</span></span>|<span data-ttu-id="0925d-115">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="0925d-116">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="0925d-117">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="0925d-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="0925d-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="0925d-119">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="0925d-120">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="0925d-121">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="0925d-122">name</span><span class="sxs-lookup"><span data-stu-id="0925d-122">name</span></span>|<span data-ttu-id="0925d-123">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="0925d-124">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0925d-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0925d-125">Child Elements</span></span>  
 <span data-ttu-id="0925d-126">없음</span><span class="sxs-lookup"><span data-stu-id="0925d-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0925d-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0925d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0925d-128">요소</span><span class="sxs-lookup"><span data-stu-id="0925d-128">Element</span></span>|<span data-ttu-id="0925d-129">설명</span><span class="sxs-lookup"><span data-stu-id="0925d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0925d-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0925d-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="0925d-131">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0925d-132">예제</span><span class="sxs-lookup"><span data-stu-id="0925d-132">Example</span></span>  
 <span data-ttu-id="0925d-133">다음 예제에서는 http 및 peernet을 통해 알림 메시지를 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0925d-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="0925d-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="0925d-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
