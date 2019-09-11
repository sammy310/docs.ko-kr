---
title: <customTrackingQueries>WCF의
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855438"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="a07c6-102">\<WCF의 customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="a07c6-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="a07c6-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a07c6-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a07c6-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a07c6-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="a07c6-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a07c6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a07c6-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a07c6-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a07c6-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a07c6-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a07c6-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a07c6-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a07c6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="a07c6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a07c6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a07c6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a07c6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a07c6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a07c6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQueries >**</span><span class="sxs-lookup"><span data-stu-id="a07c6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a07c6-113">구문</span><span class="sxs-lookup"><span data-stu-id="a07c6-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a07c6-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a07c6-114">Attributes and elements</span></span>

<span data-ttu-id="a07c6-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a07c6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a07c6-116">특성</span><span class="sxs-lookup"><span data-stu-id="a07c6-116">Attributes</span></span>

<span data-ttu-id="a07c6-117">없음</span><span class="sxs-lookup"><span data-stu-id="a07c6-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a07c6-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a07c6-118">Child elements</span></span>
  
|<span data-ttu-id="a07c6-119">요소</span><span class="sxs-lookup"><span data-stu-id="a07c6-119">Element</span></span>|<span data-ttu-id="a07c6-120">설명</span><span class="sxs-lookup"><span data-stu-id="a07c6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a07c6-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="a07c6-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="a07c6-122">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="a07c6-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a07c6-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a07c6-123">Parent elements</span></span>  
  
|<span data-ttu-id="a07c6-124">요소</span><span class="sxs-lookup"><span data-stu-id="a07c6-124">Element</span></span>|<span data-ttu-id="a07c6-125">Description</span><span class="sxs-lookup"><span data-stu-id="a07c6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a07c6-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a07c6-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a07c6-127">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a07c6-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a07c6-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="a07c6-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a07c6-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a07c6-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a07c6-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a07c6-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
