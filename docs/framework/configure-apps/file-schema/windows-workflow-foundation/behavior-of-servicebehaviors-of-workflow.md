---
title: <behavior>워크플로우의 <serviceBehaviors>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152322"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="e38e9-102">\<\<동작> 워크플로></span><span class="sxs-lookup"><span data-stu-id="e38e9-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="e38e9-103">**동작** 요소에는 서비스 동작에 대한 설정 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="e38e9-104">각 동작은 해당 **이름으로**인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="e38e9-105">서비스는 [ \<끝점>](../wcf/endpoint-element.md) 요소의 **behaviorConfigurationConfiguration** 특성을 사용하여 이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="e38e9-106">따라서 설정을 다시 정의하지 않고도 엔드포인트에서 일반 동작 구성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="e38e9-107">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e38e9-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e38e9-108">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e38e9-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e38e9-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>동작**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e38e9-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="e38e9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스 행동>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e38e9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="e38e9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<행동>**</span><span class="sxs-lookup"><span data-stu-id="e38e9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e38e9-112">구문</span><span class="sxs-lookup"><span data-stu-id="e38e9-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e38e9-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e38e9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e38e9-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e38e9-115">특성</span><span class="sxs-lookup"><span data-stu-id="e38e9-115">Attributes</span></span>  
  
|<span data-ttu-id="e38e9-116">attribute</span><span class="sxs-lookup"><span data-stu-id="e38e9-116">Attribute</span></span>|<span data-ttu-id="e38e9-117">Description</span><span class="sxs-lookup"><span data-stu-id="e38e9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e38e9-118">name</span><span class="sxs-lookup"><span data-stu-id="e38e9-118">name</span></span>|<span data-ttu-id="e38e9-119">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="e38e9-120">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e38e9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e38e9-121">Child Elements</span></span>  
  
|<span data-ttu-id="e38e9-122">요소</span><span class="sxs-lookup"><span data-stu-id="e38e9-122">Element</span></span>|<span data-ttu-id="e38e9-123">Description</span><span class="sxs-lookup"><span data-stu-id="e38e9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e38e9-124">\<버퍼>수신</span><span class="sxs-lookup"><span data-stu-id="e38e9-124">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="e38e9-125">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-125">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="e38e9-126">\<라우팅></span><span class="sxs-lookup"><span data-stu-id="e38e9-126">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="e38e9-127">서비스가 <xref:System.Activities.Tracking.EtwTrackingParticipant>를 통해 ETW 추적을 사용할 수 있도록 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-127">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="e38e9-128">\<sendMessage채널Cache></span><span class="sxs-lookup"><span data-stu-id="e38e9-128">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="e38e9-129">캐시 공유 수준, 채널 팩터리 캐시 설정 및 Send 메시징 활동을 사용하여 서비스 엔드포인트로 메시지를 전송하는 워크플로를 위한 채널 캐시 설정에 대한 사용자 지정을 가능하게 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-129">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="e38e9-130">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="e38e9-130">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="e38e9-131">워크플로 서비스 인스턴스의 상태 정보를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 유지하도록 지원하는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 기능을 구성하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-131">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="e38e9-132">\<워크플로유유></span><span class="sxs-lookup"><span data-stu-id="e38e9-132">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="e38e9-133">유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-133">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="e38e9-134">\<워크플로인스턴스관리></span><span class="sxs-lookup"><span data-stu-id="e38e9-134">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="e38e9-135">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-135">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="e38e9-136">\<워크플로처리처리되지 않은예외></span><span class="sxs-lookup"><span data-stu-id="e38e9-136">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="e38e9-137">워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-137">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e38e9-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e38e9-138">Parent Elements</span></span>  
  
|<span data-ttu-id="e38e9-139">요소</span><span class="sxs-lookup"><span data-stu-id="e38e9-139">Element</span></span>|<span data-ttu-id="e38e9-140">Description</span><span class="sxs-lookup"><span data-stu-id="e38e9-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e38e9-141">\<서비스 행동></span><span class="sxs-lookup"><span data-stu-id="e38e9-141">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="e38e9-142">서비스 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e9-142">A collection of service behavior elements.</span></span>|
