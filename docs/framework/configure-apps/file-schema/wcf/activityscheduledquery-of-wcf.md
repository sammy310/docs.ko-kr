---
description: '다음에 대 한 자세한 정보: <activityScheduledQuery> WCF'
title: <activityScheduledQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b1b5f971dccfbc650ee12a08a9ae2fa7b745db50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802361"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="5eea6-103">\<activityScheduledQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="5eea6-103">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="5eea6-104">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-104">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="5eea6-105">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-105">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="5eea6-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eea6-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="5eea6-107">구문</span><span class="sxs-lookup"><span data-stu-id="5eea6-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eea6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5eea6-108">Attributes and elements</span></span>  

<span data-ttu-id="5eea6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eea6-110">특성</span><span class="sxs-lookup"><span data-stu-id="5eea6-110">Attributes</span></span>  
  
|<span data-ttu-id="5eea6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="5eea6-111">Attribute</span></span>|<span data-ttu-id="5eea6-112">설명</span><span class="sxs-lookup"><span data-stu-id="5eea6-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="5eea6-113">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-113">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="5eea6-114">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5eea6-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5eea6-115">Child elements</span></span>

<span data-ttu-id="5eea6-116">없음</span><span class="sxs-lookup"><span data-stu-id="5eea6-116">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="5eea6-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5eea6-117">Parent elements</span></span>  
  
|<span data-ttu-id="5eea6-118">요소</span><span class="sxs-lookup"><span data-stu-id="5eea6-118">Element</span></span>|<span data-ttu-id="5eea6-119">설명</span><span class="sxs-lookup"><span data-stu-id="5eea6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="5eea6-120">부모 활동에 의해 실행이 예약 된 활동을 추적 하는 데 사용 되는 쿼리의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5eea6-120">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5eea6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eea6-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="5eea6-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="5eea6-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5eea6-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="5eea6-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
