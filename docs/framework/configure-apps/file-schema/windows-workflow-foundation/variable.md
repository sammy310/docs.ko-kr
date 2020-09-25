---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: d9b40551233f3b22db7953f1980aaf99b0ee8ae9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185355"
---
# \<variable>

<span data-ttu-id="d22e0-101">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-101">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="d22e0-102">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d22e0-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a><span data-ttu-id="d22e0-103">구문</span><span class="sxs-lookup"><span data-stu-id="d22e0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d22e0-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d22e0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d22e0-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d22e0-106">특성</span><span class="sxs-lookup"><span data-stu-id="d22e0-106">Attributes</span></span>  
  
|<span data-ttu-id="d22e0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="d22e0-107">Attribute</span></span>|<span data-ttu-id="d22e0-108">Description</span><span class="sxs-lookup"><span data-stu-id="d22e0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d22e0-109">name</span><span class="sxs-lookup"><span data-stu-id="d22e0-109">name</span></span>|<span data-ttu-id="d22e0-110">변수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-110">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d22e0-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d22e0-111">Child Elements</span></span>  

 <span data-ttu-id="d22e0-112">없음</span><span class="sxs-lookup"><span data-stu-id="d22e0-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d22e0-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d22e0-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d22e0-114">요소</span><span class="sxs-lookup"><span data-stu-id="d22e0-114">Element</span></span>|<span data-ttu-id="d22e0-115">설명</span><span class="sxs-lookup"><span data-stu-id="d22e0-115">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="d22e0-116">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-116">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d22e0-117">설명</span><span class="sxs-lookup"><span data-stu-id="d22e0-117">Remarks</span></span>  

 <span data-ttu-id="d22e0-118">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d22e0-119">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d22e0-120">[\<arguments>](arguments.md), 및 요소를 사용 [\<states>](states.md) [\<states>](states.md) 하 여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d22e0-121">다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수와 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d22e0-122">변수 및 인수는 ActivityStateRecord만 추출할 수 있으므로를 사용 하 여 추적 프로필 내에서 구독 [\<activityStateQuery>](activitystatequery.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d22e0-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d22e0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d22e0-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d22e0-124">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d22e0-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d22e0-125">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d22e0-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
