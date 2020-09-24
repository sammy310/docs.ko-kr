---
title: <activityScheduledQueries> WCF의
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 86f196437b2230d6541570aa8994d99e7b340f66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151196"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="9c574-102">\<activityScheduledQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="9c574-102">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="9c574-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c574-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9c574-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9c574-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="9c574-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c574-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="9c574-106">구문</span><span class="sxs-lookup"><span data-stu-id="9c574-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c574-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9c574-107">Attributes and elements</span></span>  

<span data-ttu-id="9c574-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c574-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c574-109">특성</span><span class="sxs-lookup"><span data-stu-id="9c574-109">Attributes</span></span>  

<span data-ttu-id="9c574-110">없음</span><span class="sxs-lookup"><span data-stu-id="9c574-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c574-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9c574-111">Child elements</span></span>  
  
|<span data-ttu-id="9c574-112">요소</span><span class="sxs-lookup"><span data-stu-id="9c574-112">Element</span></span>|<span data-ttu-id="9c574-113">설명</span><span class="sxs-lookup"><span data-stu-id="9c574-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="9c574-114">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="9c574-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c574-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9c574-115">Parent elements</span></span>  
  
|<span data-ttu-id="9c574-116">요소</span><span class="sxs-lookup"><span data-stu-id="9c574-116">Element</span></span>|<span data-ttu-id="9c574-117">설명</span><span class="sxs-lookup"><span data-stu-id="9c574-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="9c574-118">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9c574-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c574-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c574-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="9c574-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9c574-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c574-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9c574-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
