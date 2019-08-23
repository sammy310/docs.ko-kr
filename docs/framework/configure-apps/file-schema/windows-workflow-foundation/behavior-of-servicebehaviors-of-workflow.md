---
title: <behavior><serviceBehaviors> of 워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946073"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="8c68d-102">\<워크플로의 \<servicebehaviors > 동작 ></span><span class="sxs-lookup"><span data-stu-id="8c68d-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="8c68d-103">**Behavior** 요소는 서비스의 동작에 대 한 설정 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="8c68d-104">각 동작은 **이름**으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="8c68d-105">서비스는 [ \<끝점 >](../wcf/endpoint-element.md) 요소의 **behaviorConfiguration** 특성을 사용 하 여이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="8c68d-106">따라서 설정을 다시 정의하지 않고도 엔드포인트에서 일반 동작 구성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="8c68d-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c68d-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c68d-108">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8c68d-108">\<behaviors></span></span>  
<span data-ttu-id="8c68d-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8c68d-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="8c68d-110">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8c68d-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c68d-111">구문</span><span class="sxs-lookup"><span data-stu-id="8c68d-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  hostLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c68d-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c68d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8c68d-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c68d-114">특성</span><span class="sxs-lookup"><span data-stu-id="8c68d-114">Attributes</span></span>  
  
|<span data-ttu-id="8c68d-115">특성</span><span class="sxs-lookup"><span data-stu-id="8c68d-115">Attribute</span></span>|<span data-ttu-id="8c68d-116">Description</span><span class="sxs-lookup"><span data-stu-id="8c68d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c68d-117">name</span><span class="sxs-lookup"><span data-stu-id="8c68d-117">name</span></span>|<span data-ttu-id="8c68d-118">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="8c68d-119">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c68d-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c68d-120">Child Elements</span></span>  
  
|<span data-ttu-id="8c68d-121">요소</span><span class="sxs-lookup"><span data-stu-id="8c68d-121">Element</span></span>|<span data-ttu-id="8c68d-122">Description</span><span class="sxs-lookup"><span data-stu-id="8c68d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c68d-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="8c68d-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="8c68d-124">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="8c68d-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="8c68d-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="8c68d-126">사용 하 여 ETW 추적을 활용할 수 있도록 허용 하는 서비스 동작을 <xref:System.Activities.Tracking.EtwTrackingParticipant>입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="8c68d-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="8c68d-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="8c68d-128">메시지 보내기 작업을 사용 하 여 서비스 끝점으로 메시지를 보내는 워크플로를 위한 채널 캐시 설정, 캐시 공유 수준의 사용자 지정 및 채널 팩터리 캐시 설정을 가능 하 게 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="8c68d-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="8c68d-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="8c68d-130">구성할 수 있는 서비스 동작을 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 워크플로 서비스 인스턴스를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 대 한 상태 정보 유지를 지 원하는 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="8c68d-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="8c68d-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="8c68d-132">유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="8c68d-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="8c68d-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="8c68d-134">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="8c68d-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="8c68d-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="8c68d-136">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c68d-137">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c68d-137">Parent Elements</span></span>  
  
|<span data-ttu-id="8c68d-138">요소</span><span class="sxs-lookup"><span data-stu-id="8c68d-138">Element</span></span>|<span data-ttu-id="8c68d-139">Description</span><span class="sxs-lookup"><span data-stu-id="8c68d-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c68d-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8c68d-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="8c68d-141">서비스 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c68d-141">A collection of service behavior elements.</span></span>|
