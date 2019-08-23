---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 6e91078a24a950c6de027d57e3883e38f19447d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945452"
---
# <a name="activitystatequeries"></a><span data-ttu-id="cf414-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="cf414-101">\<activityStateQueries></span></span>
<span data-ttu-id="cf414-102">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="cf414-103">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="cf414-104">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="cf414-105">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="cf414-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf414-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="cf414-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cf414-107">\<system.serviceModel></span></span>  
<span data-ttu-id="cf414-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="cf414-108">\<tracking></span></span>  
<span data-ttu-id="cf414-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cf414-109">\<trackingProfile></span></span>  
<span data-ttu-id="cf414-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cf414-110">\<workflow></span></span>  
<span data-ttu-id="cf414-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="cf414-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf414-112">구문</span><span class="sxs-lookup"><span data-stu-id="cf414-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf414-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cf414-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cf414-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf414-115">특성</span><span class="sxs-lookup"><span data-stu-id="cf414-115">Attributes</span></span>  
 <span data-ttu-id="cf414-116">없음</span><span class="sxs-lookup"><span data-stu-id="cf414-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf414-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cf414-117">Child Elements</span></span>  
  
|<span data-ttu-id="cf414-118">요소</span><span class="sxs-lookup"><span data-stu-id="cf414-118">Element</span></span>|<span data-ttu-id="cf414-119">Description</span><span class="sxs-lookup"><span data-stu-id="cf414-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf414-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="cf414-120">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="cf414-121">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cf414-122">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf414-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cf414-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cf414-124">요소</span><span class="sxs-lookup"><span data-stu-id="cf414-124">Element</span></span>|<span data-ttu-id="cf414-125">설명</span><span class="sxs-lookup"><span data-stu-id="cf414-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf414-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cf414-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="cf414-127">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cf414-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf414-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf414-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cf414-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="cf414-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cf414-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="cf414-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
