---
description: 다음에 대해 자세히 알아보세요. <variable>
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 187aa0b1ab0494a9bad759c504b804580a60553e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698000"
---
# \<variable>

<span data-ttu-id="a10c3-102">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a10c3-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a10c3-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a><span data-ttu-id="a10c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a10c3-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a10c3-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a10c3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a10c3-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a10c3-107">특성</span><span class="sxs-lookup"><span data-stu-id="a10c3-107">Attributes</span></span>  
  
|<span data-ttu-id="a10c3-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a10c3-108">Attribute</span></span>|<span data-ttu-id="a10c3-109">설명</span><span class="sxs-lookup"><span data-stu-id="a10c3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a10c3-110">name</span><span class="sxs-lookup"><span data-stu-id="a10c3-110">name</span></span>|<span data-ttu-id="a10c3-111">변수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-111">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a10c3-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a10c3-112">Child Elements</span></span>  

 <span data-ttu-id="a10c3-113">없음</span><span class="sxs-lookup"><span data-stu-id="a10c3-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a10c3-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a10c3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a10c3-115">요소</span><span class="sxs-lookup"><span data-stu-id="a10c3-115">Element</span></span>|<span data-ttu-id="a10c3-116">설명</span><span class="sxs-lookup"><span data-stu-id="a10c3-116">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="a10c3-117">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-117">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a10c3-118">설명</span><span class="sxs-lookup"><span data-stu-id="a10c3-118">Remarks</span></span>  

 <span data-ttu-id="a10c3-119">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-119">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a10c3-120">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-120">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a10c3-121">[\<arguments>](arguments.md), 및 요소를 사용 [\<states>](states.md) [\<states>](states.md) 하 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-121">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a10c3-122">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-122">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a10c3-123">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로를 사용 하 여 추적 프로필 내에서 구독 [\<activityStateQuery>](activitystatequery.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c3-123">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a10c3-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a10c3-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a10c3-125">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a10c3-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a10c3-126">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a10c3-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
