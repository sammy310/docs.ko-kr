---
description: 다음에 대해 자세히 알아보세요. <sendMessageChannelCache>
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 2c77372bb44df74a1d2186500367c5164e1e5042
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739783"
---
# \<sendMessageChannelCache>

<span data-ttu-id="5ac6b-102">캐시 공유 수준, 채널 팩터리 캐시 설정 및 Send 메시징 활동을 사용하여 서비스 엔드포인트로 메시지를 전송하는 워크플로를 위한 채널 캐시 설정에 대한 사용자 지정을 가능하게 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**  
  
## <a name="syntax"></a><span data-ttu-id="5ac6b-103">구문</span><span class="sxs-lookup"><span data-stu-id="5ac6b-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ac6b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ac6b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5ac6b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ac6b-106">특성</span><span class="sxs-lookup"><span data-stu-id="5ac6b-106">Attributes</span></span>  
  
|<span data-ttu-id="5ac6b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="5ac6b-107">Attribute</span></span>|<span data-ttu-id="5ac6b-108">설명</span><span class="sxs-lookup"><span data-stu-id="5ac6b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ac6b-109">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="5ac6b-109">allowUnsafeCaching</span></span>|<span data-ttu-id="5ac6b-110">캐시 설정 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-110">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="5ac6b-111">워크플로 서비스에 사용자 지정 바인딩 또는 사용자 지정 동작이 있는 경우 캐싱이 안전하지 않을 수 있으므로 기본적으로 사용되지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-111">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="5ac6b-112">그러나 캐싱을 설정 하려는 경우이 속성을 **true** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-112">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ac6b-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ac6b-113">Child Elements</span></span>  
  
|<span data-ttu-id="5ac6b-114">요소</span><span class="sxs-lookup"><span data-stu-id="5ac6b-114">Element</span></span>|<span data-ttu-id="5ac6b-115">설명</span><span class="sxs-lookup"><span data-stu-id="5ac6b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<channelSettings>](channelsettings.md)|<span data-ttu-id="5ac6b-116">채널 캐시의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-116">Specifies the settings of the channel cache.</span></span>|  
|[\<factorySettings>](factorysettings.md)|<span data-ttu-id="5ac6b-117">채널 팩터리 캐시의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-117">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ac6b-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ac6b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5ac6b-119">요소</span><span class="sxs-lookup"><span data-stu-id="5ac6b-119">Element</span></span>|<span data-ttu-id="5ac6b-120">설명</span><span class="sxs-lookup"><span data-stu-id="5ac6b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ac6b-121">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="5ac6b-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5ac6b-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ac6b-123">설명</span><span class="sxs-lookup"><span data-stu-id="5ac6b-123">Remarks</span></span>  

 <span data-ttu-id="5ac6b-124">이 서비스 동작은 서비스 엔드포인트에 메시지를 전송하는 워크플로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-124">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="5ac6b-125">이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-125">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="5ac6b-126">기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="5ac6b-126">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="5ac6b-127"><xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="5ac6b-127">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="5ac6b-128">구성에 정의된 엔드포인트가 있는 워크플로의 경우 기본적으로 Send 활동에 캐싱을 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-128">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="5ac6b-129">기본 캐시 공유 수준 및 채널 팩터리 및 채널 캐시의 캐시 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 하세요. [Send 활동의 캐시 공유 수준 변경](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-129">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ac6b-130">예제</span><span class="sxs-lookup"><span data-stu-id="5ac6b-130">Example</span></span>  

 <span data-ttu-id="5ac6b-131">호스팅된 워크플로 서비스의 경우 애플리케이션 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-131">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="5ac6b-132">이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-132">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="5ac6b-133">다음 예제에서는 `MyChannelCacheBehavior`  사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 하 여 서비스 동작을 포함 하는 구성 파일의 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ac6b-133">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="5ac6b-134">이 서비스 동작은 특성을 통해 서비스에 추가 됩니다 `behaviorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="5ac6b-134">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ac6b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ac6b-135">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="5ac6b-136">Send 활동의 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="5ac6b-136">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
