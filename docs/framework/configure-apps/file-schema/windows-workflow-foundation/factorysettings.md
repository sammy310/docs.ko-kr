---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: fed7fe192e7bc5cb37347d2eae42f75bbf1b7dee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946319"
---
# <a name="factorysettings"></a><span data-ttu-id="01c91-101">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="01c91-101">\<factorySettings></span></span>
<span data-ttu-id="01c91-102">채널 팩터리 캐시의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-102">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="01c91-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="01c91-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="01c91-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="01c91-104">\<behaviors></span></span>  
<span data-ttu-id="01c91-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="01c91-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="01c91-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="01c91-106">\<behavior></span></span>  
<span data-ttu-id="01c91-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="01c91-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="01c91-108">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="01c91-108">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c91-109">구문</span><span class="sxs-lookup"><span data-stu-id="01c91-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01c91-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="01c91-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01c91-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01c91-112">특성</span><span class="sxs-lookup"><span data-stu-id="01c91-112">Attributes</span></span>  
  
|<span data-ttu-id="01c91-113">특성</span><span class="sxs-lookup"><span data-stu-id="01c91-113">Attribute</span></span>|<span data-ttu-id="01c91-114">설명</span><span class="sxs-lookup"><span data-stu-id="01c91-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01c91-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="01c91-115">idleTimeout</span></span>|<span data-ttu-id="01c91-116">개체가 삭제되기 전에 캐시에서 유휴 상태로 있을 수 있는 최대 시간 간격을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="01c91-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="01c91-117">leaseTimeout</span></span>|<span data-ttu-id="01c91-118">캐시에서 개체가 제거 되기 전 까지의 시간 간격을 지정 하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="01c91-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="01c91-119">maxItemsInCache</span></span>|<span data-ttu-id="01c91-120">캐시에 유지될 수 있는 최대 개체 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01c91-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="01c91-121">Child Elements</span></span>  
 <span data-ttu-id="01c91-122">없음</span><span class="sxs-lookup"><span data-stu-id="01c91-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01c91-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="01c91-123">Parent Elements</span></span>  
  
|<span data-ttu-id="01c91-124">요소</span><span class="sxs-lookup"><span data-stu-id="01c91-124">Element</span></span>|<span data-ttu-id="01c91-125">설명</span><span class="sxs-lookup"><span data-stu-id="01c91-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01c91-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="01c91-126">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="01c91-127">메시지 보내기 작업을 사용 하 여 서비스 끝점으로 메시지를 보내는 워크플로를 위한 채널 캐시 설정, 캐시 공유 수준의 사용자 지정 및 채널 팩터리 캐시 설정을 가능 하 게 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01c91-128">설명</span><span class="sxs-lookup"><span data-stu-id="01c91-128">Remarks</span></span>  
 <span data-ttu-id="01c91-129">이 서비스 동작은 서비스 엔드포인트에 메시지를 전송하는 워크플로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="01c91-130">이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="01c91-131">기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="01c91-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="01c91-132"><xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="01c91-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="01c91-133">구성에 정의된 엔드포인트가 있는 워크플로의 경우 기본적으로 Send 활동에 캐싱을 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="01c91-134">기본 캐시 공유 수준 및 채널 팩터리 및 채널 캐시의 캐시 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 하세요. [Send 활동의 캐시 공유 수준 변경](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01c91-135">예제</span><span class="sxs-lookup"><span data-stu-id="01c91-135">Example</span></span>  
 <span data-ttu-id="01c91-136">호스팅된 워크플로 서비스의 경우 애플리케이션 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="01c91-137">이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="01c91-138">다음 예제에서는 사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 하 `MyChannelCacheBehavior` 여 서비스 동작을 포함 하는 구성 파일의 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="01c91-139">이 서비스 동작은 특성을 `behaviorConfiguration` 통해 서비스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01c91-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01c91-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="01c91-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="01c91-141">Send 작업의 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="01c91-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
