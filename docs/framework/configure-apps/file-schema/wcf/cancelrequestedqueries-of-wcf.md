---
description: '다음에 대 한 자세한 정보: <cancelRequestedQueries> WCF'
title: <cancelRequestedQueries> WCF의
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 3850d7efd01f9092312567a0eba68a6e9547baad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639187"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="35230-103">\<cancelRequestedQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="35230-103">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="35230-104">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="35230-104">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="35230-105">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="35230-105">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="35230-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35230-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="35230-107">구문</span><span class="sxs-lookup"><span data-stu-id="35230-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35230-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="35230-108">Attributes and elements</span></span>  

<span data-ttu-id="35230-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35230-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35230-110">특성</span><span class="sxs-lookup"><span data-stu-id="35230-110">Attributes</span></span>

<span data-ttu-id="35230-111">없음</span><span class="sxs-lookup"><span data-stu-id="35230-111">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="35230-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="35230-112">Child elements</span></span>
  
|<span data-ttu-id="35230-113">요소</span><span class="sxs-lookup"><span data-stu-id="35230-113">Element</span></span>|<span data-ttu-id="35230-114">설명</span><span class="sxs-lookup"><span data-stu-id="35230-114">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="35230-115">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="35230-115">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35230-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="35230-116">Parent elements</span></span>  
  
|<span data-ttu-id="35230-117">요소</span><span class="sxs-lookup"><span data-stu-id="35230-117">Element</span></span>|<span data-ttu-id="35230-118">설명</span><span class="sxs-lookup"><span data-stu-id="35230-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="35230-119"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="35230-119">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35230-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35230-120">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="35230-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="35230-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="35230-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="35230-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
