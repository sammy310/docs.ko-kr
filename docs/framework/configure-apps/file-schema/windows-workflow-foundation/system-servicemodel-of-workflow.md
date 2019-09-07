---
title: 워크플로의 >를 < 합니다.
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 757a7a132a6e765e257097d251a110297c6a40bf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398609"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="842d1-102">\<워크플로의 System.servicemodel ></span><span class="sxs-lookup"><span data-stu-id="842d1-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="842d1-103">이 구성 섹션에는 모든 워크플로 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="842d1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="842d1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="842d1-105">&nbsp;&nbsp; **\<컴퓨터. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="842d1-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842d1-106">구문</span><span class="sxs-lookup"><span data-stu-id="842d1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="842d1-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="842d1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="842d1-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="842d1-109">특성</span><span class="sxs-lookup"><span data-stu-id="842d1-109">Attributes</span></span>  
 <span data-ttu-id="842d1-110">없음</span><span class="sxs-lookup"><span data-stu-id="842d1-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="842d1-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="842d1-111">Child Elements</span></span>  
  
|<span data-ttu-id="842d1-112">요소</span><span class="sxs-lookup"><span data-stu-id="842d1-112">Element</span></span>|<span data-ttu-id="842d1-113">설명</span><span class="sxs-lookup"><span data-stu-id="842d1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="842d1-114">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="842d1-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="842d1-115">이 섹션은 **Servicebehaviors** 컬렉션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="842d1-116">컬렉션의 각 요소는 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="842d1-117">각 동작 요소는 고유한 **이름** 특성으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="842d1-118">\<tracking></span><span class="sxs-lookup"><span data-stu-id="842d1-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="842d1-119">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="842d1-120">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 워크플로 [추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 [워크플로에 대 한 추적 구성](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="842d1-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="842d1-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="842d1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="842d1-122">요소</span><span class="sxs-lookup"><span data-stu-id="842d1-122">Element</span></span>|<span data-ttu-id="842d1-123">설명</span><span class="sxs-lookup"><span data-stu-id="842d1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="842d1-124">\<구성></span><span class="sxs-lookup"><span data-stu-id="842d1-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="842d1-125">.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="842d1-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
