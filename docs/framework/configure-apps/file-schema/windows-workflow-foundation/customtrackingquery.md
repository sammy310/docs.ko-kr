---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152211"
---
# \<customTrackingQuery>
<span data-ttu-id="da030-101">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da030-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="da030-102">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="da030-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="da030-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da030-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="da030-104">구문</span><span class="sxs-lookup"><span data-stu-id="da030-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da030-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="da030-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da030-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="da030-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da030-107">특성</span><span class="sxs-lookup"><span data-stu-id="da030-107">Attributes</span></span>  
  
|<span data-ttu-id="da030-108">attribute</span><span class="sxs-lookup"><span data-stu-id="da030-108">Attribute</span></span>|<span data-ttu-id="da030-109">Description</span><span class="sxs-lookup"><span data-stu-id="da030-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da030-110">activityName</span><span class="sxs-lookup"><span data-stu-id="da030-110">activityName</span></span>|<span data-ttu-id="da030-111">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da030-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="da030-112">name</span><span class="sxs-lookup"><span data-stu-id="da030-112">name</span></span>|<span data-ttu-id="da030-113">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da030-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da030-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="da030-114">Child Elements</span></span>  
 <span data-ttu-id="da030-115">없음</span><span class="sxs-lookup"><span data-stu-id="da030-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da030-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="da030-116">Parent Elements</span></span>  
  
|<span data-ttu-id="da030-117">요소</span><span class="sxs-lookup"><span data-stu-id="da030-117">Element</span></span>|<span data-ttu-id="da030-118">Description</span><span class="sxs-lookup"><span data-stu-id="da030-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="da030-119">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="da030-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da030-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da030-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="da030-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="da030-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="da030-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="da030-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
