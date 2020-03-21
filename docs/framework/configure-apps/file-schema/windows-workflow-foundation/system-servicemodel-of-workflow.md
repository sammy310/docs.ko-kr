---
title: <system.service워크의>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151951"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="ea95f-102">\<system.service워크의 모델></span><span class="sxs-lookup"><span data-stu-id="ea95f-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="ea95f-103">이 구성 섹션에는 모든 워크플로 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="ea95f-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea95f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea95f-105">&nbsp;&nbsp;**\<시스템. 서비스 모델>**</span><span class="sxs-lookup"><span data-stu-id="ea95f-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea95f-106">구문</span><span class="sxs-lookup"><span data-stu-id="ea95f-106">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore
          connectionStringName="String"
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>
     <participants>
      <add name="String"
           profileName="String"  
           type="String" />
     </participants>
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea95f-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ea95f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ea95f-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea95f-109">특성</span><span class="sxs-lookup"><span data-stu-id="ea95f-109">Attributes</span></span>  
 <span data-ttu-id="ea95f-110">None</span><span class="sxs-lookup"><span data-stu-id="ea95f-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea95f-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ea95f-111">Child Elements</span></span>  
  
|<span data-ttu-id="ea95f-112">요소</span><span class="sxs-lookup"><span data-stu-id="ea95f-112">Element</span></span>|<span data-ttu-id="ea95f-113">Description</span><span class="sxs-lookup"><span data-stu-id="ea95f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea95f-114">\<>동작</span><span class="sxs-lookup"><span data-stu-id="ea95f-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="ea95f-115">이 섹션에서는 **serviceBehaviors 컬렉션을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea95f-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="ea95f-116">컬렉션의 각 요소는 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="ea95f-117">각 동작 요소는 고유한 **이름** 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="ea95f-118">\<추적></span><span class="sxs-lookup"><span data-stu-id="ea95f-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="ea95f-119">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="ea95f-120">워크플로 추적 및 구성에 대한 자세한 내용은 [워크플로 추적 및 추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [워크플로에 대한 추적 구성을](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea95f-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea95f-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ea95f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ea95f-122">요소</span><span class="sxs-lookup"><span data-stu-id="ea95f-122">Element</span></span>|<span data-ttu-id="ea95f-123">Description</span><span class="sxs-lookup"><span data-stu-id="ea95f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea95f-124">\<구성></span><span class="sxs-lookup"><span data-stu-id="ea95f-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="ea95f-125">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ea95f-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
