---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398952"
---
# <a name="activitystatequeries"></a><span data-ttu-id="d80d0-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="d80d0-101">\<activityStateQueries></span></span>
<span data-ttu-id="d80d0-102">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="d80d0-103">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="d80d0-104">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="d80d0-105">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="d80d0-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d80d0-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d80d0-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d80d0-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d80d0-108">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d80d0-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="d80d0-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<추적 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="d80d0-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="d80d0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Tracking&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="d80d0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="d80d0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<워크플로 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d80d0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="d80d0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQueries >**</span><span class="sxs-lookup"><span data-stu-id="d80d0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80d0-113">구문</span><span class="sxs-lookup"><span data-stu-id="d80d0-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d80d0-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d80d0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="d80d0-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d80d0-116">특성</span><span class="sxs-lookup"><span data-stu-id="d80d0-116">Attributes</span></span>  
 <span data-ttu-id="d80d0-117">없음</span><span class="sxs-lookup"><span data-stu-id="d80d0-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d80d0-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d80d0-118">Child Elements</span></span>  
  
|<span data-ttu-id="d80d0-119">요소</span><span class="sxs-lookup"><span data-stu-id="d80d0-119">Element</span></span>|<span data-ttu-id="d80d0-120">설명</span><span class="sxs-lookup"><span data-stu-id="d80d0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d80d0-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d80d0-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="d80d0-122">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d80d0-123">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d80d0-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d80d0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d80d0-125">요소</span><span class="sxs-lookup"><span data-stu-id="d80d0-125">Element</span></span>|<span data-ttu-id="d80d0-126">Description</span><span class="sxs-lookup"><span data-stu-id="d80d0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d80d0-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d80d0-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="d80d0-128">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d80d0-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d80d0-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="d80d0-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d80d0-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d80d0-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d80d0-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d80d0-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
