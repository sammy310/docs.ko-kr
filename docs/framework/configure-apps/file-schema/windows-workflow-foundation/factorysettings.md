---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: d8e87799962638ac6514ebb31bbc9e209b39c98d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090929"
---
# <a name="factorysettings"></a><span data-ttu-id="46e46-101">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="46e46-101">\<factorySettings></span></span>
<span data-ttu-id="46e46-102">채널 팩터리 캐시의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-102">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="46e46-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="46e46-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="46e46-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="46e46-104">\<behaviors></span></span>  
<span data-ttu-id="46e46-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="46e46-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="46e46-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="46e46-106">\<behavior></span></span>  
<span data-ttu-id="46e46-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="46e46-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="46e46-108">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="46e46-108">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e46-109">구문</span><span class="sxs-lookup"><span data-stu-id="46e46-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46e46-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="46e46-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46e46-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46e46-112">특성</span><span class="sxs-lookup"><span data-stu-id="46e46-112">Attributes</span></span>  
  
|<span data-ttu-id="46e46-113">특성</span><span class="sxs-lookup"><span data-stu-id="46e46-113">Attribute</span></span>|<span data-ttu-id="46e46-114">설명</span><span class="sxs-lookup"><span data-stu-id="46e46-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46e46-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="46e46-115">idleTimeout</span></span>|<span data-ttu-id="46e46-116">개체가 삭제되기 전에 캐시에서 유휴 상태로 있을 수 있는 최대 시간 간격을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="46e46-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="46e46-117">leaseTimeout</span></span>|<span data-ttu-id="46e46-118">개체가 캐시에서 제거 될 되기까지의 시간 간격을 지정 하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="46e46-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="46e46-119">maxItemsInCache</span></span>|<span data-ttu-id="46e46-120">캐시에 유지될 수 있는 최대 개체 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46e46-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="46e46-121">Child Elements</span></span>  
 <span data-ttu-id="46e46-122">없음</span><span class="sxs-lookup"><span data-stu-id="46e46-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46e46-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="46e46-123">Parent Elements</span></span>  
  
|<span data-ttu-id="46e46-124">요소</span><span class="sxs-lookup"><span data-stu-id="46e46-124">Element</span></span>|<span data-ttu-id="46e46-125">설명</span><span class="sxs-lookup"><span data-stu-id="46e46-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46e46-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="46e46-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="46e46-127">캐시 공유 수준, 채널 팩터리 캐시 설정 및 Send 메시징 활동을 사용 하 여 서비스 끝점에 메시지를 보내는 워크플로 위한 채널 캐시의 설정을 사용자 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46e46-128">설명</span><span class="sxs-lookup"><span data-stu-id="46e46-128">Remarks</span></span>  
 <span data-ttu-id="46e46-129">이 서비스 동작은 서비스 엔드포인트에 메시지를 전송하는 워크플로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="46e46-130">이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="46e46-131">기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="46e46-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="46e46-132"><xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="46e46-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="46e46-133">구성에 정의된 엔드포인트가 있는 워크플로의 경우 기본적으로 Send 활동에 캐싱을 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="46e46-134">기본 캐시 공유 수준 및 채널 팩터리 및 채널 캐시의 캐시 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 하세요. [Send 활동의 캐시 공유 수준 변경](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46e46-135">예제</span><span class="sxs-lookup"><span data-stu-id="46e46-135">Example</span></span>  
 <span data-ttu-id="46e46-136">호스팅된 워크플로 서비스의 경우 응용 프로그램 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="46e46-137">이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="46e46-138">다음 예제에서는 포함 된 구성 파일의 내용을 합니다 **MyChannelCacheBehavior** 사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 하 여 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-138">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="46e46-139">이 서비스 동작은를 통해 서비스에 추가 합니다 **behaviorConfiguarion** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="46e46-139">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46e46-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="46e46-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="46e46-141">Send 작업의 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="46e46-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
