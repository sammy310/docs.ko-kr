---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399632"
---
# <a name="servicediscovery"></a><span data-ttu-id="4fad4-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="4fad4-101">\<serviceDiscovery></span></span>
<span data-ttu-id="4fad4-102">서비스 엔드포인트의 검색 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="4fad4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4fad4-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4fad4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4fad4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="4fad4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="4fad4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceDiscovery >**</span><span class="sxs-lookup"><span data-stu-id="4fad4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fad4-109">구문</span><span class="sxs-lookup"><span data-stu-id="4fad4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fad4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4fad4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4fad4-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fad4-112">특성</span><span class="sxs-lookup"><span data-stu-id="4fad4-112">Attributes</span></span>  
 <span data-ttu-id="4fad4-113">없음</span><span class="sxs-lookup"><span data-stu-id="4fad4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fad4-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4fad4-114">Child Elements</span></span>  
  
|<span data-ttu-id="4fad4-115">요소</span><span class="sxs-lookup"><span data-stu-id="4fad4-115">Element</span></span>|<span data-ttu-id="4fad4-116">설명</span><span class="sxs-lookup"><span data-stu-id="4fad4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fad4-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="4fad4-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="4fad4-118">알림 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="4fad4-119">이 섹션을 사용하여 알림 메시지를 보내기 위해 사용할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="4fad4-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="4fad4-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="4fad4-121">검색 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="4fad4-122">이 섹션을 사용하여 검색 메시지를 수신할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fad4-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4fad4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4fad4-124">요소</span><span class="sxs-lookup"><span data-stu-id="4fad4-124">Element</span></span>|<span data-ttu-id="4fad4-125">설명</span><span class="sxs-lookup"><span data-stu-id="4fad4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fad4-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4fad4-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4fad4-127">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fad4-128">설명</span><span class="sxs-lookup"><span data-stu-id="4fad4-128">Remarks</span></span>  
 <span data-ttu-id="4fad4-129">이 구성 요소가 서비스의 동작 구성에 추가되는 경우 서비스의 모든 엔드포인트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="4fad4-130">[ \<Discoveryendpoint >](discoveryendpoint.md) 또는 [ \<announcementEndpoint >](announcementendpoint.md) 자식 요소를 사용 하 여 이러한 끝점의 검색 기능을 추가로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="4fad4-131">AnnouncementEndpoint > 섹션을 사용 하 여 서비스 알림을 보내는 데 사용할 끝점 구성 (온라인/Hello 및 오프 라인/Bye)을 지정 하 여 알림을 구성 합니다. [ \<](announcementendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="4fad4-132">Discoveryendpoint > 섹션을 사용 하 여 검색 메시지를 수신할 끝점을 수동으로 지정 합니다. [ \<](discoveryendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="4fad4-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fad4-133">예제</span><span class="sxs-lookup"><span data-stu-id="4fad4-133">Example</span></span>  
 <span data-ttu-id="4fad4-134">다음 구성 예제에서는 CalculatorService를 검색할 수 있도록 지정하고 선택적으로 알림 엔드포인트를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fad4-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="4fad4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="4fad4-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
