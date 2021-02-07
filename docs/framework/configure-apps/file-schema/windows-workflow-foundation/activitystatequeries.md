---
description: 다음에 대해 자세히 알아보세요. <activityStateQueries>
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: ad324d88c481016d85b8e58ccc0857b7773d8328
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748962"
---
# \<activityStateQueries>

<span data-ttu-id="be521-102">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be521-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="be521-103">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be521-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="be521-104">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be521-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="be521-105">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be521-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="be521-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be521-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="be521-107">구문</span><span class="sxs-lookup"><span data-stu-id="be521-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be521-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="be521-108">Attributes and Elements</span></span>  

 <span data-ttu-id="be521-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be521-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be521-110">특성</span><span class="sxs-lookup"><span data-stu-id="be521-110">Attributes</span></span>  

 <span data-ttu-id="be521-111">없음</span><span class="sxs-lookup"><span data-stu-id="be521-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be521-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="be521-112">Child Elements</span></span>  
  
|<span data-ttu-id="be521-113">요소</span><span class="sxs-lookup"><span data-stu-id="be521-113">Element</span></span>|<span data-ttu-id="be521-114">설명</span><span class="sxs-lookup"><span data-stu-id="be521-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="be521-115">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="be521-115">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="be521-116">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="be521-116">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be521-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="be521-117">Parent Elements</span></span>  
  
|<span data-ttu-id="be521-118">요소</span><span class="sxs-lookup"><span data-stu-id="be521-118">Element</span></span>|<span data-ttu-id="be521-119">설명</span><span class="sxs-lookup"><span data-stu-id="be521-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="be521-120">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="be521-120">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be521-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be521-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="be521-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="be521-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="be521-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="be521-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
