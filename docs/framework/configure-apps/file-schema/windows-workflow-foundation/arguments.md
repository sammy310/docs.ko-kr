---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: cb1f96cb6ba2643e28552c354bdd5caf4d43285c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189645"
---
# \<arguments>

<span data-ttu-id="8bfc7-101">활동 상태 쿼리와 연결되는 인수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-101">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="8bfc7-102">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**  
  
## <a name="syntax"></a><span data-ttu-id="8bfc7-103">구문</span><span class="sxs-lookup"><span data-stu-id="8bfc7-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bfc7-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8bfc7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8bfc7-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bfc7-106">특성</span><span class="sxs-lookup"><span data-stu-id="8bfc7-106">Attributes</span></span>  

 <span data-ttu-id="8bfc7-107">없음</span><span class="sxs-lookup"><span data-stu-id="8bfc7-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8bfc7-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8bfc7-108">Child Elements</span></span>  
  
|<span data-ttu-id="8bfc7-109">요소</span><span class="sxs-lookup"><span data-stu-id="8bfc7-109">Element</span></span>|<span data-ttu-id="8bfc7-110">설명</span><span class="sxs-lookup"><span data-stu-id="8bfc7-110">Description</span></span>|  
|-------------|-----------------|  
|[\<argument>](argument.md)|<span data-ttu-id="8bfc7-111">활동 상태 쿼리와 연결되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-111">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bfc7-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8bfc7-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8bfc7-113">요소</span><span class="sxs-lookup"><span data-stu-id="8bfc7-113">Element</span></span>|<span data-ttu-id="8bfc7-114">설명</span><span class="sxs-lookup"><span data-stu-id="8bfc7-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="8bfc7-115">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-115">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8bfc7-116">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-116">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bfc7-117">설명</span><span class="sxs-lookup"><span data-stu-id="8bfc7-117">Remarks</span></span>  

 <span data-ttu-id="8bfc7-118">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8bfc7-119">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8bfc7-120">[\<arguments>](arguments.md), 및 요소를 사용 [\<states>](states.md) [\<states>](states.md) 하 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8bfc7-121">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8bfc7-122">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로를 사용 하 여 추적 프로필 내에서 구독 [\<activityStateQuery>](activitystatequery.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc7-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bfc7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bfc7-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8bfc7-124">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8bfc7-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8bfc7-125">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8bfc7-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
