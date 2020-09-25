---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: b38496b77d80fcb66b1b48485a9eef6abfd72299
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198823"
---
# \<serviceDiscovery>

<span data-ttu-id="0e153-101">서비스 엔드포인트의 검색 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="0e153-102">구문</span><span class="sxs-lookup"><span data-stu-id="0e153-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e153-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0e153-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0e153-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e153-105">특성</span><span class="sxs-lookup"><span data-stu-id="0e153-105">Attributes</span></span>  

 <span data-ttu-id="0e153-106">없음</span><span class="sxs-lookup"><span data-stu-id="0e153-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e153-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0e153-107">Child Elements</span></span>  
  
|<span data-ttu-id="0e153-108">요소</span><span class="sxs-lookup"><span data-stu-id="0e153-108">Element</span></span>|<span data-ttu-id="0e153-109">설명</span><span class="sxs-lookup"><span data-stu-id="0e153-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="0e153-110">알림 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="0e153-111">이 섹션을 사용하여 알림 메시지를 보내기 위해 사용할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="0e153-112">검색 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="0e153-113">이 섹션을 사용하여 검색 메시지를 수신할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e153-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0e153-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0e153-115">요소</span><span class="sxs-lookup"><span data-stu-id="0e153-115">Element</span></span>|<span data-ttu-id="0e153-116">설명</span><span class="sxs-lookup"><span data-stu-id="0e153-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0e153-117">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e153-118">설명</span><span class="sxs-lookup"><span data-stu-id="0e153-118">Remarks</span></span>  

 <span data-ttu-id="0e153-119">이 구성 요소가 서비스의 동작 구성에 추가되는 경우 서비스의 모든 엔드포인트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="0e153-120">[\<discoveryEndpoint>](discoveryendpoint.md)또는 자식 요소를 사용 하 여 이러한 끝점의 검색 기능을 추가로 구성할 수 있습니다 [\<announcementEndpoint>](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="0e153-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="0e153-121">[\<announcementEndpoint>](announcementendpoint.md)서비스 알림을 보내는 데 사용할 끝점 구성 (온라인/Hello 및 오프 라인/Bye)을 지정 하 여 알림을 구성 하려면 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="0e153-122">섹션을 사용 [\<discoveryEndpoint>](discoveryendpoint.md) 하 여 검색 메시지를 수신할 끝점을 수동으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e153-123">예제</span><span class="sxs-lookup"><span data-stu-id="0e153-123">Example</span></span>  

 <span data-ttu-id="0e153-124">다음 구성 예제에서는 CalculatorService를 검색할 수 있도록 지정하고 선택적으로 알림 엔드포인트를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e153-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e153-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e153-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
