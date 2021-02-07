---
description: 다음에 대해 자세히 알아보세요. <serviceDiscovery>
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: d6df5b8d51763429829c2ea3c2593003720b7179
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682854"
---
# \<serviceDiscovery>

<span data-ttu-id="97672-102">서비스 엔드포인트의 검색 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-102">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="97672-103">구문</span><span class="sxs-lookup"><span data-stu-id="97672-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97672-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="97672-104">Attributes and Elements</span></span>  

 <span data-ttu-id="97672-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97672-106">특성</span><span class="sxs-lookup"><span data-stu-id="97672-106">Attributes</span></span>  

 <span data-ttu-id="97672-107">없음</span><span class="sxs-lookup"><span data-stu-id="97672-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97672-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="97672-108">Child Elements</span></span>  
  
|<span data-ttu-id="97672-109">요소</span><span class="sxs-lookup"><span data-stu-id="97672-109">Element</span></span>|<span data-ttu-id="97672-110">설명</span><span class="sxs-lookup"><span data-stu-id="97672-110">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="97672-111">알림 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="97672-111">A collection of announcement endpoints.</span></span> <span data-ttu-id="97672-112">이 섹션을 사용하여 알림 메시지를 보내기 위해 사용할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-112">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="97672-113">검색 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="97672-113">A collection of discovery endpoints.</span></span> <span data-ttu-id="97672-114">이 섹션을 사용하여 검색 메시지를 수신할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-114">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97672-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="97672-115">Parent Elements</span></span>  
  
|<span data-ttu-id="97672-116">요소</span><span class="sxs-lookup"><span data-stu-id="97672-116">Element</span></span>|<span data-ttu-id="97672-117">설명</span><span class="sxs-lookup"><span data-stu-id="97672-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="97672-118">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97672-119">설명</span><span class="sxs-lookup"><span data-stu-id="97672-119">Remarks</span></span>  

 <span data-ttu-id="97672-120">이 구성 요소가 서비스의 동작 구성에 추가되는 경우 서비스의 모든 엔드포인트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97672-120">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="97672-121">[\<discoveryEndpoint>](discoveryendpoint.md)또는 자식 요소를 사용 하 여 이러한 끝점의 검색 기능을 추가로 구성할 수 있습니다 [\<announcementEndpoint>](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="97672-121">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="97672-122">[\<announcementEndpoint>](announcementendpoint.md)서비스 알림을 보내는 데 사용할 끝점 구성 (온라인/Hello 및 오프 라인/Bye)을 지정 하 여 알림을 구성 하려면 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-122">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="97672-123">섹션을 사용 [\<discoveryEndpoint>](discoveryendpoint.md) 하 여 검색 메시지를 수신할 끝점을 수동으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-123">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97672-124">예제</span><span class="sxs-lookup"><span data-stu-id="97672-124">Example</span></span>  

 <span data-ttu-id="97672-125">다음 구성 예제에서는 CalculatorService를 검색할 수 있도록 지정하고 선택적으로 알림 엔드포인트를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97672-125">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97672-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97672-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
