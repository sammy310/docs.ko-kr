---
title: <workflowInstanceQueries>WCF의
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854776"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="aa3fa-102">\<WCF의 Workflowinstancequeries&gt ></span><span class="sxs-lookup"><span data-stu-id="aa3fa-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="aa3fa-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="aa3fa-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aa3fa-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa3fa-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa3fa-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="aa3fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="aa3fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="aa3fa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="aa3fa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="aa3fa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Workflowinstancequeries&gt >**</span><span class="sxs-lookup"><span data-stu-id="aa3fa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa3fa-112">구문</span><span class="sxs-lookup"><span data-stu-id="aa3fa-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa3fa-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-113">Attributes and elements</span></span>

<span data-ttu-id="aa3fa-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa3fa-115">특성</span><span class="sxs-lookup"><span data-stu-id="aa3fa-115">Attributes</span></span>  

<span data-ttu-id="aa3fa-116">없음</span><span class="sxs-lookup"><span data-stu-id="aa3fa-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa3fa-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-117">Child elements</span></span>  
  
|<span data-ttu-id="aa3fa-118">요소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-118">Element</span></span>|<span data-ttu-id="aa3fa-119">설명</span><span class="sxs-lookup"><span data-stu-id="aa3fa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa3fa-120">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="aa3fa-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="aa3fa-121">워크플로 인스턴스 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa3fa-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-122">Parent elements</span></span>  
  
|<span data-ttu-id="aa3fa-123">요소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-123">Element</span></span>|<span data-ttu-id="aa3fa-124">설명</span><span class="sxs-lookup"><span data-stu-id="aa3fa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa3fa-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="aa3fa-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="aa3fa-126">[ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa3fa-127">설명</span><span class="sxs-lookup"><span data-stu-id="aa3fa-127">Remarks</span></span>

<span data-ttu-id="aa3fa-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="aa3fa-129">예제</span><span class="sxs-lookup"><span data-stu-id="aa3fa-129">Example</span></span>  

<span data-ttu-id="aa3fa-130">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="aa3fa-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa3fa-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aa3fa-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="aa3fa-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aa3fa-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="aa3fa-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
