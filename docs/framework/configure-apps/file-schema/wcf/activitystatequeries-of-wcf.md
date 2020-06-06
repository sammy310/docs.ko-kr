---
title: <activityStateQueries>WCF의
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850579"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="4e9e4-102">\<activityStateQueries>WCF의</span><span class="sxs-lookup"><span data-stu-id="4e9e4-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="4e9e4-103">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="4e9e4-104">예를 들어, 워크플로 인스턴스 내에서 "전자 메일 보내기" 작업이 완료 될 때마다 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="4e9e4-105">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="4e9e4-106">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="4e9e4-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="4e9e4-108">구문</span><span class="sxs-lookup"><span data-stu-id="4e9e4-108">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="4e9e4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e9e4-109">Attributes and elements</span></span>

<span data-ttu-id="4e9e4-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4e9e4-111">특성</span><span class="sxs-lookup"><span data-stu-id="4e9e4-111">Attributes</span></span>  

<span data-ttu-id="4e9e4-112">없음</span><span class="sxs-lookup"><span data-stu-id="4e9e4-112">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="4e9e4-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e9e4-113">Child elements</span></span>

|<span data-ttu-id="4e9e4-114">요소</span><span class="sxs-lookup"><span data-stu-id="4e9e4-114">Element</span></span>|<span data-ttu-id="4e9e4-115">Description</span><span class="sxs-lookup"><span data-stu-id="4e9e4-115">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="4e9e4-116">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4e9e4-117">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-117">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4e9e4-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e9e4-118">Parent elements</span></span>

|<span data-ttu-id="4e9e4-119">요소</span><span class="sxs-lookup"><span data-stu-id="4e9e4-119">Element</span></span>|<span data-ttu-id="4e9e4-120">Description</span><span class="sxs-lookup"><span data-stu-id="4e9e4-120">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="4e9e4-121">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9e4-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4e9e4-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e9e4-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="4e9e4-123">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4e9e4-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4e9e4-124">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4e9e4-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
