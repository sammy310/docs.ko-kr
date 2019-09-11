---
title: <faultPropagationQueries>WCF의
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855269"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="3f734-102">\<WCF의 faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3f734-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="3f734-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3f734-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3f734-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3f734-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="3f734-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f734-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3f734-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f734-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f734-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3f734-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3f734-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3f734-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="3f734-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<프로필 >** </span><span class="sxs-lookup"><span data-stu-id="3f734-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="3f734-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3f734-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="3f734-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3f734-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="3f734-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="3f734-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f734-115">구문</span><span class="sxs-lookup"><span data-stu-id="3f734-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f734-116">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3f734-116">Attributes and elements</span></span>

<span data-ttu-id="3f734-117">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3f734-118">특성</span><span class="sxs-lookup"><span data-stu-id="3f734-118">Attributes</span></span>

<span data-ttu-id="3f734-119">없음</span><span class="sxs-lookup"><span data-stu-id="3f734-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3f734-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f734-120">Child elements</span></span>

|<span data-ttu-id="3f734-121">요소</span><span class="sxs-lookup"><span data-stu-id="3f734-121">Element</span></span>|<span data-ttu-id="3f734-122">설명</span><span class="sxs-lookup"><span data-stu-id="3f734-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f734-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="3f734-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="3f734-124">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3f734-125">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3f734-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f734-126">Parent elements</span></span>  
  
|<span data-ttu-id="3f734-127">요소</span><span class="sxs-lookup"><span data-stu-id="3f734-127">Element</span></span>|<span data-ttu-id="3f734-128">Description</span><span class="sxs-lookup"><span data-stu-id="3f734-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f734-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3f734-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="3f734-130">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3f734-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f734-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f734-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3f734-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3f734-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3f734-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3f734-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
