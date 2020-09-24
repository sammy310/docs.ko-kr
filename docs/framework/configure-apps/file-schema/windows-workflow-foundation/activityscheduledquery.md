---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 207931f68303883c29161cc28a5fc1974d01b6b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148739"
---
# \<activityScheduledQuery>

<span data-ttu-id="34fe7-101">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="34fe7-102">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="34fe7-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34fe7-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="34fe7-104">구문</span><span class="sxs-lookup"><span data-stu-id="34fe7-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34fe7-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34fe7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="34fe7-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34fe7-107">특성</span><span class="sxs-lookup"><span data-stu-id="34fe7-107">Attributes</span></span>  
  
|<span data-ttu-id="34fe7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="34fe7-108">Attribute</span></span>|<span data-ttu-id="34fe7-109">설명</span><span class="sxs-lookup"><span data-stu-id="34fe7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34fe7-110">activityName</span><span class="sxs-lookup"><span data-stu-id="34fe7-110">activityName</span></span>|<span data-ttu-id="34fe7-111">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="34fe7-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="34fe7-112">childActivityName</span></span>|<span data-ttu-id="34fe7-113">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34fe7-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34fe7-114">Child Elements</span></span>  

 <span data-ttu-id="34fe7-115">없음</span><span class="sxs-lookup"><span data-stu-id="34fe7-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34fe7-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34fe7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="34fe7-117">요소</span><span class="sxs-lookup"><span data-stu-id="34fe7-117">Element</span></span>|<span data-ttu-id="34fe7-118">설명</span><span class="sxs-lookup"><span data-stu-id="34fe7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="34fe7-119">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="34fe7-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34fe7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34fe7-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="34fe7-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="34fe7-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="34fe7-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="34fe7-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
