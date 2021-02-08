---
description: 다음에 대해 자세히 알아보세요. <activityScheduledQuery>
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 72aa9c2d3480488d4468d008fa8a4306929c190d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802114"
---
# \<activityScheduledQuery>

<span data-ttu-id="fbbad-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="fbbad-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="fbbad-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbbad-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="fbbad-105">구문</span><span class="sxs-lookup"><span data-stu-id="fbbad-105">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbbad-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fbbad-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fbbad-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbbad-108">특성</span><span class="sxs-lookup"><span data-stu-id="fbbad-108">Attributes</span></span>  
  
|<span data-ttu-id="fbbad-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fbbad-109">Attribute</span></span>|<span data-ttu-id="fbbad-110">설명</span><span class="sxs-lookup"><span data-stu-id="fbbad-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbbad-111">activityName</span><span class="sxs-lookup"><span data-stu-id="fbbad-111">activityName</span></span>|<span data-ttu-id="fbbad-112">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="fbbad-113">childActivityName</span><span class="sxs-lookup"><span data-stu-id="fbbad-113">childActivityName</span></span>|<span data-ttu-id="fbbad-114">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbbad-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fbbad-115">Child Elements</span></span>  

 <span data-ttu-id="fbbad-116">없음</span><span class="sxs-lookup"><span data-stu-id="fbbad-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbbad-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fbbad-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fbbad-118">요소</span><span class="sxs-lookup"><span data-stu-id="fbbad-118">Element</span></span>|<span data-ttu-id="fbbad-119">설명</span><span class="sxs-lookup"><span data-stu-id="fbbad-119">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="fbbad-120">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbad-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbbad-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbbad-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fbbad-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="fbbad-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fbbad-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="fbbad-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
