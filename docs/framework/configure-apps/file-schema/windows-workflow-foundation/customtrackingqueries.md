---
description: 다음에 대해 자세히 알아보세요. <customTrackingQueries>
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 3601950742eb002f43969bea4612e830d8365509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719061"
---
# \<customTrackingQueries>

<span data-ttu-id="59e78-102">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59e78-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="59e78-103">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="59e78-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="59e78-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59e78-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="59e78-105">구문</span><span class="sxs-lookup"><span data-stu-id="59e78-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59e78-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="59e78-106">Attributes and Elements</span></span>  

 <span data-ttu-id="59e78-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59e78-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59e78-108">특성</span><span class="sxs-lookup"><span data-stu-id="59e78-108">Attributes</span></span>  

 <span data-ttu-id="59e78-109">없음</span><span class="sxs-lookup"><span data-stu-id="59e78-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59e78-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="59e78-110">Child Elements</span></span>  
  
|<span data-ttu-id="59e78-111">요소</span><span class="sxs-lookup"><span data-stu-id="59e78-111">Element</span></span>|<span data-ttu-id="59e78-112">설명</span><span class="sxs-lookup"><span data-stu-id="59e78-112">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="59e78-113">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="59e78-113">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59e78-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="59e78-114">Parent Elements</span></span>  
  
|<span data-ttu-id="59e78-115">요소</span><span class="sxs-lookup"><span data-stu-id="59e78-115">Element</span></span>|<span data-ttu-id="59e78-116">설명</span><span class="sxs-lookup"><span data-stu-id="59e78-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="59e78-117">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="59e78-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59e78-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59e78-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="59e78-119">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="59e78-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="59e78-120">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="59e78-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
