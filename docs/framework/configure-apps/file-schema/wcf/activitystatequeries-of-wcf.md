---
description: '다음에 대 한 자세한 정보: <activityStateQueries> WCF'
title: <activityStateQueries> WCF의
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 00795a26a37f62fae8aa884b5a4188be79453186
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782236"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="2952b-103">\<activityStateQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="2952b-103">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="2952b-104">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-104">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2952b-105">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-105">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2952b-106">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-106">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2952b-107">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-107">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="2952b-108">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2952b-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="2952b-109">구문</span><span class="sxs-lookup"><span data-stu-id="2952b-109">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="2952b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2952b-110">Attributes and elements</span></span>

<span data-ttu-id="2952b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-111">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2952b-112">특성</span><span class="sxs-lookup"><span data-stu-id="2952b-112">Attributes</span></span>  

<span data-ttu-id="2952b-113">없음</span><span class="sxs-lookup"><span data-stu-id="2952b-113">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="2952b-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2952b-114">Child elements</span></span>

|<span data-ttu-id="2952b-115">요소</span><span class="sxs-lookup"><span data-stu-id="2952b-115">Element</span></span>|<span data-ttu-id="2952b-116">설명</span><span class="sxs-lookup"><span data-stu-id="2952b-116">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="2952b-117">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-117">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2952b-118">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-118">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2952b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2952b-119">Parent elements</span></span>

|<span data-ttu-id="2952b-120">요소</span><span class="sxs-lookup"><span data-stu-id="2952b-120">Element</span></span>|<span data-ttu-id="2952b-121">설명</span><span class="sxs-lookup"><span data-stu-id="2952b-121">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2952b-122">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2952b-122">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2952b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2952b-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="2952b-124">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="2952b-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2952b-125">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="2952b-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
