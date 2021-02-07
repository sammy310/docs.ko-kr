---
description: 다음에 대해 자세히 알아보세요. <activityScheduledQueries>
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 1f43642edffea782a9e5257a3568868645994a46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729838"
---
# \<activityScheduledQueries>

<span data-ttu-id="293c5-102">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="293c5-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="293c5-103">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="293c5-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="293c5-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="293c5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="293c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="293c5-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="293c5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="293c5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="293c5-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="293c5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="293c5-108">특성</span><span class="sxs-lookup"><span data-stu-id="293c5-108">Attributes</span></span>  

 <span data-ttu-id="293c5-109">없음</span><span class="sxs-lookup"><span data-stu-id="293c5-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="293c5-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="293c5-110">Child Elements</span></span>  
  
|<span data-ttu-id="293c5-111">요소</span><span class="sxs-lookup"><span data-stu-id="293c5-111">Element</span></span>|<span data-ttu-id="293c5-112">설명</span><span class="sxs-lookup"><span data-stu-id="293c5-112">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="293c5-113">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="293c5-113">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="293c5-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="293c5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="293c5-115">요소</span><span class="sxs-lookup"><span data-stu-id="293c5-115">Element</span></span>|<span data-ttu-id="293c5-116">설명</span><span class="sxs-lookup"><span data-stu-id="293c5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="293c5-117">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="293c5-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="293c5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="293c5-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="293c5-119">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="293c5-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="293c5-120">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="293c5-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
