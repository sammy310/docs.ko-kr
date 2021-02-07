---
description: 자세한 내용은 <System.servicemodel> 워크플로의
title: 워크플로의>를 <합니다.
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 393c1055d6b136ed27a297e00133f5b53d12fd38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681749"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="a0083-103">\<system.serviceModel> 워크플로</span><span class="sxs-lookup"><span data-stu-id="a0083-103">\<system.serviceModel> of workflow</span></span>

<span data-ttu-id="a0083-104">이 구성 섹션에는 모든 워크플로 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-104">This configuration section contains all the workflow configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.ServiceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="a0083-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0083-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0083-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a0083-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a0083-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0083-108">특성</span><span class="sxs-lookup"><span data-stu-id="a0083-108">Attributes</span></span>  

 <span data-ttu-id="a0083-109">None</span><span class="sxs-lookup"><span data-stu-id="a0083-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0083-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a0083-110">Child Elements</span></span>  
  
|<span data-ttu-id="a0083-111">요소</span><span class="sxs-lookup"><span data-stu-id="a0083-111">Element</span></span>|<span data-ttu-id="a0083-112">설명</span><span class="sxs-lookup"><span data-stu-id="a0083-112">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors-of-workflow.md)|<span data-ttu-id="a0083-113">이 섹션은 **Servicebehaviors** 컬렉션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="a0083-114">컬렉션의 각 요소는 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="a0083-115">각 동작 요소는 고유한 **이름** 특성으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[\<tracking>](tracking.md)|<span data-ttu-id="a0083-116">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-116">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="a0083-117">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 워크플로 [추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 [워크플로에 대 한 추적 구성](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0083-117">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0083-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a0083-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a0083-119">요소</span><span class="sxs-lookup"><span data-stu-id="a0083-119">Element</span></span>|<span data-ttu-id="a0083-120">설명</span><span class="sxs-lookup"><span data-stu-id="a0083-120">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="a0083-121">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a0083-121">The root element for all configuration elements in a .NET configuration file.</span></span>|
