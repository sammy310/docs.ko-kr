---
description: '다음에 대 한 자세한 정보: <activityScheduledQueries> WCF'
title: <activityScheduledQueries> WCF의
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: b92bb2827b4c8bce43e4ee0b8dc03c7be124e3da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782249"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="7407c-103">\<activityScheduledQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="7407c-103">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="7407c-104">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-104">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7407c-105">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-105">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="7407c-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7407c-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="7407c-107">구문</span><span class="sxs-lookup"><span data-stu-id="7407c-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7407c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7407c-108">Attributes and elements</span></span>  

<span data-ttu-id="7407c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7407c-110">특성</span><span class="sxs-lookup"><span data-stu-id="7407c-110">Attributes</span></span>  

<span data-ttu-id="7407c-111">없음</span><span class="sxs-lookup"><span data-stu-id="7407c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7407c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7407c-112">Child elements</span></span>  
  
|<span data-ttu-id="7407c-113">요소</span><span class="sxs-lookup"><span data-stu-id="7407c-113">Element</span></span>|<span data-ttu-id="7407c-114">설명</span><span class="sxs-lookup"><span data-stu-id="7407c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="7407c-115">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-115">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7407c-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7407c-116">Parent elements</span></span>  
  
|<span data-ttu-id="7407c-117">요소</span><span class="sxs-lookup"><span data-stu-id="7407c-117">Element</span></span>|<span data-ttu-id="7407c-118">설명</span><span class="sxs-lookup"><span data-stu-id="7407c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="7407c-119">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7407c-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7407c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7407c-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="7407c-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="7407c-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7407c-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="7407c-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
