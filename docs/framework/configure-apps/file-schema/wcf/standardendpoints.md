---
description: 다음에 대해 자세히 알아보세요. <standardEndpoints>
title: <standardEndpoints>
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: f792f55b2c0c76727f4aaee50df072ee0c8bdbc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786657"
---
# \<standardEndpoints>

<span data-ttu-id="dbe46-102">이 구성 섹션에서는 다시 사용할 수 있는 미리 구성된 엔드포인트인 표준 엔드포인트의 컬렉션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-102">This configuration section allows you to define a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="dbe46-103">표준 엔드포인트에는 고정 값으로 설정된 하나 이상의 주소, 바인딩 및 계약 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-103">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="dbe46-104">예를 들어 검색 엔드포인트에서는 계약이 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-104">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="dbe46-105">표준 엔드포인트를 사용자 지정 바인딩 정의와 유사한 새 속성과 함께 사용하여 서비스 엔드포인트를 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-105">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoints>**  
  
## <a name="syntax"></a><span data-ttu-id="dbe46-106">구문</span><span class="sxs-lookup"><span data-stu-id="dbe46-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbe46-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dbe46-107">Attributes and Elements</span></span>  

 <span data-ttu-id="dbe46-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbe46-109">특성</span><span class="sxs-lookup"><span data-stu-id="dbe46-109">Attributes</span></span>  

 <span data-ttu-id="dbe46-110">없음</span><span class="sxs-lookup"><span data-stu-id="dbe46-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dbe46-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dbe46-111">Child Elements</span></span>  
  
|<span data-ttu-id="dbe46-112">요소</span><span class="sxs-lookup"><span data-stu-id="dbe46-112">Element</span></span>|<span data-ttu-id="dbe46-113">설명</span><span class="sxs-lookup"><span data-stu-id="dbe46-113">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="dbe46-114">고정 알림 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-114">Defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="dbe46-115">서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-115">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="dbe46-116">WCF (Windows Communication Foundation) 서비스는 요소의 알림 끝점을 지정 하 [\<serviceDiscovery>](servicediscovery.md) 고 AnnouncementClient를 사용 하 여 알림을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-116">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="dbe46-117">다른 서비스에서 알림을 수신 대기 하려는 클라이언트는 실제로 WCF 서비스 역할을 합니다. 따라서 섹션에서 해당 클라이언트에 대 한 알림 끝점을 구성 해야 합니다 [\<services>](services.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe46-117">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="dbe46-118">고정 검색 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-118">Defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="dbe46-119">서비스 구성에 추가되면 검색 메시지를 수신하는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-119">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="dbe46-120">클라이언트 구성에 추가되면 검색 쿼리를 보내는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-120">When added to the client configuration it specifies where to send the discovery queries.</span></span>|  
|[\<dynamicEndpoint>](dynamicendpoint.md)|<span data-ttu-id="dbe46-121">이 구성 요소는 애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-121">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
|[\<mexEndpoint>](mexendpoint.md)|<span data-ttu-id="dbe46-122">고정 IMetadataExchange 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-122">Defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="dbe46-123">모든 메타데이터 교환 엔드포인트가 IMetadataExchange를 계약으로 지정하므로 고유의 엔드포인트를 정의하는 대신 이 표준 지점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-123">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|<span data-ttu-id="dbe46-124">서비스에서 UDP 바인딩을 통해 알림 메시지를 보내는 데 사용하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-124">Defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="dbe46-125">고정된 계약이 있으며 두 가지 버전의 검색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-125">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="dbe46-126">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery 버전 1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-126">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="dbe46-127">알림 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-127">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|<span data-ttu-id="dbe46-128">UDP 멀티캐스트 바인딩을 통한 검색 작업에 대해 미리 구성된 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-128">Defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="dbe46-129">이 엔드포인트에는 고정된 계약이 있으며 두 가지 버전의 WS-Discovery 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-129">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="dbe46-130">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery V1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-130">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>|  
|[\<webHttpEndpoint>](webhttpendpoint.md)|<span data-ttu-id="dbe46-131">[\<webHttpBinding>](webhttpbinding.md)동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<webHttp>](webhttp.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-131">Defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="dbe46-132">REST 서비스를 작성할 때는 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-132">Use this endpoint when writing a REST service.</span></span>|  
|[\<webScriptEndpoint>](webscriptendpoint.md)|<span data-ttu-id="dbe46-133">[\<webHttpBinding>](webhttpbinding.md)동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<enableWebScript>](enablewebscript.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-133">Defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="dbe46-134">ASP.NET AJAX 애플리케이션에서 호출되는 서비스를 기록할 때 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-134">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>|  
|[\<workflowControlEndpoint>](workflowcontrolendpoint.md)|<span data-ttu-id="dbe46-135">워크플로 인스턴스의 실행(만들기, 실행, 일시 중단, 종료 등)을 제어하기 위한 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-135">Defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbe46-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dbe46-136">Parent Elements</span></span>  
  
|<span data-ttu-id="dbe46-137">요소</span><span class="sxs-lookup"><span data-stu-id="dbe46-137">Element</span></span>|<span data-ttu-id="dbe46-138">설명</span><span class="sxs-lookup"><span data-stu-id="dbe46-138">Description</span></span>|  
|-------------|-----------------|  
|\<system.ServiceModel>|<span data-ttu-id="dbe46-139">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe46-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbe46-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbe46-140">See also</span></span>

- [<span data-ttu-id="dbe46-141">표준 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="dbe46-141">Standard Endpoints</span></span>](../../../wcf/feature-details/standard-endpoints.md)
