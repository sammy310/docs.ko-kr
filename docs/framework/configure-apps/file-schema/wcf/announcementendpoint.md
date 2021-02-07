---
description: 다음에 대해 자세히 알아보세요. <announcementEndpoint>
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: d010abb789a4401e9f0591f34edb29ec2036f16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749924"
---
# \<announcementEndpoint>

<span data-ttu-id="2b827-102">이 구성 요소는 고정 알림 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="2b827-103">서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="2b827-104">WCF (Windows Communication Foundation) 서비스는 요소의 알림 끝점을 지정 하 [\<serviceDiscovery>](servicediscovery.md) 고 AnnouncementClient를 사용 하 여 알림을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="2b827-105">다른 서비스에서 알림을 수신 대기 하려는 클라이언트는 실제로 WCF 서비스 역할을 합니다. 따라서 섹션에서 해당 클라이언트에 대 한 알림 끝점을 구성 해야 합니다 [\<services>](services.md) .</span><span class="sxs-lookup"><span data-stu-id="2b827-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="2b827-106">구문</span><span class="sxs-lookup"><span data-stu-id="2b827-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b827-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2b827-107">Attributes and Elements</span></span>  

 <span data-ttu-id="2b827-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b827-109">특성</span><span class="sxs-lookup"><span data-stu-id="2b827-109">Attributes</span></span>  
  
|<span data-ttu-id="2b827-110">attribute</span><span class="sxs-lookup"><span data-stu-id="2b827-110">Attribute</span></span>|<span data-ttu-id="2b827-111">설명</span><span class="sxs-lookup"><span data-stu-id="2b827-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b827-112">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="2b827-112">discoveryVersion</span></span>|<span data-ttu-id="2b827-113">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-113">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="2b827-114">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-114">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="2b827-115">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-115">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="2b827-116">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="2b827-116">maxAnnouncementDelay</span></span>|<span data-ttu-id="2b827-117">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-117">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="2b827-118">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-118">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="2b827-119">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-119">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="2b827-120">name</span><span class="sxs-lookup"><span data-stu-id="2b827-120">name</span></span>|<span data-ttu-id="2b827-121">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-121">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2b827-122">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-122">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b827-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2b827-123">Child Elements</span></span>  

 <span data-ttu-id="2b827-124">없음</span><span class="sxs-lookup"><span data-stu-id="2b827-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b827-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2b827-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2b827-126">요소</span><span class="sxs-lookup"><span data-stu-id="2b827-126">Element</span></span>|<span data-ttu-id="2b827-127">설명</span><span class="sxs-lookup"><span data-stu-id="2b827-127">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2b827-128">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-128">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b827-129">예제</span><span class="sxs-lookup"><span data-stu-id="2b827-129">Example</span></span>  

 <span data-ttu-id="2b827-130">다음 예제에서는 http 및 peernet을 통해 알림 메시지를 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b827-130">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b827-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b827-131">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
