---
description: '다음에 대 한 자세한 정보: <workflowInstanceQuery> WCF'
title: <workflowInstanceQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 30df1a6b4fc0aeac5b7094f1a1f7d9d02599c94d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682321"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="067fb-103">\<workflowInstanceQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="067fb-103">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="067fb-104">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-104">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="067fb-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="067fb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="067fb-106">구문</span><span class="sxs-lookup"><span data-stu-id="067fb-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="067fb-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="067fb-107">Attributes and elements</span></span>  

<span data-ttu-id="067fb-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="067fb-109">특성</span><span class="sxs-lookup"><span data-stu-id="067fb-109">Attributes</span></span>  

<span data-ttu-id="067fb-110">없음</span><span class="sxs-lookup"><span data-stu-id="067fb-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="067fb-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="067fb-111">Child elements</span></span>  
  
|<span data-ttu-id="067fb-112">요소</span><span class="sxs-lookup"><span data-stu-id="067fb-112">Element</span></span>|<span data-ttu-id="067fb-113">설명</span><span class="sxs-lookup"><span data-stu-id="067fb-113">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="067fb-114">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-114">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="067fb-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="067fb-115">Parent elements</span></span>  
  
|<span data-ttu-id="067fb-116">요소</span><span class="sxs-lookup"><span data-stu-id="067fb-116">Element</span></span>|<span data-ttu-id="067fb-117">설명</span><span class="sxs-lookup"><span data-stu-id="067fb-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQueries>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="067fb-118">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-118">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="067fb-119">설명</span><span class="sxs-lookup"><span data-stu-id="067fb-119">Remarks</span></span>  

<span data-ttu-id="067fb-120"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-120">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="067fb-121">예제</span><span class="sxs-lookup"><span data-stu-id="067fb-121">Example</span></span>  

<span data-ttu-id="067fb-122">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="067fb-122">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="067fb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="067fb-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="067fb-124">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="067fb-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="067fb-125">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="067fb-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
