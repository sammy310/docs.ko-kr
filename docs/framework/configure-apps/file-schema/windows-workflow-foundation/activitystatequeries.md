---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398952"
---
# \<activityStateQueries>
<span data-ttu-id="f4fb3-101">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f4fb3-102">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f4fb3-103">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f4fb3-104">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="f4fb3-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="f4fb3-106">구문</span><span class="sxs-lookup"><span data-stu-id="f4fb3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4fb3-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f4fb3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f4fb3-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4fb3-109">특성</span><span class="sxs-lookup"><span data-stu-id="f4fb3-109">Attributes</span></span>  
 <span data-ttu-id="f4fb3-110">없음</span><span class="sxs-lookup"><span data-stu-id="f4fb3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4fb3-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f4fb3-111">Child Elements</span></span>  
  
|<span data-ttu-id="f4fb3-112">요소</span><span class="sxs-lookup"><span data-stu-id="f4fb3-112">Element</span></span>|<span data-ttu-id="f4fb3-113">Description</span><span class="sxs-lookup"><span data-stu-id="f4fb3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="f4fb3-114">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4fb3-115">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4fb3-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f4fb3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f4fb3-117">요소</span><span class="sxs-lookup"><span data-stu-id="f4fb3-117">Element</span></span>|<span data-ttu-id="f4fb3-118">Description</span><span class="sxs-lookup"><span data-stu-id="f4fb3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f4fb3-119">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4fb3-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4fb3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4fb3-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f4fb3-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f4fb3-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f4fb3-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f4fb3-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
