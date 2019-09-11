---
title: <activityScheduledQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850470"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="9a3c8-102">\<WCF의 y ></span><span class="sxs-lookup"><span data-stu-id="9a3c8-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="9a3c8-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9a3c8-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="9a3c8-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9a3c8-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a3c8-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a3c8-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="9a3c8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="9a3c8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="9a3c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="9a3c8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="9a3c8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityScheduledQueries >** ](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9a3c8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="9a3c8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="9a3c8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3c8-114">구문</span><span class="sxs-lookup"><span data-stu-id="9a3c8-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a3c8-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a3c8-115">Attributes and elements</span></span>  

<span data-ttu-id="9a3c8-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a3c8-117">특성</span><span class="sxs-lookup"><span data-stu-id="9a3c8-117">Attributes</span></span>  
  
|<span data-ttu-id="9a3c8-118">특성</span><span class="sxs-lookup"><span data-stu-id="9a3c8-118">Attribute</span></span>|<span data-ttu-id="9a3c8-119">Description</span><span class="sxs-lookup"><span data-stu-id="9a3c8-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9a3c8-120">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="9a3c8-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a3c8-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a3c8-122">Child elements</span></span>

<span data-ttu-id="9a3c8-123">없음</span><span class="sxs-lookup"><span data-stu-id="9a3c8-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9a3c8-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a3c8-124">Parent elements</span></span>  
  
|<span data-ttu-id="9a3c8-125">요소</span><span class="sxs-lookup"><span data-stu-id="9a3c8-125">Element</span></span>|<span data-ttu-id="9a3c8-126">Description</span><span class="sxs-lookup"><span data-stu-id="9a3c8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a3c8-127">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="9a3c8-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="9a3c8-128">부모 활동에 의해 실행이 예약 된 활동을 추적 하는 데 사용 되는 쿼리의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3c8-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a3c8-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a3c8-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="9a3c8-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9a3c8-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9a3c8-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9a3c8-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
