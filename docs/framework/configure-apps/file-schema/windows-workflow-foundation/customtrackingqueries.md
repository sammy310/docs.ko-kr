---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152263"
---
# \<customTrackingQueries>
<span data-ttu-id="03504-101">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03504-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="03504-102">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03504-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="03504-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03504-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="03504-104">구문</span><span class="sxs-lookup"><span data-stu-id="03504-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03504-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="03504-105">Attributes and Elements</span></span>  
 <span data-ttu-id="03504-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03504-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03504-107">특성</span><span class="sxs-lookup"><span data-stu-id="03504-107">Attributes</span></span>  
 <span data-ttu-id="03504-108">없음</span><span class="sxs-lookup"><span data-stu-id="03504-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03504-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="03504-109">Child Elements</span></span>  
  
|<span data-ttu-id="03504-110">요소</span><span class="sxs-lookup"><span data-stu-id="03504-110">Element</span></span>|<span data-ttu-id="03504-111">Description</span><span class="sxs-lookup"><span data-stu-id="03504-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="03504-112">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="03504-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03504-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="03504-113">Parent Elements</span></span>  
  
|<span data-ttu-id="03504-114">요소</span><span class="sxs-lookup"><span data-stu-id="03504-114">Element</span></span>|<span data-ttu-id="03504-115">Description</span><span class="sxs-lookup"><span data-stu-id="03504-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="03504-116">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="03504-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03504-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03504-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="03504-118">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="03504-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="03504-119">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="03504-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
