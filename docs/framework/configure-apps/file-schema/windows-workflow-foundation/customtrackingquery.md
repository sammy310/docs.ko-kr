---
description: 다음에 대해 자세히 알아보세요. <customTrackingQuery>
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 24857aca39aad825a3dd4eca83fa3a51ec440b25
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795094"
---
# \<customTrackingQuery>

<span data-ttu-id="d66f6-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="d66f6-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="d66f6-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d66f6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d66f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="d66f6-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d66f6-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d66f6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d66f6-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d66f6-108">특성</span><span class="sxs-lookup"><span data-stu-id="d66f6-108">Attributes</span></span>  
  
|<span data-ttu-id="d66f6-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d66f6-109">Attribute</span></span>|<span data-ttu-id="d66f6-110">설명</span><span class="sxs-lookup"><span data-stu-id="d66f6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d66f6-111">activityName</span><span class="sxs-lookup"><span data-stu-id="d66f6-111">activityName</span></span>|<span data-ttu-id="d66f6-112">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="d66f6-113">name</span><span class="sxs-lookup"><span data-stu-id="d66f6-113">name</span></span>|<span data-ttu-id="d66f6-114">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-114">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d66f6-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d66f6-115">Child Elements</span></span>  

 <span data-ttu-id="d66f6-116">없음</span><span class="sxs-lookup"><span data-stu-id="d66f6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d66f6-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d66f6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d66f6-118">요소</span><span class="sxs-lookup"><span data-stu-id="d66f6-118">Element</span></span>|<span data-ttu-id="d66f6-119">설명</span><span class="sxs-lookup"><span data-stu-id="d66f6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="d66f6-120">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d66f6-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d66f6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d66f6-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d66f6-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d66f6-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d66f6-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d66f6-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
